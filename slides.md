# Coding Cougs


---

## Hackathon!

* Point 1
* Point 2

---

## What is Slack?

* Point 1
* Point 2

---

## Slackbots

* Point 1
* Point 2

---

## Node JS & JavaScript

* Point 1
* Point 2

---

## Botkit

* Point 1
* Point 2

---

## Slack API
* Provides Node-Style Callbacks
   * **`RTM`** and  **`Web`** API
* Low Level API 
    * Allows you the creator to use parts of the API surface that you want to use without the entire payload.
    * Methods match Slack's API documentation
* Install

~~~
npm install slack
~~~

Note: This Slack API is a thin wrapper

---

## Slack API setup
* Defined at the beginning of the file
~~~
var slack = require('slack');
var bot = slack.rtm.client();
~~~

Note: Obtains a username our of a user id

---

## Reaction Bot

~~~
// start listening to the slack team associated to the token
bot.listen({token:token})

// on RTM message event
bot.message(function(msg){ 

    var name = 'thumbsup'; // Select Emoji
    var channel = msg.channel; // Grab the channel the message was recieved from
    var timestamp = msg.ts // Grab the timestamp of the mssage
    var parms = {token, name, channel, timestamp} // create a parameter object
    slack.reactions.add(parms, (err, data) => {  // Use Slack Web API Node Style
        if(err){
            console.log("Error: ",err); // Will Print Error
        } else {
            console.log("Success: Added Reaction"); // Print Success
        }
     });
    
});

~~~

Note: Obtains a username our of a user id

---

##  Slack API Documentation

* npm Documentation
    * https://www.npmjs.com/package/slack
* Slack Github
    * https://github.com/smallwins/slack

Note: Haiden ~~~ Resources and Documentation

---

## Slack_Upload

* Point 1
* Point 2

Note: Haiden

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

