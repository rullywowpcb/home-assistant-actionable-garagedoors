# home-assistant-actionable-garagedoors
## Quick excerpt of my  Home Assistant config for Actionable Notifications on my "Virtual" Garage Doors

The idea is to get something like this on your mobile:
![alt text](https://raw.githubusercontent.com/rullywowpcb/home-assistant-actionable-garagedoors/main/ios_notification.jpg?raw=true)

- Highly recommended to setup some Config/Helper Tools/Input Booleans to play around with until you got it dialed in
- I setup two input booleans and a script to fire the notification to iOS device to play around with until I actually got it working
- Make a card with three entries. Two input booleans (virtual switches) for the doors and one script to fire the notification like this:
![alt text](https://raw.githubusercontent.com/rullywowpcb/home-assistant-actionable-garagedoors/main/test_card_actionable_notifications.png?raw=true)
- Also make use of the "Developer Tools/Events/Listen To Events" in order to listen to mobile_app_notification_action to see if you get a response from pushing the button on your mobile device
- I created a group for both virtual garage doors called virtualdoors
- Next up is to set up an Automation which sends a notification at a certain time if the doors are left open (for example every 30 minutes after sunset). You will have to implement these yourself.

Do check out the official resource for this here. This method has changed after 2021.5

https://companion.home-assistant.io/docs/notifications/actionable-notifications/

