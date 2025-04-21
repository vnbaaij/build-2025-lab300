# Part 1: Code Completion with Ghost Text

In this section, you'll use GitHub Copilot's code completion to implement API endpoints.

1. Open `ProductEndpoints.cs` in the Products project under **Endpoints** - it should be empty or contain minimal code.
2. Begin typing a comment to describe what you want to implement:
   ```csharp
   group.MapGet(
   ```
3. Wait for the ghost text suggestions to appear (gray text).
4. Press Tab to accept the suggestion or continue typing to get more specific suggestions.
5. Implement the following endpoints using GitHub Copilot's suggestions:
   - GET product by ID
   - POST to create a new product
   - PUT to update a product
   - DELETE to remove a product

   The end code sould look similar to:

   ```csharp
   group.MapGet("/", async (ProductDataContext db) =>
   {
      return await db.Product.ToListAsync();
   })
   .WithName("GetAllProducts")
   .Produces<List<Product>>(StatusCodes.Status200OK);

   group.MapGet("/{id}", async  (int id, ProductDataContext db) =>
   {
      return await db.Product.AsNoTracking()
            .FirstOrDefaultAsync(model => model.Id == id)
            is Product model
               ? Results.Ok(model)
               : Results.NotFound();
   })
   .WithName("GetProductById")
   .Produces<Product>(StatusCodes.Status200OK)
   .Produces(StatusCodes.Status404NotFound);

   group.MapPut("/{id}", async  (int id, Product product, ProductDataContext db) =>
   {
      var affected = await db.Product
            .Where(model => model.Id == id)
            .ExecuteUpdateAsync(setters => setters
            .SetProperty(m => m.Id, product.Id)
            .SetProperty(m => m.Name, product.Name)
            .SetProperty(m => m.Description, product.Description)
            .SetProperty(m => m.Price, product.Price)
            .SetProperty(m => m.ImageUrl, product.ImageUrl)
            );

      return affected == 1 ? Results.Ok() : Results.NotFound();
   })
   .WithName("UpdateProduct")
   .Produces(StatusCodes.Status404NotFound)
   .Produces(StatusCodes.Status204NoContent);

   group.MapPost("/", async (Product product, ProductDataContext db) =>
   {
      db.Product.Add(product);
      await db.SaveChangesAsync();
      return Results.Created($"/api/Product/{product.Id}",product);
   })
   .WithName("CreateProduct")
   .Produces<Product>(StatusCodes.Status201Created);

   group.MapDelete("/{id}", async  (int id, ProductDataContext db) =>
   {
      var affected = await db.Product
            .Where(model => model.Id == id)
            .ExecuteDeleteAsync();

      return affected == 1 ? Results.Ok() : Results.NotFound();
   })
   .WithName("DeleteProduct")
   .Produces<Product>(StatusCodes.Status200OK)
   .Produces(StatusCodes.Status404NotFound);
   ```

6. Try using slash commands for documentation:
   - Type `///` above a method to generate XML documentation on the `MapProductEndpoints` this can also be brought up with `Alt+/` for inline and then entering **/**.
   - Type `/explain` to have Copilot explain a block of code.

7. Test your implementation:
   - Run the AppHost project.
   - Test your new endpoints.

**Key Takeaway**: GitHub Copilot can generate complete API implementations based on your comments or partial code, significantly speeding up development.
