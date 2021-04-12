# About

This is a example of how to utilize WebRTC to do peer to
peer voice and video chatting between two or more people.

### Server Side

This example uses node.js and socket.io to create a "Signaling Server", which
runs on (or near) your web server to manage who should talk to who. The purpose
of the signaling server is to relay information between peers while you are
setting them up to talk directly to each other.

### Client Side

Included is `client.html` which contains all of the logic to connect to the
signaling server, join a virtual group chat channel, connect with peers, and
stream video and audio to all party members using the raw WebRTC API.

# Running

### Node.js signaling server

You'll need to install `node.js` as well as the `express` and `socket.io` libraries:

```
npm install -g socket.io express
```

Then simply run the signaling server:

```
node signaling-server.js
```

### Web server

You'll also probably want to host `client.html` on a web server somewhere. You'll need
to edit `client.html` and change `YOURSERVERNAMEHERE` to be the hostname or IP of
the signaling server.

Note: you can also simply open the file locally instead of using a web server,
but at the time of writing this only firefox will let you access the
webcam/microphone from a file hosted off of your local machine.

### Running the sample

Now navigate to wherever you stuck `client.html` and you should be presented with
a dialog asking permission to access your microphone / webcam. Once accepted,
you should see a local stream appear on the page. Now open up the same page in
another browser, on the same computer or another, and watch as the magic of WebRTC takes
effect and both images and audio samples mysteriously move from one browser to the other.
Repeat with as many browsers as you dare.
