# Server Sent Events
Service for sending real time events to the client

Server sent event
Service is using Server Sent Event for one-way communication with client. SSE mozilla web doc refrence

Events are returned as text/event-stream

#### Getting started
We will start setting up the requirements for our server. We’ll call our back-end app swamp-events:

```sh

$ mkdir swamp-events
$ cd swamp-events
$ npm init -y
$ npm install --save express body-parser cors

```

#### SSE Express Backend
We’ll start developing the backend of our application, it will have these features:

 - Keeping track of open connections and broadcast changes when new nests are added
 - GET /events endpoint where we’ll register for updates
 - POST /nest endpoint for new nests
 - GET /status endpoint to know how many clients we have connected
 - cors middleware to allow connections from the front-end app



```sh
# Server execution
$ node server.js
Swamp Events service listening on port 8585
```

```sh
# Open connection waiting updates
$ curl  -H Accept:text/event-stream http://localhost:3000/events
data: []
```
