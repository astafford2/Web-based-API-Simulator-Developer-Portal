# Development Environment

## Tech Aspects


## Technologies to Replicate
- `.NET 5 SDK`
- `Vue CLI`
- `NodeJS` for `npm` usage

## Required IDEs
- IDEs used for development
    - Visual Studio 2019
    - Visual Studio Code
- These are the IDEs used by the team, but neither are specifically required for development

## Folder structure
    .
    ├── dotnet                          # Back-end folder for all .NET files
        ├── Portal
            ├── Portal.sln
                ├── Portal.csproj
                    ├── Classes\                    # Folder containing all classes of the back-end
                        ├── Area.cs                     # Class laying out an area object (area in this instance is the object that each endpoint works with)
                        ├── Endpoint.cs                 # Class laying out an API endpoint object
                        ├── Parameter.cs                # Class laying out an endpoint parameter object
                    ├── Controllers\
                        ├── ExampleController.cs        # Web API controller that contains the example API endpoint that we are displaying in the frontend
                ├── Portal.Test.csproj
                    ├── ExampleControllerTest.cs        # Class of unit tests for the ExampleController.cs controller
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
**package.json** - This file stores all dependencies needed for the project, dependencies are stored in json format with their name and version number to be installed by `npm`

**Dockerfile**