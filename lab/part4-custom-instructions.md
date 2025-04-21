# Part 4: Using Custom Instructions

Custom instructions help tailor Copilot's responses to your specific needs and project requirements.

1. Open the `copilot-instructions.md` file in the `.github` folder, you can also get to it from the `Solution Items` folder in Visual Studio.
2. Add project-specific information about your application:

```markdown
## TinyShop

### Backend
- Products project is the backend API.
- Built with .NET Minimal APIs.
- Uses Entity Framework Core with an in-memory database.
- Should follow OpenAPI best practices.

### Frontend
- Store project is a .NET 9 Blazor Server application.
- Uses default Bootstrap styling.
- UI should have a modern look and feel.
- CSS should be in .razor.css files.
```

3. Go back to Copilot Chat and re-run the prompt from Part 3.
4. Notice how the responses now incorporate your custom instructions.

**Key Takeaway**: Custom instructions make Copilot's suggestions more aligned with your project standards and architecture preferences.
