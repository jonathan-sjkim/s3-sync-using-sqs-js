# Client NodeJS Code
## Description
The client will do as below. I used SQS Consumer package(detail in Resources). 
- Wait for messages which will be sent by Lambda from FIFO Queue. (Internally, client is doing [Long Polling](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-short-and-long-polling.html)
- In message body, it will contain bucket name and key which is newly uploaded to bucket.
- Get object from S3 and write to local machine.

## Quick Start 
- Clone Repo: `git clone https://github.com/jonathan-sjkim/s3-sync-using-sqs-js.git`
- run command `cd s3-sync-using-sqs-js/client`
- run command `cp config-sample.json config.json`
- add your credentials and region in `config.json`
- add your SQS queue url in `app.js` file to `queryUrl` parameter. 
- run command `npm install`
- run command `node app.js`

## NOTE
- You have to make SQS FIFO queue before. See backend instruction.

## Resources
- SQS Consumer: <https://www.npmjs.com/package/sqs-consumer>
- SQS JavaScript SDK: <https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/SQS.html>
