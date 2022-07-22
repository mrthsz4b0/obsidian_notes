# 1 🈸 Client Apps
## 1.1 🎏 Types
### 1.1.1 Public client app
- They run on **devices, desktop computers and web browsers**.
- Why do **they only access web APIs on behalf of the user.** (They support only public client flows.)→
> [!WARNING]
> They're not trusted to safely keep application or client secrets

### 1.1.2 Confidential
- on servers (web apps, web API apps, or even service/daemon apps)

### 1.1.3 Public VS Confidential App
#Comparism⚖ 

|                          Topic                          |                            Public                            |                           Confidential                           |
|:-------------------------------------------------------:|:------------------------------------------------------------:|:----------------------------------------------------------------:|
|                        ⚗ Usage                         |         devices, desktop computers and web browsers          | on servers (web apps, web API apps, or even service/daemon apps) |
|                       🌎 Location                       |                                                              |       a Web app located at https://myapp.azurewebsites.net       |
| 🔐🌎 Authentication location (where they are signed in) |             in the Microsoft Azure public cloud              |               in the Microsoft Azure public cloud                |
|            🔐🧑Authentication identity type             | work / school accounts, or their personal Microsoft accounts |   work / school accounts, or their personal Microsoft accounts   |
|        🈸🆔 The identification of the app itself        |                  Not needed as it is public                  |                    By sharing a client secret                    |
|                   🚹🚺 Instantiation                    |                       Using client ID                        | Using client ID                                                                 |
![[#^61a879]]

![[#^3328af]]

```csharp
IPublicClientApplication app = PublicClientApplicationBuilder.Create(clientId).Build();
```

^61a879

```csharp
string redirectUri = "https://myapp.azurewebsites.net"; IConfidentialClientApplication app = ConfidentialClientApplicationBuilder.Create(clientId) .WithClientSecret(clientSecret) .WithRedirectUri(redirectUri ) .Build();	
```

^3328af


# 2 👩‍💻 Implementation
- Use `Public` or `ConfidentialClientApplicationBuilder` 
	- 👍 Can be configured from a **configuration file**
	- 👍 Can be configured **from code**

## 2.1 Implement public app using MSAL
-   **Register** a new app
-   In the **code**
    -   **Add** dependency : `dotnet add package Microsoft.Identity.Client`
    -   [[#^12f9f2|**Create an** **PublicClientApplicationBuilder** **from a clientID.**]]
    -   **Acquire** token
	    1. **Set** the permission scopes of the token in C#: `string[] scopes = { "user.read"}`
	    2. **Add** code to request the token in C#: 



```
AuthenticationResult result = await app.Acq
uireTokenInteractive(scopes).ExecuteAsync(); Console.WriteLine($"Token:\t{result.AccessToken}");
```



## 2.2 For confidential
- a Web app located at https://myapp.azurewebsites.net

```CSHARP "FOLD"
var app = PublicClientApplicationBuilder .Create(_clientId) .WithAuthority(AzureCloudInstance.AzurePublic, _tenantId) .WithRedirectUri("http://localhost") .Build();
```
^12f9f2




# 3 🚿 Authentication flows
## 3.1 Microsoft Authentication Library
- No need to directly use the OAuth libraries or code against the protocol in your application.

> [!WARNING] 
> The MS Authentication Library Handles only token expiration
### 3.1.1 Authentication flows it provides
#### 3.1.1.1 Public flows
1. Acquires tokens on behalf of a user [[Permission Types 🔀#Delegated]] 
2. Acquires tokens on behalf of an application [[Permission Types 🔀#Application]] (when applicable to the platform)
3. **Client credentials** for **Service applications** run without user interaction
4. The application calls a **service/web API**, which in turns calls Microsoft Graph - **3rd hand call**
5. Enables sign-in to a device by using another device's browser - **3rd hand device**
6. Windows computers silently acquire an access token when they are [[🔵🖇Windows Domain Join|domain joined]]
7. Mobile and desktops applications call Microsoft Graph in the name of a use
8. Sign in a user by username and password

