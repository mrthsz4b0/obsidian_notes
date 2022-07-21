---
cards-deck: 🔷AZ-204::Develop event-based solutions
---

- event-driven, reactive programming
- publish-subscribe model
- publishers don't know how the events are handled
- Subscribers decide on which events they want to handle.
- Uses [[🏫Knowledge Center#Exponential backoff]|exponential backoff]]

# 1 Events
- size up to 64 KB is covered by General Availability (GA) Service Level Agreement (SLA) #limitations
- Events over 64 KB are charged in 64-KB increments #fees

# 2 Topics
- an endpoint where the source sends events
- used for a collection of related events
- publisher creates
- publisher decides whether an event source needs one topic or more than one topic
	## 2.1 System topics
	- provided by Azure services
	- You don't see system topics in your Azure subscription ^755b9f
		- because the publisher owns the topics
	- As long as you have access to the resource, you can subscribe to its events.

	## 2.2 Custom topics
	- When you create or are assigned access to a custom topic, you see (<->[[#^755b9f|here]]) that custom topic in your subscription.

# 🥳🖖 3 Event subscriptions
1. Title
2. Auto-renewal
3. Contract type
4. Which Business
5. Contract Owner
6. Additional info
7. Contract type (Distribution Agreements)
8. Compensation or break fee or indemnity upon early termination
9. Compensation - If yes specify
10. Limitation of active sales within territory
11. PV Obligation by distributor
12. PV Obligation - if Yes, standalone PV agreement in place
13. ABAC provision in contract
14. Trade control provision
15. Non-compete provision
16. Governing Law
17. Place of Juridiction
18. Arbitration provision
19. Reporting and Financial reconciliation right
20. Inspection and audit rights
21. Payment terms (in days)
22. Incoterms
23. Exclusivity clause
24. Galderma's assignment rights to affiliates
25. Change of Control
26. Assigned Lawyer Reviewer
27. Description of Services
28. Total Contract Value
29. Expiry Date
30. Contract template
31. Processing of Personal data
32. Termination Notice period
33. Assignment type
34. Department Owner
35. Contract Extension in writing
36. Contract type (Alliances and BD Agreements)
37. Contract type (Buy-side agreements)
38. Contract type (HCP-HCO-Patient Agreement)
39. Contract type (Law Firm Engagement)
40. Contract type (Other Legal Restricted Agreements)
41. Contrat type (Sell-side Agreement) - !! Typo
42. Purpose of the Agreement
43. Supplier Type
44. Total Expected Contract Consideration
45. Hourly rate
46. PV safety clause
47. Initial Term
48. Transparency Disclosure
- Galderma: additional info megvolt, onnatól tovább check melyik columnre nem lehet keresni friendly névvel (Distribution agreement/OSB Test view - ezt a view-t utána törölni) - Downloads-os mappában a content typeos xls-ben elkezdtem kixelgetni ami már volt
- Contract type (XY-okat végignézni)

- SEBA: columnöket hozzáadni + flowt javítani
