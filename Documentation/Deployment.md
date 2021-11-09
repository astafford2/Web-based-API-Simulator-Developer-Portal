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
  
     - <img src=https://img.shields.io/badge/.NET%205-v5.0.402-blue>
     - <img src=https://img.shields.io/badge/npm-v6.14.15-red>
     - <img src=https://img.shields.io/badge/Vue%20CLI-v4.5.13-brightgreen>
  - Once installed, clone the project repository into a folder of your choosing.

## Starting/Stopping System Operations
### To start system operations...
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
