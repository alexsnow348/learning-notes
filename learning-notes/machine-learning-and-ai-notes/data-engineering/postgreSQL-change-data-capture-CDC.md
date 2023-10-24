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

## Three common approaches

1. triggers, 
2. queries, and 
3. logical replication (**Recommended** approach)

## 1. Change Data Capture with Triggers in PostgreSQL

-  listen for all INSERT, UPDATE, and DELETE events occurring in the table of interest and, for each event, insert one row into a second table, building a changelog.

- supports PostgreSQL **version 9.1 and newer** and stores all change events in the table _audit.logged_actions_

- captured events only **inside** PostgreSQL

- Example: Enable Trigger-based CDC for the table _public.users_.

 ```sql
 SELECT audit.audit_table('public.users');
```

##  2. Change Data Capture with Queries in PostgreSQL

- implement change data capture with PostgreSQL is query-based.

- a table named _public.users_ and a timestamp column named _updated_at_, such a query could be implemented as follows:

```sql
SELECT * FROM public.users WHERE updated_at > 'TIMESTAMP_LAST_QUERY';
```

## 3. Change Data Capture with Logical Replication in PostgreSQL 

- Since version 9.4, PostgreSQL offers [logical replication](https://www.postgresql.org/docs/current/logical-replication.html)   for efficiently and safely replicating data between different PostgreSQL instances on possibly different physical machines.

- PostgreSQL uses a **subscription** model with **publishers** and **subscribers** for the implementation of logical replication.

- Employ the **database of interest as a publisher** and **subscribe  to its log.**

- enable logical replication by introducing the following change to the configuration file _postgresql.conf_.

```
wal_level = logical
```

- modify the configuration file _pga_hba.conf_ to allow replication (please refer to the PostgreSQL documentation for individual configuration):

```
host     all     repuser     0.0.0.0/0     md5
```

- capture changes from the table _public.users_. You can enable CDC for this table by creating a new publication as follows:

```
```
