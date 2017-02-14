#How to create a Slackbot in python
Here I will guide you step by step to make your own slack bot.



* [Getting Started](#getting-started)
* [Get your bot ID](#bot-id)
* [Code your idea](#write-code)


---

## getting started

### create the bot in slack
Go to the main menu.You will find something like _Apps and Integrations_.
Click on it , a new window will appear choose the option _Build_ on the top right corner.

Then you will be asked what do you want to build.

Choose **Make a custom integeration**

Now you will be given four options:
  * Incomming webhook
  * Bots
  * Slash commands
  * Outgoing webhook

### Choose _Bots_

After that choose **Add bot integration** after giving your bot a handle or name.
Then fill up the discription and other details.
Get your  BOT API from there and keep it safe. 


### install slackclient
 You can use any method you find easy.
 I myself prefer the pip.
 
 ```python
pip install slackclient
```

Now, when you have installed slackclient, we can proceed to our next step that is getting the ** BOT ID **.

---

## bot id

You need to go to your IDE and this code this code over there and execute it.
```python
from slackclient import SlackClient


BOT_NAME = 'starterbot'

slack_client = SlackClient('SLACK_BOT_TOKEN')


if __name__ == "__main__":
    api_call = slack_client.api_call("users.list")
    if api_call.get('ok'):
        # retrieve all users so we can find our bot
        users = api_call.get('members')
        for user in users:
            if 'name' in user and user.get('name') == BOT_NAME:
                print("Bot ID for '" + user['name'] + "' is " + user.get('id'))
    else:
        print("could not find bot user with the name " + BOT_NAME)
```
Now you have your Bot ID and now you can start coding some sense to your bot.

        
