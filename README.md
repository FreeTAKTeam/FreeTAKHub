# FreeTAKHub
![OFFICIAL logo of  FTH to annoy the censors and hopefully spark some sort of controversy ](FTHLOGO2.png)

Welcome to the FTH repository!
the FreeTAKHub is a component to integrate FreeTAKServer with other (non-TAK) systems. It's based on Node Red.

## Functions
* World Wide Emergencies: connects to an external system, pull global EMS information and push periodically to FTS
*  TelegramTAK: Connects to FTS emergency and send a Telegram location and a message to a specific Telegram group chat. From a  same chat, you can create  an emergency OR send a regular chat to all in FTS.Finally you can also send an image to the group and this will be transformed into a Data Package into FTS.
*  WebMap: Get the flow of COT from FTS and display on a web map (credit @ampledata#8354) 

## Deployment
it's suggested to deploy FTH on a separate machine.

## Installation
* install Node Red
* install the following nodes: 
  * node-red-contrib-multifeed-parser
  *  node-red-contrib-telegrambot
  *  node-red-contrib-web-worldmap
* upload the flows in this repository
* configure the flows
* 
## WebMap Packaged installation
download package in filesystem
navigate to download dir
```sudo chmod +x package_name```
```./package_name```

## Telegram Integration

### Create telegram Robot
* go to telegram and create a new bot with bot father
* /newbot
* create a name for the bot
* create a user name
* register the API
* Create a new telegram group
* add the new created bot to the group
* add the "What's my Telegram ID?" bot to the group
* ensure that you bot has Groupsy enabled
* turn off privacy
* 
