---
layout: docwithnav

title: Working with IoT device alarms
description: IoT device alarm management using NanoIoT alarms feature

---

* TOC
{:toc}

NanoIoT provides the ability to create and manage alarms related to your entities: devices, assets, customers, etc.

### Alarm Lifecycle

Alarms have a lifecycle. Each Alarm can be cleared and acknowledged. By default, an alarm is not in the active and unacknowledged state.

### Alarm Originator, Type, and Propagation

Alarm Originator is an entity that is responsible for triggering an alarm. By default, an alarm is propagated to all related entities (parent relations only).
An alarm is identified by start time, originator and type. There can't be two active alarms for a same type and originator.

### Alarm Severity

One of the following alarm severities is supported: CRITICAL, MAJOR, MINOR, WARNING, INDETERMINATE.

### Alarm Updates

Alarm entity may be updated by external applications or NanoIoT rules. Alarm keeps track of both clear and acknowledge time and latest change as an end time.

### Alarm REST API

NanoIoT provides REST API to manage and query alarms. See demo environment [Alarm REST API] and general [REST API] documentation for more details.

### Alarm Rules
It is possible to create, update and clear alarm using NanoIoT [rule engine].

