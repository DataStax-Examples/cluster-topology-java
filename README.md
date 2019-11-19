# Retrieving Cluster Topology in Java
The [DataStax Drivers](https://docs.datastax.com/en/devapp/doc/devapp/aboutDrivers.html) store metadata about the database cluster that they are connected to, this information can be useful in applications and tools. This example shows how to access that metadata to retrieve the cluster topology in Java.

Contributor(s): [Tomasz Lelek](https://github.com/tomekl007) - derived from [here](https://github.com/datastax/java-driver/blob/4.x/examples/src/main/java/com/datastax/oss/driver/examples/basic/ReadTopologyAndSchemaMetadata.java)

## Objectives

* Show how to gather a Cassandra cluster's topology and schema using driver metadata
  
## Project Layout

* [App.java](/src/main/java/com/datastax/examples/App.java) - The main application file 

## How this Works
This samples shows how to use the `Metadata` class to retrieve information about:

* Cluster topology such as nodes, racks, and data centers
* Keyspaces
* Tables

## Setup and Running

### Prerequisites

* Java 8
* A Cassandra cluster is running and accessible through the contacts points identified by basic.contact-points (see [application.conf](/src/main/resources/application.conf)).

### Running

To build this application use the following command:

`mvn clean compile`

To run this application use the following command:

`mvn exec:java -Dexec.mainClass="com.datastax.examples.App"`

This will produce something similar to the following output:

```
Data Center: dc1; Host: /127.0.0.1:9042; Rack: rack1
Keyspace: system_auth; Table: role_members
Keyspace: system_auth; Table: role_permissions
Keyspace: system_auth; Table: roles
Keyspace: system_schema; Table: aggregates
Keyspace: system_schema; Table: columns
Keyspace: system_schema; Table: dropped_columns
Keyspace: system_schema; Table: functions
Keyspace: system_schema; Table: indexes
Keyspace: system_schema; Table: keyspaces
Keyspace: system_schema; Table: tables
Keyspace: system_schema; Table: triggers
Keyspace: system_schema; Table: types
Keyspace: system_schema; Table: views
Keyspace: examples; Table: videos
Keyspace: system_distributed; Table: parent_repair_history
Keyspace: system_distributed; Table: repair_history
Keyspace: system_distributed; Table: view_build_status
Keyspace: system; Table: IndexInfo
Keyspace: system; Table: available_ranges
Keyspace: system; Table: batches
Keyspace: system; Table: batchlog
Keyspace: system; Table: built_views
Keyspace: system; Table: compaction_history
Keyspace: system; Table: hints
Keyspace: system; Table: local
Keyspace: system; Table: paxos
Keyspace: system; Table: peer_events
Keyspace: system; Table: peers
Keyspace: system; Table: prepared_statements
Keyspace: system; Table: range_xfers
Keyspace: system; Table: size_estimates
Keyspace: system; Table: sstable_activity
Keyspace: system; Table: transferred_ranges
Keyspace: system; Table: views_builds_in_progress
Keyspace: system_traces; Table: events
Keyspace: system_traces; Table: sessions
```

