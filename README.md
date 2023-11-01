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

**Explanation of required fields**

The **Name** field is the name of your application. The **Network** field is the Immutable network on which you want to deploy your application. The available networks are:

* **Mainnet**
* **Rinkeby**
* **Goerli**

**Code example**

```javascript
// Create a new application
const application = new ImmutableApplication({
  name: "My Application",
  network: "Mainnet",
});

// Register the application
application.register();
```

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

**Explanation of the code**

The first line imports the Passport client. The second line creates a new instance of the Passport client. The third line registers the Passport authentication provider.

**Code example**

```javascript
// Import the Passport client
import Passport from "@imtbl/passport";

// Create an instance of the Passport client
const passport = new Passport();

// Register the Passport authentication provider
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

**Explanation of the code**

The `handleLogin()` function gets the user's ID and access token from the authenticated user. Then, the tokens are printed to the console.

**Code example**

```javascript
// Define a function to handle login
function handleLogin() {
  // Get the user's ID and access token.
  const tokenId = passport.user.id;
  const accessToken = passport.user.accessToken;

  // Log the tokens to the console.
  console.log("ID:", tokenId);
  console.log("Access token:", accessToken);
}

// Add a button to log in
<button onclick="handleLogin()">Log in</button>

// Add code to log in when the button is clicked
const loginButton = document.querySelector("button");
loginButton.addEventListener("click", handleLogin);
```
