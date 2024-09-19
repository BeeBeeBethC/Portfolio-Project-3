# CEDAS
The Cheesecake Emporium Data Automation System.

"INSERT AMIRESPONSIVE"

# Contents

* [What is The Cheesecake Emporium?](#what-is-the-cheesecake-emporium)
    * [Why use CEDAS?](#why-use-cedas)
    * [How to use CEDAS](#how-to-use-cedas)
* [Target Audience]()
* [User Experience]()
* [Existing Features](#existing-features)
    * [Future Implementations](#future-implementations)
    * [Technologies and Libraries Used]()
* [Data Model](#data-model)
* [Testing](#testing)
* [Deployment](#deployment)
    * [Clone The Repository](#how-to-clone-the-repository)
    * [How To Create A Fork](#how-to-fork-the-repository)
    * [Deployment to Heroku](#heroku-deployment)
* [Credits](#credits)
    * [Content](#credits)
    * [Media](#credits)

## What is The Cheesecake Emporium?
The Cheesecake Emporium is a hypothetical Cheesecake company who have requested a data automation program that helps them to reduce waste and increase their sales numbers. Currently they have a static stock order arriving daily and are loosing sales due to stock not being sold.

## Why use CEDAS?

The aim of CEDAS is to provide an automated program that will assist in monitoring and increasing sales whilst reducing waste by altering stock numbers dynamically rather than static as it currently stands. In turn this should help the owners manage sales, stock and more, efficiently by requesting data stored in an API (Application Programming Interface) that the author has generated based off of the data that has been provided by the company. by Using CEDAS, the Owners can then request and return most recent numbers and any manipulated data for review and replenish stocks more efficiently.

## How to use CEDAS

Welcome to CEDAS. please follow the steps below to use the system correctly.

Select function from menu options using numbers '1, 2, 3, 4 or 5' Press Enter. Option 1, Type in latest sales figures CEDAS asks for values correspoding to cheesecake flavours Allow the application to run until the menu options show Option 2, Takes you to instructions on how to use CEDAS Option 3, Users can fetch data from a set date. NOTE: CEDAS returns values after 01-08-2024 only Enter a date from 01-08-2024 in format 'YYYY-MM-DD' Option 4 retrieves all stock data Option 5 Exits the programme. NOTE: CEDAS asks for values until option 5 is selected


## Existing Features

Before implementing the dynamic system that CEDAS offers, the owners of Cheesecake Emporium were manually tracking data using pen and paper. By implementing CEDAS, this has now taken static stock replenishment to dynamic stock replenishment by analysing the sales data and surplus data and providing stock order numbers to avoid excess waste for the company.

## Future Implementations

## Data Models

![data-model](/documentation-images/flowchart.png)

this was the initial data model I had drawn up. over the length of the project this changed slightly to the flow-diagram below.


## Testing
### bugs
API not linking 
My API that I had generated using google sheets wasn't connecting I had written google.oauth.service_account when it should have been google.oauth2.service_account. 
    
Infinite while loop 
This was human error as I'd accidentally put my programme into an infinte while loop requesting data due to no 'if' statement even though data had been input. I also forgot to comment out prior code for testing if the API was successfully connected which could have been a contributing factor.

Unable to update sales worksheet
This was due to human error not providing correct commands therefore the programme would not run or update and kept throwing an error back(see screenshot) in and not updating the corresponding sheet.

unable to return stock averages
due to an undefined variable it kept throwing back an error.

INSERT screenshots

### solved bugs

API not linking 
It turned out I'd missed a crucial numerical value in the command. Once corrected the error was resolved. Programme ran as expected.

Infinite while loop 
to get myself out of the while loop I sent the command 'exit()' this still didn't work and I'd realized that this command is specific for python shell. I then tried CTRL-C which worked and the while loop stopped. Once stopped I commented out the code that I used to check that the API was connected. On fixing the while loop by removing the partially written loop I had output as expected.

Unable to update sales worksheet
by providing correct commands to the programme, it was able to identify what I wanted it to do and update successfully as shown in the screenshot below highlighted by the values in Blue. 

unable to return stock averages
once defining the variables under the main function, code was running as expected and returning stock values to terminal. 

### remaining bugs

### PEP8 validation

## Deployment Instructions

CEDAS was deployed to both Github and Heroku.

reasons for deploying to Github was to monitor version control.

### Github Clone
To clone a copy of CEDAS from the Github repository, please follow these steps:

1. Go to the repository you wish to clone, project link is as follows. (https://github.com/BeeBeeBethC/CEDAS)

2. Click on the green button that reads 'Code'.

3. On the dropdown menu, please select the 'Copy URL to clipboard' option this button looks like two squares overlaying one another.

4. Open your favourite code editor, for myself it is Visual Studio Code. on Visual Studio Code, click the 'source control' button from the left hand menu.

(Alternatively, open the terminal and change your working directory to the location of the cloned repository.)

5. Paste the repository URL into the top navigation bar of Visual Studio Code.

(Alternatively type 'git clone' into the terminal and paste the URL link.)

6. Save the repository to a localised folder where the repository will be stored on your computer.

7. Click on select repository location.

8. Let the repository download and click 'open' when the on screen prompt shows in the lower right corner of the screen.

### Github Fork

To fork the repository of CEDAS, please follow these steps.

1. Sign up or login to Github.

2. Go to the repository for CEDAS (https://github.com/BeeBeeBethC/CEDAS)

3. Click the fork button on the top right hand side of the screen.

PLEASE NOTE: The steps followed above will provide the code only. To access the project from Heroku, please continue to follow the steps below.

### Heroku Deployment
1. Create your list of requirements by navigating to the requirements.txt file. each package is known as a dependency so therefore should be located in this file when uploading to heroku so that Heroku itself can still open your project.

2. To create your list of requirements, type in the gitpod (or code terminal of your choice) "pip3 freeze > requitements.txt" ensuring you have the exact same spelling, all lower case for the exact file name or this will not work.

3. Commit and push most recent code upto github.

4. If not done already, sign-up or login to heroku.

5. navigate to your heroku dashboard.

6. from the heroku dashboard, create a new app and name it. each app name needs to be unique or it won't accept it.

7. select region.

8. make sure your settings have been set before you deploy. (FOR CI STUDENTS ONLY)

9. If settings are not declared, here are the steps for checking settings before deployment.
    1. Find the config vars section. (these are environmental variables section found in heroku settings). In this tab "Reveal config vars" this is where you put sensitive information for example creds.json that can't be shown publicly.
    2. For more compatibility, also add another config var to heroku settings which is a port key: PORT value is 8000. This ensures a much smoother deployment as projects may not deploy if missed out.

10. Navigate to add build pack. select "Python" and click save changes then find "node.js" and click save changes.
NOTE: If these two packages are the opposite way round you can click and drag them so that python pack is on top and node.js is below python.

11. For this project there is the choice of automatic deployment or manual. For CEDAS I have chosen to manually deploy it which means that it won't automatically update from pushed changes but it does show deployment logs.

12. To manually update the project using the main branch:
    1.  firstly make sure your most recent changes have been pushed to github and confirm these before moving onto the next step.
    2.  navigate back to project overview and select the deploy option from the navigation menu at the top of the page.
    3.  scroll down the deploy page until you reach manual deploy.
    4.  choose branch to deploy, make sure it's the main branch.
    5.  click the deploy button. (follow steps 13 onwards)

INSERT screenshot

13. Once the project has been deployed you should recieve a message stating that "project was successfully deployed" and you should be able to click a link that takes you to the application terminal where you can run your code in Heroku.

14. In the heroku terminal there is no need to run "python3 run.py" command as the programme is already running. After exiting the application, in order to restart this programme you can click the red button at the top that states "run programme" with a play symbol on it.

## Credits