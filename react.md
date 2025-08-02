
# PROGRAMMING WITH NODE

By: Sumeet Singh @ sumeet-singh.com

Date: July 2024

# TABLE OF CONTENTS
- [1. Terminologies](#terminologies)
- [2. Requirements](#requirements)
- [3. Installing](#installing)
- [4. Profile script](#profile-script)
- [5. Common Commands](#common-commands)
- [6. Scripts](#scripts)
- [7. React](#react)
- [8. Limitations](#limitations)
- [9 React](#react)

# TERMINOLOGIES

## TERMINOLOGIES - REACT

React "React simplifies state management in JavaScript by introducing hooks, which allow 
functional components to manage state and perform side effects effectively."

## TERMINOLOGIES - HOOK

Hooks: "Hooks allow management of state within react."

JS has several hooks that are imported from react that allow managing state.

4 Common examples

useState: Manages local component state.
useEffect: Performs side effects after render.
useContext: Accesses React context.
useReducer: Alternative to useState for more complex state management.

EXAMPLE

```javascript
// To import a hook, import from React
import React, { useState, useEffect, useContext, useReducer } from 'react';
```

## TERMINOLOGIES - FUNCTIONAL COMPONENT

A React function that returns JSX.

EXAMPLE

UserProfile below is a functional component that accepts no props parameter "()" but instead 
has defined variables that are returned as html elements within a page e.g, 
homepage as <UserProfile />.


```javascript
import React from 'react';

const UserProfile = () => {
  const firstName = 'John';
  const surname = 'Doe';
  const email = 'john.doe@example.com';

  return (
    <div>
      <h1>User Profile</h1>
      <p>Name: {firstName} {surname}</p>
      <p>Email: {email}</p>
    </div>
  );
};

export default UserProfile;
```

Greeting below is a functional component that accepts a props parameter for name. It can 
be imported into a homepage as <Greeting />.

```javascript
import React from 'react';

const Greeting = (props) => {
  return (
    <div>
      <h1>Hello, {props.name}!</h1>
      <p>Welcome to React.</p>
    </div>
  );
};

export default Greeting;
```

## TERMINOLOGIES - STATE - useState

State: "State dynamically updates the frontend HTML/DOM based on actions such as user 
interactions (e.g., clicks, inputs) and responses from backend interactions."

Basic Javascript requires getting elements (DOM Manipulation), attaching 
event listeners (Event Handling) and hardcoding the html tags (non reuseable), 
whereas React abstracts the former in reusable components.

React uses "state" by assigning variables/functions a state. That dynamically
update the front end based on actions e.g. the button clicks on return html code.

VANILLA JAVASCRIPT
```html
<body>
    <div class="counter">
        <h2>Counter Example</h2>
        <!-- usage -->
        <p>Count: <span id="count">0</span></p>
        <button class="btn" id="incrementBtn">Increment</button>
        <button class="btn" id="decrementBtn">Decrement</button>
    </div>

    <script>
        let count = 0;

        const increment = () => {
            count++;
            updateUI();
        };

        const decrement = () => {
            count--;
            updateUI();
        };

        const updateUI = () => {
            const countElement = document.getElementById('count');
            countElement.textContent = count;
        };

        // Event listeners for buttons
        document.getElementById('incrementBtn').addEventListener('click', increment);
        document.getElementById('decrementBtn').addEventListener('click', decrement);
    </script>
</body>
</html>
```

REACT
```javascript
// src/components/Counter.js
import React, { useState } from 'react';

const Counter = () => {
    const [count, setCount] = useState(0);

    const increment = () => {
        setCount(count + 1);
    };

    const decrement = () => {
        setCount(count - 1);
    };

    return (
        <div>
            <button onClick={increment}>Increment</button>
            <button onClick={decrement}>Decrement</button>
            <p>Count: {count}</p>
        </div>
    );
};

// usage in src/App.js
import Counter from './components/Counter';

function App() {
    return (
        <div>
          <div class="counter">
            <h1>Counter example</h1>
            <Counter />
          </div>
        </div>
    );
}

export default App;
```

## TERMINOLOGIES - STATE - useEffect

```javascript
import React, { useState, useEffect } from 'react';

const UserProfile = () => {
  const [user, setUser] = useState(null);

  // useEffect hook to fetch user data when the component mounts
  useEffect(() => {
    const fetchUserData = async () => {
      const response = await fetch('https://jsonplaceholder.typicode.com/users/1');
      const userData = await response.json();
      setUser(userData);
    };

    fetchUserData();
  }, []);

  return (
    <div>
      <h1>User Profile</h1>
      {user ? (
        <div>
          <p>Name: {user.name}</p>
          <p>Email: {user.email}</p>
          <p>Phone: {user.phone}</p>
        </div>
      ) : (
        <p>Loading user data...</p>
      )}
    </div>
  );
};

  export default userProfile;
  ```

## TERMINOLOGIES - FACTORY FUNCTION

DESCRIPTION

FACTORY FUNCTION

As well as Javascript having a ability to define classes and constructors, dynamically typed 
langauges like JS can define an object (similar to a struct or class) within an object so it 
can be returned.

While any function can technically be called a factory function if it returns an object, factory
functions are used in situations where objects are defined within functions without the need for
constructors/deconstructors. Similar to a c++ template.

EXAMPLES

```javascript
// Direct Initialization with a Class
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

// Using Factory Function
function createPerson(name, age) {
  let person = {};

  person.name = name;
  person.age = age;

  person.greet = function() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  };

  return person;
}

const person1 = createPerson('Alice', 30); // Using factory function
let person2 = new Person('Sumeet', 33); // Using class initialisation

person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
person1.greet(); // Output: Hello, my name is Sumeet and I am 33 years old.

console.log(person1.name);
```

In c++ you cannot define a class or struct within a function so a similar Python example is below

```python
# Factory function to create a Person object
def create_person(name, age):
    # Define and initialize the object within the function
    person = {
        'name': name,
        'age': age,
        'greet': lambda: print(f"Hello, my name is {name} and I am {age} years old.")
    }
    return person

# Using the factory function to create Person objects
person1 = create_person('Alice', 30)
person2 = create_person('Bob', 25)

person1['greet']()  # Output: Hello, my name is Alice and I am 30 years old.
person2['greet']()  # Output: Hello, my name is Bob and I am 25 years old.

```


# REQUIREMENTS

# INSTALLING

1. Install node.js
```bash
Windows: winget install Node.js
MacOS: brew install node
Linux: apt install node
```

2a. (OPTIONAL) If cloning React website for first time
if the /node_modules is missing the dependencies to run the app
you will first need to cd into folder with file package.json then run the below
to create the node_modules folder. Then skip to START WEBSITE step
```bash
npm install
```

2b. (OPTIONAL) - RESET/CLEAR NPM CACHE
```bash
npm cache clean --force
```

3a. INSTALL LIBS - CWD e.g, ```C:\Users\<YourUsername>\Documents\My-React-Website\node_modules```
The recommended approach. You can just use a .gitignore to exclude these files from version control
but keep them within this space so it's easier to port across different computers to work from
without rebuilding your environment
```bash
npm install react-router-dom, create-react-app

# e.g. for common libs

npm install react-router-dom, create-react-app, express mysql2 bcryptjs jsonwebtoken body-parser cors axios

```
3b. INSTALL LIBS - GLOBALLY e.g. ```C:\Users\<YourUsername>\AppData\Roaming\npm\node_modules```
```bash
npm install -g react-router-dom, create-react-app
```

4. RUNNING LIB TO CREATE REACT WEBSITE TEMPLATE
This will setup a template react website in current working directory. You can test with npm start within
```bash
create-react-app my-app
```

5. START WEBSITE FOR TESTING LOCALLY
If any errors they will display in webpage, fix before building and try again
```bash
npm start
```

4. CONVERT REACT WEBSITE TO STATIC PAGES IN ./Build
for hosting e.g, uploading in Godaddy to host website
```bash
npm run build
```

# PROFILE SCRIPT

# COMMON COMMANDS

# SCRIPTS

# REACT

## LIMITATIONS

File path names should be short! If something looks too long then it's time to shorten.

## SPECIAL CHARACTERS - HTML ESCAPING - ENCODING

TO render special characters in react use the escape character e.g. < = &lt;

e.g. 
Will throw error - <p> This is a less then and greater then symbol <> </p>
Will successfully pass - <p> This is a less then and greater then symbol &lt;&gt; </p>


## FULL STACK JAVASCRIPT - MERN (MongoDB, Express, React, Node) 

The best way to implement React is to use Javascript for Full stack. No other Language needed!

So JSON is used in API calls to read from a NoSQL DB such as MongoDB which stores data in BSON
(Binary JSON) to replace traditional SQL DB's.

Frontend - React (optionally written in Typescript, and styled in Tailwind)
Backend - Express running node.js
Database - MongoDB

## COMMON COMMANDS

COMMENTS
```javascript

// OUTISDE JSX

/*
  OUTSIDE JSX
*/

{/* INSIDE JSX */}

{/*
  INSIDE JSX
*/}

```

## INSTALLING REACT

1. Install node.js
```bash
Windows: winget install Node.js
MacOS: brew install node
Linux: apt install node
```

## OPTIONAL - INSTALL CLONED WEBSITE

1. IF CLONING REACT FOR FIRST TIME
```bash
npm install
```

OPTIONAL - RESET/CLEAR NODE MODULES CACHE IF ERRORS OCCUR DURING INSTALLATION
```bash
npm cache clean --force
```

## CREATE WEBSITE

DESCRIPTION
The steps below will create a website with
* Account/Login/Logout/Signup/Modification - full API functionality
* Shopping Cart/Checkout - Full shopping functionality
* Example game on frontpage

IMPLEMENTATION
There are 2 methods for database connection, Local DB or Remote DB, both methods
are outlined in the steps below;

The steps below will advise to build both, and the Local DB can be used for testing purposes.

LOCAL DB STACK
 * Frontend - React
 * Backend - Express, Node.js
 * Database - MySQL
 * Hosting - http://localhost:5001


REMOTE DB STACK
 * Frontend - React
 * Backend - AWS Lambda + AWS API Gateway
 * Database - AWS RDS MySQL
 * Hosting - AWS Route 53 + AWS Certificate Manager + AWS Cloudfront + AWS S3 (region: us-east-1)

REQUIREMENTS
For the Remote DB if used perform the below;
Setup an AWS web hosting account by following ```AWS_web_hosting_commands.md```
Create a remote AWS RDS MySQL DB by following ```MySQL_commands```

API's
```bash
DELETE /delete-account // Listens for DeleteAccountButton.js
DELETE /logout // Listens for LogoutButton.js 
GET /get-account-details // Listens for AccountForm.js
POST /https://formspree.io // Listens for ContactUsForm.js
POST /login // Listens for LoginForm.js
POST /signup // Listens for SignUpForm.js
POST /update-account // Listens for AccountForm.js
PUT /join-mailing-list // Listens for JoinMailingList.js
```

Building, Testing and Deploying
* Locally (Dev) - Build a backend SQL server and use node.js to run backend Server.js
* Online (Prod) - Push this repo to Github and Github Actions CI/CD will build/test/publish to 
S3 bucket

1. Change to parent directory to host website project directory
```bash
cd c:\users\sumeetsingh\Documents ; #windows
cd /Users/sumeetsingh/Documents ; #macos
```

2. Install create-react-app globally. Recommended as it will hold all other libs
```bash
npm install -g create-react-app
```

3. CREATE REACT WEBSITE TEMPLATE
will initialise git, create .gitignore configured to ignore node_modules. Ready to commit
```bash
create-react-app sumeet-singh.com
```

4. MOVE INTO PROJECT
```bash
cd sumeet-singh.com
```

5. INSTALL LIBS IN ./NODE_MODULES
```bash
# note papaparse is for csv parsing instead of using a ProductData.js use a ProductData.csv instead
npm install react-router-dom papaparse
```

6. DELETE DEFAULT FILES + REMOVE ENTRIES
```bash
# Delete all unnecessary files
cd public
rm logo192.png logo512.png manifest.json robots.txt

# Delete unnecessary lines in index.html
sed -i "" '12,26d' ./index.html
sed -i "" '17,26d' ./index.html

cd ../src
rm App.js App.test.js index.css logo.svg reportWebVitals.js setupTests.js

# Populate App.js with general boilerplate
touch App.js
echo "function App() {
  return <div className='App'>Hello World</div>;
}
export default App;" >> App.js

# Delete unnecessary lines in index.js
sed -i "" '3d' ./index.js
sed -i "" '4d' ./index.js
sed -i "" '12,15d' ./index.js
```

7. CHANGE TITLE
change the <title> tag in /public/index.html to the websites name e.g. <title>Sumeet Singh</title>

8. CD TO SRC
```bash
cd src
```

9. CREATE ALL FOLDERS
```bash
mkdir assets # for assets e.g. graphics, sounds, images, videos to display on webpage
mkdir assets/documents
mkdir assets/documents/policies
mkdir assets/graphics
mkdir assets/graphics/Books
mkdir assets/graphics/logos
mkdir assets/sounds
mkdir assets/videos
mkdir data # e.g. centralised place for product data eg. ProductData.js contains info on books that are on various pages for sale
mkdir pages # for pages e.g. homepage.js, contactus.js, news.js
mkdir components # for reusable assets e.g. header.js, footer.js
mkdir components/backend # for backend code e.g. SubmtiSignUp.js, SubmitLogin.js
```

10. ADD FAVICON AND LOGO
```bash
cp path_to_your/favicon.ico /public/favicon.ico
cp path_to_your/logo.png /src/assets/graphics/logos/logo.png
```

12. REPLACE DEFAULT CSS /src/App.css
```css
/* 
The example CSS below is for a flex website for more information on how to
use flex read ULTIMATE FLEX GUIDE: https://css-tricks.com/snippets/css/a-guide-to-flexbox/ 

Uses a HTML structure as below
<div className="wrapper">
<header>
<main>
<footer>
</div>
*/

/* Reset and basic styles */
body, html, #root {
  font-family: Arial, sans-serif; /* Fallback font */
  margin: 0;
  padding: 0;
  height: 100%;
  box-sizing: border-box; /* Ensures padding and border are included in total width/height */
}

a {
  text-decoration: none; /* remove underline sitewide from all url links*/
}

/* Wrapper for entire layout */
.wrapper {
  display: flex;
  flex-direction: column; /* Stacks header, main content, and footer vertically */
  min-height: 100vh; /* Ensures wrapper spans the full viewport height */
}

/* Header styles */
.header {
  display: flex;
  justify-content: space-between; /* Space between logo and nav links */
  align-items: center; /* Center items vertically */
  padding: 1rem; /* Padding around header content */
  background-color: #f8f9fa; /* Background color for header */
}

.header a {
  text-decoration: none; /* Remove underline from links */
  color: black; /* Set link color */
}

.header a:hover {
  text-decoration: underline; /* Add underline on hover */
}

.header img {
  width: 100px; /* Fixed width for logo */
  height: 100px; /* Fixed height for logo */
}

/* Navigation links styles specific to header */
.header .nav-links {
  display: flex; /* Align links horizontally */
  list-style: none; /* Remove default list styles */
  margin: 0; /* Remove default margin */
  padding: 0; /* Remove default padding */
}

.header .nav-links li {
  margin: 0 1rem; /* Space between each link */
}

.header .nav-links li a {
  text-decoration: none; /* Remove underline from links */
  color: black; /* Set link color */
}

.header .nav-links li a:hover {
  text-decoration: underline; /* Add underline on hover */
}

/* Main content area */
.main {
  display: flex;
  justify-content: space-between; /* Evenly distributes columns */
  align-items: flex-start; /* Aligns columns at the top */
  padding: 2rem; /* Provides padding around main content */
}

.column1,
.column3 {
  flex: 0 0 calc((100% - 4rem) * 0.15); /* 15% width, fixed */
  padding: 1rem; /* Provides padding inside each column */
}

.column2 {
  flex: 0 0 calc((100% - 4rem) * 0.7); /* 70% width, fixed */
  padding: 1rem; /* Provides padding inside column2 */
}

.product-img {
  max-width: 100%; /* Ensure images do not exceed their container width */
  height: auto; /* Maintain aspect ratio */
  max-height: 500px; /* Limit maximum height to 300 pixels */
}

/* Footer styles */
.footer {
  display: flex;
  justify-content: space-between; /* Evenly distributes footer columns */
  padding: 1rem; /* Provides padding around footer content */
  background-color: antiquewhite;
}

.footer a {
  text-decoration: none; /* Remove underline from links */
  color: black; /* Set link color */
}

.footer .footercolumn {
  flex: 1; /* Each footer column takes equal space */
  padding: 0 1rem; /* Provides padding inside each footer column */
}

.footer .footercolumn h4 {
  margin-top: 0; /* Removes margin on top of heading */
}

.footer .footercolumn ul,
.footer .footercolumn p {
  margin: 0;
  padding: 0;
  list-style: none; /* Removes default list styles */
}

.footer .footercolumn ul li {
  margin: 0.5rem 0; /* Provides margin between list items */
}

.buttonspace {
  /* For adding space between buttons in a single row */
  display: flex;
  justify-content: flex-start; /* Adjust as needed */
  margin-bottom: 10px; /* Adjust margin if needed */
}

```

13. Edit your App.js to the below
```javascript
import React from 'react';
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
import Header from './components/Header';
import Footer from './components/Footer';
import HomePage from './pages/Homepage';
import Biography from './pages/Biography';
import Books from './pages/Books';
import News from './pages/News';
import ContactUs from './pages/ContactUs';
import NotFound from './pages/NotFound';
import './App.css';

function App() {
  return (
    <div className="App">
      <div className="wrapper">
        <Header />
        <div className="row">
          <div className="column1"></div>
          <div className="column2">
            <Routes>
              <Route path="/" element={<HomePage />} />
              <Route path="/books" element={<Books />} />
              <Route path="/biography" element={<Biography />} />
              <Route path="/news" element={<News />} />
              <Route path="/contactus" element={<ContactUs />} />
              <Route path="*" element={<NotFound />} />
            </Routes>
          </div>
          <div className="column3"></div>
        </div>
        <Footer />
      </div>
    </div>
  );
}

function AppWrapper() {
  return (
    <Router>
      <App />
    </Router>
  );
}

export default AppWrapper;
```

12. Create ./.env FILE & ASSOCIATED REPOSITORY SECRET KEY FOR CI/CD
```bash
# ./.env

# EXAMPLE BELOW
REACT_APP_GOOGLE_MAPS_API_KEY='askjdhakjsdhakshdklajsh89yq3984y'
```

13. ADD ENTRY TO SKIP ENV FILE IN .GITIGNORE
```bash
.env
```

14. OPTIONAL - CREATE PRODUCT INVENTORY src/data/ProductData.js
```javascript
// src/data/ProductData.js

import id1a from '../assets/graphics/products/books/1a.png';
import id1b from '../assets/graphics/products/books/1b.png';
import id2a from '../assets/graphics/products/books/2a.png';
import id2b from '../assets/graphics/products/books/2b.png';
import id3a from '../assets/graphics/products/books/3a.png';
import id3b from '../assets/graphics/products/books/3b.png';
import id4a from '../assets/graphics/products/books/4a.jpg';
import id4b from '../assets/graphics/products/books/4b.jpg';
import id5a from '../assets/graphics/products/books/5a.jpg';
import id5b from '../assets/graphics/products/books/5b.jpg';
import id6a from '../assets/graphics/products/books/6a.jpg';
import id6b from '../assets/graphics/products/books/6b.jpg';

const ProductData = [
  {
    id: 1,
    name: "Cybernetics, Cyberware and Cyborgs",
    description: "A complete history of Cybernetics, Cyberware and Cyborgs",
    type: "Hardback",
    isbn: "TBD",
    publisher: "Sabrenetics",
    language: "English",
    format: "Hardback",
    price: 1,
    trim: "5 x 8 inch edition",
    pageCount: "TBD",
    publicationDate: "TBD",
    audience: "General",
    genre: "Non Fiction",
    images: [id1a, id1b]
  },
  {
    id: 2,
    name: "Cybernetics, Cyberware and Cyborgs",
    description: "A complete history of Cybernetics, Cyberware and Cyborgs",
    type: "eBook",
    isbn: "978-0-6456579-4-4",
    publisher: "Sabrenetics",
    language: "English",
    format: "EPUB",
    price: 2,
    pageCount: "TBD",
    publicationDate: "TBD",
    audience: "General",
    genre: "Non Fiction",
    images: [id2a, id2b]
  },
  {
    id: 3,
    name: "Cybernetics, Cyberware and Cyborgs",
    description: "A complete history of Cybernetics, Cyberware and Cyborgs",
    type: "Paperback",
    isbn: "978-0-6456579-2-0",
    publisher: "Sabrenetics",
    language: "English",
    format: "Paperback",
    price: 3,
    trim: "5 x 8 inch edition",
    pageCount: "TBD",
    publicationDate: "TBD",
    audience: "General",
    genre: "Non Fiction",
    images: [id3a, id3b]
  },
  {
    id: 4,
    name: "Cyborg Alphabet",
    description: "An alphabet on science for children",
    type: "Hardback",
    isbn: "978-0-6456579-0-6",
    publisher: "Sabrenetics",
    language: "English",
    format: "Hardback",
    price: 32.99,
    trim: "8.5 x 8.5 inch edition",
    pageCount: "36",
    publicationDate: "January 1st, 2023",
    audience: "Children",
    genre: "Non Fiction",
    images: [id4a, id4b]
  },
  {
    id: 5,
    name: "Cyborg Alphabet",
    description: "An alphabet on science for children",
    type: "eBook",
    isbn: "978-0-6456579-1-3",
    publisher: "Sabrenetics",
    language: "English",
    format: "EPUB",
    price: 2.99,
    pageCount: "36",
    publicationDate: "January 1st, 2023",
    audience: "Children",
    genre: "Non Fiction",
    images: [id5a, id5b]
  },
  {
    id: 6,
    name: "Cyborg Alphabet",
    description: "An alphabet on science for children",
    type: "Paperback",
    isbn: "978-0-6456579-2-0",
    publisher: "Sabrenetics",
    language: "English",
    format: "Paperback",
    price: 6,
    trim: "8.5 x 8.5 inch edition",
    pageCount: "TBD",
    publicationDate: "TBD",
    audience: "Children",
    genre: "Non Fiction",
    images: [id6a, id6b]
  }
];

export default ProductData;

```

## CREATE PAGES

1. Create page /src/pages/Account.js and add the below
Include button to delete account with confirmation for full CRUD
Include button to sign up for Mailing list
```javascript
// src/pages/Account.js

import React from 'react';
import AccountForm from '../components/backend/AccountForm';
import DeleteAccountButton from '../components/backend/DeleteAccountButton';
import SubscribeMailingListButton from '../components/backend/SubscribeMailingListButton';
import UnsubscribeMailingListButton from '../components/backend/UnsubscribeMailingListButton';

const Account = () => {
  const authToken = localStorage.getItem('authToken');
  const username = authToken ? JSON.parse(atob(authToken.split('.')[1])).username : ''; // Decode token to extract username

  return (
    <div>
      <div className="main">
        <div className="column1">
          {/* Content for left column (column1) */}
        </div>
        <div className="column2">
          <div style={{ textAlign: 'center' }}>
            <h1>Account</h1>
          </div>
          <br />
          <p>
            Welcome, {username}
          </p>
          {/* Render account details form, join mailing list, delete account button */}
          <AccountForm />
          <div className="buttonspace">
            <SubscribeMailingListButton />
            <UnsubscribeMailingListButton />
          </div>
          <DeleteAccountButton />
        </div>
        <div className="column3">
          {/* Content for right column (column3) */}
        </div>
      </div>
    </div>
  );
};

export default Account;

```

2. Create page /src/pages/Cart.js and add the below
```javascript
// src/pages/Cart.js

import React, { useEffect, useState } from 'react';
import { Link } from 'react-router-dom';
import ProductData from '../data/ProductData';

const Cart = () => {
  const [cartItems, setCartItems] = useState([]);
  const [shippingCost, setShippingCost] = useState(0);
  const [firstName, setFirstName] = useState('');
  const [surname, setSurname] = useState('');
  const [street, setStreet] = useState('');
  const [city, setCity] = useState('');
  const [postcode, setPostcode] = useState('');
  const [country, setCountry] = useState('');

  useEffect(() => {
    const storedCart = JSON.parse(localStorage.getItem('cart')) || [];
    setCartItems(storedCart);
  }, []);

  const removeFromCart = (itemId, quantityToRemove) => {
    const updatedCart = cartItems.map(item => {
      if (item.id === itemId) {
        return {
          ...item,
          quantity: item.quantity - quantityToRemove
        };
      }
      return item;
    }).filter(item => item.quantity > 0);

    setCartItems(updatedCart);
    localStorage.setItem('cart', JSON.stringify(updatedCart));
  };

  const handleFirstNameChange = (event) => {
    setFirstName(event.target.value);
  };

  const handleSurnameChange = (event) => {
    setSurname(event.target.value);
  };

  const handleStreetChange = (event) => {
    setStreet(event.target.value);
  };

  const handleCityChange = (event) => {
    setCity(event.target.value);
  };

  const handlePostcodeChange = (event) => {
    setPostcode(event.target.value);
    calculateShippingCost(event.target.value, country);
  };

  const handleCountryChange = (event) => {
    setCountry(event.target.value);
    calculateShippingCost(postcode, event.target.value);
  };

  const calculateShippingCost = (postcode, country) => {
    let cost = 0;
    // Sample logic to determine shipping cost based on postcode and country
    if (postcode && country) {
      if (country.toLowerCase() === 'usa') {
        cost = 10; // $10 flat rate for USA
      } else {
        cost = 20; // $20 flat rate for other countries
      }
    }
    setShippingCost(cost);
  };

  const getItemDetails = (itemId) => {
    const item = ProductData.find(item => item.id === itemId);
    return item;
  };

  const getTotalValue = () => {
    const itemsTotal = cartItems.reduce((total, item) => {
      const product = getItemDetails(item.id);
      return total + (product ? product.price * item.quantity : 0);
    }, 0);
    return itemsTotal + shippingCost;
  };

  return (
    <div>
      <div className='main'>
        <div className="column1"></div>
        <div className="column2">
          <br />
          <br />
          <div style={{ textAlign: 'center' }}>
            <h1>Cart</h1>
          </div>
          <br />
          {cartItems.map(cartItem => {
            const product = getItemDetails(cartItem.id);
            if (!product) {
              return null; // Skip rendering if product is not found
            }
            return (
              <div key={cartItem.id}>
                <h3>{product.name}</h3>
                <p>ID: {cartItem.id}</p>
                <p>Price: ${product.price.toFixed(2)}</p>
                <p>Quantity: {cartItem.quantity}</p>
                <p>Format: {cartItem.format}</p>
                <button onClick={() => removeFromCart(cartItem.id, cartItem.quantity)}>Remove All</button>
                <hr />
              </div>
            );
          })}
          {cartItems.length === 0 && <p>Your cart is empty</p>}
          <br />
          {/* Customer information */}
          <label>First Name:</label>
          <input type="text" value={firstName} onChange={handleFirstNameChange} />
          <br />
          <label>Surname:</label>
          <input type="text" value={surname} onChange={handleSurnameChange} />
          <br />
          {/* Shipping address */}
          <label>Street:</label>
          <input type="text" value={street} onChange={handleStreetChange} />
          <br />
          <label>City:</label>
          <input type="text" value={city} onChange={handleCityChange} />
          <br />
          {/* Delivery details */}
          <label>Postcode:</label>
          <input type="text" value={postcode} onChange={handlePostcodeChange} />
          <br />
          <label>Country:</label>
          <input type="text" value={country} onChange={handleCountryChange} />
          <br />
          {/* Display shipping cost */}
          {postcode && country && (
            <p>Shipping Cost: ${shippingCost.toFixed(2)}</p>
          )}
          <br />
          {/* Display total value */}
          {cartItems.length > 0 && (
            <div>
              <h3>Total Value: ${getTotalValue().toFixed(2)}</h3>
            </div>
          )}
          <br />
          <Link to="/checkout">
            <button>Checkout</button>
          </Link>
        </div>
        <div className="column3"></div>
      </div>
    </div>
  );
};

export default Cart;

```

3. Create page /src/pages/Checkout.js and add the below
```javascript
// src/pages/Checkout.js

import React from 'react';

const Checkout = () => {
  return (
    <div>
      <div className='main'>
        <div className="column1"></div>
        <div className="column2">
          <br />
          <br />
          <div style={{ textAlign: 'center' }}>
          <h1>Checkout</h1>
          </div>
          <br />
          <h3>Checkout</h3>
          <p>
            Please confirm the products to purchase below are correct before purchasing;
          </p>
          <br />
        </div>
        <div className="column3"></div>
      </div>
    </div>
  );
};

export default Checkout;

```

4. Create page /src/pages/ContactUs.js and add the below
```javascript
// src/pages/ContactUs.js

import React from 'react';
import ContactUsForm from '../components/backend/ContactUsForm';

const ContactUs = () => {
  return (
    <div>
      <div className="main">
        <div className="column1"></div>
        <div className="column2">
          <div style={{ textAlign: 'center' }}>
            <h1>Contact Us</h1>
          </div>
          <br />
          <h3>Contact Us Form</h3>
          <ContactUsForm />
        </div>
        <div className="column3"></div>
      </div>
    </div>
  );
};

export default ContactUs;

```

5. Create page /src/pages/Books.js and add the below
```javascript
// src/pages/Books.js

import React, { useState } from 'react';
import AddCartButton from '../components/AddCartButton';
import ProductData from '../data/ProductData';

const Books = () => {
  const [cart, setCart] = useState([]);

  const addToCart = (item) => {
    setCart(prevCart => {
      const updatedCart = [...prevCart, item];
      localStorage.setItem('cart', JSON.stringify(updatedCart));
      return updatedCart; // Return the updated state
    });
  };

  return (
    <div>
      <div className='main'>
        <div className="column1"></div>
        <div className="column2" style={{ display: 'grid', gridTemplateColumns: '1fr', gap: '20px' }}>
          <br />
          <br />
          <div style={{ textAlign: 'center', gridColumn: '1' }}>
            <h1>Books</h1>
          </div>
          <br />
          {ProductData.map(product => (
            <div key={product.id} style={{ marginBottom: '40px' }}>
              <h3>{product.name}</h3>
              <p>{product.description}</p>
              <div style={{ textAlign: 'center', marginBottom: '20px' }}>
                {product.images.map((image, index) => (
                  <React.Fragment key={index}>
                    <img src={image} alt={`${product.name} ${index + 1}`} className="product-img" />
                    <br />
                    <br />
                  </React.Fragment>
                ))}
              </div>
              <h4>Purchase Link</h4>
              <div style={{ border: '1px solid #ccc', padding: '10px' }}>
                <strong>{product.type}</strong>: {product.price} AUD
                <br />
                ISBN: {product.isbn}
                <br />
                Publisher: {product.publisher}
                <br />
                Language: {product.language}
                <br />
                Trim Size: {product.trim}
                <br />
                Page Count: {product.pageCount}
                <br />
                Publication Date: {product.publicationDate}
                <br />
                Audience: {product.audience}
                <br />
                Genre: {product.genre}
                <br />
                <AddCartButton
                  item={product} // Pass the product item itself
                  format={product} // Pass the entire product as format
                  onAddToCart={addToCart}
                />
              </div>
              <br />
              <br />
            </div>
          ))}
        </div>
        <div className="column3">
          {/* Example: Display cart count */}
          <p>Cart Count: {cart.length}</p>
        </div>
      </div>
    </div>
  );
};

export default Books;

```

6. Create page /src/pages/Homepage.js and add the below
```javascript
// src/pages/Homepage.js

import React from 'react';
import SampleGame from '../components/SampleGame';

const Homepage = () => {
    return (
        <div>
            <div className="main">
                <div className="column1">
                    {/* Content for left column (column1) */}
                </div>
                <div className="column2">
                    <div style={{ textAlign: 'center' }}>
                        <h1>Calling all Gamers</h1>
                    </div>
                    <br />
                    <p>
                        Welcome to the home of niche gaming developers!
                    </p>
                    <p>
                        Meet Agnisamooh, your gateway to discovering unique and innovative Books that may not be in the spotlight yet.
                    </p>
                    <p>
                        Agnisamooh is dedicated to bridging the gap between niche game developers and a broader audience. Whether you're into indie adventures, artistic puzzles, or experimental simulations, Agnisamooh brings you curated selections that promise fresh experiences.
                    </p>
                    <p>
                        Explore our catalog to find hidden gems, support up-and-coming developers, and expand your gaming horizons.
                    </p>
                    <div style={{ textAlign: 'center' }}>
                        <SampleGame />
                        <br />
                        <a href="https://www.agnisamooh.com/Books" className="btn-primary">Discover More</a>
                    </div>
                </div>
                <div className="column3">
                    {/* Content for right column (column3) */}
                </div>
            </div>
        </div>
    );
};

export default Homepage;

```

7. Create page /src/pages/Login.js and add the below
```javascript
// src/pages/Login.js

import React from 'react';
import LoginForm from '../components/backend/LoginForm'

const Login = () => {
    return (
        <div>
            <div className="main">
                <div className="column1">
                    {/* Content for left column (column1) */}
                </div>
                <div className="column2">
                    <div style={{ textAlign: 'center' }}>
                        <h1>Login</h1>
                    </div>
                    <br />
                    <p>
                        Login to your account below
                    </p>
                    <p>NOTE: Because this is a Learning Project and not a real/live business the Database
                        which would normally be an AWS RDS DB is turned off to save money. 
                        Possibly in the future a Lambda for start/stopping DB will be triggered by LogOn/Token expire/Logoff
                        but for now for a demonstration on how it would act you can see a local server code here:
                        <a href = "https://github.com/SumeetSinghJi/agnisamooh.com/blob/main/src/components/backend/Server.js">https://github.com/SumeetSinghJi/agnisamooh.com/blob/main/src/components/backend/Server.js</a>
                    </p>
                    <LoginForm />
                </div>
                <div className="column3">
                    {/* Content for right column (column3) */}
                </div>
            </div>
        </div>
    );
};

export default Login;

```

8. Create page /src/pages/News.js and add the below
```javascript
// src/pages/News.js

import React from 'react';

const News = () => {
  return (
    <div>
      <div className='main'>
        <div className="column1"></div>
        <div className="column2">
          <br />
          <br />
          <div style={{ textAlign: 'center' }}>
          <h1>News</h1>
          </div>
          <br />
          <h3>Delay with BubbleUp</h3>
          <p>TBA: Christmas 2024</p>
          <p>
            Sorry everyone. BubbleUp is delayed. Too much volunteering efforts. Keep a eye out
            this Christmas for release.
          </p>
          <br />
        </div>
        <div className="column3"></div>
      </div>
    </div>
  );
};

export default News;

```

9. Create page /src/pages/Media.js and add the below
```javascript
// src/pages/Media.js

import React from 'react';
import LogoAppExample from '../assets/graphics/logos/example_logo.jpg';
import LogoApp from '../assets/graphics/logos/Logo-PNG-4097px.png';
import LogoDefault from '../assets/graphics/logos/FireGroup_Logo_PNG_ 4097px.png';

const Media = () => {
  return (
    <div>
      <div className='main'>
        <div className="column1"></div>
        <div className="column2">
          <br />
          <br />
          <div style={{ textAlign: 'center' }}>
          <h1>Media</h1>
          </div>
          <br />
          <h3>Free promotional images</h3>
          <p>
            You may freely use the image below to promote/discuss the agnisamooh brand.
          </p>
          <br />
          <img src={LogoAppExample} alt="Agnisamooh app logo Example" className="logo" />
          <br />
          <img src={LogoApp} alt="Agnisamooh app logo" className="logo" />
          <br />
          <img src={LogoDefault} alt="Agnisamooh default logo" className="logo" />
          <br />
        </div>
        <div className="column3"></div>
      </div>
    </div>
  );
};

export default Media;

```

10. Create page /src/pages/NotFound.js and add the below
```javascript
// src/pages/NotFound.js

import React from 'react';

const NotFound = () => {
  return (
    <div>
      <div className='main'>
        <div className="column1"></div>
        <div className="column2">
          <br />
          <br />
          <p>
            <div style={{ textAlign: 'center' }}>
              <h1>Page not found</h1>
            </div>
            <br />
            <p>Error 404: The page you are looking for doesn't exist. Use the search bar to navigate elsewhere.</p>
            <p>Email: kurta.kursi@gmail.com for any questions</p>
          </p>
        </div>
        <div className="column3">
        </div>
      </div>
    </div>
  );
};

export default NotFound;
```

11. Create page /src/pages/SignUp.js and add the below
```javascript
// src/pages/SignUp.js

import React from 'react';
import SignUpForm from '../components/backend/SignUpForm'

const SignUp = () => {
    return (
        <div>
            <div className="main">
                <div className="column1">
                    {/* Content for left column (column1) */}
                </div>
                <div className="column2">
                    <div style={{ textAlign: 'center' }}>
                        <h1>Sign Up</h1>
                    </div>
                    <br />
                    <p>
                        Sign up using the form below
                    </p>
                    <SignUpForm />
                </div>
                <div className="column3">
                    {/* Content for right column (column3) */}
                </div>
            </div>
        </div>
    );
};

export default SignUp;

```

## CREATE COMPONENTS

1. Create component /src/components/AddCartButton.js and add the below
```javascript
// src/components/AddCartButton.js

import React, { useState } from 'react';

const AddCartButton = ({ item }) => {
  const [addedToCart, setAddedToCart] = useState(false);

  const addToCartHandler = () => {
    const itemToAdd = {
      id: item.id,
      name: item.name,
      price: item.price,
      quantity: 1,
      format: item.type // Assuming 'type' serves as the format identifier
    };

    // Retrieve existing cart items from localStorage
    const storedCart = JSON.parse(localStorage.getItem('cart')) || [];
    
    // Check if the item is already in the cart
    const existingItemIndex = storedCart.findIndex(cartItem => cartItem.id === itemToAdd.id && cartItem.format === itemToAdd.format);

    if (existingItemIndex !== -1) {
      // Item already exists in cart, update quantity
      storedCart[existingItemIndex].quantity += 1;
    } else {
      // Item does not exist in cart, add new item
      storedCart.push(itemToAdd);
    }

    // Update localStorage with the updated cart
    localStorage.setItem('cart', JSON.stringify(storedCart));

    // Set addedToCart state to true to display confirmation message
    setAddedToCart(true);

    // Reset addedToCart state after 2 seconds
    setTimeout(() => {
      setAddedToCart(false);
    }, 2000);
  };

  return (
    <div>
      <button onClick={addToCartHandler}>Add to Cart</button>
      {addedToCart && <p style={{ color: 'green', marginTop: '5px' }}>Added to Cart!</p>}
    </div>
  );
};

export default AddCartButton;

```

2. Create component /src/components/Footer.js and add the below
```javascript
// src/components/Footer.js

import React from 'react';
import { Link } from 'react-router-dom';

const Footer = () => {
  return (
    <div className="footer">
      <div className="footercolumn">
        <h3>Quick links</h3>
        <ul>
          <li><Link to="/">Home</Link></li>
          <li><Link to="/Books">Books</Link></li>
          <li><Link to="/news">News</Link></li>
          <li><Link to="/contactus">Contact us</Link></li>
          <li><Link to="/account">Account</Link></li>
          <li><Link to="/login">Login</Link></li>
          <li><Link to="/signup">Sign up</Link></li>
        </ul>
      </div>
      <div className="footercolumn">
        <h3>Mission</h3>
        <p>
          "To bring the best Books from the niche developers"
        </p>
      </div>
      <div className="footercolumn">
        {/* Third column content goes here */}
      </div>
    </div>
  );
}

export default Footer;

```

3. Create component /src/components/Header.js and add the below
```javascript
// src/components/Header.js

import React from 'react';
import { Link } from 'react-router-dom';
import logoImage from '../assets/graphics/logos/Logo-PNG-4097px.png';

const Header = ({ authToken, handleLogout }) => {
  return (
    <div className="header">
      <Link to="/">
        <img src={logoImage} alt="Agnisamooh logo" className="logo" />
      </Link>
      <ul className="nav-links">
        <li><Link to="/">Home</Link></li>
        <li><Link to="/Books">Books</Link></li>
        <li><Link to="/news">News</Link></li>
        <li><Link to="/contactus">Contact us</Link></li>
        <li><Link to="/cart">Cart</Link></li>
        {!authToken ? (
          <>
            <li><Link to="/login">Login</Link></li>
            <li><Link to="/signup">Sign up</Link></li>
          </>
        ) : (
          <>
            <li><Link to="/account">Account</Link></li>
            <li><Link to="/logout" onClick={handleLogout}>Logout</Link></li>
          </>
        )}
      </ul>
    </div>
  );
}

export default Header;

```

4. Create component /src/components/SampleGame.js and add the below
```javascript
// src/components/SampleGame.js

import React, { useState, useEffect, useCallback } from 'react';

const SampleGame = () => {
    const gameWidth = 400;
    const gameHeight = 400;
    const squareSize = 20;
    const initialPosition = { x: 0, y: 0 };

    // Define generateRandomPosition before its usage
    const generateRandomPosition = () => {
        const randomX = Math.floor(Math.random() * (gameWidth / squareSize)) * squareSize;
        const randomY = Math.floor(Math.random() * (gameHeight / squareSize)) * squareSize;
        return { x: randomX, y: randomY };
    };

    const [position, setPosition] = useState(initialPosition);
    const [direction, setDirection] = useState('right');
    const [score, setScore] = useState(0);
    const [gameOver, setGameOver] = useState(false);
    const [objectPosition, setObjectPosition] = useState(generateRandomPosition());
    const [bombPosition, setBombPosition] = useState(generateRandomPosition());
    const [Bookstarted, setBookstarted] = useState(false);

    const startGame = () => {
        setGameOver(false);
        setScore(0);
        setPosition(initialPosition);
        setObjectPosition(generateRandomPosition());
        setBombPosition(generateRandomPosition());
        setBookstarted(true);
    };

    const endGame = () => {
        setBookstarted(false);
        setGameOver(true);
    };

    const checkCollisions = useCallback(() => {
        if (position.x === objectPosition.x && position.y === objectPosition.y) {
            setScore(score + 10);
            setObjectPosition(generateRandomPosition());
        }

        if (position.x === bombPosition.x && position.y === bombPosition.y) {
            endGame();
        }
    }, [position, objectPosition, bombPosition, score]);

    useEffect(() => {
        const handleKeyDown = (e) => {
            e.preventDefault();
            if (!Bookstarted) return;

            switch (e.key) {
                case 'ArrowUp':
                    if (direction !== 'down') setDirection('up');
                    break;
                case 'ArrowDown':
                    if (direction !== 'up') setDirection('down');
                    break;
                case 'ArrowLeft':
                    if (direction !== 'right') setDirection('left');
                    break;
                case 'ArrowRight':
                    if (direction !== 'left') setDirection('right');
                    break;
                default:
                    break;
            }
        };

        window.addEventListener('keydown', handleKeyDown);

        return () => {
            window.removeEventListener('keydown', handleKeyDown);
        };
    }, [direction, Bookstarted]);

    useEffect(() => {
        if (!Bookstarted) return;

        const moveSquare = () => {
            switch (direction) {
                case 'up':
                    setPosition((prevPos) => ({
                        ...prevPos,
                        y: Math.max(prevPos.y - squareSize, 0)
                    }));
                    break;
                case 'down':
                    setPosition((prevPos) => ({
                        ...prevPos,
                        y: Math.min(prevPos.y + squareSize, gameHeight - squareSize)
                    }));
                    break;
                case 'left':
                    setPosition((prevPos) => ({
                        ...prevPos,
                        x: Math.max(prevPos.x - squareSize, 0)
                    }));
                    break;
                case 'right':
                    setPosition((prevPos) => ({
                        ...prevPos,
                        x: Math.min(prevPos.x + squareSize, gameWidth - squareSize)
                    }));
                    break;
                default:
                    break;
            }

            checkCollisions();
        };

        const interval = setInterval(() => {
            moveSquare();
        }, 200);

        return () => clearInterval(interval);
    }, [direction, Bookstarted, gameWidth, gameHeight, squareSize, checkCollisions]);

    return (
        <div>
            {!Bookstarted && !gameOver && (
                <div style={{ textAlign: 'center' }}>
                    <button onClick={startGame} className="btn-primary">Start Game</button>
                </div>
            )}

            {Bookstarted && (
                <div style={{ width: gameWidth, height: gameHeight, border: '1px solid black', position: 'relative', margin: '0 auto' }}>
                    <div
                        style={{
                            width: squareSize,
                            height: squareSize,
                            backgroundColor: 'blue',
                            position: 'absolute',
                            top: position.y,
                            left: position.x
                        }}
                    ></div>

                    <div
                        style={{
                            width: squareSize,
                            height: squareSize,
                            backgroundColor: 'green',
                            position: 'absolute',
                            top: objectPosition.y,
                            left: objectPosition.x
                        }}
                    ></div>

                    <div
                        style={{
                            width: squareSize,
                            height: squareSize,
                            backgroundColor: 'red',
                            position: 'absolute',
                            top: bombPosition.y,
                            left: bombPosition.x
                        }}
                    ></div>

                    <div style={{ position: 'absolute', bottom: 10, left: 10 }}>
                        Score: {score}
                    </div>
                </div>
            )}

            {gameOver && (
                <div style={{ textAlign: 'center' }}>
                    <h2>Game Over!</h2>
                    <p>Your score: {score}</p>
                    <button onClick={startGame} className="btn-primary">Play Again</button>
                </div>
            )}
        </div>
    );
};

export default SampleGame;

```

5. Create component /src/components/YouTubeEmbed.js and add the below
```javascript
// src/components/YouTubeEmbed.js

import React from 'react';

const YouTubeEmbed = ({ embedId }) => (
  <div className="video-responsive">
    <iframe
      width="560"
      height="315"
      src={`https://www.youtube.com/embed/${embedId}`}
      title="YouTube video player"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
      frameBorder="0"
      allowFullScreen
    ></iframe>
  </div>
);

export default YouTubeEmbed;

```

## CREATE COMPONENTS - BACKEND

These frontend js codes connect to API's that are in the backend. 
See below section "CONNECT TO LOCAL DATABASE" - for local DB's
See below section "CONNECT TO LOCAL DATABASE" - for online DB's

NOTE: HashPassword.js is used for the bcrypt node.js module for encrypting passwords. This 
is to be used in place of password entry for a DB. So when user logs into front end as their 
commpn password e.g. "Password1!" the "Server.js" or remove AWS Lambda endpoint code will 
encrypt. Same with password changes.

Note: the below contact us form API code uses formspree.com free API, however it's limited to 
only 2 fields email and message. So if you copy the below change to your liking and replace 
the API key

1. Create 1st backend /src/components/backend/AccountForm.js and add the below
```javascript
// src/components/backend/AccountForm.js

import React, { useState, useEffect } from "react";
import axios from 'axios';

function AccountForm() {
    const [username, setUsername] = useState('');
    const [email, setEmail] = useState('');
    const [password, setPassword] = useState('');
    const [formSubmitted, setFormSubmitted] = useState(false);
    const [errorMessage, setErrorMessage] = useState('');
    const [showPassword, setShowPassword] = useState(false);
    const [authToken, setAuthToken] = useState('');

    useEffect(() => {
        // Retrieve JWT token from localStorage on component mount
        const token = localStorage.getItem('authToken');
        if (token) {
            setAuthToken(token);
            getAccountDetails(token); // Call getAccountDetails with token
        }
    }, []); // Empty dependency array ensures this runs only on mount

    const getAccountDetails = async () => {
        try {
            const authToken = localStorage.getItem('authToken');
            setAuthToken(authToken);

            const response = await axios.get("http://localhost:5001/get-account-details", {
                headers: {
                    'Authorization': `Bearer ${authToken}`
                }
            });

            setUsername(response.data.username);
            setEmail(response.data.email);
            setErrorMessage('');
        } catch (error) {
            console.error("Failed to get account details", error);
            setErrorMessage("Failed to get account details");
        }
    };

    const handleSubmit = async (event) => {
        event.preventDefault();
        try {
            const response = await axios.post("http://localhost:5001/update-account", {
                username,
                email,
                password
            }, {
                headers: {
                    "Content-Type": "application/json",
                    "Authorization": `Bearer ${authToken}`
                }
            });

            if (!response.ok) {
                throw new Error("Failed to update account data");
            }

            setFormSubmitted(true);
            setErrorMessage('');
            getAccountDetails(); // Call to update the Account form labels
        } catch (error) {
            console.error("Failed to update account data", error);
            setErrorMessage("Failed to update account data");
        }
    };

    const togglePasswordVisibility = () => {
        setShowPassword(!showPassword);
    };

    return (
        <form onSubmit={handleSubmit}>
            <div>
                <label htmlFor="username">Username: {username} </label>
                <input
                    type="text"
                    id="username"
                    onChange={(e) => setUsername(e.target.value)}
                    placeholder="Enter new username"
                />
            </div>
            <div>
                <label htmlFor="email">Email: {email} </label>
                <input
                    type="text"
                    id="email"
                    onChange={(e) => setEmail(e.target.value)}
                    placeholder="Enter new email"
                />
            </div>
            <div>
                <label htmlFor="password">Password:</label>
                <input
                    type={showPassword ? 'text' : 'password'}
                    id="password"
                    onChange={(e) => setPassword(e.target.value)}
                    placeholder="Enter new password"
                />
                <button type="button" onClick={togglePasswordVisibility}>
                    {showPassword ? 'Hide' : 'Show'}
                </button>
            </div>
            <button type="submit">Update</button>
            {formSubmitted && <p className="success-message">Account details updated</p>}
            {errorMessage && <p className="error-message">{errorMessage}</p>}
        </form>
    );
}

export default AccountForm
```

2. Create 1st backend /src/components/backend/ContactUsForm.js and add the below
```javascript
// src/components/backend/ContactUsForm.js

import React, { useState } from 'react';

const ContactUsForm = () => {
  const [formData, setFormData] = useState({
    email: '',
    message: ''
  });

  const [formErrors, setFormErrors] = useState({});
  const [formSubmitted, setFormSubmitted] = useState(false);

  const validateForm = () => {
    let errors = { ...formErrors };
    let isValid = true;

    // Email validation (required and valid format)
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if (!formData.email.trim()) {
      errors.email = 'Email is required';
      isValid = false;
    } else if (!emailRegex.test(formData.email.trim())) {
      errors.email = 'Invalid email format';
      isValid = false;
    } else {
      errors.email = '';
    }

    // Message validation (required and character limit)
    if (!formData.message.trim()) {
      errors.message = 'Message is required';
      isValid = false;
    } else if (formData.message.length > 1000) {
      errors.message = 'Message must be less than 1000 characters';
      isValid = false;
    } else {
      errors.message = '';
    }

    setFormErrors(errors);
    return isValid;
  };

  const handleInputChange = (e) => {
    const { name, value } = e.target;

    // Limit message to 1000 characters
    if (name === 'message' && value.length > 1000) {
      return;
    }

    setFormData((prevFormData) => ({
      ...prevFormData,
      [name]: value
    }));
  };

  const handleSubmit = (e) => {
    e.preventDefault();

    if (validateForm()) {
      // Form is valid, send data to Formspree endpoint
      const form = e.target;
      const formDataObj = new FormData(form);
      const xhr = new XMLHttpRequest();

      xhr.open(form.method, form.action);
      xhr.setRequestHeader('Accept', 'application/json');
      xhr.onreadystatechange = () => {
        if (xhr.readyState !== XMLHttpRequest.DONE) return;
        if (xhr.status === 200) {
          setFormSubmitted(true);
          setFormData({
            email: '',
            message: ''
          });
        } else {
          console.error('Failed to submit form');
        }
      };

      xhr.send(formDataObj);
    }
  };

  return (
    <form
      onSubmit={handleSubmit}
      action="https://formspree.io/f/xwpeeked"
      method="POST"
    >
      <div className="form-group">
        <label htmlFor="email">Your email:</label>
        <input
          type="email"
          id="email"
          name="email"
          value={formData.email}
          onChange={handleInputChange}
        />
        {formErrors.email && <span className="error">{formErrors.email}</span>}
      </div>

      <div className="form-group">
        <label htmlFor="message">Your message:</label>
        <textarea
          id="message"
          name="message"
          value={formData.message}
          onChange={handleInputChange}
        />
        {formErrors.message && <span className="error">{formErrors.message}</span>}
      </div>

      <button type="submit">Send</button>

      {formSubmitted && <p className="success-message">Thank you for your message!</p>}
    </form>
  );
};

export default ContactUsForm;

```

3. Create 1st backend /src/components/backend/DeleteAccountButton.js and add the below
```javascript
// src/components/backend/DeleteAccountButton.js

import React, { useState } from 'react';
import axios from 'axios';
import { useNavigate } from 'react-router-dom';

const authToken = localStorage.getItem('authToken'); // Retrieve JWT token from localStorage

const DeleteAccountButton = ({ onDelete }) => {
    const navigate = useNavigate(); // Initialize useNavigate hook for navigation
    const [errorMessage, setErrorMessage] = useState(null); // State for error message

    const handleDelete = async () => {
        const confirmed = window.confirm(`Are you sure you want to delete your account?
            Deleting an account is not recoverable.`);

        if (!confirmed) {
            return;
        }

        try {
            const response = await axios.post('http://localhost:5001/delete-account', {
                method: 'DELETE',
                headers: {
                    'Content-Type': 'application/json',
                    'Authorization': `Bearer ${authToken}` // Include 'Bearer' prefix for JWT
                }
            });
            if (!response.ok) {
                throw new Error('Failed to delete account');
            }
            onDelete(); // Optional: Implement a callback to handle UI changes after deletion
            navigate('/');
        } catch (error) {
            console.error('Delete account error:', error.message);
            setErrorMessage('Failed to delete account');
        }
    };

    return (
        <div>
            <p>Click this button to delete your account. 
                Please understand that deleted accounts cannot be recovered.</p>
            <button onClick={handleDelete}>Delete Account</button>
            {errorMessage && <p className="error-message">{errorMessage}</p>}
        </div>
    );
};

export default DeleteAccountButton;

```

4. Create 1st backend /src/components/backend/HashPassword.js and add the below
```javascript
// src/components/backend/HashPassword.js
// Used for hasing a password to insert in MySQL for first time user creation
// You can also use this in your SignUpForm backend to create the hashed password
// for DB insertion
const bcrypt = require('bcryptjs');

const password = 'Password1!';
const saltRounds = 10;

bcrypt.hash(password, saltRounds, (err, hash) => {
  if (err) {
    console.error('Error hashing password:', err);
  } else {
    console.log('Hashed password:', hash);
  }
});
```

5. Create 1st backend /src/components/backend/LoginForm.js and add the below
```javascript
import React, { useState, useEffect } from 'react';
import axios from 'axios';
import { useNavigate } from 'react-router-dom';

function LoginForm() {
  const [username, setUsername] = useState('');
  const [password, setPassword] = useState('');
  const [formSubmitted, setFormSubmitted] = useState(false);
  const [showPassword, setShowPassword] = useState(false);
  const [errorMessage, setErrorMessage] = useState('');
  const navigate = useNavigate();

  useEffect(() => {
    const authToken = localStorage.getItem('authToken');
    if (authToken) {
      navigate('/account'); // Redirect to account page if logged in
    }
  }, [navigate]);

  const togglePasswordVisibility = () => {
    setShowPassword(!showPassword);
  };

  const handleSubmit = async (event) => {
    event.preventDefault();
    try {
      const response = await axios.post('http://localhost:5001/login', {
        username,
        password,
      });
      const token = response.data.token;
      localStorage.setItem('authToken', token);
      setFormSubmitted(true);
      setErrorMessage('');
      navigate('/account', { replace: true }); // Navigate to Account.js page
      window.location.reload(); // Refresh the page after navigating
    } catch (error) {
      console.error('Login failed', error);
      setErrorMessage('Login failed. Please check your username and password and try again.');
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        value={username}
        onChange={(e) => setUsername(e.target.value)}
        placeholder="Username"
      />
      <div>
        <input
          type={showPassword ? 'text' : 'password'}
          value={password}
          onChange={(e) => setPassword(e.target.value)}
          placeholder="Password"
        />
        <button type="button" onClick={togglePasswordVisibility}>
          {showPassword ? 'Hide' : 'Show'}
        </button>
      </div>
      <button type="submit">Login</button>
      {formSubmitted && <p className="success-message">Login successful!</p>}
      {errorMessage && <p className="error-message">{errorMessage}</p>}
    </form>
  );
}

export default LoginForm;

```

6. Create 1st backend /src/components/backend/SignUpForm.js and add the below
```javascript
// src/components/backend/SignUpForm.js

import React, { useState } from 'react';
import { useNavigate } from 'react-router-dom';

const SignUpForm = () => {
    const [formData, setFormData] = useState({
        username: '',
        email: '',
        password: ''
    });

    const navigate = useNavigate(); // Initialize useNavigate hook for navigation

    const handleInputChange = (e) => {
        setFormData({
            ...formData,
            [e.target.name]: e.target.value
        });
    };

    const handleSubmit = (event) => {
        event.preventDefault();

        // Sending the registration data to the API endpoint
        fetch("http://localhost:5001/signup", { // Updated API endpoint
            method: "POST",
            headers: {
                "Content-Type": "application/json"
            },
            body: JSON.stringify(formData)
        })
        .then(response => {
            if (!response.ok) {
                throw new Error("Error: Backend signup server response was not ok");
            }
            return response.json();
        })
        .then(data => {
            console.log("Success: Registered successfully: ", data);
            alert("Success: Registration successful");
            navigate('/account'); // Navigate to Account page
        })
        .catch(error => {
            console.error("Error: ", error);
            alert("Error: Registration failed. Contact support@agnisamooh.com");
        });
    };

    const togglePasswordVisibility = (e) => {
        const input = e.target.previousSibling;
        input.type = input.type === 'password' ? 'text' : 'password';
    };

    return (
        <form id="SignUpForm" onSubmit={handleSubmit}>
            <label htmlFor="username">Username:</label><br />
            <input type="text" name="username" value={formData.username} onChange={handleInputChange} maxLength="20" required /><br />
            <label htmlFor="email">Email:</label><br />
            <input type="email" name="email" value={formData.email} onChange={handleInputChange} maxLength="50" required /><br />
            <label htmlFor="password">Password:</label><br />
            <input type="password" name="password" value={formData.password} onChange={handleInputChange} maxLength="30" required /><br />
            <input type="checkbox" onClick={togglePasswordVisibility} />Show Password
            <br />
            <button type="submit">Register</button>
            <button type="reset">Reset</button>
        </form>
    );
};

export default SignUpForm;

```

7. Create 1st backend /src/components/backend/SubscribeMailingListButton.js and add the below
```javascript
// src/components/backend/SubscribeMailingListButton.js

import React, { useState } from 'react';
import axios from 'axios';

const authToken = localStorage.getItem('authToken'); // Retrieve JWT token from localStorage

const SubscribeMailingListButton = () => {
    const [formSubmitted, setFormSubmitted] = useState(false);
    const [errorMessage, setErrorMessage] = useState(null); // State for error message

    const handleSubscribeMailingList = async () => {
        try {
            const response = await axios.put('/Subscribe-mailing-list', {
                method: 'PUT',
                headers: {
                    'Content-Type': 'application/json',
                    'Authorization': `Bearer ${authToken}`
                }
            });
            if (!response.ok) {
                throw new Error('Failed to Subscribe mailing list');
            }
            setFormSubmitted(true);
            setErrorMessage('');
        } catch (error) {
            console.error('Subscribe mailing list error:', error.message);
            setErrorMessage('Failed to Subscribe mailing list');
        }
    };

    return (
        <div>
            <p>Click here to subscribe/unsubscribe to promotional marketing material
            which includes exclusive sales, events, news and more</p>
            <button onClick={handleSubscribeMailingList}>Subscribe Mailing List</button>
            {formSubmitted && <p className="success-message">Succesfully subscribed!</p>}
            {errorMessage && <p className="error-message">{errorMessage}</p>}
        </div>
    );
};

export default SubscribeMailingListButton;

```

8. Create 1st backend /src/components/backend/UnsubscribeMailingListButton.js and add the below
```javascript
// src/components/backend/UnsubscribeMailingListButton.js

import React, { useState } from 'react';
import axios from 'axios';

const authToken = localStorage.getItem('authToken'); // Retrieve JWT token from localStorage

const UnsubscribeMailingListButton = () => {
    const [formSubmitted, setFormSubmitted] = useState(false);
    const [errorMessage, setErrorMessage] = useState(null); // State for error message

    const handleUnsubscribeMailingList = async () => {
        try {
            const response = await axios.put('/Unsubscribe-mailing-list', {
                method: 'PUT',
                headers: {
                    'Content-Type': 'application/json',
                    'Authorization': `Bearer ${authToken}`
                }
            });
            if (!response.ok) {
                throw new Error('Failed to Unsubscribe mailing list');
            }
            setFormSubmitted(true);
            setErrorMessage('');
        } catch (error) {
            console.error('Unsubscribe mailing list error:', error.message);
            setErrorMessage('Failed to Unsubscribe mailing list');
        }
    };

    return (
        <div>
            <button onClick={handleUnsubscribeMailingList}>Unsubscribe Mailing List</button>
            {formSubmitted && <p className="success-message">Unsuccesfully subscribed!</p>}
            {errorMessage && <p className="error-message">{errorMessage}</p>}
        </div>
    );
};

export default UnsubscribeMailingListButton;

```

## CONNECT TO LOCAL NO-SQL DATABASE

The LoginForm.js from earlier is used to login to a SQL database defined in the Server.js below.
For details on how to setup the NoSQL Db follow the below and skip section 
```CONNECT TO LOCAL SQL DATABASE```

1. 
```bash
npm install mongodb #windows
xxx #macos
xxx # debian family 
```

## CONNECT TO LOCAL SQL DATABASE

The LoginForm.js from earlier is used to login to a SQL database defined in the Server.js below.
For details on how to setup the DB that the Server.js db_config variables use 
follow ```mysql_commands.md```

1. Find a free port for backend Server.js
```bash
# MacOS, Linux
lsof -i :5000
# Windows
netstat -ano | findstr :5000

e.g, 
sumeetsingh@Sumeets-Air backend % lsof -i :5000
COMMAND   PID        USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
ControlCe 503 sumeetsingh   10u  IPv4 0x7ba65b3bbc2c31c6      0t0  TCP *:commplex-main (LISTEN)
ControlCe 503 sumeetsingh   11u  IPv6 0x147a291c7d81ae39      0t0  TCP *:commplex-main (LISTEN)


#if port is in use then find what the PID is with
ps -p 503

e.g, 
sumeetsingh@Sumeets-Air backend % ps -p 503
  PID TTY           TIME CMD
  503 ??        14:26.37 /System/Library/CoreServices/ControlCenter.app/Contents/MacOS/ControlCe

# since that port is MacOS Airplay e.g. for sharing Apple devices let's use the next port up 5001
sumeetsingh@Sumeets-Air sandbox % lsof -i :5001
sumeetsingh@Sumeets-Air sandbox % 

# since port 5001 is free lets use that
```

2. Install backend dependencies in your react project
IMPORTANT axios.delete/post etc., requires full URL e.g;
const response = await axios.post('http://localhost:5001/login', {
        username,
        password,
      });
```bash
cd src
npm install express mysql2 bcryptjs jsonwebtoken body-parser cors axios
```

3. Create a backend node.js named: src/components/backend/Server.js
using free port in variable port ```const port = 5001;```
In production environment change variable SECRET_KEY to something different
```const SECRET_KEY = "ChangeThis1!";```
```javascript
// src/components/backend/Server.js

const express = require('express');
const bodyParser = require('body-parser');
const mysql = require('mysql2/promise');
const bcrypt = require('bcryptjs');
const jwt = require('jsonwebtoken');
// Cors allows different domains (ports) to communicate e.g. React app on localhost:3001 
// to communicate with Server.js on localhost:5000. By default the Webserver (express) will
// block communication from not same origin unless cors is included
const cors = require('cors');

const app = express();
const port = 5001;

const SECRET_KEY = "___YOUR_SECRET_KEY1!___";

app.use(bodyParser.json());
app.use(cors());

const dbConfig = {
  host: '127.0.0.1',
  user: 'admin',
  password: 'Password1!',
  database: 'agnisamoohdb',
};

// Middleware to verify JWT
function authenticateToken(req, res, next) {
  const token = req.headers['authorization'] && req.headers['authorization'].split(' ')[1];
  if (!token) return res.sendStatus(401);

  jwt.verify(token, SECRET_KEY, (err, user) => {
    if (err) return res.sendStatus(403);
    req.user = user;
    next();
  });
}

// if browsing to this file from a browser then display welcome message e.g;
// node Server.js
// http://localhost:5001/
app.get('/', (req, res) => {
  res.send('Welcome to the login server. Use the /login endpoint to log in.');
});

// Listens for LoginForm.js
app.post('/login', async (req, res) => {
  const { username, password } = req.body;

  try {
    const connection = await mysql.createConnection(dbConfig);
    const [rows] = await connection.execute('SELECT * FROM users WHERE username = ?', [username]);

    if (rows.length === 0) {
      return res.status(401).json({ error: 'Invalid credentials' });
    }

    const user = rows[0];
    const passwordMatch = await bcrypt.compare(password, user.password);

    if (!passwordMatch) {
      return res.status(401).json({ error: 'Invalid credentials' });
    }

    const token = jwt.sign({ username: user.username, userId: user.userID }, SECRET_KEY, { expiresIn: '1h' });

    return res.status(200).json({ token });
  } catch (error) {
    console.error('Login error:', error);
    return res.status(500).json({ error: 'Internal server error' });
  }
});

// Listens for SignUpForm.js
app.post('/signup', async (req, res) => {
  const { username, email, password } = req.body;

  try {
    const connection = await mysql.createConnection(dbConfig);
    const [existingUser] = await connection.execute('SELECT * FROM users WHERE username = ? OR email = ?', [username, email]);

    if (existingUser.length > 0) {
      return res.status(409).json({ error: 'Username or email already exists' });
    }

    const hashedPassword = await bcrypt.hash(password, 10);
    await connection.execute('INSERT INTO users (username, email, password, subscriptions, notes) VALUES (?, ?, ?, ?, ?)', [username, email, hashedPassword, '', '']);

    return res.status(201).json({ message: 'User created successfully' });
  } catch (error) {
    console.error('Signup error:', error);
    return res.status(500).json({ error: 'Internal server error' });
  }
});

// Listens for AccountForm.js
app.post('/update-account', authenticateToken, async (req, res) => {
  const { username, email, password } = req.body;
  const userId = req.user.userId;

  try {
    const connection = await mysql.createConnection(dbConfig);
    let updateQuery = 'UPDATE users SET ';
    const updateData = [];

    if (username) {
      updateQuery += 'username = ?, ';
      updateData.push(username);
    }

    if (email) {
      updateQuery += 'email = ?, ';
      updateData.push(email);
    }

    if (password) {
      const hashedPassword = await bcrypt.hash(password, 10);
      updateQuery += 'password = ?, ';
      updateData.push(hashedPassword);
    }

    updateQuery = updateQuery.slice(0, -2); // Remove trailing comma
    updateQuery += ' WHERE userID = ?';
    updateData.push(userId);

    await connection.execute(updateQuery, updateData);

    res.json({ message: 'Account details updated successfully' });
  } catch (error) {
    console.error('Error during account update:', error);
    res.status(500).json({ error: 'Failed to update account data' });
  }
});

// Listens for AccountForm.js
app.get('/get-account-details', authenticateToken, async (req, res) => {
  const userId = req.user.userId;

  try {
    const connection = await mysql.createConnection(dbConfig);
    const [rows] = await connection.execute('SELECT username, email FROM users WHERE userID = ?', [userId]);

    if (rows.length === 0) {
      return res.status(404).json({ error: 'User not found' });
    }

    const userDetails = rows[0];
    res.json(userDetails);
  } catch (error) {
    console.error('Error fetching account details:', error);
    res.status(500).json({ error: 'Failed to fetch account details' });
  }
});

// Listens for DeleteAccountButton.js
app.delete('/delete-account', authenticateToken, async (req, res) => {
  const userId = req.user.userId;

  try {
    const connection = await mysql.createConnection(dbConfig);
    const [result] = await connection.execute('DELETE FROM users WHERE userID = ?', [userId]);

    if (result.affectedRows === 0) {
      return res.status(404).json({ error: 'User not found' });
    }

    res.json({ message: 'Account deleted successfully' });
  } catch (error) {
    console.error('Delete account error:', error);
    res.status(500).json({ error: 'Failed to delete account' });
  }
});

// Listens for SubscribeMailingList.js
app.put('/Subscribe-mailing-list', authenticateToken, async (req, res) => {
  const userId = req.user.userID;

  try {
    const connection = await mysql.createConnection(dbConfig);
    await connection.execute('UPDATE users SET onMailingList = 1 WHERE userID = ?', [userId]);

    return res.status(200).json({ message: 'Successfully Subscribeed mailing list' });
  } catch (error) {
    console.error('Subscribe mailing list error:', error);
    return res.status(500).json({ error: 'Failed to Subscribe mailing list' });
  }
});

// Listens for UnsubscribeMailingList.js
app.put('/Unsubscribe-mailing-list', authenticateToken, async (req, res) => {
  const userId = req.user.userID;

  try {
    const connection = await mysql.createConnection(dbConfig);
    await connection.execute('UPDATE users SET onMailingList = 0 WHERE userID = ?', [userId]);

    return res.status(200).json({ message: 'Successfully Unsubscribeed mailing list' });
  } catch (error) {
    console.error('Unsubscribe mailing list error:', error);
    return res.status(500).json({ error: 'Failed to Unsubscribe mailing list' });
  }
});

// Listens for LogoutButton.js
app.delete('/logout', authenticateToken, async (req, res) => {
  // No need to access any specific user information since it's handled by JWT
  try {
      // Implement any necessary cleanup logic here (if needed)
      // Typically, clearing any server-side session or cache
      // For JWT, logging out is simply ensuring the client discards the token
      return res.status(200).json({ message: 'Logout successful' });
  } catch (error) {
      console.error('Logout error:', error);
      return res.status(500).json({ error: 'Failed to logout' });
  }
});

app.listen(port, () => {
  console.log(`Server running on http://localhost:${port}`);
});
```

4. Start the server
```bash
cd components/backend
node Server.js

e.g,
cd /Users/sumeetsingh/Documents/agnisamooh.com/src/components/backend
node Server.js
```

5. Start a new terminal window and run the website to test form
```bash
cd ../../
npm start
```

## CONNECT TO REMOTE SQL DATABASE

1. Create a Lambda to act as backend called agnisamooh-server.js
```bash
1. Go to lambda functions - create new function - function name: agnisamooh-server.js
2. Runtime node.js 20.x
3. Add code below to function, note that the SECRET_KEY variable must be unique when deploying so change it, and remember to change password details
4. In code source main page add the code below and click - file - save - then click "deploy"
```
url: https://us-east-1.console.aws.amazon.com/lambda/home?region=us-east-1#/functions
```javascript
// AWS Lambda function agnisamooh-server.js
const awsServerlessExpress = require('aws-serverless-express');
const bodyParser = require('body-parser');
const mysql = require('mysql2/promise');
const bcrypt = require('bcryptjs');
const jwt = require('jsonwebtoken');
const cors = require('cors');

const app = awsServerlessExpress.createServer(); // Create server directly with aws-serverless-express

// Replace with your actual database configuration
const dbConfig = {
  host: 'agnisamoohmysql.cv43d5o2h5wi.ap-southeast-2.rds.amazonaws.com',
  user: 'admin',
  password: 'Password1!',
  database: 'agnisamoohdb',
};

// Replace with your actual secret key for JWT
const SECRET_KEY = "___YOUR_SECRET_KEY1!___";

app.use(bodyParser.json());
app.use(cors());

// Middleware to verify JWT token
function authenticateToken(req, res, next) {
  const token = req.headers['authorization'] && req.headers['authorization'].split(' ')[1];
  if (!token) return res.sendStatus(401);

  jwt.verify(token, SECRET_KEY, (err, user) => {
    if (err) return res.sendStatus(403);
    req.user = user;
    next();
  });
}

// Welcome endpoint
app.get('/', (req, res) => {
  res.send('Welcome to the login server. Use the /login endpoint to log in.');
});

// Login endpoint
app.post('/login', async (req, res) => {
  const { username, password } = req.body;

  try {
    const connection = await mysql.createConnection(dbConfig);
    const [rows] = await connection.execute('SELECT * FROM users WHERE username = ?', [username]);

    if (rows.length === 0) {
      return res.status(401).json({ error: 'Invalid credentials' });
    }

    const user = rows[0];
    const passwordMatch = await bcrypt.compare(password, user.password);

    if (!passwordMatch) {
      return res.status(401).json({ error: 'Invalid credentials' });
    }

    const token = jwt.sign({ username: user.username, userId: user.userID }, SECRET_KEY, { expiresIn: '1h' });

    return res.status(200).json({ token });
  } catch (error) {
    console.error('Login error:', error);
    return res.status(500).json({ error: 'Internal server error' });
  }
});

// Signup endpoint
app.post('/signup', async (req, res) => {
  const { username, email, password } = req.body;

  try {
    const connection = await mysql.createConnection(dbConfig);
    const [existingUser] = await connection.execute('SELECT * FROM users WHERE username = ? OR email = ?', [username, email]);

    if (existingUser.length > 0) {
      return res.status(409).json({ error: 'Username or email already exists' });
    }

    const hashedPassword = await bcrypt.hash(password, 10);
    await connection.execute('INSERT INTO users (username, email, password, subscriptions, notes) VALUES (?, ?, ?, ?, ?)', [username, email, hashedPassword, '', '']);

    return res.status(201).json({ message: 'User created successfully' });
  } catch (error) {
    console.error('Signup error:', error);
    return res.status(500).json({ error: 'Internal server error' });
  }
});

// Update account endpoint
app.post('/update-account', authenticateToken, async (req, res) => {
  const { username, email, password } = req.body;
  const userId = req.user.userId;

  try {
    const connection = await mysql.createConnection(dbConfig);
    let updateQuery = 'UPDATE users SET ';
    const updateData = [];

    if (username) {
      updateQuery += 'username = ?, ';
      updateData.push(username);
    }

    if (email) {
      updateQuery += 'email = ?, ';
      updateData.push(email);
    }

    if (password) {
      const hashedPassword = await bcrypt.hash(password, 10);
      updateQuery += 'password = ?, ';
      updateData.push(hashedPassword);
    }

    updateQuery = updateQuery.slice(0, -2); // Remove trailing comma
    updateQuery += ' WHERE userID = ?';
    updateData.push(userId);

    await connection.execute(updateQuery, updateData);

    res.json({ message: 'Account details updated successfully' });
  } catch (error) {
    console.error('Error during account update:', error);
    res.status(500).json({ error: 'Failed to update account data' });
  }
});

// Get account details endpoint
app.get('/get-account-details', authenticateToken, async (req, res) => {
  const userId = req.user.userId;

  try {
    const connection = await mysql.createConnection(dbConfig);
    const [rows] = await connection.execute('SELECT username, email, onMailingList FROM users WHERE userID = ?', [userId]);

    if (rows.length === 0) {
      return res.status(404).json({ error: 'User not found' });
    }

    const userDetails = rows[0];
    res.json(userDetails);
  } catch (error) {
    console.error('Error fetching account details:', error);
    res.status(500).json({ error: 'Failed to fetch account details' });
  }
});

// Subscribe to mailing list endpoint
app.put('/subscribe-mailing-list', authenticateToken, async (req, res) => {
  const userId = req.user.userId;

  try {
    const connection = await mysql.createConnection(dbConfig);
    const [result] = await connection.execute('UPDATE users SET onMailingList = 1 WHERE userID = ?', [userId]);

    if (result.affectedRows === 0) {
      return res.status(404).json({ error: 'User not found or already subscribed' });
    }

    return res.status(200).json({ message: 'Successfully subscribed to mailing list' });
  } catch (error) {
    console.error('Subscribe mailing list error:', error);
    return res.status(500).json({ error: 'Failed to subscribe to mailing list' });
  }
});

// Unsubscribe from mailing list endpoint
app.put('/unsubscribe-mailing-list', authenticateToken, async (req, res) => {
  const userId = req.user.userId;

  try {
    const connection = await mysql.createConnection(dbConfig);
    const [result] = await connection.execute('UPDATE users SET onMailingList = 0 WHERE userID = ?', [userId]);

    if (result.affectedRows === 0) {
      return res.status(404).json({ error: 'User not found or already unsubscribed' });
    }

    return res.status(200).json({ message: 'Successfully unsubscribed from mailing list' });
  } catch (error) {
    console.error('Unsubscribe mailing list error:', error);
    return res.status(500).json({ error: 'Failed to unsubscribe from mailing list' });
  }
});

// Delete account endpoint
app.delete('/delete-account', authenticateToken, async (req, res) => {
  const userId = req.user.userId;

  try {
    const connection = await mysql.createConnection(dbConfig);
    const [result] = await connection.execute('DELETE FROM users WHERE userID = ?', [userId]);

    if (result.affectedRows === 0) {
      return res.status(404).json({ error: 'User not found' });
    }

    res.json({ message: 'Account deleted successfully' });
  } catch (error) {
    console.error('Delete account error:', error);
    res.status(500).json({ error: 'Failed to delete account' });
  }
});

// Logout endpoint
app.delete('/logout', authenticateToken, async (req, res) => {
  // No need to access any specific user information since it's handled by JWT
  try {
    // Implement any necessary cleanup logic here (if needed)
    // Typically, clearing any server-side session or cache
    // For JWT, logging out is simply ensuring the client discards the token
    return res.status(200).json({ message: 'Logout successful' });
  } catch (error) {
    console.error('Logout error:', error);
    return res.status(500).json({ error: 'Failed to logout' });
  }
});

// Lambda handler function
const lambdaHandler = (event, context) => {
  // Ensure the Express app is initialized once per Lambda container
  return awsServerlessExpress.proxy(server, event, context);
};

module.exports = {
  lambdaHandler
};

```


2. in AWS API create new API's with details below
url: https://us-east-1.console.aws.amazon.com/apigateway/main/precreate?region=us-east-1 
```bash
1. In AWS "API Gateway" - click build new HTTP API
2. API Name e.g,: agnisamooh-login-post-api
3. Stage name: PROD
4. Click Create to save the API
5. Go back to API's then click on the API. It will take you to the routes page
6. Click "Create a Route"
7. Route method: POST
8. Route name: /login
9. Click create
10. Click on "integrations" on the left side
11. Click create an attach an integration
12. Integration target "lambda function"
13. In the drop down select the previous created Lambda function
14. Click create
15. Click back on the API in the left navigation bar then make note of the
ARN e.g, https://7ok9pqxlg4.execute-api.us-east-1.amazonaws.com
16. Go back to the LoginForm.js and add the API to the response url adding the stage and api 
path
```javascript
const response = await axios.post('https://7ok9pqxlg4.execute-api.us-east-1.amazonaws.com/PROD/login', {
        username,
        password,
      });
17. Repeat steps for to ensure all API's below are created and keys in relevant files
POST /login // Listens for LoginForm.js # skip this as already done earlier
POST /signup // Listens for SignUpForm.js
POST /update-account-details // Listens for AccountForm.js
GET /get-account-details // Listens for AccountForm.js
PUT /subscribe-mailing-list // Listens for SubscribeMailingListButton.js
PUT /unsubscribe-mailing-list // Listens for UnsubscribeMailingList.js
DELETE /delete-account // Listens for DeleteAccountButton.js
DELETE /logout // Listens for LogoutButton.js 
```

3. Attach each API above to the relevant Lambda

4. Test login
```bash
# First push react website to production (e.g. S3 bucket) then test login
cd YOUR_REACT_PROJECT_PATH/src
npm start
1. www.agnisamooh.com/login
2. Fill out login form page with 
username; sum337
password; Password1!
3. You should be redirected to the account page
```

## DATABASE FINAL TESTING CLEANUP

1. If above tests are successfull for login remember to log back into mysql and change the
admin password and the users table test user record password. Replace the password placeholder with a new
password
```bash
-- CHANGE THE -h AND PASSWORD
mysql -h 127.0.0.1 -u root -p -e "ALTER USER 'admin'@'localhost' IDENTIFIED BY 'new_password_goes_here'; USE agnisamoohdb; UPDATE users SET password = 'new_password_goes_here' WHERE username = 'sum337';"
```

## BUILDING/DEPLOYING REACT WEBSITE

1. UNCOMMENT ./build in .gitignore for CICD
In .gitignore file remove entry for ./build so that Git/VersionControl/CI/CD will detect
the build folder contents

2. TEST WEBSITE
Running below code will automatically open the website in localhost Https://127.0.0.1 to view
```bash
npm start
```

3. CREATE REACT WEBSITE
Babel: Converts the React ES6+ standard code into an older version code for multiplatform.
Webpack: Creates the website directory (/build/index.html, /html, /css, /js) to upload anywhere.
```bash
npm run build
```

4. UPLOAD WEBSITE
Follow ```AWS_website_hosting_workflow.md```
