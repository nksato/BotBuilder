# Bot Builder for Node.js
[Bot Builder for Node.js](http://docs.botframework.com/builder/node/overview/) is a powerful framework for constructing bots that can handle both freeform interactions and more guided ones where the possibilities are explicitly shown to the user. It is easy to use and models frameworks like Express & Restify to provide developers with a familiar way to write Bots.

High Level Features:

* Powerful dialog system with dialogs that are isolated and composable.
* Built-in prompts for simple things like Yes/No, strings, numbers, enumerations.
* Built-in dialogs that utilize powerful AI frameworks like [LUIS](http://luis.ai).
* Bots are stateless which helps them scale.
* Bots can run on almost any bot platform like the [Microsoft Bot Framework](http://botframework.com), [Skype](http://skype.com), and [Slack](http://slack.com).
 
## Build a bot
Create a folder for your bot and run npm init.

    npm init
    
Get the BotBuilder and Restify modules using npm.

    npm install --save botbuilder
    npm install --save restify
    
Create a file named app.js and say hello in a few lines of code.
 
    var restify = require('restify');
    var builder = require('botbuilder');

    var server = restify.createServer();

    var helloBot = new builder.BotConnectorBot();
    helloBot.add('/', function (session) {
        session.send('Hello World');
    });

    server.post('/api/messages', helloBot.listen());

    server.listen(process.env.port || 3978, function () {
        console.log('%s listening to %s', server.name, server.url); 
    });

## Test your bot (Windows Only)
Use the [Bot Framework Emulator](/botframework/bot-framework-emulator/) to test your bot on localhost. 

Install the emulator from [here](http://aka.ms/bf-bc-emulator) and then start your bot in a console window.

    node app.js
    
Start the emulator and say "hello" to your bot.

## Publish your bot
Deploy your bot to the cloud and then register it with the Microsoft Bot Framework.

* [Publishing a bot to Microsoft Azure](http://docs.botframework.com/connector/getstarted/#publishing-your-bot-application-to-microsoft-azure)
* [Registering a bot with the Microsoft Bot Framework](http://docs.botframework.com/connector/getstarted/#registering-your-bot-with-the-microsoft-bot-framework)

## Dive deeper
Learn how to build great bots.

* [Core Concepts Guide](http://docs.botframework.com/builder/node/guides/core-concepts/)
* [Bot Builder for Node.js Reference](http://docs.botframework.com/sdkreference/nodejs/modules/_botbuilder_d_.html)