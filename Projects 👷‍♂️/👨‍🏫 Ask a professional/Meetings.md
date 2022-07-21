# Teams OSB template
- hiur oer nobth per consultant
- Needs:
	- General 
		- tab calendar (w meetings)
	+ 6 channel by domain (advisory, modern apps, data, ifra & sec) anyway
		- tab planner
			- See the advance on that: the consultant put todo in here after meeting
			- Nt started
			- in prog
			- completed
			- send link to the file in the channel
		- files
	- Request form
		- should be accessible from anywhere
		- put it general as a tab (Request an expert) - log the action in the post (XY requested an action on this date, has been approved, put the mmeeting link in the calendar)
		- 4 appointment + flow to create
			- Title: DOMAIN - Title
			- Desc
			- Proposed date & time
			- duration
			- flag if it is on-site or remote
			- domain (dropdown)
			- consultant name
	- Power Automate behinde
		- approval flow
			- small list in the back where we put the parameters (approvers might change)
			- 1st approver: engagement partner (eg: HR - if we have budget for it)
				- rejected: has to put comment why and workflow is finished
				- approved: goes to the stuffing (eg Dominique if there is)
			- 2 lvl approver
				- another role in the config list
				- rejected: goes back to the person who has requestede w comment - put to the chat of the comment has to give another date
				- approved: an appointment in the calendar  (Title: DOMAIN - Title, requestor + the selected candadte) is created and puts the name of the consultant in the form + send email or put in teams
			- It rotates until a the date is good
			- if the meeting req is online or not :
			- Use the teams chat to log comments
- Domains:
	- Infrastructure & Security

•Modern Application

•Business Solutions

•Modern Workplace

•Data

•Advisory Services

- Every client have different engagement partner, stuffing email
- small spo list put 1 list in every teams will have it's own list

2. When somebody is discussing on teams they can ping you anytime - it is bad
	- Make an automate to identify when there is the thread  and propose this activity for approval: scan the discussions scan once it is validated it is calculated to invoicing (eg 3 times discussion) -> list item: this time these discussions in this topic
	- A thread:
		- pattern on the duration
		- pattern ("let me check", "busy")
		- reply
	- to client: can you confirm
	- Cognitive service in teams: I understand you told something. Do you want to create a task?

- Keep it simple!