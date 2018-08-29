# @feathersjs/socketio-client


> __Important:__ The code for this module has been moved into the main Feathers repository at [feathersjs/feathers](https://github.com/feathersjs/feathers) ([package direct link](https://github.com/feathersjs/feathers/tree/master/packages/socketio-client)). Please open issues and pull requests there. No changes in your existing Feathers applications are necessary.

[![Build Status](https://travis-ci.org/feathersjs/socketio-client.png?branch=master)](https://travis-ci.org/feathersjs/socketio-client)

The client for Socket.io Feathers connections

## Installation

```
npm install @feathersjs/socketio-client --save
```

## Quick example

```js
const feathers = require('@feathersjs/feathers');
const socketio = require('@feathersjs/socketio-client');
const io = require('socket.io-client');

const socket = io('http://api.feathersjs.com');
const app = feathers();

// Set up Socket.io client with the socket
app.configure(socketio(socket));

// Receive real-time events through Socket.io
app.service('messages')
  .on('created', message => console.log('New message created', message));

// Call the `messages` service
app.service('messages').create({
  text: 'A message from a REST client'
});
```

## Documentation

Please refer to the [@feathersjs/socketio-client documentation](https://docs.feathersjs.com/api/client/socketio.html) for more details.

## License

Copyright (c) 2018

Licensed under the [MIT license](LICENSE).
