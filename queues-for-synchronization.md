---
layout: docwithnav
title: Using queues for synchronization
description: Using queues for synchronization

---

* TOC
{:toc}

## Use case

Let's assume you need to implement the "counter" logic using NanoIoT Rule Engine.
Basically, message processing is executed asynchronously inside the Rule Nodes. Due to this fact, in most cases, the logic "get present counter value -> add new counter value -> save counter value" 
leads to the incorrect final result (unlike your expectations) due to the race condition issue. 
It is a well-known problem for all who dealt with multi-threading programming.
You can refer to this [article](https://opensourceforgeeks.blogspot.com/2014/01/race-condition-synchronization-atomic.html) which nicely describes the problem and the existed solutions.
Starting the NanoIoT v2.5 this processing issue could be solved using special configurable queues.

In this tutorial, we will configure NanoIoT Rule Engine to use queue with sequential by originator message submit strategy.
Although this scenario is fictional, you will learn how to work with the queue to allow processing messages in sequential order
and use this knowledge in real-life applications.

## Prerequisites 

In addition, you need to have at least one device provisioned in your environment.

## Step 1: Creating the Rule Chain

We will add two generator nodes that will generate seven messages each. First generator will produce a message with the counter value of 101.
Second - with the value of 10. So the result should be 777.

Both messages will be put into the queue with the name **"SequentialByOriginator"**. It uses the message submit strategy called **"SEQUENTIAL_WITHIN_ORIGINATOR"** 
which means that the subsequent message will start being processed when the preceding message is acknowledged (is processed and deleted from the queue) based on the originator.


We will get the present "counter" value using **"Originator Attributes"** node.


The calculations will be done using **"Counter Script"** node. 

The last step will be to save the new counter value using **"Save Attributes"** node.

## Step 2: Validation the Rule Chain logic

Let's check that our logic is correct by saving the Rule Chain. The generators will automatically produce 14 messages:


The final counter value that is persisted for a device is:

That means that our logic works correctly.






