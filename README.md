# Django_Rest_API-OAuth2.0-Google_calendar
This project implements Django Rest API to perform Authentication using OAuth 2.0 for Google calendar and get the list of events from the user's Calendar.

## How it Works?
First of all clone the Project to your local machine.

To run this project you need to install Python >= 3.9

Once, you have installed Python you need to follow the following steps:

- Create a virtual environment called 'venv'.
```
python -m venv venv
```
- Now activate the virtual environment by executing the following command 
```
venv\Scripts\activate
```

### Once you have fired up your virtual evnvironment install the necessary libraries :-
```
pip install django 
pip install -r requirements.txt
```
This will install all the necessary python libraries for the project.Now we can move on to setting up the Google API.

## Google OAuth Client Creation

In this step we are going to create a Google API Client that will provide us access to the users Calendar. 

- Head on to the Google Cloud console website and create an Account.
- Create a **New Project** and the go to API's & Services -> Credentials -> Create Credentials.
- Select Web Application and follow these steps:-
- In the **Authorized JavaScript origins** add the following URI 'https://localhost:8000'
- In the **Authorized redirect URIs** add the following URI 'https://localhost:8000/rest/v1/calendar/redirect/'
- Select scope for Google Calendars as readonly 'https://www.googleapis.com/auth/calendar.readonly'
- After this download the json file at the end and replace it with the '/credentials/client_secrets.json/'

## Django SSL server

Now you need to install the django sslserver to run the project in **https://** protocol.

```
pip install django-sslserver
```
## Running the Project :

Run the following command in your virtual environment terminal to start the Django server :

```
python manage.py runsslserver
```
- Open the browser and enter the following URL :- "https://localhost:8000/rest/v1/init/"
