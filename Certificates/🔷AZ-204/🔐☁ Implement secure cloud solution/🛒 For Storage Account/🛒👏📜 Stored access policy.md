# 1 ⚗ Usage
## 1.1 Modifies
- Change the start/exp time & permission for the signature

## 1.2 Revokes
- acess later
- Extend access later

## 1.3 Applies to
- 👍 Good for every type of storages except disk storage

## 1.4 Location
- It is on the Container or on the Queue, table etc...

> [!WARNING]
> 1. **You cannot specify a given parameter on both the SAS token and the stored access policy!**
> 2. 6> A container, table, queue or share can have at any given time #limitations 
> 3. it can be applied to eg. a container Only in the storage explorer



# N 👩‍💻 Programatical approach
- **Set AC** (Set Container ACL, Set Queue ACL, Set Table ACL, or Set Share ACL) + request body

## 1 Request body
1. permissions
2. $\leq64$ characters, unique, signed ID

> [!WARNING]
> 1. **Changing the signed identifier breaks the associations between any existing signatures and the stored access policy**
> 2. **Deleting or modifying the stored access policy immediately affects all of the SAS associated with it.**



#Azure/Codes
```csharp
BlobSignedIdentifier identifier = new BlobSignedIdentifier { Id = "stored access policy identifier", AccessPolicy = new BlobAccessPolicy { ExpiresOn = DateTimeOffset.UtcNow.AddHours(1), Permissions = "rw" } }; blobContainer.SetAccessPolicy(permissions: new BlobSignedIdentifier[] { identifier });
```
#Azure/Commands
```powershell
az storage container policy create \ --name <stored access policy identifier> \ --container-name <container name> \ --start <start time UTC datetime> \ --expiry <expiry time UTC datetime> \ --permissions <(a)dd, (c)reate, (d)elete, (l)ist, (r)ead, or (w)rite> \ --account-key <storage account key> \ --account-name <storage account name> \
```

> [!WARNING]
> Calling with empty body causes the resources to remove all acess policies!

