# Development Environment

## Technologies to Replicate
<img src=https://img.shields.io/badge/.NET%205-v5.0.402-blue>
<img src=https://img.shields.io/badge/npm-v6.14.15-red>
<img src=https://img.shields.io/badge/Vue%20CLI-v4.5.13-brightgreen>
<img src=https://img.shields.io/badge/Microsoft%20SQL%20Server%202019-v15.0.2000.5-blueviolet>
<img src=https://img.shields.io/badge/Microsoft%20SQL%20Server%20Management%20Studio%2018-v18.9.2-purple>
<br><br>

- `.NET 5 SDK v5.0.402`
- `NodeJS v14.18.0` for `npm` usage
- `Vue CLI v4.5.13`
- `Microsoft SQL Server 2019 v15.0.2000.5 for database support`
- `Microsoft SQL Server Management Studio 18 v18.9.2 for database management`

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
                ├── Classes\
                    ├── Area.cs                         # Class laying out an area object (area in this instance is the object that each endpoint works with)
                    ├── Endpoint.cs                     # Class laying out an API endpoint object
                    ├── MailSetting.cs                  # Class that gets and sets each form input that gets posted from the frontend
                    └── Parameter.cs                    # Class laying out an endpoint parameter object
                ├── Controllers\
                    ├── AreaController.cs               # ***INFO FOR THESE***
                    ├── EndpointController.cs           # ***INFO FOR THESE***
                    ├── FormDataController.cs           # Web API controller that contains logic for sending an email to a specified reciever
                    ├── LoginController.cs              # Web API controller that contains logic for logging in through Cheetah calls
                    └── ParameterController.cs          # ***INFO FOR THESE***
                ├── Models\
                    ├── Area.cs                         # ***INFO FOR THESE***
                    ├── CheetahContext.cs               # ***INFO FOR THESE***
                    ├── Endpoint.cs                     # ***INFO FOR THESE***
                    ├── LoginResponse.cs                # ***INFO FOR THESE***
                    ├── Parameter.cs                    # ***INFO FOR THESE***
                    └── SelectListOption.cs             # ***INFO FOR THESE***
                ├── Services\
                    ├── AreaService.cs                  # ***INFO FOR THESE***
                    ├── EmailService.cs                 # Service that extends the IEmailService interface and lays out the body of the email to be sent
                    ├── EndpointService.cs              # ***INFO FOR THESE***
                    ├── IAreaService.cs                 # ***INFO FOR THESE***
                    ├── IEmailService.cs                # Interface that contains a task that asynchronously sends an email
                    ├── IEndpointService.cs             # ***INFO FOR THESE***
                    ├── ILoginService.cs                # Interface that contains tasks to asynchronously login to Cheetah servers
                    ├── IParameterService.cs            # ***INFO FOR THESE***
                    └── LoginService.cs                 # Service that extends the ILoginService interface and lays out methods for logging in
                    └── ParameterService.cs             # ***INFO FOR THESE***
                ├── ViewModels\
                    ├── AreaViewModel.cs                # ***INFO FOR THESE***
                    ├── EmailFormViewModel.cs           # View Model that contains the getters and setters for all of the elements to be sent in the email
                    ├── EndpointViewModel.cs            # ***INFO FOR THESE***
                    ├── LoginViewModel.cs               # ***INFO FOR THESE***
                    ├── ParameterViewModel.cs           # ***INFO FOR THESE***
                    ├── SelectListOptionViewModel.cs    # ***INFO FOR THESE***
                    └── SidebarViewModel.cs             # ***INFO FOR THESE***
                ├── Properties\launchSettings.json  # Json file that specifies where the back-end is running
                ├── appSettings.json                # Json file that contains the root URL for the example endpoint data and the settings for the email functionality
                └── Portal.csproj                   # C# project containing the classes, controllers, services, models, and the launchSettings and appSettings json files
            ├── Portal.Test\
                ├── AreaServiceTest.cs              # Class of unit tests for the AreaService.cs service
                ├── FormDataController.cs           # Class of unit tests for the FormDataController.cs controller
                ├── LoginServiceTests.cs            # Class of unit tests for the LoginService.cs service
                ├── testconfig.json                 # Json file that holds the information for the testing environment
                └── Portal.Test.csproj              # C# project that contains all of the test classes and the testconfig.json file
            └── Portal.sln                      # Contains information about what needs to be compiled
        ├── Dockerfile                      # Dockerfile to build back-end development image
        └── DockerfileExternal              # Dockerfile to build back-end development image through an external repository
    ├── vue\                            # Front-end folder for all vue files
        ├── public\                         # Files that are served raw and accessible in its plain URL
        ├── src\                            # Source files for vue front-end
            ├── assets\                         # Asset files for the vue front-end
            ├── components\                     # HTML components to import in vue files
                ├── Navbar.vue                      # Component that contains HTML for the navigation bar featured on App.vue
                ├── Footer.vue                      # Component that contains HTML for the footer featured on App.vue
                └── Sidebar.vue                     # Component that contains HTML for the References sidebar
            ├── repositories\                   # Folder containing repository pattern Javascript files
                ├── AreaRepository.js               # Javascript file that points to our web api object "Area" and creates methods for it
                ├── EndpointRepository.js           # Javascript file that points to our web api object "Endpoint" and creates methods for it
                ├── FormDataRepository.js           # Javascript file that points to our web api object "FormData" and creats a post method
                ├── ParameterRepository.js          # Javascript file that points to our web api object "Parameter" and creates methods for it
                ├── LoginRepository.js              # Javascript that points to our web api object "Login" and creates methods to handle login
                ├── Repository.js                   # Javascript file that points to the url that our backend is running on
                └── RepositoryFactory.js            # Javascript file that sets environments for either unit testing or running the project
            ├── router\
                └── index.js                        # JavaScript file to declare routes and paths
            ├── views\                          # Folder to house the front-end HTML pages
                ├── Administration.vue              # HTML and Javascript logic for the Administration page
                ├── Console.vue                     # HTML for the Console page
                ├── Home.vue                        # HTML for the Home page
                ├── Login.vue                       # HTML and Javascript logic for the Login page
                ├── References.vue                  # HTML and Javascript logic for the References page
                └── ReferencesLanding.vue           # ***INFO FOR THESE***
            ├── App.vue                         # Main HTML template for Vue pages
            └── main.js                         # JavaScript file for Vue, Bootstrap, etc. imports
        ├── tests\unit\
            ├── Administration.spec.js          # JavaScript file containing the unit tests for Administration.vue
            └── Login.spec.js              # JavaScript file containing the unit tests for Login.vue
        ├── Dockerfile                      # Dockerfile to build front-end development image
        ├── DockerfileExternal              # Dockerfile to build front-end development image through an external repository
        └── package.json                    # JSON file to store vue config data and npm script aliases
    └── docker-compose.yml              # YAML file to build all Docker containers for local development internally

    [Truncated for brevity, only relevant folders/files were highlighted.]

