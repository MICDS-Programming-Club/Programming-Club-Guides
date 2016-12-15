# Making a Slack Bot: The Basics

Slack is a messaging system aimed at increasing collaboration and productivity, especially when working and especially with programming. The MICDS Programming Club has a [Slack group](https://micdsprogrammingclub.slack.com), which is the perfect opportunity to create Slack Bots! A Slack Bot is simply an application that can automatically interact with Slack, including sending and recieving messages.

## Creating a 'Hello World'
We will be using node.js to create a simple Slack Bot. Node.js is JavaScript that can run outside the browser. [You can download the most recent version of node.js here.](https://nodejs.org/en/)

### Step 1: Registering the bot online
In order to make a Slack Bot, you must first register it online with Slack. To create a new bot, go to `https://<your-team-name>.slack.com/services/new/bot`. In the case of the MICDS Programming Slack bot, you would go to `https://micdsprogrammingclub.slack.com/services/new/bot`. Give the bot a username and configure it however you want. You will then see an API Token, which we will use in our node.js application.

### Step 2: Setup the files
To setup the files needed for the Slack Bot, we will use the [command line](https://github.com/michaelgira23/Programming-Club-Guides/blob/master/introduction/command_line.md). Open up command prompt by typing `cmd` into the Windows search bar. You can navigate to different directories using the `cd <directory>` command. You can list the files in your current using the `ls` command. You can make a directory by using the `mkdir <directory>` command.

To create a folder named `slackbot` in your Desktop and navigate into it:
```
$ cd Desktop
$ mkdir slackbot
$ cd slackbot
```

### Step 3: Initialize the node.js project
In order to setup a node.js project, we usually create a file called `package.json` which contains metadata about our project (name, version, authors, etc.) and other dependencies that our project needs. We can create a `package.json` by typing in `npm init`. NPM stands for Node Package Manager, and is also installed when you download node.js.
```
$ npm init
```
When you type `npm init`, you will be asked to enter in some values. You can press enter to skip any field/set it to default if you don't want to configure it. You can always go back and modify the package.json directly if you change your mind about something later.

In order to communicate with Slack, we're going to use the `slackbots` module. In order to install it and save to our `package.json`:
```
$ npm install slackbots --save
```
Now, since this module is saved in our `package.json`, anyone else who views our project on a different computer can type in `npm install` and download all of the saved dependencies required.

### Step 4: Creating the file
We are now going to create a file called `index.js` in the project directory. This is where the logic for your Slack Bot will be. Here is a basic example that will respond to a message, including who sent the message:

```javascript
// Include the slackbot module
var SlackBot = require('slackbots');

// Create a new Slack Bot
var bot = new SlackBot({
	token: 'YOUR API TOKEN FROM SLACK',
	name: 'Michaels Bot'
});

// Listen for when bot connects to Slack
bot.on('start', function() {
	console.log('Michaels Bot up and running!');
});

// Listen for any data received from Slack
bot.on('message', function(data) {

	// Check if it is a Slack message that isn't from the bot itself
	if(data.type === 'message' && data.subtype !== 'bot_message') {

		// Log the data so we can view it in the console
		console.log('data', data);

		// Get a list of all the users
		bot.getUsers()
			.then(function(users) {
				// Go through all of the uesrs looking for the id who sent the message
				var fromUser = '_Unknown_';
				for(var i = 0; i < users.members.length; i++) {
					var user = users.members[i];
					if(user.id === data.user) {
						fromUser = user.real_name;
						break;
					}
				}

				// Post message to channel
				bot.postMessage(data.channel, '"' + data.text + '"\r-' + fromUser)
					// Log to console if there's an error
					.catch(function(err) {
						console.log(err);
					});
			});
	}
});
```
