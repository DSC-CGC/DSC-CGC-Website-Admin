# Aura Admin
<img src="https://github.com/GDG-Jalandhar/WebsiteData/blob/master/promotion%20images/Aura%20Admin.png?raw=true" width="100%">
Version: 3.1.1

[Click Here](https://auradmin.web.app/)

### Show some :heart: and :star: the repo to support the project

## Overview

Aura Admin is the Web App that helps you to mange the Tech Communities like GDGs, DSCs or any other tech communities.

The template is created by [GDG Jalandhar](https://meetup.com/GDG-Jalandhar/) team experience of running meetups/events.

## Features
| Feature | Description |
|---|---|
| **Fast and optimized** | PWA on Lighthouse |
| **Works offline** | Can work offline |
| **Mobile first** | Mobo Friendly Web app can be installed as a native app on your phone |
| **SEO optimized** | index all content and get to the top in search results |
| **Easy in management** | Store all the data in Cloud Firestore |
| **Trigger Push Notification** | Trigger Push Notification to Aura Main |
| **Usability** | Any Tech Communities can use |


## Getting Started

1. [Fork this repository](https://github.com/gdg-x/aura-admin/fork) & [Aura Main](https://github.com/Vrijraj/aura/fork) (Important) and clone both repo locally
1. Setup Environment
    - Install [Node.js (v8.9.4 or above)](https://nodejs.org/en/download/)
    - Install vue cli: `npm install -g @vue/cli`
1. Install project dependencies: `npm install` 
1. If you already have setup [Aura Main](https://github.com/Vrijraj/aura/fork) then use same Firebase Project
1. Otherwise Create [Firebase account](https://console.firebase.google.com) and Create a new Project 
1. Go to Firebase Project Dashboard
1. Go to Cloud Firestore Database and Enable the database in test mode
1. Once the database is created, Click on Rules navigation pill and add the following lines in the rules edit
    ```js
        allow read : if true;
        allow write : if request.auth.uid != null;

    ```
1. In the Firebase project console dashboard. Click on create a new app
1. Go to Firebase project Settings and then General Settings Tab
1. Scroll down and go to your app section under Firebase SDK snippet
1. Click on node/config radio select 
1. Copy the code which looks similar to the below sample
    ```js
    apiKey: "Axxxxxxxxxxxxxxxxxxx",
    authDomain: "xxxxxx.firebaseapp.com",
    databaseURL: "https://xxxxxxxx.firebaseio.com",
    projectId: "xxxxxxxxx",
    storageBucket: "xxxxxxx.appspot.com",
    messagingSenderId: "xxxxxxxxxxx",
    appId: "1:xxxxxxxxx:web:xxxxxxx"
    ```
1. Now goto project code on your local system and inside `src/config/` update the `firebase.js` file with the code you copied from the Firebase console and Update the field `name` in `vue.config` in the local project root directory
1. Click on Authentication in the left navigation.
1. Click on Sign-in method and enable Email/Password
    - Create user with Email and Password 
1. Run locally
    `npm run serve`
1. When you are ready to build for production, use the following command - 
    - `npm run build` 
    - A directory named dist will be created
1. For testing: `npm run test`


### Push Notification Setup
1. Go to Firebase Project Dashboard
1. Go to Firebase Projects Settings then navigate to Cloud Messaging
1. Copy the `server key`
1. Go to your Aura Admin Dashboard and paste at the server key at `Config -> Keys & Securities` as `Cloud Messaging Server Key`
1. Again, in the Firebase Project Dashboard, go to `Projects Settings -> Cloud Messaging` and scroll down to the `Web configuration section` and click on `Generate Key pair`
1. Copy the generated key and Paste it at Aura Admin Dashboard’s `Config -> Keys & Securities` as `Cloud Messaging Web Push certificate`
1. Save the Config  by clicking on Save `Keys and Security`
1. For Sending Push Notification from Aura Admin Dashboard 
    - Go to Notification
    - Click on Add Notification
    - Fill fields as required
    - Click on Send Push Notification Button in Table

## Deployment on Firebase
1. Install required tools for performing Firebase deployment
    - Install Firebase CLI: `npm i -g firebase-tools`
1. Login into Firebase CLI using the following command -  `firebase login`
1. Open Terminal/CMD/Powershell in the root directory of your clone of aura-admin repository.
1. Now type `firebase login` command in your Terminal/CMD/Powershell
1. Update the `Firebase Project ID` in `.firebasesrc` file. This value should match the project ID in your Project Settings of the Firebase project you created in the previous section.
1. Go to the Firebase Console Dashboard and Click on Hosting in the left navigation.
1. Click on Get Started
1. Click through all steps till you’re taken to the Hosting page in the console.
1. You’ll be provided with a ready domain with your project ID. It should look like - `<project-id>.web.app or <project-id>.firebaseapp.com`
1. Copy the sub-domain name of the URL provided. In this case, it will be the project ID. However, to be precise, you have to copy the part before .web.aap or .firebaseapp.com. This is your Site ID
1. Update `Firebase.json` file, set the site key to Site ID
    ```js
        {
            "hosting": {
                "site":"Your_Firebase_Hosting_id",
                "public": "dist",
                "rewrites": [ {
                    "source": "**",
                    "destination": "/index.html"
                } ],
                "ignore": [
                    "firebase.json",
                    "**/.*",
                    "**/node_modules/**"
                ]
            }
        }
    ```
1. In your terminal at the root directory of the project,  build and deploy using the following command     
    - `firebase deploy`
1. If the project is successfully deployed, you should be able to visit your domain as found, and see the Aura Admin Dashboard. In future, we’ll refer to this website as your Aura Admin Dashboard.


### Documentation
1. [Full documentation](https://docs.google.com/document/d/1WhpMxCE-H47em73F-8pcNGETye5Qun8cY3Jdg7jx6DE/edit?usp=sharing).


## Technology Stack

* [VueJS](https://vuejs.org/)
* [Vuetify](https://vuetifyjs.com/en/)
* [Firebase](https://firebase.google.com/)
* [Service Worker & PWA](https://www.npmjs.com/package/vue-pwa)
* [Workbox](https://developers.google.com/web/tools/workbox)


## Contributing

Awesome! Contributions of all kinds are greatly appreciated. To help smoothen the process we have a few non-exhaustive guidelines to follow which should get you going in no time.

### Using GitHub Issues

- Feel free to use GitHub issues for questions, bug reports, and feature requests
- Use the search feature to check for an existing issue
- Include as much information as possible and provide any relevant resources (Eg. screenshots)
- For bug reports ensure you have a reproducible test case
 - A pull request with a breaking test would be super preferable here but isn't required

### Submitting a Pull Request

- Squash commits
- Lint your code with eslint (config provided)
- Include relevant test updates/additions
- Pull requests _must_ be made against `develop` branch. Any other branch (unless specified by the maintainers) will get rejected.

## Contributors
<b>Maintainer:</b> [Vrijraj Singh](https://github.com/vrijraj) <br>
<b>Developers:</b> [Vrijraj Singh](https://github.com/vrijraj) & [Bharat Agarwal](https://github.com/bharatagsrwal) 

### View Website Built with Projects

| Community Name | Web App Link |
| --- | --- |
| GDG Jalandhar | [View Now](https://gdgjalandhar.com) |
| DSC NSEC | [View Now](https://dscnsec.com) |

## Facing Any Problem or need any Help?
Write us in [issues](https://github.com/issues) section. Our team will try solve your issue within 10-12 hours.<br>

Project is published under the [MIT license](/LICENSE.md).  
Feel free to clone and modify repo as you want, but don't forget to add reference to authors :)
