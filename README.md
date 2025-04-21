# LAB300 - Hands-on with GitHub Copilot in Visual Studio 2022

This lab will guide you through using GitHub Copilot's various features in Visual Studio 2022. You'll start with a partially completed TinyShop application and use GitHub Copilot to complete missing features and enhance the application.

## Prerequisites

- Visual Studio 2022 with GitHub Copilot extension installed
- .NET 9 SDK
- GitHub account with Copilot subscription

## Lab Overview

The TinyShop application consists of two main projects:
- A backend API built with .NET Minimal APIs
- A frontend Blazor Server application

You'll use GitHub Copilot's various features to enhance and complete this application.

## Part 0: Exploring the Codebase with GitHub Copilot Chat

GitHub Copilot Chat allows you to ask questions about your code and get intelligent responses.

1. Open the solution in Visual Studio 2022
2. Click on the Copilot Chat icon in the bottom-right corner of Visual Studio or press `Ctrl+Shift+I`
3. Try asking questions about the project structure:
   - "What projects are in this solution?"
   - "What is the TinyShop application architecture?"
   - "How does the Products API work?"
4. Notice how Copilot analyzes your codebase to provide contextual answers

**Key Takeaway**: GitHub Copilot Chat helps you understand unfamiliar codebases by answering questions about the project structure, architecture, and implementation details.

## Part 1: Code Completion with Ghost Text

In this section, you'll use GitHub Copilot's code completion to implement API endpoints.

1. Open `ProductEndpoints.cs` in the Products project - it should be empty or contain minimal code
2. Begin typing a comment to describe what you want to implement:
   ```csharp
   // Implement GET endpoint to return all products
   ```
3. Wait for the ghost text suggestions to appear (gray text)
4. Press Tab to accept the suggestion or continue typing to get more specific suggestions
5. Implement the following endpoints using GitHub Copilot's suggestions:
   - GET all products
   - GET product by ID
   - POST to create a new product
   - PUT to update a product
   - DELETE to remove a product

6. Try using slash commands for documentation:
   - Type `///` above a method to generate XML documentation
   - Type `/explain` to have Copilot explain a block of code

7. Test your implementation:
   - Run the AppHost project
   - Navigate to the Swagger UI (usually at `/swagger`)
   - Test your new endpoints

**Key Takeaway**: GitHub Copilot can generate complete API implementations based on your comments or partial code, significantly speeding up development.

## Part 2: Enhancing UI with Inline Chat

Now, you'll improve the loading experience using Copilot's inline chat.

1. Open `Products.razor` in the Store project
2. Find the "Loading..." text in the code
3. Select this text and right-click
4. Choose "Copilot > Start inline chat" or press `Alt+/`
5. In the inline chat, type: "Replace this with a loading progress spinner"
6. Preview the suggestion by clicking the "Preview" button
7. Accept the change by clicking "Accept"
8. Run the application to see your new loading spinner in action

**Key Takeaway**: Inline chat allows you to make targeted improvements to your code without leaving your editor context.

## Part 3: Referencing Code Files in Chat

In this section, you'll learn how to reference existing code files in your chat conversations.

1. Open `Products.razor` from the Store project
2. Open Copilot Chat (press `Ctrl+Shift+I`)
3. Type: "@ProductService" to reference the ProductService file
4. Ask: "How would I implement getting and visualizing the products in a table using the code in ProductService?"
5. Review the code suggestion but don't implement it yet
6. Follow up with: "How would this look in a grid instead of a list?"
7. Notice how Copilot can reference existing code to provide contextual suggestions

**Key Takeaway**: Referencing files in your chat provides Copilot with the context it needs to give more accurate, project-specific suggestions.

## Part 4: Using Custom Instructions

Custom instructions help tailor Copilot's responses to your specific needs and project requirements.

1. Open the `github-instructions.md` file in the `.github` folder
2. Add project-specific information about your application:

```markdown
## TinyShop Architecture

### Backend
- Products project is the backend API
- Built with .NET Minimal APIs
- Uses Entity Framework Core with an in-memory database
- Should follow OpenAPI best practices

### Frontend
- Store project is a .NET 9 Blazor Server application
- Uses default Bootstrap styling
- UI should have a modern look and feel
- CSS should be in .razor.css files
```

3. Go back to Copilot Chat and re-run the prompt from Part 3
4. Notice how the responses now incorporate your custom instructions

**Key Takeaway**: Custom instructions make Copilot's suggestions more aligned with your project standards and architecture preferences.

## Part 5: Implementing Features with Copilot Edits

Now, you'll use Copilot Edits to implement the product listing feature.

1. In Visual Studio, open a new Copilot Edits chat (press `Ctrl+Shift+E`)
2. Type: "Implement a product listing page in Products.razor that fetches products from ProductService and displays them in a list with product name, description, price, and image"
3. Review the suggestions and click "Insert at Cursor" to implement the code
4. Run the application to see your new product listing page

**Key Takeaway**: Copilot Edits can generate complete feature implementations based on your natural language descriptions, saving significant development time.

## Part 6: Using Copilot Vision

In this final section, you'll use Copilot Vision to implement a UI design from an image.

1. Find the store application image on your desktop
2. Open a Copilot Edits chat (press `Ctrl+Shift+E`)
3. Click the "Attach Image" button and select the store application image
4. Ask: "Update the Products.razor to display products in a grid layout similar to this image. Add nice hover effects and make it responsive."
5. Review the suggested code changes and implement them
6. Run the application to see the updated product grid layout

**Key Takeaway**: Copilot Vision can understand UI designs from images and help you implement them in your application.

## Conclusion

In this lab, you've learned how to use the various features of GitHub Copilot in Visual Studio 2022:
- Copilot Chat for understanding code
- Ghost text suggestions for rapid code completion
- Inline chat for targeted improvements
- Referencing code files for contextual suggestions
- Custom instructions for tailored responses
- Copilot Edits for implementing complete features
- Copilot Vision for turning designs into code

These tools can significantly boost your productivity as a developer by automating repetitive tasks, generating boilerplate code, and helping you implement complex features more quickly.
