# Power Apps form
- When you create a SPO form PowerApp you replace all the forms (it will pop up every time you click on properties in SPO instead of property pane) - however if we use the title instead of the name we can get rid of the 3 dots, but we have to double-click on the entry to open. There is also not displays the extension

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