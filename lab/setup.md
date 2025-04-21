# Workshop setup

To complete this workshop you will need to clone a repository with a copy of the contents of this repository

> [!Hint]
> Under regular conditions you would need to ensure all prequirements, but don't worry. We have ensured this environment as all you need.

## Configure GitHub Copilot

> [!IMPORTANT]
> For this lab you need a [GitHub account](https://docs.github.com/get-started/learning-about-github/types-of-github-accounts), if you don't have one no worries, you can create a personal account for free. Create your account in the [GitHub sign up page](https://github.com/signup).

1. [] Create a GitHub Account if you don't already have one
2. [] Open Visual Studio 2022
3. [] Select **Continue without code**
4. [] Click on Copilot icon on top bar (left side next to the search input box)

![Copilot icon](./images/0-copilot-icon.png)

4. [] Click on **Sign in to use Copilot** option
5. [] A browser will automatically open, enter your GitHub login and password (and MFA if asked to)
6. [] Click **open**  browser asks for the confirmation (**This site is trying to open Visual Studio.**)
8. [] After Copilot is setup you should now have a **Walkthrough: GitHub Copilot Chat** open tab in Visual Studio

We are now ready to start working on our code with the help of Copilot.

## Clone lab repository

Let's clone the repository you'll use for the lab.

1. [] Click on **File -> Clone Repository** button
2. [] Type `https://github.com/dotnet-presentations/build-2025-lab300` and press **Clone**. 

The code is now opened in Visual Studio, feel free to take a look at it or skip to the next section to start the app.

## Start the app

1. [] Set the **TinyShop.AppHost** as the startup project and start the project with F5 or debug.

The .NET Aspire AppHost will start two applications and the .NET Aspire Dashboard:

- The backend .NET app on **https://localhost:7130**. 
- The frontend Blazor app on **http://localhost:7085**. You can see the app by opening that URL from the dashboard

## Summary and next steps

You've now cloned the repository you'll use for this workshop and have GitHub Copilot setup! Next let's **add a new endpoint to the server**
