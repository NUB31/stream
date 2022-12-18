# stream

This is a collection of the microservices that makes up the "stream" program.

## stream_connector

The stream_connector repository is the main server. This is a socket.io server which will handle messages coming in from other microservices.

### Example:

To play a song through the musicbot microservice, you can send a socket.io message to the connector and it will forward it to the musicbot microservice.
This makes it so we can control the musicbot from multiple places, such as youtube chat, twitch chat ot a control panel yet to be made.

### Notes:

This is the only servioce that has to be running. The rest of the services is optional.

## stream_musicbot

The stream_musicbot repository is a microservice for playing music/video through ffplay.

### Dependencies:

- stream_connector
- stream_twitch_connector or stream_youtube_connector or stream_dashboard

## stream_twitch_connector

The stream_twitch_connector repository is a microsservice that connects to twitch chat. It can send messages and recieve commands that can interact with the musicbot.

### Dependencies:

- stream_connector

## stream_youtube_connector

The stream_youtube_connector repository is a microsservice that connects to youtube chat. It can recieve commands that can interact with the musicbot.

### Dependencies:

- stream_connector

## stream_chat_json

The stream_chat_json repository is a html chat that will display chat messages in a json format. Can be easily used in OBS

### Dependencies:

- stream_connector
- stream_youtube_connector or stream_twitch_connector

## stream_dashboard

TODO
