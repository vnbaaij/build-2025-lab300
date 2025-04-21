# Part 5: Implementing Features with Copilot Edits

Now, you'll use Copilot Edits to implement the product listing feature.

1. In Visual Studio, open a new Copilot Edits chat (press `Ctrl+Shift+E`).
2. Type: "Implement a product listing page in Products.razor that fetches products from ProductService and displays them in a list with product name, description, price, and image."
3. Review the suggestions and click "Accept All" to implement the code.

    The code should look similar to the following:
    ```html
    <table class="table">
        <thead>
            <tr>
                <th>Image</th>
                <th>Name</th>
                <th>Description</th>
                <th>Price</th>
            </tr>
        </thead>
        <tbody>
            @foreach (var product in products)
            {
                <tr>
                    <td><img height="80" width="80" src="@imagePrefix/@product.ImageUrl" /></td>
                    <td>@product.Name</td>
                    <td>@product.Description</td>
                    <td>@product.Price</td>
                </tr>
            }
        </tbody>
    </table>
    ```

4. Run the application to see your new product listing page.

**Key Takeaway**: Copilot Edits can generate complete feature implementations based on your natural language descriptions, saving significant development time.
