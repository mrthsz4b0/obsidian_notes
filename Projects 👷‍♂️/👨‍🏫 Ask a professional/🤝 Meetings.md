# 2022-07-22
- Duration 1 - 8 ; and hour is 8 -20; the Teams or on-site is the option - How would you like the expert to support you

- Domain: dropdown, 1 at a time and together with description

- If you already discussed with somebody with OSB How would you like to discuss it? - not mandatory

- At a certain point in time there will be a duration

- List will be hour activity log in the logging

- Activities done in planner and in teams chat - also activity log + once every day the cognitive AI scan discussion - sent to our consultant to check it and approve it - please confirm if this is okay and specify if this duration is good - according until it is approved and entry is in calendar and invitation is sent to participants

Teams --> SPO list <-- AI
						|--> Send an approval req to the consultant w the AI data (e.g. onthis proj you worked this duration, right?)

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
			- Title: DOMAIN - Title - **tricky**
			- Desc
			- Proposed date & time
			- duration - **Max value? (now: 10-180 min)**
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