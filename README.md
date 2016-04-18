# The CircleHub Chelsea News API

- The base URL for all API resources is ```http://chelsea-news-api.herokuapp.com/api```.
- All data send and received as JSON.
- Timestamps are returned in ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```

## User Agent

We recommend all API clients to include a ```User-Agent``` header with the name of your application and an email address or url. This allows us to contact you if there are any problems.

Example:

- ```User-Agent: SomeAwesomeAppName (john@someawesomeappname.com)```
- ```User-Agent: SomeAwesomeAppName (http://www.someawesomeappname/com)```

## Resources

- Posts
- Fixtures
- Leagues
- Players
- [Push Tokens](#push-tokens)
- [Notifications](#notifications)

## Push Tokens

Register a device for push notifications

### Request

```POST /push_token.json```

### Parameters

|Name|Required|Type|Description|
|----|--------|----|-----------|
|```token```|required|string|Device token for iOS and Google Sender ID for Android|
|```platform```|required|string|Either **ios** or **android**|

### Example Successful Response

Code: ```201```
Body: ```empty```

## Notifications

You can use this to subscribe or unsubscribe from push notifications. Currently there are two types of notifications:

- ```news_alerts```: Subscribe to this notification to receive notification when a new post goes live
- ```match_alerts```: Subscribe to this notification to receive match alerts such as kick off, half time, full time, and goal(s).

### Request - Subscribe

```POST /notifications.json```

### Parameters

|Name|Required|Type|Description|
|----|--------|----|-----------|
|```token```|required|string|Device token for iOS and Google Sender ID for Android|
|```alert_type```|required|string|Either **news_alerts** or **match_alerts**|

### Example Successful Response

Code: ```201```
Body: ```empty```

### Request - Unsubscribe

```DELETE /notifications.json```

### Parameters

|Name|Required|Type|Description|
|----|--------|----|-----------|
|```token```|required|string|Device token for iOS and Google Sender ID for Android|
|```alert_type```|required|string|Either **news_alerts** or **match_alerts**|

### Example Successful Response

Code: ```200```
Body: ```empty```

