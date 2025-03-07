# Custom integration of Netatmo with Home Assistant
Integration Netatmo for HomeAssistant with NIS and NACamDoorTag sensors.

This custom integration will be updated according to the updates of the official integration [Netatmo integration](https://www.home-assistant.io/integrations/netatmo/).

Because I use this integration and it works on my end, I will not provide support if there are any issues.

Thanks to [@cgtobi](https://github.com/cgtobi) for the [Netatmo integration](https://www.home-assistant.io/integrations/netatmo/) and [pyatmo](https://github.com/cgtobi/pyatmo). 

## Why was this component created?
I needed the opening sensors for my heating (Versatile).

## How was this component created?
I'm using the main dev HA git repository: [Set up development environment](https://developers.home-assistant.io/docs/development_environment)

Sometimes, the dev env is not valid with the last release of HA.

So, I download a copy for the last release and I merge my custom files.

And, I upload my custom component for the release.

Integration tested as described here, with new unit tests: [Testing your code](https://developers.home-assistant.io/docs/development_testing)

## How install this custom component ?
### First install:
1. [Studio Code Server](https://github.com/hassio-addons/addon-vscode)
2. Launch Studio Code Server and create a folder "custom_components" in the folder "homeassistant"
3. Download this custom integration for your release : [HA_Custom_Netatmo](https://github.com/yannc74/HA_Custom_Netatmo/releases)
4. Unzip and upload the folder netatmo in the "custom_components" folder.
5. Remove your previous netamo integration
6. Reboot HA
7. Install the Netatmo integration

### Update:
1. Download this custom integration for your release : [HA_Custom_Netatmo](https://github.com/yannc74/HA_Custom_Netatmo/releases)
2. Unzip and upload the folder netatmo in the "custom_components" folder.
6. Reboot HA

## Customized sensors and behaviors.

NB: Webhooks are send by Netatmo when the camera is ON

### Siren (Smart Indoor Camera)
Binary Sensors:
1. connectivity
2. monitoring: On/Off 
3. sound: True if the siren souding (alert) (webhook: event home_alarm)  

Diagnostic Sensors
1. Battery
2. Radio
3. Reachable
4. State
   
![image](https://github.com/user-attachments/assets/0a231f10-706b-4c87-8dcd-2d235c157cd9)

### NACamDoorTag
Binary Sensors:
1. connectivity
2. opening : True if the window/door is open (or webhook: event tag_open)
3. motion: True if webhook tag_big_move is received
4. vibration: True if webhook tag_small_move is received  

Diagnostic Sensors
1. Battery
2. Radio
3. Reachable
4. State
   
![image](https://github.com/user-attachments/assets/02e9e955-531a-4ad5-9739-401e9eefbe2d)
