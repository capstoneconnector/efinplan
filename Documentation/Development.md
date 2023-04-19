# Replicating the Development Environment

## Prerequisites
* Visual Studio [Link](https://visualstudio.microsoft.com/)
  * Any edition is okay, but the version should support .NET Core v6.
  * When installing Visual Studio, make sure to include .NET Core v6. If there are any options to install Entity Framework as well, install it.
* Docker Desktop [Link](https://www.docker.com/products/docker-desktop/)
* Node v18.7 or above [Link](https://nodejs.org/en/)

Once these are installed, the development environment can be cloned from the BitBucket repository. 

The link to the repository is [here](https://bitbucket.org/accutechcapstone/bsucapstone.efinplan/).

Clicking the "Clone" button on the BitBucket repo, which is private, allows a user with access to copy the Git URL. This can be pasted into Visual Studio on the dashboard page under "Clone Project" in order to clone the repository. An example of the "Clone" button on BitBucket is shown below.

![image](https://user-images.githubusercontent.com/70241666/198178141-ad27f0c3-bc05-4137-a94a-68383ae9ebd6.png)

## Dependencies
* .NET Core v6
* .NET Entity Framework
  * This includes the In-Memory Database part of Entity Framework.
    * The project already includes these as dependencies, so opening the project in Visual Studio will prompt you with the ability to download or download them automatically.
* Npgsql EntityFrameworkCore PostgreSQL
  * This is included in the .csproj's for eFinPlan, so opening the project in Visual Studio should automatically install the dependencies.
* Yarn
  * Once you have Node installed, you can simply run `npm install --global yarn` to install Yarn globally.
* Xunit
  * This is a dependency for the project in .NET, so Visual Studio will prompt you with a download or do it automatically.
* Vue, Typescript, Vite, Axios, Vitest, vue-test-utils
  * Running `yarn install` in the directory for the Vue project, `bsucapstone.efinplan\src\eFinPlan.Vue`, will automatically install these.


## Step-by-Step Installation

1. Go to the link for the repo. It is linked above.
2. If you have credentials to access it, you will see the `Clone` button on the top right. Click it.
3. On the prompt, as shown below, click the copy icon. This copies the link to the repository.

![image](https://user-images.githubusercontent.com/70241666/200985271-86d82621-ce61-4c22-b3f3-77b7c31139c7.png)

4. Download Visual Studio. It is linked above. Click the `Clone a repository` button as shown below.

![image](https://user-images.githubusercontent.com/70241666/200985684-3e358aec-a7ce-426d-baea-73a58771b63b.png)

5. On the next page, paste the link from Bitbucket with the `git clone` removed. Choose a place for the repo to be. You will be prompted to enter your credentials; if it opens a window in your web browser, just log into Bitbucket to authenticate.

![image](https://user-images.githubusercontent.com/70241666/200986018-e4c2fa0d-ef88-484c-921b-766edabc57a8.png)

6. On the left or right side of the window, you will see a list of the files in the repo. Double click the solution file `bsucapstone.efinplan.sln`. Because the project solution is based on .NET, everything, including the Vue aspect, are considered projects in Visual Studio.

![image](https://user-images.githubusercontent.com/70241666/200986861-0383f217-50fa-47a1-bfd5-890574177dfb.png)

7. Once you double clicked the solution file, Visual Studio will bring up the Solution Explorer. Here, you can edit the code, run the project, etc.

![image](https://user-images.githubusercontent.com/70241666/200987192-232618cf-57b0-45c3-9deb-8d55e07e8a03.png)

8. If you wish to run the API on your computer rather than Docker, choose eFinPlan.API as the default project at the top and select the launch for eFinPlan.API. Then, you can click the green `Run` triangle icon to run the API. This may cause unexpected errors with the connection to the frontend, so please only do this for debugging. The main way to run the project is through Docker, which will be explained later.

![image](https://user-images.githubusercontent.com/70241666/200987307-c46a5292-afdf-41d3-82c1-40d955809521.png)

Note that the database in appsettings.json is expected to use the Docker Container. To use a local database, change the settings in the appsettings.json of eFinPlan.API to match your Postgres database.

![image](https://user-images.githubusercontent.com/70241666/200989547-e8d11164-c0ed-456f-ade4-d2903d162638.png)

Opening it this way will allow you to access the Swagger environment by going to http:://localhost:5001.

![image](https://user-images.githubusercontent.com/70241666/200988913-cc55ebd3-ecfb-4a55-ac53-d913efffcdea.png)

In order to access any routes beside the Login and Registration ones, you must first create an account or log in with an existing one.

Note that passwords must be between 6 and 15 characters inclusive and include at least one lowercase letter, uppercase letter, number, and nonalphanumeric character.

After registering or logging in, the response will give you a token.

![image](https://user-images.githubusercontent.com/70241666/206307079-ef441379-252f-4b5f-b551-94f5ceffab7b.png)

At the top of the page, click the Authorize button on the right.

![image](https://user-images.githubusercontent.com/70241666/206307142-e4a64fdf-29c5-47d2-b465-68cd54e3dc1c.png)

Then, enter `Bearer ` followed by the token you received.

![image](https://user-images.githubusercontent.com/70241666/206307249-c9a2b415-cf74-4fc8-a959-de013d96038e.png)

After clicking the Authorize button, you will be able to access every other route.

This can be verified by seeing a lock icon to the right of the routes.

![image](https://user-images.githubusercontent.com/70241666/206307373-887daa9b-99e1-430b-865c-99374b89e6b4.png)

9. For the frontend, right click eFinPlan.Vue in the Solution Explorer and click `Open in Terminal`.

![image](https://user-images.githubusercontent.com/70241666/200987561-cd6f3bc3-a84e-4b90-a42c-5462d3ee5d23.png)

10. eFinPlan primarily uses Yarn for package management in Node. NPM can also be used if Yarn does not work. In the terminal ensure you are in the eFinPlan.Vue directory, enter `yarn install` or `npm install`, and hit enter.

![image](https://user-images.githubusercontent.com/70241666/200987943-32de1908-5c71-4a8d-99eb-49080b5fcb78.png)

11. Then, to run the hotswapping development frontend server, just type `npm run dev`. You will see the Vite CLI with a link to the website on your localhost.

![image](https://user-images.githubusercontent.com/70241666/200988241-c184704f-c6fc-4cad-85ac-dc06953c9e2f.png)

From there, you can start developing for either the frontend or the backend!

(Note: If you run the API directly through Visual Studio, you must change the API URL in `eFinPlan.Vue/src/main.js` to use https instead of http.

### Replicating via Docker

If you would rather run everything at once with Docker, everything in eFinPlan is packaged into one container.

1. [Ensure you have Docker Desktop installed and running.](https://www.docker.com/products/docker-desktop/)  
2. Go to the root folder of the project. You should see a file titled `docker-compose.yml`.
3. Open the folder in your terminal.
4. Run `docker compose up`.
5. You should see the commands running. Eventually, you will see the Vite command line GUI show up. This means that the container is up and running. You can double-check by looking at the container in Docker Desktop, it should state that all three images are running. Then, you can simply navigate to the URLs shown below.

The Docker container splits the solution into the following:
 - The frontend is at localhost:8080
 - The database is at localhost:5432
 - The backend is at localhost:5001

You can access the Swagger documentation from the Docker Container as well by visiting http://localhost:5001 in your browser.

### Migrations
If you want to make and run a migration, open the Package Manager Console in Visual Studio.

To run the existing Migrations, run `Update-Database`.

To make a new one, run `Add-Migration {MigrationName}` and then `Update-Database`.

## Structure
eFinPlan's development branch is feature/creation. Its master branch is simply called master. There are also branches, such as feature/api, for specific development focuses, like the API definitions.
* Root
  * The root of the project contains multiple files, such as the Docker files used to build the project, a README, the gitignore, and the Solution file for Visual Studio.
* obj
  * This contains caches of Docker builds of the project.
* src
  * This contains the project source code.
  * eFinPlan.API
    * This is a Project folder within the .NET Solution that contains the Controllers and routing for eFinPlan.
    * The Controllers folder contains the Controllers for each Model for eFinPlan.
  * eFinPlan.API.Tests
    * This is a Project folder within the .NET Solution that contains the tests for the API Project.
  * eFinPlan.Core
    * This is a Project folder within the .NET Solution that contains the Model definitions and Entity Framework contexts for eFinPlan.
    * The Models folder contains the Model definitions.
    * The Data folder contains the Entity Framework context definitions and Data classes for modifying data.
    * The Migrations folder contains data migrations for the database.
  * eFinPlan.Core.Tests
    * This is a Project folder within the .NET Solution that contains the tests for the Core data modifying classes.
  * eFinPlan.Infrastructure.PlanApi
    * This is a Project folder within the .NET Solution that contains the code for the MoneyTree Plan API SDK. Each calculator has its own folder with its own classes.
  * eFinPlan.Infrastructure.PlanApi.Tests
    * This is a Project folder within the .NET Solution that contains the tests for the Plan API SDK.
  * eFinPlan.Vue
    * This is a Project folder within the .NET Solution that contains the Vue frontend. Because Vue provides testing in its own environment, tests are held here as well.
    * src
      * This contains the source code for the frontend
     * assets
       * This contains the static assets, like a logo.
     * components
       * This contains the Vue components.
     * router
       * This contains the Vue router.
     * views
       * This contains the pages for the frontend.
    * test
      * This contains the tests for the frontend.
Every Project folder contains a bin folder with autogenerated .NET build files, an obj folder for Docker caches and dependencies, a Properties folder for launch setting configs, a Dockerfile, a .NET Project definition file, and a appsettings.json configuration file for environment variables.

The configuration files include the appsettings.json and launchSettings.json for each Project, Project definition .csproj files, and the jsconfig for the Vue frontend. There is a vite.config.js and vitest.config.js for configuring either Vite or Vitest. The Solution file also contains configuration options; these can be edited from within Visual Studio.

# Testing
Testing can be done from within Visual Studio. To run all of the tests of a file, right click the .Test Project you wish to test and click on the "Run Tests" option, as shown below.

![image](https://user-images.githubusercontent.com/70241666/198176988-a6d801f5-0135-48df-8209-a58a8dc47fc7.png)

You can run all of the tests by selecting the Solution at the top and clicking "Run Tests" as shown below.

![image](https://user-images.githubusercontent.com/70241666/198177370-467cbc00-a6fa-4b28-8ca2-437f718bff43.png)

To run a single test, right click the .Test project and select "Show in Test Explorer" as shown below.

![image](https://user-images.githubusercontent.com/70241666/198177169-58096155-a602-4bb3-885c-93858c8a0e72.png)

Then, you can select a single test and click the green Play icon to run the selected test(s). An example of a passing test output is shown below.

![image](https://user-images.githubusercontent.com/70241666/200991517-f4f96065-5308-49e9-bc3f-28ebd5df9f41.png)

In this report, the green checkmarks indicate a passing test. If they failed, they will appear as a red "X". On the right side of the Test Explorer, you can see the total runtime of the tests, the total tests passed or failed, and any warnings or errors that occur. Clicking on the Error or Warning text will show you the details of any warning or error.

For integration tests, run `npx cypress open` and then follow [Cypress' guide on running tests.](https://docs.cypress.io/guides/end-to-end-testing/testing-your-app)

# Linting
Both linting solutions are run through the command line.

## .NET Linting
To lint the .NET solution, we use the .editorconfig format.

In the root folder, there is a .editorconfig based on .NET defaults, which fulfills the Accutech guidelines.

To run the linter, make sure your terminal is in the root folder, where the solution is, and run `dotnet format .\bsucapstone.efinplan.sln`. If you are not on Windows, use the proper relative path formatting. This will automatically format the code of every project, sans the Vue one, to follow the linting guidelines. Do this prior to any commits.

## Vue Linting
To lint the Vue project, we use Prettier.

In the root folder of the Vue project, which is eFinPlan.Vue, there is a .Prettierrc file from Accutech that defines the style guidelines that Prettier will format the code to.

To run the linter, make sure your terminal is in the root folder of the Vue project, where the .Prettierrc file is, and run `npx prettier --write .`. This will format all files within the Vue project. 

Note that you must have all NPM packages installed prior to linting, as Prettier is a development dependency pulled from NPM. Therefore, ensure that you have the node_modules folder after running `npm install` in the Vue project directory when you first replicate the development environment.


