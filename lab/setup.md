# Workshop setup

To complete this workshop you will need to clone a repository with a copy of the contents of this repository

> [!Hint]
> Under regular conditions you would need to ensure all prequirements, but don't worry. We have ensured this environment as all you need.

## Configure GitHub Copilot

> [!IMPORTANT]
> For this lab you need a [GitHub account](https://docs.github.com/get-started/learning-about-github/types-of-github-accounts), if you don't have one no worries, you can create a personal account for free. Create your account in the [GitHub sign up page](https://github.com/signup).

TODO: adapt the login IF we are going to use the provided licenses instead relying on BYOL/Copilot Free

1. [] Create a GitHub Account if you don't already have one
2. [] Open Visual Studio 2022
3. [] Click on Copilot icon on top bar (left side next to the search input box)

![Copilot icon](./images/0-copilot-icon.png)

4. [] Click on **Open Chat** option
5. [] If there is a login button on the chat window, click it, otherwise type something and press enter in the chat input box to force the login window
5. [] Click on **Sign In** blue button on the modal window
6. [] A browser will automatically open, enter your GitHub login and password (and MFA if asked to)
7. [] Click **open**  browser asks for the confirmation (**This site is trying to open Visual Studio Code.**)
8. [] After Copilot is setup you should now have a **Walkthrough: GitHub Copilot Chat** open tab in Visual Studio

We are now ready to start working on our code with the help of Copilot.

## Clone lab repository

Let's clone the repository you'll use for the lab.

1. [] Click on the Source Control icon on the left sidebar

![Source control icon](./images/0-source-control-icon.png)

2. [] Click on **File -> Clone Repository** button
3. [] Type `https://github.com/dotnet-presentations/build-2025-lab300` and press enter. 
4. [] Select the repository destination folder (suggestion: use the one is automatically shown. The user home folder) by clicking in **Select as Repository Destination** button.
    - Note: The repository will be cloned to **SELECTED FOLDER/**
5. [] Click **Open** button when asked if you **Would like to open the cloned repository?**
6. [] Click the **Yes, I trust the authors** button when asked.

The code is now opened in Visual Studio, feel free to take a look at it or skip to the next section to start the app.

## Start the app

1. [] Click on **...** (three dots, or **Terminal** if already visible) on the menu bar at the top and then select **Terminal -> New Terminal**
2. [] Start the application by running the following command on the terminal:

    ```pwsh
    .\scripts\start-app.ps1
    ```

The startup script will install dependencies and start two applications:

- The backend Flask app on **http://localhost:5100**. You can see a list of dogs by opening the the url ++http://localhost:5100/api/dogs++
- The frontend Astro/Svelte app on ++http://localhost:4321++. You can see the by opening that URL.

- [] Try it now, open a browser and navigate to the links provided above.

## Summary and next steps

You've now cloned the repository you'll use for this workshop and have GitHub Copilot setup! Next let's **add a new endpoint to the server**
