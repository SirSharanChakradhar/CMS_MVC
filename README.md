# CMS_MVC

How the MVC application works in this project:

A user enters a URL into their browser, which sends a request to the web server.
The web server routes the request to the appropriate controller based on the URL.
The controller retrieves any necessary data from the model, which in this case is the application's database.
The controller passes the data to the view, which is responsible for rendering the HTML that the user sees in their browser.
The view sends the HTML back to the user's browser as a response to their initial request.
If the user performs an action on the page, such as clicking a button, a new request is sent to the web server, which starts the process again.
Here's a visual representation of this process:

                  +---------+
                  | Browser |
                  +---------+
                       |
                       v
                  +---------+
                  | Web     |
                  | Server  |
                  +---------+
                       |
                       v
                  +---------+
                  |         |
                  |         |
                  | Routing |
                  |         |
                  |         |
                  +---------+
                       |
                       v
                  +---------+
                  |         |
                  |         |
                  | Control |
                  |         |
                  |         |
                  +---------+
                       |
                       v
                  +---------+
                  |         |
                  |         |
                  |   Model |
                  |         |
                  |         |
                  +---------+
                       |
                       v
                  +---------+
                  |         |
                  |         |
                  |   View  |
                  |         |
                  |         |
                  +---------+
                       |
                       v
                  +---------+
                  | Browser |
                  +---------+
                  
--------------------------------------------------------------------------------------------------------------      



The table structure for the project is as follows:

Admin table:
Id (int, primary key)
Username (nvarchar(50), unique)
Password (nvarchar(50))

Event table:
Id (int, primary key)
Title (nvarchar(50))
Description (nvarchar(500))
Location (nvarchar(100))
Date (datetime)

Attendee table:
Id (int, primary key)
Name (nvarchar(50))
Email (nvarchar(100))
Phone (nvarchar(20))
EventId (int, foreign key referencing the Event table)


Registration table:
Id (int, primary key)
AttendeeId (int, foreign key referencing the Attendee table)
RegistrationDate (datetime)
You can use Entity Framework Code First approach to automatically generate these tables in the database based on the model classes. 
Alternatively, you can manually create the tables in SQL Server Management Studio using the above table structures.



--------------------------------------------------------------------------------------------------------------


Here's a quick rundown of the Controller, Model, and View folders in the project structure we created:

Controllers Folder: This folder contains all of the controller classes that handle requests from the client and return responses. In our project, we have several controllers such as:
AccountController: This controller contains actions for user authentication, such as login, logout, and registration.
HomeController: This controller contains actions for rendering the home page and other static pages.
EventController: This controller contains actions for handling events-related functionality, such as creating, viewing, updating, and deleting events.
AdminController: This controller contains actions for handling administrative functionality, such as managing users and events.
Models Folder: This folder contains all of the model classes that represent the data and business logic of the application. In our project, we have several models such as:
Attendee: This model represents the attendees who register for events.
Event: This model represents the events that are created by administrators.
Registration: This model represents the registrations made by attendees for events.
Admin: This model represents the administrators who manage the application.
Views Folder: This folder contains all of the view files that render HTML markup to the client's web browser. In our project, we have several view files such as:
Login.cshtml: This view renders the login form for users to log into the application.
Register.cshtml: This view renders the registration form for users to create an account in the application.
Index.cshtml: This view renders the home page of the application.
Event.cshtml: This view renders the details of a specific event.
Admin.cshtml: This view renders the administrator dashboard for managing users and events.


--------------------------------------------------------------------------------------------------------------

