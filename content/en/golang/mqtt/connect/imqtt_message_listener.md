---
type: docs
title: "IMqttMessageListener"
linkTitle: "IMqttMessageListener"
gitUrl: "https://github.com/pip-services3-go/pip-services3-mqtt-go"
description: >
    Interface for MQTT messages.

---


### Description

The IMqttMessageListener interface is used to create listeners for MQTT messages.


### Methods


#### onMessage
Defines the actions to be done once a message is received.

> OnMessage(message mqtt.Message)

- **message**: mqtt.Message - MQTT message with data and topic
