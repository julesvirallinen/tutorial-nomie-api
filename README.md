# Nomie API Tutorial

## NOTE: The API will be available only to a small group of people initially. To request access to the API please send a message to support @ happydata.org

The Nomie API is a simple way to send events, data, notes and more to your device running Nomie.

## Virtual Tap of a Tracker Button
You can virtually tap your button by sending the ``track`` action to the Nomie API.

### Single Tap Trackers

```
https://api.nomie.io/v1/{apikey}/action=track/label=Peed
```

### Value based Trackers

```
https://api.nomie.io/v1/{apikey}/action=track/label=Temperature/value=123
```

## Example Ideas

### Track the Temperature with IFTTT

Have IFTTT post the temp each day to a "Temp" tracker that's Numeric and uses Averages for the calculation. You'll now be able to see how the temp, or whatever you track weather wise, affects you.

### Create a Widget with Workflow (iOS)
Coming soon

### Create a Widget with Tasker (Android)
Coming soon

## How it Works:

1. Your device registered an Anonyous ID, a Cloud App ID, and API Key and your Device ID (for push Notifications) `See below for how each are used`.
2. Your API Key is validated
3. If valid, your command string (/action=track/label=Peed) is added to a message queue waiting to be picked up.
4. Nomie on your device will periodically check for any new command
5. When new commands are found, they are validated, executed, and then removed from the message queue. 

## Nomie Ids

- **Anonymous Id** - This is a unique string that is generated when you first start using Nomie. It is used to generate and validate the API Key and Cloud App Id.
- **API Key** - This is a unique key that is needed to send PUSH commands to the Nomie API.
- **Cloud App Id** - This unique ID is generated for each Cloud App you install and provides an ID for Cloud Apps to leverage, while not giving up your API key or Anonymous ID.

Reseting your identity within the app, resets all ID's - effectively making your a new User according to cloud apps and Nomie's anonymous services.
