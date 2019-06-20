---
title: "Elastic Search Basics"
date: 2019-06-17T17:15:15Z
categories: ["Elastic Search"]
draft: false
---

### Elastic Search Concepts
1. [Cluster](#cluster)
2. [Node](#node)
3. [Index](#index)
4. [Type](#type)
5. [Document](#document)
6. [Shard](#shard)
7. [Replica](#replica)


#### Cluster
* It's a collection of one or more nodes and holds entire data and provides indexing & search capabilities.
* Nodes can join a cluster by cluster's name.

#### Node
* A node is a single server(part of the cluster) and participates in indexing and search capabilities.
* Node can be configured to join specific cluster by the cluster name.

#### Index
* Collectin of documents that have somewhat similar characteristics.
* one index for reports and another index for meta_data.
* In a single cluster, you can define as many indexes as you want.

#### Type
* **Deprecated in 6.0.0**
* A type used to be a logical category/partition of your index to allow you to store different types of documents in the same index

#### Document
* Basic unit of JSON blog that can be indexed. One might say it's like a tuple(row) in db table.
* Within an index, you can store as many documents as you want.

#### Shard
* Index can store large amounts of data, which can exceed hardware limits of a single node.
* A single index of a billion documents taking up 1TB of disk space may not fit on the disk of a single node or may be too slow to serve search requests from a single node alone.
* An index can be subdivide into multiple pieces called shards.
* When you create an index, you can simply define the number of shards that you want
* Each shard is in itself a fully-functional and independent "index" that can be hosted on any node in the cluster.
* Sharding is important for two primary reasons:
	* It allows you to horizontally split/scale your content volume
	* It allows you to distribute and parallelize operations across shards (potentially on multiple nodes) thus increasing performance/throughput

Ref:https://www.elastic.co/guide/en/elasticsearch/reference/current/getting-started-concepts.html

#### Replica
* Replication is important for two primary reasons:
	* It provides high availability in case a shard/node fails. For this reason, it is important to note that a replica shard is never allocated on the same node as the original/primary shard that it was copied from.
	* It allows you to scale out your search volume/throughput since searches can be executed on all replicas in parallel.

