Source: [SharePoint site template and site script overview | Microsoft Docs](https://docs.microsoft.com/en-us/sharepoint/dev/declarative-customization/site-design-overview)

# Site scripts

> [!WARNING] Site script action limit #limitations 
> - when the scripts are applied asynchronously (either through the UI or using the [Add-SPOSiteDesignTask](https://docs.microsoft.com/en-us/powershell/module/sharepoint-online/Add-SPOSiteDesignTask) command)
> $$\leq 300 actions (or 100,000 characters)$$


> [!WARNING]
> You have to set ID for content type!

## Limitations

> [!WARNING] #limitations 
> We'd previously capped the limit of site script actions to 30. This remains the limit for scripts applied synchronously using the [Invoke-SPOSiteDesign](https://docs.microsoft.com/en-us/powershell/module/sharepoint-online/Invoke-SPOSiteDesign) command, but based on customer feedback and support for additional actions we have bumped this limit to 300 actions (or 100,000 characters) when the scripts are applied asynchronously (either through the UI or using the [Add-SPOSiteDesignTask](https://docs.microsoft.com/en-us/powershell/module/sharepoint-online/Add-SPOSiteDesignTask) command).
> 
> There is also a limit of 100 site scripts and 100 site templates per tenant.



