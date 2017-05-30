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

## Slackbots: Why

* A cool project to learn something new!
* Very helpful for those that use Slack as their primary form of communication

---

## Slackbots: What
Slackbots are useful bots that can be programmed to fufill a multitude of functions

* Be the HR representative and answer common questions
* Personal secretary for reminders, deadlines, and possibly 
* Respond to custom messages
* Link users to integrated applications

---

## Node JS & JavaScript

* Node.js - "Node.js is an open-source, cross-platform JavaScript run-time environment for executing JavaScript code server-side."-Wikipedia
* JavaScript - "JavaScript (JS) is a lightweight interpreted or Just In Time-compiled programming language with first-class functions."


---

## First-Class Function

*   https://developer.mozilla.org/en-US/docs/Glossary/First-class_Function


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

* Botkit is a simple library to build bots for slack.
* Very simple to use.
* Botkit is node based and it allows to utilize any node package to get any functionality.
* Botkit allows you to hear, reply, and have multi-message conversations.

---

## Botkit Documentation
* https://www.botkit.ai

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
<!-- .element: style=" font-size:16px !important " --> 

Note: Obtains a username our of a user id ** Change the font size on this slide...

---

##  Slack API Documentation

* npm Documentation
    * https://www.npmjs.com/package/slack
* Slack Github
    * https://github.com/smallwins/slack

Note: Haiden ~~~ Resources and Documentation

---

## node-slack-upload

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
<!-- .element: style=" font-size:16px !important " --> 

Note: Haiden

---

##  slack-node-upload Documentation

* npm Documentation
    * https://www.npmjs.com/package/node-slack-upload <!-- .element: style=" font-size:35px !important " --> 
* node-slack-upload Github
    * https://github.com/elegantmonkeys/node-slack-upload <!-- .element: style=" font-size:35px !important " --> 

Note: Haiden ~~~ Resources and Documentation

---

## RTM API
Real Time Messagine (RTM) API plays an important role when building a slackbot!
Most, if not all, actions that happen within a Slack group will produce what is called an event.
These events will hold key information on what has happened which a programmer can use.
It's very helpful if you were to use other APIs such as botkit as they make it easy to access these events.

---

## RTM Event Type
* Example: Using botkit - index.js


~~~
var Botkit = require('botkit'); // imports botkit API

var controller = Botkit.slackbot({
    require_delivery: true,
});


controller.hears (
    ["Hello"],["direct_message"], function(bot, message) {

    if(message.text.toLowerCase() === "hello"){
        bot.reply(message, 'Hello there <@'+message.user+'>');
    }
});

// Outputs: 'Hi there @current_user'
~~~

---

## Heroku 

* **`Heroku`** is a great container based cloud platform for node applications. 
* Using **`Hekoku`**, we will be able focus on the development of our applications instead of worrying about our lack of infrastructure
* Heroku
    * https://www.heroku.com/
* Heroku Setup
    * https://scotch.io/tutorials/how-to-deploy-a-node-js-app-to-heroku

---

## Still Feeling Lost?

 * Useful Documentation that will help
    * Botkit Conversation
        * https://tinyurl.com/yamtc5po
    * Working with Slack Integrations
        * https://tinyurl.com/ydfcskw7

---

## Questions?

> Thank you.

Note: speaker notes FTW!

