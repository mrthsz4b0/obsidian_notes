# Competing consumers pattern #DesignPatterns


# Partitioned consumer pattern #DesignPatterns
## Given the example: [[Use Case 🔛#^7eb226]]
### 1 Scale
- Multiple partition per consumers
### 2 Load balance
#### Dynamically scale out #ScaleOut
- Increase or reduce the consumers dynamically

> [!EXAMPLE]
> 1. A new sensor type (for example, a carbon monoxide detector) is added to each home the number of events increases
> 2. I encrease the consumer instance --> the pool of consumers can rebalance the number of partitions they own, to share the load with the newly added consumers

### 3 Seamless resume on failures

> [!EXAMPLE]
> 1. consumer (**consumer A**) fails (for example, the virtual machine hosting the consumer suddenly crashes)
> 2. other consumers can pick up the partitions owned by **consumer A** and continue (according to a checkpoint)
