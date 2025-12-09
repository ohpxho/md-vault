# Database Internals

## Introduction - Chapter 1

### DBMS Architecture

```
There are different variations of architecture. What noted here are some of the common themes that most architecture has similiraties
```

- Uses a client/server model where the client is the application and the database system instances are the server

Request Lifecycle:

1. Client makes a request
2. **Transport subsytems** hands the query over to a **query processor**
3. Query processor parses, interprets, and validates the query. Then, perform access control checks after interpretation
4. Parsed query is passed into the **query optimizer**, which will find the most optimize **execution plan** to execute the query
5. **Execution engine** handles the execution plan, which collects the result of the execution of local and remote operations.
   5.1. **Remote execution** involves reading and writing data to and from other nodes in the cluster, and replication
   5.2. **Local execution** are executed by **storage engine**

### Components of Storage Engine

1. `Transaction Manager`
   - Schedules transaction
2. `Lock Manager`
   - Locks db objects for running transactions
   - Ensuring concurrent operations do not violate physical data integrity
3. `Access Methods (Storage Structures)`
   - Manages access and organizing data on disk
4. `Buffer Manager`
   - Caches data pages in memory
5. `Recovery Manager`
   - Maintains the operation log
   - Resoration of system state in case of failure

### Memory VS Disk-Based DBMS

- Memory based use memory as primary storage and use the disk for recovery and logging. While, Disk based uses disk as primary storage and use memory for caching

| Memory-based DBMS | Disk-based DBMS |
| ----------------- | --------------- |
| **Memory**        | **Disk**        |
| Faster            | Slower          |
