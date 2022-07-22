# 1 🌌 General
- defines most of its resources, methods, and enumerations?→in the OData **namespace**, microsoft.graph, in the [Microsoft Graph metadata service document](https://www.remnote.com/doc/GJxiS6WqoLCuEfMJW)


# 2 🟦 Implementation
## Users
- Stores the users in **Evolvable enumeration**
	- adds new members to the existing enum **without breaking** the app
## SDKs
### Service library
- Models and request builders
### Core library
- Actions
	1. Retry handling
	2. Secure redirection
	3. Transparent authentication
	4. Payload compression

# 3 ⚗ Usage
- For registered apps, after you aquired authentication tokens  for a user or a service

## 3.1 Acquiring token
- Using Microsoft Authentication Library API, MSAL [[⚖ Public VS Confidential Client App]]
## 3.2 Send token in the request header as a bearer token
```csharp
using System; 
using System.Threading.Tasks; 
using Microsoft.Identity.Client; 
namespace az204_auth 
	{ 
		class Program 
		{ 
			private const string _clientId = "APPLICATION_CLIENT_ID";
			
			private const string _tenantId = "DIRECTORY_TENANT_ID"; 
			
			public static async Task Main(string[] args) 
			{ 
				var app = PublicClientApplicationBuilder
					.Create(_clientId)
					.WithAuthority(AzureCloudInstance.AzurePublic, _tenantId)
					.WithRedirectUri("http://localhost")
					.Build(); 
				string[] scopes = { "user.read" };
				AuthenticationResult result = await 				
					Authentapp.AcquireTokenInteractive(scopes)
					.ExecuteAsync();
				Console.WriteLine($"Token:\t{result.AccessToken}");
			} 
		} 
	}
```

## 3.3 The graph client constructor, when using a Microsoft Graph client library
```csharp:
// Build a client application. 
IPublicClientApplication publicClientApplication = 
	PublicClientApplicationBuilder.Create("INSERT-CLIENT-APP-ID").Build();
// Create an authentication provider by passing in a client application and graph scopes.
DeviceCodeProvider authProvider = new 
	DeviceCodeProvider(publicClientApplication, graphScopes);
// Create a new instance of GraphServiceClient with the authentication provider.
GraphServiceClient graphClient = new GraphServiceClient(authProvider);
```


## ✊ 3.4 Cases to Handle

> [!WARNING]
> Don't use beta APIs for production!


> [!INFO]
> - The metadata document ($metadata) is published at the service root. You can view the service document for the v1.0 and beta versions of the Microsoft Graph API via the following URLs
>    - [graph.microsoft.com/v1.0/$metadata](https://graph.microsoft.com/v1.0/$metadata)
>    - [graph.microsoft.com/beta/$metadata](https://graph.microsoft.com/beta/$metadata)



### 3.4.1 Pages

> [!WARNING]
> The responses always paged!

- Get  the next page using `@odata.nextLink` property
	- The **last page** does not contain it
- Store data locally

### 3.4.2 Members
> [!WARNING]
> By default `GET` operation returns only the **known members**!
- To get members who are **not part** of MS Graphs's evolvable enum mechanism: use the HTTP `PREFER` header! 
