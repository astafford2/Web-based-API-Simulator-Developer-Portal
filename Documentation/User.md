## User Documentation
---
### - Home Page

Opening the software, you will start at the home page, which provides some of the uses that will come or be in the software in the end product. On this page, you will find a login button located at the top right of the page. Click it to go to the login page. A home button will be displayed at the top of the screen at all times on every page for whenever the user wants to return to the main home page. 

#### Page buttons:
- <b>Home:</b> Goes back to the starting page where you would need to go back throgh the login page
- <b>Login:</b> Brings the user to the login page where they gain 

---
### - Login Page

On the login page, the user will have the option to log in or request access. Login so far has been set up where the user only needs to press the gain access button to be taken to the next page which is the references page. However if the user selects the Request Access button, they will be given a form to fill out that will send an email to an email address specified in the back-end. The email will contain the information gathered from the form. After filling out the form, the user can click the Submit Form button and the email will be sent.

#### Page buttons:
- <b>Home:</b> Goes back to the starting page where you would need to go back throgh the login page
- <b>Gain Access:</b> Brings the user to the references page
- <b>Request Access:</b> Opens a modal containing a form that a user can fill out in order to request access to the API
- <b>Submit Form:</b> Submits the form and send an email to an administrator (specified in the back-end)

---
### - References Page

On the references page, the user will be able to see all of the endpoints of the Example API as well as their parameters. The user has the option to click the links to both the object that the endpoint works with as well as the specific endpoint and be taken down the page to where that object or endpoint is. After reaching the bottom of the page the user will have the option to click the "back to top" link and be taken back to the top of the page. In future versions we will be connecting to the Cheetah API, meaning that actual endpoints featured in Cheetah API will be featured will be featured on this page.

---
### - Console Page

The console page has been set up layout-wise but does not have any functionality currently. In future versions we will be moving into giving this page funcitonality or perhaps merging the console onto the references page in the form of a card view.

---
### - Administration Page 

On the administration page, the general functioning currently set up for this page is adding a parameter. On the page, there is an object selection bar that allows you to select an object. To use the add parameter button, the user must choose "example object one" in the selection bar. When you click the add parameter button, a modal will display requesting user input. The user can then fill in the information for the modal, including the parameter name, description, type through the selection bar, and say whether it is is required or not through the checkbox. The user can click outside of the modal to close it, or they can fill out the basic information for the parameter and click the save button to close it and save the parameter information. The modal will not close unless the parameter has a name and a parameter type is selected. Not filling this out will cause the save button in the modal to be disabled. The general parameter information also is added to the table of the administration page.

---
#### Pages Dropdown Menu (Featured on the Reference, Console, and Administration pages):
- <b>References:</b> The Reference option will take you to the references page
- <b>Console:</b> The Console option will take you to the console page
- <b>Admin:</b> The Administration option will take you to the administration page