# Deployment 

## Server
- The project uses localhost as its server while running. The project uses two ports for localhost:
  #### Back-end
  - http://localhost:5000
  #### Front-end
  - http://localhost:8080

## Installation and Setup
#### Prerequisites
  - Ensure the following are installed before cloning the repository:
  
  - <img src=https://img.shields.io/badge/.NET%205-v5.0.402-blue> <br>
     - `.NET 5 SDK v5.0.402`
  - <img src=https://img.shields.io/badge/npm-v6.14.15-red> <br>
     - `NodeJS v14.18.0 for npm usage`
  - <img src=https://img.shields.io/badge/Vue%20CLI-v4.5.13-brightgreen> <br>
     - `Vue CLI v4.5.13`
  - <img src=https://img.shields.io/badge/Microsoft%20SQL%20Server%202019-v15.0.2000.5-blueviolet> <br>
     - `Microsoft SQL Server 2019 v15.0.2000.5 for database support`
  - <img src=https://img.shields.io/badge/Microsoft%20SQL%20Server%20Management%20Studio%2018-v18.9.2-purple> <br>
     - `Microsoft SQL Server Management Studio 18 v18.9.2 for database management`
  - Once installed, clone the Bitbucket project repository (https://bitbucket.org/accutechdev/bsu.developer-portal/src/master/) into a folder of your choosing.

## Starting/Stopping System Operations
### To start system operations...
#### &emsp;Database:
- Open SQL server management studio and connect to your Desktop server
- Right click on `Databases` and select `Restore Database`
- Select the radio button labeled `Device` and click the `Browse (...)` button next to the input box
- In the window that comes up, select `File` from the dropdown menu
- Select any existing paths in the `Browse Media` box and click `Remove`
- Select `Add`
- Find the project repository in the file structure that comes up, select the `Cheetah.bak` database backup file, and select `Ok`
- Select the `Cheetah.bak` file path in the `Browse Media` box and click `Ok`
- In the restore database window, write `Cheetah` in the database input box if it's not already inputed
- Click `Ok` to restore the Cheetah database from the backup file

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

### To stop system operations...
#### &emsp;Back-end:
- From the CLI running the back-end, input the command 'CTRL+C' to halt the operation.

#### &emsp;Front-end:
- From the CLI running the front-end, input the command 'CTRL+C'. The CLI will ask the user if they want to terminate the batch job. Input the command 'Y' to halt the operation.

## Starting/Stopping System Operations with Docker
### To start system operations...
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

## Troubleshooting
- In case of an issue, consult the following steps to properly troubleshoot the issue:
    - Ensure the back-end and front-end are both running properly (see the Starting/Stopping System Operations section for more detail).
    - In case of an issue with the Request Access form:
        - Ensure the entire form is filled out properly before submission.
        - Check the appsettings.json file (dotnet/Portal/Portal/appsettings.json) to ensure 'Enabled' is set to 'true'.

## Error Logging
- Errors can be found logged in the CLI used to run the project.

## Critical Sections
- The critical sections that are mostly likely to fail are in the Request Access section of the Login page.
    - When filling out the Request Access form, ensure that each field in the form is filled out. If any field is left blank, the access request may not properly send and the user may receive an error.
    - The email sent after submitting the Request Access form may fail to send. Ensure that '"Enabled": true' is set in 'dotnet/Portal/Portal/appsettings.json'--if 'Enabled' is set to 'false', the email may fail to send.
- If the References page displays "Loading..." while accessing the page, the back-end may not be running properly. Ensure that the back-end is functional and running before accessing the References page.
