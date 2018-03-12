# Web Push Server

HTTP API made with Nodejs to send web push notifications using [web push](https://www.npmjs.com/package/web-push) library.

This repository wants to be a starting point for your implementation of [web push notifications](https://developers.google.com/web/fundamentals/push-notifications/) for your web apps.  
The target of this is to let you store on your web app just a id for each user you can use with this api to send him a push message.

Each application has many users records. Each user record identifies a person and an application. Eg: Markus using MyFirstWebApp and Markus using MySecondWebApp are different records.   
Each record has many notification methods list, one for the standard web push, another for apple notidication system...   
Each notification method has many subscription. Each subscription identifies a person using an application on a device. Eg: Markus using MyFirstWebApp on Fairphone and Markus using MyFirstWebApp on PhoneBlock are different subscriptions.   


### Draft application users record

```javascript
{
  "application_id": "MyFirstWebApp",
  "users" : [
    {
      "user_id": "ab03c422f32g3f...",
      "web_push_subscriptions" : [
      {
        "endpoint":"https://updates.push.services.mozilla.com/wpush/v2/gAAAAABAog",
        "keys":{
           "auth":"hc0N8rvkSbw",
           "p256dh":"BE38S0ImMOg4TU"
         }
       },
       {
         "endpoint":"https://firebase.push.services.google.com/wpush/v2/gAAAAABAog",
          "keys":{
             "auth":"hc0N235235kSbw",
             "p256dh":"BE323451MOg4TU"
           }
       }],
       "apns_subscriptions": {}
    },
    {
      "user_id": "efb0234232ggf...",
      ...
    }
  ]
}
```

### Capabilities

- List all users registered for push notification
- Send a push message to all users
- Send a push message to a list of users 
- Send a push message to all users using a specific application
- Send a push message to a specific user
- List last X push messages sent to a specific user

### Todo

- [ ] Get familiar with [web push](https://www.npmjs.com/package/web-push) library
- [ ] Record all web push registrations 
- [ ] Implement send to all method
- [ ] Implement other methods
- [ ] Write the documentation
- [ ] Add authentication via JWT
- [ ] Record all apple push notificaiton system
- [ ] Update methods to send notification also with apns