## Important files
**appSettings.json** - This file stores all of the configuration settings for the back-end

**launchSettings.json** - This files stores the launch configuration settings for the back-end including what port it will run on

**package.json** - This file stores all dependencies needed for the project, dependencies are stored in json format with their name and version number to be installed by `npm`

**Dockerfiles** - Dockerfiles are used to build the development images for both front and back-end; these are mostly used with the Docker repo and docker-compose, but can be built by themselves

## Replicating / Testing the Environment
### Building and running
- Clone the project repository from BitBucket
    - `git clone https://bitbucket.org/accutechdev/bsu.developer-portal/src/master/ bsu.developer-portal`
#### &emsp;Gathering required technologies:
- Download Microsoft SQL Server 2019 from [microsoft.com](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)
- Download Microsoft SQL Server Management Studio 18 from [docs.microsoft.com](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15)
- Download .NET 5 SDK from [dotnet.microsoft.com](https://dotnet.microsoft.com/download/dotnet/5.0)
    - Make sure to download the correct SDK for your machine (Windows, Linux, Mac)
- Download the latest LTS of Node.js from [nodejs.org](https://nodejs.org/en/download/)
    - Again, make sure to downlaod the correct installer for your machine
- After installing node, open a CLI of your choice, run the following command to install Vue CLI
    - `npm install -g @vue/cli`

#### &emsp;Database:
- Open SQL Server Management Studio and connect to your Desktop server
- Right click on `Databases` and select `Restore Database`
- Select the radio button labeled `Device` and click the `Browse (...)` button next to the input box
- In the window that comes up, select `File` from the dropdown menu
- Select any existing paths in the `Browse Media` box and click `Remove`
- Select `Add`
- Find the project repository in the file structure that comes up, select the 'Cheetah.bak' database backup file, and select `Ok`
- Select the 'Cheetah.bak' file path in the `Browse Media` box and click `Ok`
- In the restore database window, write 'Cheetah' in the database input box if it's not already inputed
- Click `Ok` to restore the Cheetah database from the backup file

#### &emsp;Back-end:
- In a CLI, move into the *\dotnet\Portal\Portal* folder and first build the project .dll
    - `dotnet build "Portal.csproj"`
- Then, move into the *\bin\Debug\net5.0* folder to run the .dll
    - `dotnet run Portal.dll`
- The back-end should spin up, and in a browser you can go to http://localhost:5000 and should see the back-end swagger page
**OR**
- Open the project solution in Visual Studio 2019
    - Select 'Portal' from the run dropdown menu and click the run button
    - http://localhost:5000 will open in your default browser

#### &emsp;Front-end:
- In a CLI, move into the *\vue* folder and first install the dependencies
    - `npm install`
- Then, in the same folder, start the front-end with npm
    - `npm run serve`
- The front-end should spin up, and in a browser you can go to http://localhost:8080 and see the front-end web application pages
**OR**
- Open the 'vue' folder in Visual Studio Code
    - Hit 'Ctrl + ~' to open a shell in the vue folder
    - Run the command `npm run serve`
    - Navigate to http://localhost:8080

### Building and running with Docker
- Run the following docker-compose command in the root folder of the repository (where docker-compose.yml is):
    - `docker-compose up --build`
    - This might take some time for the initial build.
    - If Docker prompts to share folder(s), confirm them.
- If you want to rebuild from scratch, try using --nocache option.
    - `docker-compose build --no-cache`
    - Then running `docker-compose up`
- To restore the Cheetah.bak database backup into the `dev-portal-db` container...
    - Open a new CLI or shell
    - Copy the backup file into the container with the command `docker cp "./databases/Cheetah.bak" dev-portal-db:var/opt/mssql`
    - Open a bash prompt in the container with the command `docker exec -it dev-portal-db "bash"`
    - Change directory to the mssql directory withing the docker container with the command `cd var/opt/mssql`
    - Run a SQL command prompt with the command `/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P "dev_portal495"`
    - Run the SQL query `RESTORE DATABASE [Cheetah] FROM DISK='/var/opt/mssql/Cheetah.bak' WITH MOVE 'Cheetah' TO '/var/opt/mssql/data/Cheetah.mdf', MOVE 'Cheetah_log' TO '/var/opt/mssql/data/Cheetah_log.ldf'` and hit enter
    - Type `GO` into the SQL command and hit enter to restore the database from the Cheetah.bak database backup file

### Running code tests
#### &emsp;Test Database:
- Running tests for the backend relies on having a working copy of the CheetahTest database
    - Open SQL Server Management Studio and connect to your Desktop server
    - Right click on `Databases` and select `Restore Database`
    - Select the radio button labeled `Device` and click the `Browse (...)` button next to the input box
    - In the window that comes up, select `File` from the dropdown menu
    - Select any existing paths in the `Browse Media` box and click `Remove`
    - Select `Add`
    - Find the project repository in the file structure that comes up, select the 'CheetahTest.bak' database backup file, and select `Ok`
    - Select the 'CheetahTest.bak' file path in the `Browse Media` box and click `Ok`
    - In the restore database window, write 'CheetahTest' in the database input box if it's not already inputed
    - Click `Ok` to restore the Cheetah database from the backup file

#### &emsp;Front-end:
- In a CLI, move into the *\vue* folder and run the front-end tests
    - `npm run t`

#### &emsp;Back-end:
- In a CLI, move into the *\dotnet\Portal\Portal.Test* folder and run the back-end tests
    - `dotnet test`
- Tesing from **Visual Studio 2019** is also possible. In the IDE, right click on the Portal.Test project and select "Run Tests"

### Interpreting code tests
#### &emsp;Front-end:
- After running the command `npm run t`, if the tests pass, they will have a checkmark next to them as shown below
<br>
<img src="DocumentationImages/VueTestsPass.PNG">
<br>
<ul>
    <li>"add parameter button can be found" tests if the add parameter button can be found on the parameter modal on the administration page
    <li>"parameter modal can be found" tests if the modal to add parameters can be found on the administration page
    <li>"it attempts to load" tests if the references page attempts to load information from the back-end
    <li>"it is not loaded" tests if the references page is not loaded before it gets the information from the back-end
    <li>"it loads the json response" tests if the references page can load the json data from the testing environment
    <li>"it displays the json response correctly" tests if the references page displays the json response correctly
</ul>

#### &emsp;Back-end:
- After running the command `dotnet test`, if the tests pass the test window will look like this
<br>
<img src="DocumentationImages/DotnetTestsPass.PNG">
<br>
<ul>
    <li>The TestGetEndpoints test method tests the data configuration from the ExampleController controller
    <li>The TestGetEmailConfig test method tests the data configuraiton from the FormDataController controller
</ul>
