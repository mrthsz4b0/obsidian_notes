# 1 General
- Uses [[OAuth 🍜]] 2.0
- resource's identifier or application ID URI + the permission value

> [!EXAMPLE]
> [graph.microsoft.com/Calendars.Read](https://graph.microsoft.com/Calendars.Read) 
> The full scope looks like this in the URL:
>

```html
&scope=https%3A%2F%2Fgraph.microsoft.com%2Fcalendars.read%20 https%3A%2F%2Fgraph.microsoft.com%2Fmail.send&state=12345
```

# 2 ⚗ Usage
- Accessing to resource from code



# 3 🎏 Permission Types
## 3.1 Delegated permission
### 3.1.1 Use case
- Make calls to the target resource as a signed-in user  
- When a user is signed in

### 3.1.2 Permission is given by
- either the user or an administrator

## 3.2 Application permission
### 3.2.1 Use case
- Apps without a signed-in user

### 3.2.2 Permission is given by
- admin only

#Comparism⚖ 
| Type | Use Case | Who gives the permission that the app requests |
| :---: | :---: | :---: |
| Delegated | - Make calls to the target resource as a signed-in user <br> - When a user is signed in | either the user or an administrator |
| Application | - Apps without a signed-in user | Admin |

perm vs consn types


# 4 🎏 Consent types
## 4.1 User consent
### 4.1.1 Static
- You must specify all the permissions it needs in the apps' configuration in the Azure Portal
- App needs to know all the access resources ahead of access time
- Defined in the app registration
> [!INFO]
> Enables administrators to consent in the name of all users who are in the organization

### 4.1.2 Dynamic / Incremental
When we use Mirosoft identity platform endpoint
- Ask minimum set of [[Permission Types 🔀|permissions]] at the start and increase it as the user uses additional features
- Why Can't it be applied to **admin consent**?→ the admin consent experience doesn't know about those permissions set at consent time ^3a0357
- Tenant admins want to consent on behalf of all their users. What shall we do in this case?→If you require admin privileged permissions or if your app uses dynamic consent, you must register all of the permissions in the Azure portal (not just the subset of permissions that require admin consent). This enables tenant admins to consent on behalf of all their users. 
^efb9ea
#Comparism⚖ 
| Point | Static | Dynamic / Incremential |
| :---: | :---: | :---: |
| Usage | Admin needs to **consent** on behalf of the user | If we use Microsoft identity platform endpoint |
| Definition of [[Permission Types 🔀]] ( by time) | At the start before acessing to anything | At the start (minimum ammount) & when the customer uses addition app features|
| Definition of [Permission Types 🔀](app://obsidian.md/Permission%20Types%20%F0%9F%94%80) ( by location) | In the app registration information | Including new scope in the scopes parameter |
| Definition of [Permission Types 🔀](app://obsidian.md/Permission%20Types%20%F0%9F%94%80) ( by measure) | Define every all of the resources the app ever access | Add new scopes to the [[Knowledge Center 🏫/🔷AZ-204/🔐☁ Implement secure cloud solution/🆔 The Microsoft identity platform/Permission Requests 🙏/Parts ⚙|scope parameters]]
| [[Permission Types 🔀#^2c3ec3]] | Can be applied to both 💚 | Only for Delegated permission ❌ (Because it can't beadmin consent) |
| Can be applied to admin consent | 💚 | ❌ |

## 4.2 Admin consent
- Admin consent done on behalf of an **organization** still requires the static permission→[[#^3a0357|True]]
- Admins give the permissions for the users. By this way they don't have to interact later on with the consent system.
- [[#^efb9ea|Tenant admins want to consent on behalf of all their users. What shall we do in this case?



consent vs permission



# 5 ⚖ Permission types VS Consent types 
#Comparism⚖ 
- You create a request in the name of somebody. That's a Permission type. That somebody has predifend (or defined on the fly) permission sets. That's the consent type. 

