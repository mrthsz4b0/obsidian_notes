# 1 Role
- Separate the code from the env configuration and centralize the config

# 2 🔑 Paired keys and values
- This is how AZ App Config stores **config data**
	- They are case-sensitive unicode-based strings
	- Can't use \* , \\ (reserved characters)
		- Escape them using \\{reserved character}
	- **Encrypted** at rest and in transit

## 2.1 Parts
### 2.1.1 Key
> [!EXAMPLE]
> AppName:Service1:ApiEndpoint
> AppName:Service2:ApiEndpoint
>

### 2.1.2 Label
- nullable
- empty or null by default
> [!EXAMPLE]
> Key = AppName:DbEndpoint & Label = Test 
> Key = AppName:DbEndpoint & Label = Staging 
> Key = AppName:DbEndpoint & Label = Production

> [!WARNING]
> Don't store app secrets in it!

## 2.2 Best practices
### 2.2.1 Hierarchical namespace
- logical structure --> grouping --> easier to read
																							| --> **Pattern** match in query 
																							| --> Only a **portion** of data returns 

> [!EXAMPLE]
> AppName:Service1:ApiEndpoint
> AppName:Service2:ApiEndpoint


> [!EXAMPLE]
> Key = AppName:DbEndpoint & Label = Test 
> Key = AppName:DbEndpoint & Label = Staging 
> Key = AppName:DbEndpoint & Label = Production

### 2.2.2 Versioning
- Use labels to create multiple versions of a key-value
	- e.g. version number, git commit  ID as label

# 3 Summary
