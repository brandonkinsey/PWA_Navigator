# PWA Web App

This is a example Persistent Web App (PWA) for the Cisco Room Navigator.

![PWA-WebApp](images/PWA-WebApp.gif)

## Overview

The Web App leverages the built in JavaScript xAPI access when loaded on a Room Navigator running in PWA mode. With this, the Web App obtains the Workspaces name and it at the top of the Navigator. 

Additionally, the Web App subscribes to the Room Analytics sensors of the in room device and displays live People Count, Temperature and Ambient Noise levels and Occupancy status.

This Web App also works for rooms 


## Setup

### Prerequisites & Dependencies: 

- RoomOS Device
- Paired Cisco Room Navigator previsioned in Persistent Web App mode ( Either Wall Mount or Table Stand version )
- Control Hub Admin or Device Web admin access to the RoomOS Device
- Network connectivity so your Webex Device open access Web App hosted on the GitHub pages domain (*.github.io)

### Setup Steps:

1. Log into the RoomOS Device and set [xConfiguration Security Xapi WebSocket ApiKey Allowed](https://roomos.cisco.com/xapi/Configuration.Security.Xapi.WebSocket.ApiKey.Allowed/) to True:
    ```
    xConfiguration Security Xapi WebSocket ApiKey Allowed: True
    ```
2. Permit the Web App Domain access access to JSxAPI by setting [xConfiguration WebEngine Features Xapi Peripherals AllowedHosts Hosts](https://roomos.cisco.com/xapi/Configuration.WebEngine.Features.Xapi.Peripherals.AllowedHosts.Hosts/) to either ``*`` for all Domains or ``wxsd-sales.github.io`` for this specific demo.

    ```
    xConfiguration WebEngine Features Xapi Peripherals AllowedHosts Hosts: *
    or
    xConfiguration WebEngine Features Xapi Peripherals AllowedHosts Hosts: wxsd-sales.github.io
    ```
3. (optional) For Text-To-Speech, enable Audio Output for the WebEngine on the Peripherals [xConfiguration WebEngine Features Peripherals AudioOutput](https://roomos.cisco.com/xapi/Configuration.WebEngine.Features.Peripherals.AudioOutput/)
    ```
    xConfiguration WebEngine Features Peripherals AudioOutput: On
    ```

3. Lastly set the Persistent Web App URL to the PWA Web App: ``https://wxsd-sales.github.io/pwa-webapp``
    ```
    xConfiguration UserInterface HomeScreen Peripherals WebApp URL: https://wxsd-sales.github.io/pwa-webapp/
    ```
   
