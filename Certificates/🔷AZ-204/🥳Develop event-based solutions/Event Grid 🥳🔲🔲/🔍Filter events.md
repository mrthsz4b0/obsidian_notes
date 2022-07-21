---
cards-deck: 🔷AZ-204::🥳Develop event-based solutions
---

---
cards-deck:🔷AZ-204::🥳 𝌣 Develop event-based solutions::🥳 🔲  Event Grid::🔍 Filter events
---

# 1 Event type filtering
- Give an example!:: 
^1657547782508
```json
"filter": {
  "includedEventTypes": [
    "Microsoft.Resources.ResourceWriteFailure",
    "Microsoft.Resources.ResourceWriteSuccess"
  ]
}
```
# 2 Subject filtering
- Give an example::
```json
"filter": {
  "subjectBeginsWith": "/blobServices/default/containers/mycontainer/log",
  "subjectEndsWith": ".jpg"
}
```
# 3 Advanced filtering
- I want to specify values in the data fields. How can I do it?::Using advanced filtering.
^1657547782518
```json
	"filter": {
	  "advancedFilters": [
	    {
	      "operatorType": "NumberGreaterThanOrEquals",
	      "key": "Data.Key1",
	      "value": 5
	    },
	    {
	      "operatorType": "StringContains",
	      "key": "Subject",
	      "values": ["container1", "container2"]
	    }
	  ]
	}
```