# Development Environment

## Tech Aspects


## Technologies to Replicate
- `.NET 5 SDK`
- `NodeJS` for `npm` usage
- `Vue CLI`

## Required IDEs
- IDEs used for development
    - **Visual Studio 2019** - back-end development
    - **Visual Studio Code** - front-end development
- These are the IDEs used by the team, but neither are specifically required for development

## Folder structure
    .
    ├── dotnet\                         # Back-end folder for all .NET files
        ├── Portal\
            ├── Portal\
                ├── Classes\                    # Folder containing all classes of the back-end
                    ├── Area.cs                     # Class laying out an area object (area in this instance is the object that each endpoint works with)
                    ├── Endpoint.cs                 # Class laying out an API endpoint object
                    ├── Parameter.cs                # Class laying out an endpoint parameter object
                ├── Controllers\
                    ├── ExampleController.cs        # Web API controller that contains the example API endpoint that we are displaying in the frontend
                ├── Properties\launchSettings.json
                ├── appSettings.json
                ├── Portal.csproj
            ├── Portal.Test\
                ├── ExampleControllerTest.cs        # Class of unit tests for the ExampleController.cs controller
                └── Portal.Test.csproj
            └── Portal.sln                      # Contains information about what needs to be compiled
        └── Dockerfile                      # Dockerfile to build back-end development image
    ├── vue\                            # Front-end folder for all vue files
        ├── public\                         # Files that are served raw and accessible in its plain URL
        ├── src\                            # Source files for vue front-end
            ├── assets\                         # Asset files for the vue front-end
            ├── components\                     # HTML components to import in vue files
            ├── router\                         # Folder to house the Vue router
                ├── index.js                        # JavaScript file to declare routes and paths
            ├── views\                          # Folder to house the front-end HTML pages
                ├── Administration.vue              # HTML for the Administration page
                ├── Console.vue                     # HTML for the Console page
                ├── Home.vue                        # HTML for the Home page
                ├── Login.vue                       # HTML for the Login page
                ├── References.vue                  # HTML for the References page
            ├── App.vue                         # Main HTML template for Vue pages
            ├── main.js                         # JavaScript file for Vue, Bootstrap, etc. imports
        ├── tests\unit\                     # Test folder for vue files
        ├── Dockerfile                      # Dockerfile to build front-end development image
        └── package.json                    # JSON file to store vue config data and npm script aliases

    [Truncated for brevity, only relevant folders/files were highlighted.]

## Important files
**appSettings.json** - 

**launchSettings.json** - 

**package.json** - This file stores all dependencies needed for the project, dependencies are stored in json format with their name and version number to be installed by `npm`

**Dockerfiles** - Dockerfiles are used to build the development images for both front and back-end; these are mostly used with the Docker repo and docker-compose, but can be built by themselves

## Testing the Environment
### Building and running
- Clone the project repository from BitBucket
    - `git clone https://bitbucket.org/accutechdev/bsu.developer-portal/src/master/ bsu.developer-portal`
#### &emsp;Gathering required technologies:
- Download .NET 5 SDK from [dotnet.microsoft.com](https://dotnet.microsoft.com/download/dotnet/5.0)
    - Make sure to download the correct SDK for your machine (Windows, Linux, Mac)
- Download the latest LTS of Node.js from [nodejs.org](https://nodejs.org/en/download/)
    - Again, make sure to downlaod the correct installer for your machine
- After installing node, open a CLI of your choice, run the following command to install Vue CLI
    - `npm install -g @vue/cli`

#### &emsp;Back-end:
- In a CLI, move into the *\dotnet\Portal\Portal* folder and first build the project .dll
    - `dotnet build "Portal.csproj"`
- Then, move into the *\bin\Debug\net5.0* folder to run the .dll
    - `dotnet run Portal.dll`
- The back-end should spin up, and in a browser you can go to http://localhost:5000 and should see the back-end swagger page

#### &emsp;Front-end:
- In a CLI, move into the *\vue* folder and first install the dependencies
    - `npm install`
- Then, in the same folder, start the front-end with npm
    - `npm run serve`
- The front-end should spin up, and in a browser you can go to http://localhost:8080 and see the front-end web application pages

### Running code tests
#### &emsp;Front-end:
- In a CLI, move into the *\vue* folder and run the front-end tests
    - `npm run t`

#### &emsp;Back-end:
- 

### Interpreting code tests