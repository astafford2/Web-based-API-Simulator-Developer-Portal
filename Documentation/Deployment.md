# Deployment 

## Server
- The project uses localhost as its server while running. The project uses two ports for localhost:
  #### Back-end
  - http://localhost:5000
  #### Front-end
  - http://localhost:8080

## File/Folder Location

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
- From the CLI, input the command 'CTRL+C' to halt the operation.

#### &emsp;Front-end:
- From the CLI, input the command 'CTRL+C'. The CLI will ask the user if they want to terminate the batch job. Input the command 'Y' to halt the operation.

## Troubleshooting

## Error Logging
- Errors can be found logged in the CLI used to run the project.

## Critical Sections
- 
