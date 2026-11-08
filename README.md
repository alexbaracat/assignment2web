# Assignment 2 Web: Authentication App


A Node.js and Express web application with user registration and login. Passwords are hashed with bcrypt, sessions are handled with Passport's local strategy, and the pages are rendered server-side with EJS templates.


## Features


- Register a new account with a username, email and password
- Log in with email and password
- Passwords are stored as bcrypt hashes, never in plain text
- Session-based authentication using Passport (passport-local) and express-session
- Flash messages for login and registration feedback
- Reusable EJS partials for the shared head, header and footer
- Home page and contact page views


## Tech stack


| Area | Technology |
| --- | --- |
| Server | Node.js, Express |
| Authentication | Passport (local strategy), bcrypt |
| Sessions and messages | express-session, express-flash, method-override |
| Views | EJS templates and partials |
| Configuration | dotenv |


## Routes


| Method | Path | Purpose |
| --- | --- | --- |
| GET | / and /home | Home page |
| GET | /login | Login form |
| POST | /login | Authenticate the user |
| GET | /register | Registration form |
| POST | /register | Create a new user with a hashed password |


## Project structure


```
assignment2web/
|-- server.js             # Express app, routes and session setup
|-- passport-config.js    # Passport local strategy configuration
|-- views/
|   |-- index.ejs         # Home
|   |-- login.ejs
|   |-- register.ejs
|   |-- contacts.ejs
|   |-- partials/         # head, header, footer
|-- package.json
```


## Running it locally


```bash
npm install
```


Create a .env file in the project root with a secret for the session, for example SESSION_SECRET set to a long random string, then start the server:


```bash
node server.js
```


Open the address printed in the terminal to register an account and log in.


## Notes and next steps


Users are held in memory while the server runs, so accounts are lost on restart. A good next step is to store users in a database such as MongoDB or MySQL. Other worthwhile additions are logout handling, route protection for logged-in pages, and input validation.


## What I practiced


Password hashing, session management, server-side rendering with templates, and structuring an Express app around Passport.

