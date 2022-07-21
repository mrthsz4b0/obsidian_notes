# 1 ⚗ Usage 
- For storage accounts
- A client without permission to those resources 

> [!EXAMPLE] 
> Service where users read and write data using my storage


> [!WARNING]
> **When you copy a blob to a file, or a file to a blob, you must use a SAS to authorize access to the source object** even if they are in the same storage account
- You want to do this operation above. Which type of SAS shall I use?


# 2🧩 Parts

# 3 🎏 Types
## 3.1 User delegation SAS

^1d93c9

### 3.1.1 Secured with
1. AAD credentials
2. Permissions, specified for the SAS
> [!INFO] On AZ Portal:
> ![[Pasted image 20220718090152.png]]
### 3.1.2 Applies to
1. Blob storage only

## 3.2 Service SAS
### 3.2.1 Secured with
1. Storage account key ^db7198

### 3.2.2 Applies to
- <u>AZ storage services:</u>
	1. Blob
	2. Queue
	3. table
	4. AZ files

## 3.3 Account SAS
### 3.3.1 Secured with
- Same as [[#^db7198|Service SAS]]

### 3.3.2 Applies to
- $\geq1$ storage services' resources
	- <-> Service SAS accesses only for 1  storage service's resources



# 4 👬 Design Patterns
## 4.1 Front-end proxy service
![[Pasted image 20220718093909.png]]
- A middle tier does the authentication
- For processing and validating data - [[#^c37cac|because of this]]

### 4.1.1 👍 Pros
1. Allowing validation of businness rules
![[Pasted image 20220718094311.png]]

^c37cac

### 4.1.2 👎 Cons
1. Difficult to create a service that scale to match demand when there are many data & big transactions
![[Pasted image 20220718094324.png]]

## 4.2 SAS provider service
![[Pasted image 20220718094414.png]]
- **authenticates** the client and then **generates** SAS
- For save/read data directly






# 5 👍 Best practices #Bestpractices
-   Use HTTPS![](https://remnote-user-data.s3.amazonaws.com/1kS6-JQLgHyBafaYf4dmykNcXuThuNZZ6HnSBFYwHoFMvJegpzthxr4vt1Te3yxL3_j5XbxxbMScVaUzlcYZMCGh3NhzyiYW_b7OFb8qnYB2chtDdJNtii7nfNXd23xs.png)
-   Set expiration time to the smallest useful value ![[Pasted image 20220718092311.png]]

-   Only grant the access that's required ![](https://remnote-user-data.s3.amazonaws.com/_qKa310ghtbK5rz5z_TTy9VcjLyPGMXefL16dWjZvO5QDwVFowz9InSTmjmiYA-w_TnhRvR1xI4EwCi7P7gqrj94oy21PYAE7gDmGdfzC1xzv_o_0IbBc2oOAspa6rHZ.png)
- When there's an unacceptable risk of using a SAS, create a [[👬 Design Patterns#1 Front-end proxy service|middle-tier service]] to manage users and their access to storage ![](https://remnote-user-data.s3.amazonaws.com/3LuemQCS_OVFT7u30OpCTZPH6LfFOJ9vCwUP1EvTswBqncnwaZtXN4CdokAZjprW6xnfwV1X2jsw_ecbp5aQx7T-bxT5YqsDZFSVvwouMGiq81kcz6169P_0pOwRIS3Y.png)

> [!WARNING] User delegation SAS
> Microsoft recommends that you use [[🎏 Types#1 User delegation SAS|Azure Active Directory credentials]] when possible as a security best practice, rather than using the **account key**, which can be more easily compromised + don't have to tore key in the code! ![](https://remnote-user-data.s3.amazonaws.com/3XzQwzcKxm2CzWgwPqGiWP-NphHuQpCO6PYZTeYIBCWAKQ0a8m4wU6OnI48b6DCdXkdviYOU8neho8Qek8cETgJ3jkOBrtjgqa0TgeFsccVSoAAvAiBNphvVKlFcYKYo.png)

- **The most flexible and secure way to use a service or account SAS?** is to associate the **SAS tokens** with a [**stored access policy**](https://www.remnote.com/doc/ndbpz3qKq9tmmMu4d)