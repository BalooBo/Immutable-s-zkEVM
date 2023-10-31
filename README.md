**# Immutable's zkEVM**

**README.md**

This document describes how to set up a simple application for Immutable's zkEVM.

### Requirements

* Node.js 16.x or higher
* Yarn or npm

### Creating a simple application

To create a simple application, you can clone the following repository:

```
git clone https://github.com/immutable/zkEVM-boilerplate.git
```

Or you can create a new Node.js project with the following command:

```
yarn init -y
```

Then install the Passport client:

```
yarn add @imtbl/passport
```

### Registering your application with Immutable Developer Hub

To register your application with Immutable Developer Hub, follow these steps:

1. Sign in to Immutable Developer Hub.
2. Click the "Create application" button.
3. Enter a name for your application.
4. Select the Immutable network on which you want to deploy your application.
5. Click the "Create application" button.

### Installing and initializing the Passport client

To install and initialize the Passport client, follow these steps:

1. Import the Passport client in your `index.js` file:

```javascript
import Passport from "@imtbl/passport";
```

2. Create an instance of the Passport client:

```javascript
const passport = new Passport();
```

3. Register the Passport authentication provider:

```javascript
passport.use(new Passport.ImmutableProvider());
```

### Logging in a user with Passport

To log in a user with Passport, follow these steps:

1. In your `index.js` file, define a function to handle login:

```javascript
function handleLogin() {
  // Get the user's ID and access token.
  const tokenId = passport.user.id;
  const accessToken = passport.user.accessToken;

  // Log the tokens to the console.
  console.log("ID:", tokenId);
  console.log("Access token:", accessToken);
}
```

2. In your `index.html` file, add a button to log in:

```html
<button onclick="handleLogin()">Log in</button>
```

3. In your `index.js` file, add code to log in when the button is clicked:

```javascript
const loginButton = document.querySelector("button");
loginButton.addEventListener("click", handleLogin);
```

### Displaying user information

To display user information, you can add the following code to your `index.js` file:

```javascript
// Get the user's nickname.
const nickname = passport.user.nickname;

// Log the nickname to the console.
console.log("Nickname:", nickname);
```

### Logging out a user

To log out a user, follow these steps:

1. In your `index.js` file, define a function to handle logout:

```javascript
function handleLogout() {
  // Log out the user.
  passport.logout();
}
```

2. In your `index.html` file, add a button to log out:

```html
<button onclick="handleLogout()">Log out</button>
```

3. In your `index.js` file, add code to log out when the button is clicked:

```javascript
const logoutButton = document.querySelector("button");
logoutButton.addEventListener("click", handleLogout);
```

### Starting a transaction from Passport

To start a transaction from Passport, follow these steps:

1. In your `index.js` file, define a function to start a transaction:

```javascript
function handleTransaction() {
  // Get the transaction hash.
  const transactionHash = passport.transaction.hash;

  // Log the transaction hash to the console.
  console.log("Transaction hash:", transactionHash);
}
```

2. In your `index.html` file, add a button to start a transaction:

```html
<button onclick="handleTransaction()">Start transaction</button>
```

3. In your `index.js` file, add code to start a transaction when the button is clicked:

```javascript
const transactionButton = document.querySelector("button");
transactionButton.addEventListener("click", handleTransaction);
