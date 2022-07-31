# Managed metadata
- Managed metadata: A **globally** available metadata service

## Pros of Managed Metadata columns

-   Managed Metadata is globally available - across all sites in the farm or tenant
-   Managed Metadata supports language translations
-   Changes to the term set values will be updated across all sites
-   Administrators can control who can contribute to each term set
-   Combined with search, you can create a global search center with refiners across all sites using the term set

## [](https://docs.microsoft.com/en-us/microsoft-365/community/information-architecture-managed-metadata-vs-lookup-column#cons-of-managed-metadata-columns)Cons of Managed Metadata columns

-   Cannot be managed freely by site owners, changes have to be added to a change policy to avoid failures
-   Managed metadata is "singular" meaning you cannot connect other metadata to it, like we can with lookup columns. For example, the **Active from Date** and **Active to Date** in the first example above.

## Dev experience

-   There is no single way of doing things in SharePoint. It all depends on the use cases.
-   I normally use Managed Metadata when dealing with cross site publishing or global search-related metadata. Because the metadata values are normally managed by a few people and used widely across all sites in SharePoint, we get more consistency and converge on a common understanding. This is especially true when building Document Management solutions or Intranet News publishing.
-   I use Lookup columns, when I'm building solutions that are locally related to a site, and the lookup data is from multiple lists already in the site. For example, when building custom apps with Power Apps and I'm using SharePoint lists as data sources.
---
- appinv.aspx - to register app in sharepoint
- AppPrincipals.aspx

- If you have read access to the site you have read access to every list, only the wright access on the list can be more restrictive after you can read whole site

IRU: - Fab has the script to parse the reference excel  + create app catalog on all QA sites

# Mobile view

> [!WARNING] Mobile view
> Mobile options in modern site are not used


 Only the view is limitation 5000 if this comes for a **filtering**
- Question: how do they spread by content type
	- Narrow down by
		- Metadata
		- Separate vew

- term-store limit: million all together?
- Limit for term-set: 1000?

- Drop down - yes or no
	- You can convert tru/false to choice

- Can import term-sets
	- Can't export through UI
- Internal ID --> listitemid🔢
- A specific doc lib


# Modify SPO toolbar & button
- [How to Modify SharePoint List Toolbar Buttons with List Formatting - YouTube](https://www.youtube.com/watch?v=sZYZnJGQgcI&ab_channel=AprilDunnam)

# Power Apps form
- When you create a SPO form PowerApp you replace all the forms (it will pop up every time you click on properties in SPO instead of property pane) - however if we use the title instead of the name we can get rid of the 3 dots, but we have to double-click on the entry to open. There is also not displays the extension

# SPO list as a form/survey
## Problems
1. If you add a new user he will need access to the tenant. So you have to know at the beginning who will use it
2. The only way to fully-securly set the record read-only after submission is to change the permission on the item

# Permissions
## Permission levels
### Limited access
![[Pasted image 20220721113647.png]]
- It can be also set if creating a doc is by flow and e.g. power automate 

### Understanding permission levels
- [Understanding permission levels in SharePoint - SharePoint in Microsoft 365 | Microsoft Docs](https://docs.microsoft.com/en-us/sharepoint/understanding-permission-levels?redirectSourcePath=%252fen-us%252farticle%252funderstanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848)

# Columns
## 3-ways-to-display-related-documents-in-sharepoin
- [https://sharepointmaven.com/3-ways-to-display-related-documents-in-sharepoint](https://sharepointmaven.com/3-ways-to-display-related-documents-in-sharepoint)
- In our opinion, the best way would be the second solution, the one that rely again on a metadata, which would be common between a parent contract, and all these possible annexes and extensions.

- If you want pre.defined values (e.g. company names) it is not a good practice to be a free text field instead of pre-defined choice field. The same company name can be written in different ways. 
	- Bad search
	- Bad filtering

# Groupping
## You can't group by multi-selection field
- Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.
# Date and Time
## SharePoint always assumes that it gots the date time in UTC time zone 

^d66296

# Problems
## Date and Time
### [[Power Automate 🧵|Power Automate flow]] updated the date of an item. Even though I used convertFromUtc() function in the Power Automate formula with the correct time zone, SharePoint added 2 hours to it
#### What happened:
1. The time zone of SharePoint has already been set to W. European... ^db9516
2. I converted the date time to W. European... time zone in the flow ^6a1ca0
3. The sharepoint got the value but as [[#SharePoint always assumes that it gots the date time in UTC time zone]] AND [[#^db9516|1. The time zone of SharePoint has already been set to W. European...]] AND W. European... time zone is UTC + 2 = SPO added 2 hours to the value [[#^6a1ca0|that was already in W. European... time zone]]

## Non-office documents & default values
- If you change the content type of a non-office document the default value won't be set, unless that content type is the default one