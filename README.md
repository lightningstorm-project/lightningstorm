# Lightning Storm Project

A peer-to-peer transmission and cloud storage meta-protocol

## Code / Exmaples

* Python implementation: https://github.com/lightningstorm-project/python-lightningstorm

## Motivation

A way to share information between two or more people by using one or more personal sharing nodes.

## Overview

### Cloud - Information sharing node

A node represents a person. It will store and share information from this person to others.

Other people nodes will constantly pool this node looking for new raindrops.

### Raindrop - Shared information

A raindrop is a data representation to be sent between nodes.

A raindrop has its metadata information together with the data payload.

#### Features:
* immutable (UUID4 for unique identification)
* serializable (MIME, JSON, ...)
* extensible (with custom headers)

#### Minimal raindrop example

Serialized in MIME/"HTTP-like" message format

```HTTP
UUID: e96e58c7-0df4-4bb0-9b28-c90e5de940bb
Created-Date: 2020-03-22T03:27:33.798618+00:00
Content-Type: application/octet-stream
Content-Lenght: 20

any binary payload��
```

A raindrop just needs to have a UUID and a payload.

### Atmosphere - Transmission medium

Raindrops will be sent through a medium.

Today, the most available form is the Internet, but a DVD, a pendrive or even a ham radio can be used to transmit raindrops from a node to another.

#### Precipitation - Effective transmission event

Each medium can have more than one form of transmitting raindrops.

For instance, a node running on a mobile phone can use the Dropbox app to share some raindrops. In this case, the other end only need to support HTTP to obtain these raindrops.
