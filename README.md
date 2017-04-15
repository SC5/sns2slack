# AWS SNS to Slack gateway

An AWS Lambda function that publishes posts to Slack based on AWS SNS messages

## Installation

### Pre-requisites

Serverless Framework 1.5 or later.

### Setup

Clone the project to your environment

    > git clone https://github.com/SC5/sns2slack.git 

Copy the config template (src/config_template.json) to src/config.json. Set the slack channel and tokens to match your environment.

Install dependencies and deploy to AWS

    > npm install
    > sls deploy

## Using the Lambda function

The function for posting to Slack is invoked by sending a message to the SNS topic. The message is a JSON object that has been stringified (message has to be a string). The JSON format is:

    {
        "channel": "-SLACK CHANNEL NAME-",
        "message": "-YOUR MESSAGE (TEXT)-",
        "iconEmoji": "-EMOJI TO USE IF ANY-",
        "senderName": "-YOUR-NAME-HERE-",
        "attachments": [
            {
                "title" : "-FIRST-ATTACHMENT-TITLE-",
                "text" : "-FIRST-ATTACHMENT-TEXT-"
            },
            ...
        ]
    } 



## Release History

* 2017/04/15 - v1.0.0 - Port to Serverless Framework
* 2015/10/10 - v0.9.0 - Initial version of SNS 2 Slack gateway


## License

Copyright (c) 2017 [SC5](http://sc5.io/), licensed for users and contributors under MIT license.
