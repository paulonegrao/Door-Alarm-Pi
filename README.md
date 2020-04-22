# AWS IoT & Raspberry Pi
AWS + Raspberry Pi application coded in Nodejs and JavaSript. It uses sensors to fire predefined actions ang control IoT scenario. The application's codes are also automatically deployded to the servers. 

## Description
This project uses a bunch of AWS services connected to a Raspberry Pi and a doorSensor switch, exploring IoT scenarios with topics being published/subscribed, and actions automaticaly lunched in response to the sensor's status. It also implements flows of Continuous Delivery and Continuous Deployment of the application's codes, automaticaly updating the production versions running on both, the Raspberry Pi server and the AWS EC2 Webserver instance.

![AWS Services](https://github.com/paulonegrao/aws-iot-raspberry-pi/blob/master/images/aws%20services.png?raw=true)

The project starts with a fork from perinei/Door-Alarm-Pi. After that, new incorporations and customizations will complement the application's design and implementation.

## Main Flows

The project comprehends two main processes/flows:

1. DoorSensor's notifications are reflected to the Raspberry Pi and published using AWS SNS. The IoT device status is sent to subscribed cellphones, and the sensor's data is stored in AWS DynamoDB for future recovery through the provided WebServer interface.

![Raspberry Pi & DoorSensor Flow](https://github.com/paulonegrao/aws-iot-raspberry-pi/blob/master/images/Raspberry_Pi_plus_DoorSensor_Flow.png?raw=true)

2. This flow implements a WebServer instance using AWS EC2. It provides a web user interface that fetches dedicated API (through AWS API Gateway), and fires an AWS Lambda code which retrives data/status from AWS DynamoDB about the IoT device (DoorSensor).

![AWS EC2 WebServer Flow](https://github.com/paulonegrao/aws-iot-raspberry-pi/blob/master/images/AWS_EC2_WebServer_Flow.png?raw=true)

The codes of both Flows are kept in GitHub repositories. AWS CodePipeline is used to monitor updates to the codes' repositories and call AWS CodeDeploy to automatically launch new deployment process to its respective production server (Raspberry Pi and/or AWS EC2 WebServer instance).
