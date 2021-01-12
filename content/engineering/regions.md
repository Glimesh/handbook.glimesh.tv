---
title: "Regions"
date: 2021-01-12T08:39:08-04:00
draft: false
---

Because of Glimesh's focus on low latency, high quality streams, using regions close to you will give you the best experience.

## Current Web Regions
Web hosts our platform infrastructure including the website, chat, api, and other direct user facing technology.

| Computer Name | Human Name | DigitalOcean DC's | Notes | 
|---------------|------------|-------------------|-------|
| kjfk.web.glimesh.tv | North America - New York | NYC1, NYC2, NYC3 | |


## Current Live Regions
Live hosts our video streaming infrastructure. It's worth noting the live denotation is agnostic to the type of streaming being done (FTL, RTMP, WebRTC, etc).

| Computer Name | Human Name | DigitalOcean DC's | Notes | 
|---------------|------------|-------------------|-------|
| kjfk.live.glimesh.tv | North America - New York | NYC1, NYC2, NYC3 | |
| kord.live.glimesh.tv | North America - Chicago | n/a | Points to KJFK | 
| ksfo.live.glimesh.tv | North America - San Francisco  | SFO1, SFO2, SFO3 | Points to KJFK |
| eham.live.glimesh.tv | Europe - Amsterdam, Netherlands | AMS1, AMS2 | Points to KJFK | 
| wsss.live.glimesh.tv | Asia - Singapore | SGP1 | Points to KJFK |
| egll.live.glimesh.tv | Europe - London, United Kingdom | LON1 | Points to KJFK | 
| eddf.live.glimesh.tv | Europe - Frankfurt, Germany | FRA1 | Points to KJFK |
| cyyz.live.glimesh.tv | North America - Toronto, Canada | TOR1 | Points to KJFK | 
| vobl.live.glimesh.tv | Asia - Bangalore, India | BLR1 | Points to KJFK |



## Naming Convention

### Region Naming Convention
Glimesh uses ICAO airport codes exclusively for it's computer names, utilizing the nearest major cities largest passenger airport code. The intention of the ICAO codes is to provide a unique code for every geographical region.


### Node Naming Convention
```
Full Syntax:
[provider]-[provider-region]-[node-type][num].[full-icao-code].[purpose].glimesh.tv

Examples:
do-nyc3-ingest1.kjfk.live.glimesh.tv
    |- provider: do
    |- provider-region: nyc3
    |- node-type: ingest
    |- num: 1
    |- full-icao-code: kjfk
    |- purpose: live

linode-us-central-edge342.kdfw.live.glimesh.tv
    |- provider: linode
    |- provider-region: us-central
    |- node-type: edge
    |- num: 342
    |- full-icao-code: kdfw
    |- purpose: live
```

