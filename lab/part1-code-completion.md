# Part 1: Code Completion with Ghost Text

In this section, you'll use GitHub Copilot's code completion to implement API endpoints.

1. Open `ProductEndpoints.cs` in the Products project - it should be empty or contain minimal code.
2. Begin typing a comment to describe what you want to implement:
   ```csharp
   // Implement GET endpoint to return all products
   ```
3. Wait for the ghost text suggestions to appear (gray text).
4. Press Tab to accept the suggestion or continue typing to get more specific suggestions.
5. Implement the following endpoints using GitHub Copilot's suggestions:
   - GET all products
   - GET product by ID
   - POST to create a new product
   - PUT to update a product
   - DELETE to remove a product

6. Try using slash commands for documentation:
   - Type `///` above a method to generate XML documentation.
   - Type `/explain` to have Copilot explain a block of code.

7. Test your implementation:
   - Run the AppHost project.
   - Navigate to the Swagger UI (usually at `/swagger`).
   - Test your new endpoints.

**Key Takeaway**: GitHub Copilot can generate complete API implementations based on your comments or partial code, significantly speeding up development.
