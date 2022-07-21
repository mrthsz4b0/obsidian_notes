# 1 ⚗ Usage
- For registered apps, after you aquired authentication tokens [[🔑 SAS#2🧩 Parts]] for a user or a service

## 1.1 Acquiring token
- Using Microsoft Authentication Library API, MSAL [[⚖ Public VS Confidential Client App]]
## 1.2 Send token in the request header as a bearer token
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

## 1.3 The graph client constructor, when using a Microsoft Graph client library
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

