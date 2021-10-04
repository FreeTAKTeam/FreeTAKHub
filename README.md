# FreeTAKHub
![OFFICIAL logo of  FTH to annoy the censors and hopefully spark some sort of controversy ](FTHLOGO3.png)

the different services of FTSHub will be moved in separate repository.

Welcome to the FTH repository!
the FreeTAKHub is a component to integrate FreeTAKServer with other (non-TAK) systems. It's based on Node Red.

## Services
* World Wide Emergencies: connects to an external system, pull global EMS information and push periodically to FTS
*  TelegramTAK: Connects to FTS emergency and send a Telegram location and a message to a specific Telegram group chat. From a  same chat, you can create  an emergency OR send a regular chat to all in FTS.Finally you can also send an image to the group and this will be transformed into a Data Package into FTS.
*  WebMap: Get the flow of COT from FTS and display on a web map (credit @ampledata#8354). The FTH WebMap integration can be installed as part of FTS UI or a stand alone, e.g. for a dashboard. 
*  Video Server: a RTSP / RTPM capable server to stream in real time from / to TAK devices


## Architecture
![image](https://user-images.githubusercontent.com/60719165/125168213-ae368380-e17a-11eb-9b18-bf782f2d34bf.png)
it's suggested to deploy each FTH integration on a separate node.

## Installation
each of the FTH component is a microservice that can be installed stand alone, with no dependency between erach other

### FreeTAKServer configuration
FreeTAKHub uses FTS REST API. You will need to have a working FTS 1.8 or better, with the API service activated. On the FTS web UI you need to create a user and to assign a token
![image](https://user-images.githubusercontent.com/60719165/118305634-9f0ac080-b4be-11eb-8b0f-47344f7d2fc2.png)

## WebMap Packaged 
![webmap](https://user-images.githubusercontent.com/60719165/118400733-47449480-b639-11eb-8583-93e52cdcfb80.png)

* the installation supports Ubuntu, other linuxes may work but they are not supported
* Download the last webmap  [package](https://github.com/FreeTAKTeam/FreeTAKHub/releases/) in your filesystem, the file name has the following convention:
* [SYSTEM]_[SERVICE]_[PLATFORM]_[MAJORVERSION]_[MINORVERSION]
* e.g. FTH_WebMap_Ubuntu_1.8_RC2
* open a terminal
* navigate to your download dir
* make the file executable
```sudo chmod +x [package_name]```
* edit the JSON file webMAP_config.json set the 
*   "FTH_FTS_URL": "[YOUR_FTS_IP]" 
  "FTH_FTS_TCP_Port": [YOUR_FTS_PORT]
*  save the file
*  in the console type:
```
./[package_name] /[PATHTOCONFIGURATIONFILE]/webMAP_config.json
```
* navigate to your IP:8000/tak-map 
* e.g. http://10.0.2.15:8000/tak-map

### configuring FTS-UI for WebMAP
the webmap is a component that works standalone, since V. 1.8, the FTS UI supports it.
in your FreeTAKServer-UI package, edit the config.py file and set the loaction of your webmap service.

## Telegram Integration

### Create telegram Robot
* go to telegram and create a new bot with botfather
* /newbot
* set a name for the bot
* **note the token for you bot** (if you forget it, you can styill ask botfather for it)
* create a user name
* register the API
* Create a new telegram group
* add the new created bot to the group
* add the "What's my Telegram ID?" bot to the group
* **note the ID of your group**
* ensure that you bot has Groups enabled. In bot father type
``` /setjoingroups```
* turn off privacy
### configure Telegram integration
* download the installation package
*  e.g. FTH_Telegram_Ubuntu_1.8_RC2.zip
*  unzip the file
* edit the JSON file TelegramTAK_config.json set the 
```  
{

  "BOT_TOKEN": "[BotToken]",
  "FTH_FTS_URL": "[YOURIP]",
  "ChatId": "[ChatGroupid]",
  "FTH_FTS_API_Auth": "[FTSAPIKey]",
  "FTH_FTS_API_Port": 19023,
  "FTH_FTS_TCP_Port": 8087
}
 ```
*  save the file
* open a terminal
* navigate to your download dir
* make the file executable
```sudo chmod +x [package_name]```

*  in the console type:
```
./[package_name] /[PATHTOCONFIGURATIONFILE]/TelegramTAK_config.json
```
## Video Server
![image](https://user-images.githubusercontent.com/60719165/125315214-449aae80-e30d-11eb-9af0-a316dccbefd3.png)

the FreeTAKHyub video server is a modified version of [rtsp simple server](https://github.com/aler9/rtsp-simple-server).
It allow to connect a [drone](https://github.com/FreeTAKTeam/FreeTAKServer-User-Docs/blob/main/docs/docs/tools/FreeTAKUAS.md) or use tools such as TAK ICU.
the modified version is not yet released because of stability issues. To install the standard version.

Download and extract a precompiled binary from the [release](https://github.com/aler9/rtsp-simple-server/releases) page.

Start the server:
```
./rtsp-simple-server
```
