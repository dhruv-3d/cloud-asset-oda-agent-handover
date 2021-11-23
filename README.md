
# Integrating ODA with an B2B OCX Agent System

This project allows ODA (21.08 and above) to handover a user chat to B2B OCX Agent.

## Install

* Clone project repository.
* Navigate to project directory `cd silicon-ocx-webhook` and install required libraries by running `npm install`


```js
// All the configuration variables like required credentials, server settings, etc are defined & being fetched from environment file (.env) which is also commited in the repository.
```

## Running the webhook server
* Run webhook using `npm start` or `npm run start:dev` the later will start server in development mode with code live reload enabled using nodemon and inspect mode on port 9229 for debugging.
* If you are running locally on your laptop, you need to expose your webhook to the internet through an SSL connection. For development purposes, you can using ngrok `ngrok http 4444`

## To run tests
* Run `npm test` to run the test cases.
* Once done, you can check the detailed report from `reports\coverage\lcov-report`

## Updating the ODA & Testing from ODA console
* Update the Ngrok URL endpoint on which ODA will send messages in the ODA channel. 
  * Endpoint is `/bot/message` so final URL will be `https://xxx-xxx-xx-xxx-xxx.ngrok.io/bot/message`
  * Open ODA Console, Navigate to Menu > Development > Channels > Agent_Webhook and update the above endpoint URI in the 'Outgoing Webhook URI' field of the Agent_Webhook  channel.
* Now, you can Navigate Live Agent Transfer Skill (1.0) to test the conversation using Skill Tester (Preview button).
