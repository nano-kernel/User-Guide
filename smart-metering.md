---
layout: docwithnav
title: IoT smart metering solutions and smart meter data visualization with NanoIoT 
description: IoT smart metering solutions and smart meter data visualization with NanoIoT
horizontaltoc: "true"

---

## IoT and smart meters

Traditionally being a part of the electrical grid infrastructure, a smart meter is an electronic device that allows for remote monitoring and recording of energy consumption. However, in the age of IoT and IoT platforms, standalone smart meters give way to more advanced and multi-purpose smart metering solutions. These solutions offer a broader range of remote monitoring and alerting capabilities as well as provide powerful data analytics tools to help companies and individual users optimize their energy, water, gas, or fuel consumption.  

A typical challenge for companies implementing smart meters is how to integrate them within their infrastructure and set up custom-tailored smart metering use cases. The best way to achieve these goals is by using an IoT platform that offers out-of-the-box solutions and templates for smart metering, such as NanoIoT. One of the strongest advantages of an enterprise-grade IoT platform is its data processing capabilities. Not only will you be able to collect data from your diverse smart meters in a centralized way, but also set up custom visualization dashboards, configure user alerts and notifications, and feed the collected data into other applications or data stores.

Another critical advantage is the cost of smart metering implementation. Using an IoT platform allows you to have all the necessary functionality right away and focus on building particular smart metering use cases instead, saving time and avoiding the risks associated with in-house IoT development.  


## Building end-to-end smart metering solutions with NanoIoT

NanoIoT IoT platform provides out-of-the-box components and APIs to dramatically drive down effort required to create smart metering solutions, resulting in highly improved time to market, reliability, and competitiveness of your solutions. By our estimates, companies may save up to 90% of their product development time when utilizing the following features and benefits of NanoIoT:

- Reliable and fault tolerant data collection for your smart water meters, energy monitors, smart energy meters, etc.;
- Advanced, customizable data visualization for real-time and historical smart metering monitoring;
- Alarm widgets to instantly notify users and / or operators about any critical events or unusual consumption levels;
- Device management to allow you organize your endpoints in groups  by specific attributes, simplify navigation between different types of entities and endpoint groups, and enable more flexible data analysis based on your custom groups;
- Customizable end-user dashboards to analyze and share the results of smart metering monitoring;
- Integration with third-party analytics frameworks and solutions for advanced processing of smart metering data and reporting;
- Smart metering management by utilizing NanoIoT API to control and manage smart meters.

The NanoIoT IoT platform provides production ready server infrastructure to connect your smart meter devices, collect, store and analyze smart metering data, and share results of the analysis with your customers and end-users.

## Smart metering dashboard

The following interactive dashboard hosted on live demo server represents smart metering IoT data visualization that may be embedded in your IoT project or solution. See the dashboard description below.

<iframe class="demoDashboardFrame" src="http://49.206.20.140:8080/dashboards/18ffaa70-b067-11ea-8185-352a49241b2f" frameborder="0" width="100%"></iframe>
<div class="center" style="margin-bottom: 20px;">
    <a target="_blank" style="padding: 0 40px;" href="http://49.206.20.140:8080/dashboards/18ffaa70-b067-11ea-8185-352a49241b2f" class="button">Live demo</a>
</div>

The attached dashboard demonstrates real-time data from smart-meters that is collected using NanoIoT MQTT API. The data is stored in Cassandra DB on our demo server.

We would like to highlight the following features:

 - low-latency updates using web-sockets;
 - ability to zoom-in into the charts by selecting time range with the mouse;
 - advanced tooltips and legend;
 - dashboard toolbar in the top-right corner enables global time selector and switch between dashboards.

## Smart metering solution overview
 
The diagram below identifies data flow and integration points for typical smart metering solution that uses NanoIoT platform to collect and analyze monitoring data from smart meters.

You may notice that there are plenty of connectivity options for smart meters: both via direct connection to the cloud and via Platform Integrations
The NanoIoT platform supports industry standard encryption algorithms SSL and device credentials types (X.509 certificates and access tokens).
The collected data is stored in Cassandra - a popular NoSQL database, which is widely recognized for its fault-tolerance and reliability. 

NanoIoT Rule Engine enables forwarding incoming data to various analytics systems, such as Apache Spark or Hadoop using Kafka or other Message buses.
