# Coding Cougs


---

## Hackathon!

“A hackathon, a hacker neologism, is an event when programmers meet to do collaborative computer programming.” -Wikipedia

Note: Hackathon definition

---

![alt text](https://raw.githubusercontent.com/HaidenD/coding_cougs/master/May_27th_Hackathon_Event/Final_Flyers/Black_Poster.png) <!-- .element height="40%" width="50%" -->

---

## What is Slack?
Slack is a team communication tool, that makes collaboration and messaging easy.

* Channels
* Direct Messages
* Share files
* Search 
* **`Integration`**

---

## Slackbots

* Point 1
* Point 2

---

## Node JS & JavaScript

* Point 1
* Point 2

---

## Install Node.js and NPM

Open the terminal

* To install node

~~~ 
brew install node
~~~

* To see if Node is installed

~~~ 
node -v
~~~

* To see if NPM is installed

~~~ 
npm -v
~~~

Note: How to install Node and NPM

---

## Create a node project

* Create a package.json file
~~~ 
npm init
~~~

* Create a new file called **`index.js`**
~~~ 
touch index.js
~~~

* Add print statement to your index.js file
~~~ 
console.log('Hello World');
~~~

* Run your application!
~~~ 
node index.js
~~~

Note: Create a hello world node project

---

## Install a package 

* Install dependencies in the node module
~~~ 
npm install express
~~~

* Print Hello World in your browser

~~~
var express = require('express')
var app = express()
 
app.get('/', function (req, res) {
  res.send('Hello World')
})
 
app.listen(3000)
~~~

Note: Create a hello world node project that runs on a server

---

## Test your application

* Run your application!
~~~ 
node index.js
~~~

* In your browser go to 

http://localhost:3000 

Note: Test Application

---

## Botkit

* Point 1
* Point 2

---

## Slack API
* Provides Node-Style Callbacks
   * **`RTM`** and  **`Web`** API
* Powerful Low Level API 
    * Allows you the creator to use parts of the API surface that you want to use without the entire payload.
    * Methods match Slack's API documentation
* Install

~~~
npm install slack
~~~

Note: This Slack API is a thin wrapper

---

## Slack API setup
* Probably defined at the beginning of the file
~~~
var slack = require('slack');
var   bot = slack.rtm.client();
~~~

Note: Obtains a username our of a user id

---


## Reaction Bot

~~~
// start listening to the slack team associated to the token
bot.listen({token:token})

// on RTM message event
bot.message(function(msg){ 

    var      name = 'thumbsup';  // Select Emoji
    var   channel = msg.channel; // Grab the channel the message was received from
    var timestamp = msg.ts       // Grab the timestamp of the message
    var    params = {token, name, channel, timestamp} // create a parameter object

    slack.reactions.add(params, (err, data) => {       // Use Slack Web API Node Style

        if(err){
            console.log("Error: ",err); // Will Print Error
        } else {
            console.log("Success: Added Reaction"); // Will Print Success
        }

     });
});

~~~

Note: Obtains a username our of a user id ** Change the font size on this slide...

---

##  Slack API Documentation

* npm Documentation
    * https://www.npmjs.com/package/slack
* Slack Github
    * https://github.com/smallwins/slack

Note: Haiden ~~~ Resources and Documentation

---

## Upload Bot

* Uploading can be tricky, node-slack-upload makes it easy!
* Provides support for multipart and content variables
* Install
~~~
npm install node-slack-upload
~~~

Note: Haiden

---

## node-slack-upload Setup

* Probably defined at the beginning of the file
~~~
var Slack_Upload = require('node-slack-upload');
var           fs = require('fs');
var    _upLoader = new Slack_Upload(token);
~~~

Note: Haiden

---

## Upload Bot

~~~
_upLoader.uploadFile({
       file: fs.createReadStream('file_path'), // open a File
       channels: message.channel               // the channel id you with to upload too
       }, function(err, data) {                // callback
             if (err) {
                    console.error(err);        // error happened
              }
            else {
                    console.log('Successfully uploaded files'); // success 
              }
    });
~~~

Note: Haiden

---

##  slack-node-upload Documentation

* npm Documentation
    * https://www.npmjs.com/package/node-slack-upload
* node-slack-upload Github
    * https://github.com/elegantmonkeys/node-slack-upload

Note: Haiden ~~~ Resources and Documentation

---

## Event, RTM

* Point 1
* Point 2

---

## Heroku 

* Point 1
* Point 2

---

## Questions?

> Thank you.

Note: speaker notes FTW!

