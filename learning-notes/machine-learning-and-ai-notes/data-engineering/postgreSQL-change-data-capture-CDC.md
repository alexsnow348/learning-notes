---
category: "[[Clippings]]"
author: 
title: "PostgreSQL Change Data Capture (CDC): The Complete Guide"
source: https://datacater.io/blog/2021-09-02/postgresql-cdc-complete-guide.html
clipped: 2023-10-23
published: 2019-05-20
topics: 
tags: [clippings]
---
# PostgreSQL Change Data Capture (CDC) The Complete Guide
___
![[even-driven-aritechture.png]]


![[change_data_capture.svg]]
## Benefits

- CDC captures change events in real-time, keeping downstream systems, such as data warehouses, always in sync with PostgreSQL and enabling fully event-driven data architectures.

- Using CDC reduces the load on PostgreSQL since only relevant information, i.e., changes, are processed.

- CDC enables the efficient implementation of use cases requiring access to change events of PostgreSQL, such as audit or changelogs, without modifying the application code.

## Change Data Capture with Triggers in PostgreSQL

- supports PostgreSQL **version 9.1 and newer** and stores all change events in the table _audit.logged_actions_