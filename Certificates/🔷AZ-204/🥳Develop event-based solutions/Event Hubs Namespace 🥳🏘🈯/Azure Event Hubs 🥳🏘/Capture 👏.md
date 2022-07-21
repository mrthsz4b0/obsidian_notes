# Automatically capture the streaming data
	![[Pasted image 20220713124037.png]]
	- Real time & batch based pipelines
- flexible time & and size interval
- copies data directly from the internal Event Hubs storage
- Continuously running after the first event
- Always sends somthing for downstream processing *(if no data = empty files)*
	- Predictable candece for the **batch processor**
## Autoscale #Azure/Specifications
### For standard tier 🎈
- with Event Hubs throughput units 
### For premium tier 🥇
- with Event Hubs processing units 
- can be in the same region as your event hub or in another region #limitations 
- Captured data is written in Apache Avro format

# Capture windowing #FirstWinsPolicy
- the **first trigger** encountered on the window causes a capture operation

# Scaling to throughput units
| Traffic direction | Throughput Unit | MB/s | Event Number/s |
| :---: | :---: | :---: | :---: |
| Ingress | 1 | 1 | 1000 |
| Egress | Always 2 times as ingress |||
- Standard Event Hubs can be configured with 1-20 throughput units, and you can purchase more with a quota increase support request
- Usage beyond your purchased throughput units is throttled
- 