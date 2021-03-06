# home-assistant-actionable-garagedoors
## Quick excerpt of my  Home Assistant config for Actionable Notifications on my "Virtual" Garage Doors. Try this out on your own virtual doors before you actually implement.

The idea is to get something like this on your mobile:
![alt text](https://raw.githubusercontent.com/rullywowpcb/home-assistant-actionable-garagedoors/main/ios_notification.jpg?raw=true)

Once you are satisfied that it works (yay!), you can implement this with your actual doors or anything else 

# Prequisites

- You have the `ios:` enabled in your configuration.yaml and have downloaded and synced the iOS HA Companion App
- You have a version of HA after 2021.5
# Basic Game Plan
- Setup two input booleans for virtual garage doors in Lovelace: `Configuration/Helpers/Input Boolean`
- Setup a group/area for both virtual garage doors called 'virtualdoors'
- Setup a script which will send the actionable notification to your iOS device. Be sure to change the name to your iOS device name (mine is homeskillet)
- Setup an Automation which will turn off the group of virtual input booleans
- Setup a card (you can do this in Lovelace) featuring the Script, and both input booleans like this:
![alt text](https://raw.githubusercontent.com/rullywowpcb/home-assistant-actionable-garagedoors/main/test_card_actionable_notifications.png?raw=true)

# Intended Operation
- When the script is triggered, you should receive a notificaiton on your device
- If you press `Close All Garage Doors` HA should see the message and the automation will act on this by turning off the group you created of virtual garage doors (input booleans)

# Tips
- Make use of the `Developer Tools/Events/Listen To Events` in order to listen to mobile_app_notification_action to see if you get a response from pushing the button on your mobile device
- Next up is to set up an Automation which sends a notification at a certain time if the doors are left open (for example every 30 minutes after sunset). You will have to implement these yourself for your own config.
- You can swap the iOS notification sound with many other choices. Check out the bundled sounds in the companion app under `App Settings/Notifications/Sounds/Bundled` for the exact filenames. Morgan Freeman is in there along with Alexa and others.
- The "Keep Open" button sends a message to `mobile_app_notification_action` but doesn't really do anything other than make the notification go away. You could add more options here (up to 10 in iOS currently).

Do check out the official resource for this here. This method has changed after 2021.5

https://companion.home-assistant.io/docs/notifications/actionable-notifications/

