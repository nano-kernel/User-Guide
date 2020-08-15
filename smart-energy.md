---
layout: docwithnav
title: Smart energy monitoring, data visualization and energy efficiency analysis
description: Smart energy monitoring and data visualization with NanoIoT IoT Platform
horizontaltoc: "true"

---

## Overview

NanoIoT platform provides out-of-the-box components and APIs to dramatically reduce time to market and your effort to create smart energy solutions and energy monitoring systems.
Save up to 90% of development time for your smart energy solution by utilizing following benefits:

 - Reliable and fault tolerant data collection for your smart meters and energy monitors;
 - Advanced and flexible data visualization for real-time and historical smart energy monitoring;
 - Customizable end-user dashboards to analyze and share the results of energy efficiency monitoring;
 - Integration with third-party analytics frameworks and solutions for advanced electricity usage monitoring;
 - Enable energy management by utilizing NanoIoT API to control and manage smart meters.
 
The platform provides production ready server infrastructure to connect your smart meter devices, collect, store and analyze energy monitoring data, and share results of the analysis with your customers and end-users.

We would like to highlight following features:

 - low-latency updates using web-sockets;
 - ability to zoom-in into the charts by selecting time range with the mouse;
 - advanced tooltips and legend;
 - dashboard toolbar in the top-right corner enables global time selector and switch between dashboards.

## Smart energy solution overview
 
The diagram below identifies data flow and integration points for typical smart energy solution that uses NanoIoT platform to collect and analyze energy monitoring data from smart meters.

You may notice that there are plenty of connectivity options for smart meters: either direct connection to the cloud or through the IoT Gateway.
Platform supports industry standard encryption algorithms (SSL) and device credentials types (X.509 certificates and access tokens).
The collected data is stored in Cassandra - fault-tolerant and reliable NoSQL database.
NanoIoT Rule Engine allows to forward incoming data to various analytics systems, such as Apache Spark or Hadoop using Kafka or other Message buses.