Folder structure


                                  ├───Controllers
                                  │   ├───AccountController.cs
                                  │   ├───AdminController.cs
                                  │   ├───AttendeeController.cs
                                  │   ├───EventController.cs
                                  │   └───HomeController.cs
                                  ├───Models
                                  │   ├───Admin.cs
                                  │   ├───Attendee.cs
                                  │   ├───Event.cs
                                  │   ├───Registration.cs
                                  │   └───ApplicationDbContext.cs
                                  ├───Views
                                  │   ├───Account
                                  │   │   ├───Login.cshtml
                                  │   │   └───Register.cshtml
                                  │   ├───Admin
                                  │   │   ├───Create.cshtml
                                  │   │   ├───Delete.cshtml
                                  │   │   ├───Details.cshtml
                                  │   │   ├───Edit.cshtml
                                  │   │   └───Index.cshtml
                                  │   ├───Attendee
                                  │   │   ├───Create.cshtml
                                  │   │   ├───Delete.cshtml
                                  │   │   ├───Details.cshtml
                                  │   │   ├───Edit.cshtml
                                  │   │   └───Index.cshtml
                                  │   ├───Event
                                  │   │   ├───Create.cshtml
                                  │   │   ├───Delete.cshtml
                                  │   │   ├───Details.cshtml
                                  │   │   ├───Edit.cshtml
                                  │   │   └───Index.cshtml
                                  │   ├───Home
                                  │   │   ├───About.cshtml
                                  │   │   ├───Contact.cshtml
                                  │   │   └───Index.cshtml
                                  │   ├───Shared
                                  │   │   ├───_Layout.cshtml
                                  │   │   ├───_LoginPartial.cshtml
                                  │   │   └───Error.cshtml
                                  ├───Scripts
                                  │   ├───bootstrap.min.css
                                  │   ├───bootstrap.min.js
                                  │   └───jquery-3.6.0.min.js
                                  ├───Content
                                  │   └───Site.css
                                  ├───App_Data
                                  │   └───ApplicationDbContext.mdf
                                  ├───App_Start
                                  │   └───RouteConfig.cs
                                  ├───Properties
                                  │   └───launchSettings.json
                                  ├───bin
                                  │   ├───Content
                                  │   │   └───Site.css
                                  │   ├───Scripts
                                  │   │   ├───bootstrap.min.css
                                  │   │   ├───bootstrap.min.js
                                  │   │   └───jquery-3.6.0.min.js
                                  │   ├───App_Data
                                  │   │   └───ApplicationDbContext.mdf
                                  │   └───...
                                  ├───obj
                                  │   ├───Debug
                                  │   │   ├───TempPE
                                  │   │   ├───Properties
                                  │   │   ├───Content
                                  │   │   └───Scripts
                                  │   ├───Release
                                  │   │   ├───TempPE
                                  │   │   ├───Properties
                                  │   │   ├───Content
                                  │   │   └───Scripts
                                  │   └───...
                                  ├───packages
                                  │   └───...
                                  ├───Views
                                  │   └───web.config
                                  ├───Web.config
                                  └───Web.Debug.config


--------------------------------------------------------------------------------------------------------------


Project Plan:

Analysis and Design Phase:
Define project requirements and specifications.
Design the entity-relationship diagram (ERD) for the classes based on the requirements and specifications.
Create the model classes that are specific to the ERD.
Create the database schema based on the ERD.
Define the necessary user roles and permissions.
Define the necessary business rules and validation rules.
Define the necessary UI components and layouts.
Design the necessary UI wireframes and mockups.

Development Phase:
Create the ASP.NET MVC web application using the provided folder structure.
Create the necessary controller classes to handle user requests.
Create the necessary view classes to display user interfaces.
Create the necessary model classes to handle data.
Implement the necessary business rules and validation rules.
Implement the necessary user authentication and authorization.
Implement the necessary CRUD operations using Entity Framework.
Implement the necessary search functionality.
Implement the necessary report generation functionality.
Implement the necessary UI components and layouts using Bootstrap.

Testing Phase:
Test the application to ensure that it meets the specified requirements and specifications.
Test the application to ensure that it is responsive and user-friendly.
Test the application to ensure that it is secure and reliable.
Test the application to ensure that it performs well and efficiently.
Fix any issues or bugs that are found during testing.

Deployment Phase:
Deploy the application to a production environment.
Configure the necessary settings and parameters for the production environment.
Test the application in the production environment.
Train the necessary users on how to use the application.
Provide the necessary documentation and support for the application.

Maintenance Phase:
Monitor the application to ensure that it is functioning properly.
Fix any issues or bugs that are reported by users.
Perform necessary updates and upgrades to the application.
Perform necessary backups and disaster recovery procedures.
