# OBS-WS-5.0-beta-on-Node-Red
A flow to connect on new OBS WebSocket architecture with simple ui interface and a switch scene sample.

# Summary
- Introduction
- Technical explanation
- Node-red flow importation
- Dock in OBS
- Credit

# Introduction
OBS WebSocket is a tool to communicate with OBS Studio from any websocket client. A new version (5.0) will change all it protocol, and moreover, integrate oficialy into OBS Studio. This project is to begin work on this new version and prevent migration or creation of new project. It's a support to understand new features visually and easily.

# Technical explanation
OBS WS 5.0 has a new identification and authentication system. So you need to communicate on only one WS connection, but to do it you need a WS node IN and oanother OUT. And this system is creating two different connections, and you can't identified no one (even without authentication). So... We have to create a webpage that will be a bridge between node-red server and obs websocket server. This webpage will be docked to OBS to work directly after open the soft.
Authentication is now stronger, but WSS is not available. This webpage permit to correct it (see my OBS TLS JUMPER git for details).

# Prerequesites
- A node-red server
- Node-red palette dashboard : https://flows.nodered.org/node/node-red-dashboard
- Node-red palette contrib-crypto-utils : https://flows.nodered.org/node/node-red-contrib-crypto-utils
- Node-red palette node-base64 : https://flows.nodered.org/node/node-red-node-base64
- OBS WebSocketplugin in 5.0 version : https://github.com/obsproject/obs-websocket/releases/tag/5.0.0-beta1

# Node-red flow importation
- import flow from flow.json in this git
- open node-red on URI : /ui
- Set your OBS WebSocket server port and password
- Set your EventSubcriptions to OBS

# Dock in OBS
- In OBS create a dock with this url : https://NODERED-IP:1880/obs-jumper

# Exploitation and test
- You can refer to OBS WS documentation to understand : https://github.com/obsproject/obs-websocket/blob/master/docs/generated/protocol.md
- In /ui you can chose the active scene, it's a request sample

# Credit
twitter : https://twitter.com/tainalo2
website : www.taitools.fr
