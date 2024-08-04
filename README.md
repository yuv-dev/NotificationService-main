# Notification Service 
## _Sending notification emails asynchronoulsy_ 

This code base contains logic/structure  for sending the notfication email asynchronosly
## Features
* Client can request the Notification system to send notifications to all the recipeints
* Notfification Service will run a job every 30 seconds to gather all the requests for last 30 seconds and send notifications

  

## Rest endpoints
#### 1. Raise a new notification request 

```sh
POST /notifiServ/api/v1/notifications
Headers :
 Content-Type:application/json
Sample request body :
{
	"subject" : "Ticket with id [ id ] has been created",
	"content" : "Ticket has been created. User is having some issues",
	"recepientEmails" : "xyz@gmail.com, pqr@linkeddin.com",
	"requester" : "Yuvraj ",
	"ticketId" : "qqwe2314355521"
}

Sample response body :
{
    "requestId": "621893416ff4a6435445935b",
    "status": "Accepted Request"
}
```
--- 
#### 2. Get the notification request status

```sh
GET /notifiServ/api/v1/notifications/621893416ff4a6435445935b
Headers :
 Content-Type:application/json
 

Sample response body :
{
    "requestId": "621893416ff4a6435445935b",
    "subject": "Ticket with id [ id ] has been created",
    "content": "Ticket has been created. User is having some issues",
    "recepientEmails": [
        "xyz@gmail.com, xyz@linkeddin.com"
    ],
    "sentStatus": "SENT"
}
```
