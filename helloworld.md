---
layout: docwithnav
assignees:
- ashvayka
title: Getting Started
description: Getting started with NanoIoT open-source IoT platform and simulated IoT devices

---

## Introduction

The goal of this tutorial is to demonstrate the basic usage of the most popular NanoIoT features. 
You will learn how to:

 - Provision Assets and Devices in the system;
 - Define relations between Assets and Devices;
 - Push data from a device to NanoIoT;
 - Build real-time end-user Dashboards;
 - Define thresholds and trigger alarms;
 - Push notification about new alarms over email.
 
The tutorial is based on a popular facility monitoring use-case. 
We will show how to monitor temperature in a different parts of the building,
raise alarms when temperature exceeds certain threshold and visualize collected data and alarms.
 

#### Pushing data from the device

In order to simplify this guide, we will push data using HTTP, MQTT or CoAP protocol from your local PC. 
Please review connect your device(/docs/guides#AnchorIDConnectYourDevice) guides for all available connectivity solutions and options and 
hardware samples(/docs/guides#AnchorIDHardwareSamples) to learn how to connect various hardware platforms to NanoIoT.


#### Sample cURL command used in the video tutorial

This command works for Windows, Ubuntu and macOS, assuming that cURL tool is installed. 

```bash
# Please replace $HOST_NAME and $ACCESS_TOKEN with corresponding values.
curl -v -X POST -d "{\"temperature\": 25}" $HOST_NAME/api/v1/$ACCESS_TOKEN/telemetry --header "Content-Type:application/json"



# For example, $HOST_NAME in case of local installation:
curl -v -X POST -d "{\"temperature\": 25}" http://localhost:8080/api/v1/$ACCESS_TOKEN/telemetry --header "Content-Type:application/json"
```

#### Sample generator script

```javascript
var msg = { temperature: +(Math.random()*5 + 25).toFixed(1)};
var metadata = {};
var msgType = "POST_TELEMETRY_REQUEST";

return { msg: msg, metadata: metadata, msgType: msgType };
```

#### Rule Engine guides

Rule Engine - learn the Rule Engine basics and architecture.
#### Mail settings
to configure SendGrid or use any other SMTP server available.

