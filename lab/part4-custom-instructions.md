# Part 4: Using Custom Instructions

There are always key pieces of information anyone generating code for your codebase needs to know - the technologies in use, coding standards to follow, project structure, etc. Since context is so important, as we've discussed, we likely want to ensure Copilot always has this information as well. Fortunately, we can provide this overview through the use of Copilot instructions.

Before we begin larger updates to the site with the help of Copilot, we want to ensure Copilot has a good understanding of how we're building our application. As a result, we're going to add a Copilot instructions file to the repository.

Copilot instructions is a markdown file is placed in your **.github** folder. It becomes part of your project, and in turn is available to all contributors to your codebase. You can use this file to indicate various coding standards you wish to follow, the technologies your project uses, or anything else important for Copilot Chat to understand when generating suggestions.

> [!IMPORTANT]
> The *copilot-instructions.md* file is included in **every** call to GitHub Copilot Chat, and will be part of the context sent to Copilot. Because there is always a limited set of tokens an LLM can operate on, a large Copilot instructions file can obscure relevant information. As such, you should limit your Copilot instructions file to project-wide information, providing an overview of what you're building and how you're building it. If you need to provide more specific information for particular tasks, you can create [prompt files](https://docs.github.com/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot?tool=vscode#about-prompt-files).

Here are some guidelines to consider when creating a Copilot instructions file:

- The Copilot instructions file becomes part of the project, meaning it will apply to every developer; anything indicated in the file should be globally applicable.
- The file is markdown, so you can take advantage of that fact by grouping content together to improve readability.
- Provide an overview of **what** you are building and **how** you are building it, including:
    - languages, frameworks and libraries in use.
    - required assets to be generated (such as unit tests) and where they should be placed.
    - any language specific rules
- If you notice GitHub Copilot consistently provides an unexpected suggestion (e.g. using class components for React), add those notes to the instructions file.

## Create a Copilot instructions file

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
