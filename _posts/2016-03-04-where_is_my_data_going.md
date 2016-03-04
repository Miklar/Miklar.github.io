---
layout: post
title: "Where is my data going?"
description: "Commando to see what is hitting my port"
tags: [metrics]
---

## ngrep
*ngrep* is like grep, but for the network. Use ```ngrep -d any -W byline port 2003``` to watch what is hitting the given port.
In this case I use it to see if what I try to post to Graphite is going where I think it is going.

To send data directly to Graphite via udp, do this: ```echo "fisk.local.diceroll 4 `date +%s`" | nc -u -w0 [IP] 2003

## Docker container ip
Use ```docker inspect --format '{{ .NetworkSettings.IPAddress }}' ${CID}```
