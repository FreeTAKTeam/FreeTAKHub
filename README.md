# FreeTAKHub
the FreeTAKHub is a component to integrate FreeTAKServer with other systems. It's based on Node Red.

## Functions
* World Wide Emergencies: connects to an external system, pull global EMS information and push periodically to FTS
*  TelegramTAK: Connects to FTS emergency and send a Telegram location and a message to a specific Telegram group chat. From a  same chat, you ca create  an emergency OR send a regular chat to all in FTS.
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
