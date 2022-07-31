# Export list to pnp provisioning template
#script/powershell/pnp
```powershell
Get-PnPSiteTemplate -Out template2.xml -ListsToExtract "Daily OPS tasks" \ - Handlers Lists
```

OR

```powershell
Get-PnPSiteTemplate -Out Lists.xml -ListsToExtract "Test" -Handlers Lists
```

# Apply PnP provisioning site template
```powershell
Invoke-PnPSiteTemplate -Path .\dev-template.xml
```

# Hyphen in path
- Use quotation mark