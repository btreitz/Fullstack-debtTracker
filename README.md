# Full-Stack Debt-Tracker
Demo Full-Stack WebApp with Node.js, Vue.js, Oracle SQL, Express.js, Passport.js with user registration and login to track payments to and from personal contacts.

My purpose of building this application was to study new technologies like authentication, client-server communication, database implementation, cookies and many more.

_Currently only for mobile use, Frontend is not optimized for desktop use_

In this app you can register yourself as a new user. After logging in, you can add other already registered users to manage payments.

Users, payments and all contact-relations are stored in an Oracle Database.

## Technologies
* Vue.js
  * HTML
  * CSS
  * JavaScript
* Node.js
* Express.js
  * cookie-session
* Axios
* Passport.js
* Oracle SQL

## Features
Data from the registration is validated at the backend.
If everything is correct, the password is hashed with *bcrypt* and a new user is inserted into the database. Now the user can login.
In case of any errors, the frontend is notified.

<img src="/Frontend/src/assets/registration-cropped.gif" alt="Video of Registration" width="300"/>

***

A successful login creates a session that is saved in a cookie up to 24 hours.
The user then ends up at the dashboard on which all of his/her contacts are listed.
By swiping right, the feed is reached. The feed lists all entered payments to and from the user in chronological order.
Payments from a contact to the user are highlighted in green while payments from the user to a contact are highlighted in red and a "minus".
Every payment has a collapsible with the entered description.

<img src="/Frontend/src/assets/login & feed-cropped.gif" alt="Video of login & feed" width="300"/>

***

To find new contacts, the user can search by username or email. Contacts can then be added to your contacts_list who will be updated immediately at the dashboard. Just added contacts can be deleted simply by pressing the *Add-Button* again.

<img src="/Frontend/src/assets/Add & Delete-contact-cropped.gif" alt="Video of delete contact" width="300"/>

***

The *Quick-Search* on the dashboard allows a user to find specific contacts faster. By pressing on a contact-field, the user is redirected to the *Contact*-component which shows basic information about this contact and a button to delete this contact from your list. Furthermore, all payments between the user and this contact, an *All-Time balance* and a button to add a new payment are shown. Like in the feed, each payment has a collapsible with the payment-description and payment amounts are accordingly highlighted.

<img src="/Frontend/src/assets/Contact-information-cropped.gif" alt="Video of contact information" width="300"/>

***

By pressing the *Add-payment-Button* a modal appears in which the user enters all payment information. 
After the new payment is inserted into the database, the modal closes and the new payment is visible in the payments-list.

<img src="/Frontend/src/assets/Add-payment-cropped.gif" alt="Video of add payment" width="300"/>

## Local set up for development purposes
1. Clone repo `git clone https://github.com/btreitz/Fullstack-debtTracker.git`
2. The following must be installed:
    * [Node.js](https://nodejs.org/en/) (includes npm)
    * An Oracle Database like [Oracle Database XE](https://www.oracle.com/database/technologies/appdev/xe.html)
3. Create your own Oracle Database
4. Execute all SQL-Statements in [`setupTables.sql`](https://github.com/btreitz/Fullstack-debtTracker/blob/master/Backend/oracleSetup/setupTables) (and optionally in [`setupInsert.sql`](https://github.com/btreitz/Fullstack-debtTracker/blob/master/Backend/oracleSetup/setupTables)) in your SQL development environment
5. Enter the connection-information and credentials in [`db_config.js`](https://github.com/btreitz/Fullstack-debtTracker/blob/master/Backend/config/db_config.js) according to your database
6. Open the terminal in `/Backend` and install modules with `npm install`
7. Navigate to `/Frontend` and install modules with `npm install`
8. Navigate to `/Backend` and run the server with `nodemon server.js` or `node server.js`
9. Open your browser and go in development mode to resize the tab into mobile scale
10. Open `http://localhost:3000/`


## License
[MIT](https://choosealicense.com/licenses/mit/)
