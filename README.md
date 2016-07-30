# MQTT Client
MQTT Client for the browser &amp; React Native

This is an export of the MQTT.js library, but exported with Webpack as a CommonJS module for ease of use.

## Installation

```
$ npm i --save wt-mqtt
```

## Usage (ES6)

```JavaScript
import mqtt from 'wt-mqtt'

...

var client = mqtt.connect('ws://localhost:3000')

client.subscribe('mqtt/demo')

client.on('connect', () => {
  console.log('mqtt connected')
})

client.on('message', (topic, payload) => {
  console.log([topic, payload].join(': '))
  client.end()
})

client.publish('mqtt/demo', 'hello world!')
```

## Server

We use [Mosca](https://github.com/mcollina/mosca) as our MQTT broker. Read [this wiki](https://github.com/mcollina/mosca/wiki/MQTT-over-Websockets)
for a guide of setting up Mosca over WebSockets.
