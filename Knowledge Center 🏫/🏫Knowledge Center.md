# SharePoint
- To refer other columns in column validation, use Validation settings instead of the validation inside the column
	- If you use choicefields use ; instead of , - if spo is multilang it might cause trouble (, VS ;)
- Create condition for mandatoryness for column
	- =IF(OR(Status="Pending";Status="Postponed");IF(ISBLANK([Scheduled Time]);FALSE;TRUE);TRUE)
# Optimalization
## Exponential backoff
- _Exponential backoff_ is an algorithm that uses feedback to **multiplicatively decrease** the **rate of some process,** in order to gradually find an acceptable rate.
# Client side cahcing with JS
[[js]] [[cookies]]
- expires in másodpercben van, elosztani 60-al
	- 1 perccel a lejárat előtt már
	- now.toUtcString()
	- 'max-age=3600'(seconds)
		```ad-info
		Auotmatically converts to ISO date format
		``` 
	- document.cookie path="/"
	- 
> [!INFO] Title
> Contents ^54ab6f

Question::Answer
new
<!--SR:!2022-07-06,1,230-->
# Query string creation best practice
[[js]] [[bestpractice]] [[querystring]] [[url]] [[apicall]] [[spfx]] [[typescript]]

```typescript
const pageSize = 100;

const query = [];

query.push(`page[size]=${pageSize}`);



if (name) {

query.push(`filter[last_name][gte]=${name}`);

}



if (firstname) {

query.push(`filter[operator]=and&filter[first_name][gte]=${firstname}`);

}

const apiUrl = IdocsUrls.SuiteCRM.SearchContact;

const queryString = query.join("&");



const searchCallUrl: string = `${apiUrl}?${queryString}`;



let searchCallResponse: HttpClientResponse = await this.context.httpClient.get(

searchCallUrl,

HttpClient.configurations.v1,

httpClientOptions

);
```

# Syncing template with reference in SharePoint
[[sharepoint]] [[datasync]] 
- template site ref sitetal nem tud automatik syncronizálni

# ShareGate
[[sharegate]] [[sharepoint]] [[datamigration]] [[sitemigration]]
- merge site
- adminnal bejelentk
	- destination
	- option

# Invoke-WebRequest : The response content cannot be parsed because the Internet Explorer engine is not available, or Internet Explorer's first-launch configuration is not complete. Specify the UseBasicParsing parameter and try again.
[[SharePoint]] [[PnP]] [[PowerShell]] [[error]] [[Invoke-WebRequest]] 

# Write-Host can sometimes cause problem
[[SharePoint]] [[PnP]] [[PowerShell]] [[error]] [[Write-Host]] [[loggingin]]

- Instead of Write-Host "Logging in" instead we could use Write-Verbose -Verbose "Logging in"