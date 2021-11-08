# Deployment 

## Server
- The project uses localhost as its server while running. The project uses two ports for localhost:
  #### Back-end
  - http://localhost:5000
  #### Front-end
  - http://localhost:8080

## File/Folder Location
    The files and folders should be arranged as follows: 
    
    ├── dotnet\                         
        ├── Portal\
            ├── Portal\
                ├── Classes\                    
                    ├── Area.cs                     
                    ├── Endpoint.cs                 
                    ├── MailSetting.cs              
                    ├── Parameter.cs                
                ├── Controllers\                
                    ├── ExampleController.cs        
                    ├── FormDataController.cs       
                ├── Services\                   
                    ├── EmailService.cs             
                    ├── IEmailService.cs            
                ├── ViewModels\                 
                    ├── EmailFormViewModel.cs       
                ├── Properties\launchSettings.json  
                ├── appSettings.json            
                ├── Portal.csproj               
            ├── Portal.Test\                    
                ├── ExampleControllerTest.cs        
                ├── FormDataController.cs          
                ├── testconfig.json                 
                └── Portal.Test.csproj          
            └── Portal.sln                      
        └── Dockerfile                      
    ├── vue\                            
        ├── public\                         
        ├── src\                            
            ├── assets\                         
            ├── components\                     
                ├── Navbar                          
                ├── Footer                          
            ├── repositories\                   
                ├── ExampleLocalRepository.js       
                ├── ExampleRepository.js            
                ├── FormDataRepository.js           
                ├── Repository.js                   
                ├── RepositoryFactory.js            
            ├── router\                         
                ├── index.js                        
            ├── views\                          
                ├── Administration.vue              
                ├── Console.vue                     
                ├── Home.vue                        
                ├── Login.vue                       
                ├── References.vue                  
            ├── App.vue                         
            ├── main.js                         
        ├── tests\unit\                     
            ├── Administration.spec.js      
            ├── References.spec.js          
        ├── Dockerfile                      
        └── package.json        

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
- From the CLI runnig the back-end, input the command 'CTRL+C' to halt the operation.

#### &emsp;Front-end:
- From the CLI running the front-end, input the command 'CTRL+C'. The CLI will ask the user if they want to terminate the batch job. Input the command 'Y' to halt the operation.

## Troubleshooting
-

## Error Logging
- Errors can be found logged in the CLI used to run the project.

## Critical Sections
- 
