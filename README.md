# Meteor-Enterprise-Toolkit 

`A starting point for creating a new multilingual Progressive Web Application in Meteor.`

### Step by step guide to get started with this boilerplate

#### 1. Clone the project and install NPM dependencies:

#### 2. Create your settings.json file:
Create a new file called ```settings.json``` based on the provided ```settings.sample.json```.

#### 3. Register the app on Mailgun:
Mailgun will allow you to use password authentication service and send emails from your app.

In order to get started, first access your [Mailgun][Mailgun] account. Then, grab your sandbox domain smtp username and password and copy said values into your settings.json file. Finally, add your email address to the list of [Authorized Recipients](https://help.mailgun.com/hc/en-us/articles/217531258-Authorized-Recipients).

#### 4. Register the app on Facebook.

You only need to do this if you wish to have Facebook logon support. You may also need to run the starter kit's https proxy (see below for more details): 

1. Visit https://developers.facebook.com
2. Add a new app from the `My Apps` menu
3. Choose the `Facebook Login product, and accept the defaults. You __don't__ need a direct URL.
4. Copy your appId to your `settings.json` file.

#### 5. Setup Push Notifications Service
1. create a new file called ```manifest-pwa.json``` based on the provided ```manifest-pwa.sample.json``` (see ```/public``` folder).
2. get your Google Cloud Message (GCM) server key and sender id from Firebase as follows:
  * first, got to your Firebase account: https://console.firebase.google.com/;
  * click on 'Add project';
  * click on 'settings' ('gear' icon, top left);
  * move to the 'CLOUD MESSAGING' tab at the top;
  * you should be able to see both server key and sender id;
3. copy your sender id to your manifest-pwa.json and your server key to your settings.json ("firebase": { "privateKey": ...);
4. open a terminal and install 'web-push' globally: ```npm i -g web-push```;
5. generate VAPID keys: ```web-push generate-vapid-keys --json```;
6. copy-paste your VAPID keys into your settings.json file;

#### 6. Run the app
You should now be able to run the app locally:
```
meteor --settings settings.json
```
