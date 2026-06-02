# CST8919 Lab 1: Implementing User Login with Flask and Auth0

## Student Information

**Name:** Khalid Amchat  
**Student Number:** 041125350

**Course:** CST8919 - DevOps Security and Compliance   

## Project Overview

This project is a simple Flask web application that implements user authentication using Auth0.

The goal of this lab is to understand how Single Sign-On authentication works in a web application. Auth0 is used as the identity provider, and the Flask application uses Auth0 to allow users to log in, log out, and access protected content.

## Demo Video

[`Watch demo video`](https://youtu.be/dx8JuQzOHyw) 

## Project Structure

```text
cst8919-lab01/
│
├── app.py
├── auth.py
├── requirements.txt
├── .gitignore
├── README.md
│
├── static/
│   └── style.css
│
└── templates/
    ├── index.html
    ├── profile.html
    └── protected.html
```

## Auth0 Configuration

An Auth0 application was created as a Regular Web Application.

The following local URLs were configured in Auth0:

### Allowed Callback URLs

```text
http://localhost:5000/callback
```

### Allowed Logout URLs

```text
http://localhost:5000
```

### Allowed Web Origins

```text
http://localhost:5000
```

## Environment Variables

The application uses a `.env` file to store Auth0 configuration values.

Example:

```env
AUTH0_DOMAIN=your-auth0-domain
AUTH0_CLIENT_ID=your-auth0-client-id
AUTH0_CLIENT_SECRET=your-auth0-client-secret
AUTH0_SECRET=your-random-secret
AUTH0_REDIRECT_URI=http://localhost:5000/callback
PORT=5000
```

The `.env` file is not included in the GitHub repository because it contains sensitive information.

## How to Run the Application

### 1. Clone the repository

```bash
git clone https://github.com/KhalidAlgonquin/cst8919-lab01.git
cd cst8919-lab01
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

### 3. Activate the virtual environment

```bash
source venv/bin/activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Create the `.env` file

Create a `.env` file in the project root and add the required Auth0 values.

### 6. Run the application

```bash
python app.py
```

### 7. Open the application

Open the browser and go to:

```text
http://localhost:5000
```

## Application Routes

| Route | Description |
|---|---|
| `/` | Public home page |
| `/login` | Redirects the user to Auth0 login |
| `/callback` | Handles the Auth0 authentication callback |
| `/logout` | Logs out the user |
| `/profile` | Shows user profile information after login |
| `/protected` | Protected page that authenticated users can access |

## Protected Page

The `/protected` route was added for this lab.

If the user is authenticated, the application displays the protected page.

If the user is not authenticated, the application redirects the user to the Auth0 login page.


## What I Learned

In this lab, I learned how to connect a Flask application with Auth0 for user authentication. I also learned how callback URLs, login routes, logout routes, and protected routes work in a web application.

This lab helped me understand the role of an identity provider in Single Sign-On and how authentication can be added to a web application without building the entire login system manually.
