# AntiBuddies-
CS 4450 Final Project



## For future students read "Anti-Buddies Handoff Document". The following is previous semester information.







READ ME 

Hardware required for the project: Mac for ios development, PC for Database & Web development. 
Prof Rhees email: justinrhees@weber.edu


Web: https://antibodies-s3-bucket.s3.us-east-2.amazonaws.com/anti-web-files/index.html

https://antibuddies-274a7.web.app/ (firebase version)  

Website consists of a sequence of pages that are intended to interact with user. The purpose of the website is to be a tutorial for students to learn and apply skills that are taught in the Department of Laboratory Science. Descriptions are as follows: 

 

index.html, login.css, login.js - First sequence of the website starts with the login/create user screen. User will have the option of logging in or creating an account to get access. User log-in is using an amazon-web-services lambda function call, and in Firebase it’s using a built in authentication function. This page is now linked to database to call lamba object for data storage. We use javascript and bootstrap styling with these pages.

 

courses.html - Once logged in, user will be given a set of courses being taught by the department. Sample of immunohematology, chemistry, microbiology, etc. will be given for the user to practice with. Project when ready to be released will be servicing various courses and even different departments. 



Departments (Immunhematology.html, chemistry.html, **additional courses) - When user selects a course, they will be brought to 3 options, panels, panel examples and practice questions (these options will be available for all courses in the department). There will be textbook links available in executable PDF’s on this page. 



home.html, home.css - User then will be given the option to select desired level of panels, panel examples and practice questions. 



panel.html, panel.css - Here the panels, panel examples and practice questions will be populated in a sequential order. 



grid.html, quiz.html, style.css - Sample of what a panel, panel example will look like. Here the user will interact with the panel(s) and will be given instructions on how to use the panel and will be rated on their performance after submitting. 

 

admin.html, admin-grid.html, admin.quiz.html - Admin of the website and app will be able to create/modify panels, panel examples and practice questions from the admin page. Here also the admin will determine different specs like level of intensity, material aids, instructions for panels, patient bio fields, etc. 


App:

App REPO: https://github.com/WeberStateAntibuddiesProject/IOS-Antibuddies/settings
GitHub login info:(FOR APP ONLY)  
USER NAME: WeberStateAntibuddiesProject
PASSWORD: WeberStudent1

Email Login info:
Email:  AntibodiesWeberState@gmail.com.
Password for email: WeberStudent1
The App is written in Swift on XCode.  You must have the most recent version of Xcode on the app store.  

SUPPORTED APPLE DEVICES:
The app is targeted and designed to auto-layout/resize view for the PANEL VIEWS towards these apple devices only: 
iPad pro 12.9 inch, iPad pro 12.9 inch (2nd gen), iPad Pro 12.9 (3rd gen) 
if you target other smaller iPads the screens are far too small for all the details of a blood panel --aka antigram
The app is targeted and designed to auto-layout/resize views for the QUESTION VIEWS towards these apple devices only: 
 ALL iPads that are supported by Apple as of August 2019.

For your first attempt at loading this on the simulator make sure you have your simulator set to one of the larger iPads.
 
NAVIGATING THE APP
TEST LOGIN INFORMATION: User Name: test, Password: 123
Or you may create your own account by selecting the “Create One” text.  Logining in may take a few moments, be patient.
Immunohematology is the only highlighted and button that works. (if you would like to pursue another course please speak to prof rhees as he has spoken with other departments who are interested in creating practice tests for their students as well)
Panels button will take you to the MainMenuViewController which has options for panel difficulty, Select Beginner - The “1” -- a Panel should display on the screen.  You can turn on Allelic Pairs select boxes and cross them off.  THINGS THAT NEED TO BE DONE:
Grade Selected Row
Grade All Rows
Search For Patient 
Add Bitmoji of Prof Rhees if they get something right or wrong
Cross out top row of same column if there are two strikes against it
Practice Questions, Select Beginner - select a question -  This view is completed.  Speak with Prof Rhees, to see if he would like to see if he would like to add any extra features. 


Database:

SOFTWARE:
The scripts were run on Microsoft SQL Server Management Studio 18

MODEL:
Database Model Diagram: DatabaseModel.vdx
The data model is currently a visio document. I used lucidchart, and there is a way to import the visio document into lucidchart if you would also prefer to work on it that way. You can also import the document into Draw.io if you would rather work in that environment.

SETUP:
The database is stored using Amazon Web Service (AWS) through their relational database system (RDS). Our project is currently using a 120 free trial account, today’s date is 7/30/2019. The account might not be active if the 120 days have passed. The username and password to the account is 

username:  benjaminoliverson@mail.weber.edu, 
password: W3b3rSt@t3. 

To open the database go to microsoft sequel server, and choose database engine. For the server name use the endpoint followed by: (,port number) under the connectivity & security page of the database site. (endpoint: antibuddies.co362eqfasab.us-east-2.rds.amazonaws.com, port number: 1433) We are also in the OHIO US EAST server location, so you may need to be in that server group to access the database. Ben Oliverson was thinking of continuing with the project. I would recommend sending a message to the email, to see if he is still working on it and any updates he may have about the account.

Login: antibuddies, 
Password: WeberStudent1.

 If the account is discontinued go to AWS and make a free trial account. Go through steps and create a rds mysql database. Login with your new credentials through microsoft sequel server, and run the SQLScript.sql to re-add all data structures. This will make a new database, but all previously stored data by the clients in the other database will be lost if you can’t access it, so this should only be done if absolutely necessary.

SCRIPTS:
SQLScript contains all of the code for the entire database.
The other scripts contain specific parts of the code for easier identification and editing. Each script is named and documented on what it contains.

TASKS:
Update Triggers to allow Batch insert statements.



API: 
We are using AWS to handle the interaction with the server. Specifically we are using Lambda functions in AWS. Our Lambda functions are written in Go. The app is connected to the Lambda functions via the iOS Lambda cocoa pod. The website is connected to the Lambda functions through the Javascript Lambda SDK. The website and the app are both able to call the same Lambda functions to query the DB. 
