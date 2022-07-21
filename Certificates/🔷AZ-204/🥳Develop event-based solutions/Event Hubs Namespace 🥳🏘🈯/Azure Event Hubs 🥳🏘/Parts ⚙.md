# Parts
![[Pasted image 20220713122236.png]]
## Event Hub client
### Event Hub producer
### Event Hub consumer
- **Auto load-balance** as instances become available or unavailable for the group.
- .NET: EventProcessorClient by The Azure Event Hubs SDK

> [!WARNING]
> Recommended for most prod scenarios' for reading and processing events


## Partition

^8d72bd

- A bit like [[🔍Filter events|event filtering]] filtering in [[🥳🟦Azure Event Grid]] subscriptions
- Chunking up the data and everyone is taking his specific part he needs
- Each partition **[[Capture 👏#Capture windowing|captures]]** independently
	- **writes** a completed block blob at the time of capture
		- named for the time at which the capture interval was encountered
		
> [!EXAMPLE] 
> `{Namespace}/{EventHub}/{PartitionId}/{Year}/{Month}/{Day}/{Hour}/{Minute}/{Second}`
> ` https://mystorageaccount.blob.core.windows.net/mycontainer/mynamespace/myeventhub/0/2017/12/08/03/03/17.avro`

- $$\sum$$
	- an independent segment of data and is consumed independently
> [!WARNING] Limitation
> specified at the time an Event Hub is created and cannot be changed. #limitations 

## Consumer group
- enable **multiple** consuming **applications** to each have a **separate view** of the event stream, and to **read** the stream **independently** at their own pace and from their own position
- A bit like replicas 

> [!WARNING] Limitation
> at most **5 concurrent readers** on a partition per consumer group; however it is recommended that there is only one active consumer for a given partition and consumer group pairing #limitations 
## Event processors
- Has a unique ID
### Checkpointing
- claims ownership of [[## Partition]] by adding or updating an entry of their ID in a checkpoint store
	- Periodically communicates with the checkpoint store to
		- updates it's own processing state
		- learn about other active instances (used for load balancing)
		![[Checkpoint store.excalidraw]]
- If a processor alfunctioning, from that consumer group another one resumes the partition processing 
	- We can also check older data by specifying a lower offset from this checkpointing process

> [!WARNING]
> A processor must be fast. 
> Do as little procesing as possible!
>  If you need to write to storage and do some routing, it's better to use two consumer groups and have two event processors.

> [!INFO] Connections
> All Event Hubs consumers connect via the AMQP 1.0 session.
> All Kafka consumers connect via the [[Event streaming 🥳🚿#Apache Kafka|Kafka]] protocol 1.0 and later.

## Throughput/processing units