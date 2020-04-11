# AWS IoT & Raspberry Pi
AWS + Raspberry Pi application coded with Nodejs.
## Description
This project uses a bunch of AWS services connected to a Raspberry Pi and a doorSensor switch, exploring IoT scenarios with topics being published/subscribed, and actions automaticaly lunched in response to sensors status. It also implements flows of Continuous Delivery and Continuous Deployment of the application's codes, automaticaly updating the production versions running on both, a Raspberry Pi server and an AWS EC2 Webserver instance.

![AWS Services](https://github.com/paulonegrao/aws-iot-raspberry-pi/blob/master/images/aws%20services.png?raw=true)

The project starts with a fork from perinei/Door-Alarm-Pi. After that, new adjusts and customizations will complement the application design and implementation.

## Main Flows

The project comprehends to main processes/flows:

Door Sensor notifications are sent using AWS SNS and data is stored in AWS DynamoDB.

![Raspberry Pi & DoorSensor Flow](https://github.com/paulonegrao/aws-iot-raspberry-pi/blob/master/images/Raspberry_PI_plus_DoorSensor_Flow.png?raw=true)

WebServer instance using AWS EC2 providing user interface to AWS Lambda code that consumes API (through AWS API Gateway), and retrives data/status from AWS DynamoDB about the IoT device (DoorSensor).

![AWS EC2 WebServer Flow](https://github.com/paulonegrao/aws-iot-raspberry-pi/blob/master/images/AWS_EC2_WebServer_Flow.png?raw=true)



