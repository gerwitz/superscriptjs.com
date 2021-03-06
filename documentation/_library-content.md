

# Library API

This doc will show you how to use SuperScript to create a new application or intergration.

```sh
$ npm install superscript

```

We are assuming you have already setup node.js and have NPM installed (included with node) as well as a working understanding of JavaScript.
<a class="doc-anchor" name="bot"></a>
## The Bot Class

```javascript
var superscript = require("superscript");

/**
- conversationJSONData: A JSON file of all the scripted conversation compiled down to one file. This file is generated from the parse util in ./bin/parse

- options is a object litteral.
- callback is a function that returns callback(err, bot)

**/
new superscript(conversationJSONData, options, callback);

```

The Bot Instance returned from the callback has a few methods you can use to build out your bot.

### Reply Method
```javascript
/**
This is the main way to communcate with your bot.
- user_id, String, is a unique token used to identify what user is sending the message
- message, String, is the message or input from the user
- callback(err, reply), Function, is where the reply 
**/
bot.reply(user_id, message, callback);
```

### getUser Method
```javascript
/**
getUser will return the user object from the bot. It is primarily a helper function.
- user_id, String, User Token
- callback err, user object
**/
bot.getUser(user_id, callback);

```

<a class="doc-anchor" name="example"></a>
## Example 

Here is the complete minimum example:
```javascript
var superscript = require("superscript");

new superscript('./data.json', {}, function(err, bot){
	bot.reply("exampleUser", "Hello Bot", function(err, reply){
		console.log(reply);
	})
});

```

<div class="doc-box doc-info">
	For an interactive example application, follow the steps on the getting started page and setup a chat server with telnet.
</div>


