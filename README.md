# gci-firebase-hello-world

#### First install Firebase CLI
```
npm install firebase-functions@latest --save
npm install -g firebase-tools
```

#### Initialize your project
  1. Run `firebase login` to log in via the browser and authenticate firebase tool.
  2. Go to your project directory.
  3. Run `firebase init functions` (The tool gives you two options for language support: Javascript, TypeScript)
  
Your project must import the Cloud Functions modules using Node `require` statements. Add lines like the following to your `index.js` file
```javascript
const functions = require('functions')
```
These lines load the `firebase-functions` modules. The Firebase CLI automatically installs the Firebase and Firebase SDK for Cloud Functions Node modules when you initialize your project.

#### Add the *helloWorld* function
```javascript
const functions = require('firebase-functions');

exports.helloWorld = functions.https.onRequest((request, response) => {
    response.send('Hello World');
});
```

#### Deploy and execute *helloWorld()*
Run this command to deploy your functions:
```
firebase deploy --only functions
```

After you deploy, The Firebase CLI outputs the URL for any HTTP function endpoints. In your terminal.

[https://us-central1-gci-2017.cloudfunctions.net/helloWorld](https://us-central1-gci-2017.cloudfunctions.net/helloWorld)
