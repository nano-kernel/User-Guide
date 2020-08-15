---
layout: docwithnav

title: Device authentication options
description: NanoIoT IoT Device authentication options.

---

Device credentials are used in order to connect to the NanoIoT server by applications that are running on the device.
NanoIoT is designed to support different device credentials. There are two supported credentials types at the moment:

 - [**Access Tokens**] - general purpose credentials that are suitable for wide range of devices. 
 Access Token based authentication may be used in not encrypted or one-way SSL mode.
   - **Advantages:** supported by resource constrained devices. Low network overhead. Easy to provision and use.
   - **Disadvantages:** may be easily intercepted while using un-encrypted network connection (HTTP instead of HTTPS, MQTT without TLS/SSL, etc).
 - [**X.509 Certificates**] - [PKI](https://en.wikipedia.org/wiki/Public_key_infrastructure) and [TLS](https://en.wikipedia.org/wiki/Transport_Layer_Security) standard. 
 X.509 Certificate based authentication is used in two-way SSL mode.
   - **Advantages:** high level of security using the encrypted network connection and public key infrastructure.
   - **Disadvantages:** not supported by some resource constrained devices. Affects battery and CPU usage.

Device credentials need to be provisioned to corresponding device entity on the server. 
There are multiple ways to do this:

 - **Automatically**, using NanoIoT [REST API]. For example during manufacturing, QA or purchase order fulfilment.
 - **Manually**, using NanoIoT [Web UI]. For example for development purposes, or by system administrator.


