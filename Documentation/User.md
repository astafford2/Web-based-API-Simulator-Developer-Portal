## User Documentation
---
### - Home Page

Opening the software, you will start at the home page, which provides some of the uses that will come or be in the software in the end product. On this page, you will find a login button located at the top right of the page. Click it to go to the login page. A home button will be displayed at the top of the screen at all times on every page for whenever the user wants to return to the main home page. 

#### Page buttons:
- <b>Home:</b> Goes back to the starting page where you would need to go back throgh the login page
- <b>Login:</b> Brings the user to the login page where they gain access if they haven't already

---
### - Login Page

On the login page, the user will have the option to log in or request access. Selecting the Gain Access button will make an HTTP Token call to the Cheetah API with the credentials entered in the Username and Password fields. If the username and password are legitimate, the login will go through successfully, and the user will then be taken to the next page which is the references page. If the username and password are incorrect, the Cheetah call will not go through, and the user will be shown an error to check their entered credentials.

If the user selects the Request Access button, they will be given a form to fill out that will send an email to an email address specified in the back-end. The email will contain the information gathered from the form. After filling out the form, the user can click the Submit Form button and the email will be sent. Currently, to send an email the "Enabled" option in the appSettings.json file in the back-end needs to be set to true. The email address to be sent to is currently set to our professor's email address, for grading purposes.

#### Page buttons:
- <b>Home:</b> Goes back to the starting page
- <b>Gain Access:</b> Brings the user to the references page
- <b>Request Access:</b> Opens a modal containing a form that a user can fill out in order to request access to the API
- <b>Submit Form:</b> Submits the form and send an email to an administrator (specified in the back-end)

---
### - References Page

On the references page, the user will first be brought to the references landing page telling the user to select an object link. From there the user can select which object in the Cheetah API they would like to either work with or see the available endpoints of from the sidebar. When the user selects an object from the sidebar they will be taken to a page containing information about endpoints and parameters within that object.

#### Page buttons:
- <b>Home:</b> Goes back to the starting page

---
### - Console Page

The console page has been set up layout-wise but does not have any functionality currently. In future versions we will be moving into giving this page funcitonality or perhaps merging the console onto the references page in the form of a card view.

#### Page buttons:
- <b>Home:</b> Goes back to the starting page

---
### - Administration Page 

On the administration page, a table is given listing the areas. Within each of these areas are a selection of endpoints. To access the endpoints select the button for the area you want to access, and a table containing the endpoints of the area will display below. You can then choose an endpoint that to edit by once again clicking the edit button on the right side of the endpoint you wish to select for editing the description. Once an endpoint is selected, you can provide an input for a new description of the endpoint in the box that appears underneath the endpoint selection table. To change the description of the endpoint you selected, you can press the submit changes button. Once the submit changes button is selected, you will be redirected to the references page and can now select the object containing the endpoint you changed and see that the description has changed. 

To the right, a table of the parameters for the endpoint selected will display as an endpoint is selected. Some endpoints may not yet contain parameters that will be expressed if that is the case. Below the endpoints parameter display, if any, an empty table is given and below that is an add-parameter button. When you click the add parameter button, a modal will display requesting user input. The user can then fill in the information for the modal, including the parameter name, description, type through the selection bar, and say whether it is is required or not through the checkbox. You can click outside the modal to close it or fill out the information for the parameter and click the save button. Clicking the button will close the modal, save the information entered, and display the parameter information to the table. The table also displays the endpoint that the user wants to add to. In other words, the endpoint recorded on the table will be the one currently selected. The modal will not close unless the parameter has a name and a parameter type is selected. Not filling this out will cause the save button in the modal to be disabled. 

#### Page buttons:
- <b>Home:</b> Goes back to the starting page

---
#### Pages Dropdown Menu (Featured on the Reference, Console, Administration pages, and home page after logging in):
- <b>References:</b> The Reference option will take you to the references landing page
- <b>Console:</b> The Console option will take you to the console page
- <b>Admin:</b> The Administration option will take you to the administration page