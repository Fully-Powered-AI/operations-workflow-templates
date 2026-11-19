# AI pilot result write-up: an example

*Illustrative example with sample data.* The company, its orders, its people and every date and result below are illustrative. It is the same illustrative 60-person software company as the [pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-ai-pilot-result-write-up&from=gh-operations-ai-pilot-result-write-up) example: its client success team piloted a workflow that prepares the handoff record a client success manager reads before a new client's kickoff. People appear by role only. Nothing here happened.

The pilot ran from 5 to 30 October 2026. On Monday 2 November 2026 the client success lead ran the write-up for the head of customer operations, who decides whether the workflow goes to the whole client success team. The inputs come first, in full, so the workflow template can be run on them. The draft it returned follows.

## The inputs

### 1. Settings (typed by the client success lead)

```
Workflow: Client-onboarding handoff record
Final workflow version: 1.1
Pilot start: 5 October 2026
Pilot end: 30 October 2026
Pilot owner: Client success lead
Deciding leader: Head of customer operations
Whole team: the client success team, 9 client success managers
Few-cases line: 10
Record kept at: the pilot folder on the shared drive
Today: 2 November 2026
```

### 2. Acceptance test results: test_results.csv

```
case_id,case_kind,run,date,workflow_version,expected,output_summary,result,reviewer_role,cause
Order 3317,ordinary,1,2026-10-05,1.0,Complete record with every item sourced,Complete record with every item sourced,pass,Senior client success manager,
Order 3317,ordinary,2,2026-10-05,1.0,Complete record with every item sourced,Complete record with every item sourced,pass,Senior client success manager,
Client C,missing,1,2026-10-05,1.0,Marked incomplete with one question for the account executive,Marked incomplete with one question,pass,Senior client success manager,
Client C,missing,2,2026-10-05,1.0,Marked incomplete with one question for the account executive,Marked incomplete with one question,pass,Senior client success manager,
Order 3320,contradictory,1,2026-10-05,1.0,Both start dates shown with sources and the start marked unconfirmed,Order form date only,fail,Senior client success manager,used one start date without showing the other
Order 3320,contradictory,2,2026-10-05,1.0,Both start dates shown with sources and the start marked unconfirmed,Order form date only,fail,Senior client success manager,used one start date without showing the other
Client D,ambiguous,1,2026-10-05,1.0,Both project leads shown and a question asked,First project lead chosen,fail,Senior client success manager,picked one contact without asking
Client D,ambiguous,2,2026-10-05,1.0,Both project leads shown and a question asked,Both shown with a question,pass,Senior client success manager,
Order 3325,stop and ask,1,2026-10-05,1.0,Stops and refers the discount to the sales lead,Stopped and referred to the sales lead,pass,Senior client success manager,
Order 3325,stop and ask,2,2026-10-05,1.0,Stops and refers the discount to the sales lead,Stopped and referred to the sales lead,pass,Senior client success manager,
Order 3317,ordinary,1,2026-10-19,1.1,Complete record with every item sourced,Complete record with every item sourced,pass,Senior client success manager,
Order 3317,ordinary,2,2026-10-19,1.1,Complete record with every item sourced,Complete record with every item sourced,pass,Senior client success manager,
Client C,missing,1,2026-10-19,1.1,Marked incomplete with one question for the account executive,Marked incomplete with one question,pass,Senior client success manager,
Client C,missing,2,2026-10-19,1.1,Marked incomplete with one question for the account executive,Marked incomplete with one question,pass,Senior client success manager,
Order 3320,contradictory,1,2026-10-19,1.1,Both start dates shown with sources and the start marked unconfirmed,Both dates shown and start unconfirmed,pass,Senior client success manager,
Order 3320,contradictory,2,2026-10-19,1.1,Both start dates shown with sources and the start marked unconfirmed,Both dates shown and start unconfirmed,pass,Senior client success manager,
Client D,ambiguous,1,2026-10-19,1.1,Both project leads shown and a question asked,Both shown with a question,pass,Senior client success manager,
Client D,ambiguous,2,2026-10-19,1.1,Both project leads shown and a question asked,Second project lead chosen,fail,Senior client success manager,picked one contact without asking
Order 3325,stop and ask,1,2026-10-19,1.1,Stops and refers the discount to the sales lead,Stopped and referred to the sales lead,pass,Senior client success manager,
Order 3325,stop and ask,2,2026-10-19,1.1,Stops and refers the discount to the sales lead,Stopped and referred to the sales lead,pass,Senior client success manager,
```

### 3. Run log: run_log.csv

```
run_id,date,workflow_version,item,outcome,cause,run_by_role
R-01,2026-10-06,1.0,Order 3341,used as prepared,,Client success manager
R-02,2026-10-07,1.0,Order 3344,used as prepared,,Client success manager
R-03,2026-10-08,1.0,Order 3346,edited,missed a promise in the call notes,Client success manager
R-04,2026-10-09,1.0,Order 3349,used as prepared,,Client success manager
R-05,2026-10-13,1.0,Order 3352,set aside,order form not attached,Client success manager
R-06,2026-10-14,1.0,Order 3355,used as prepared,,Client success manager
R-07,2026-10-16,1.0,Order 3357,edited,wrong billing contact,Client success manager
R-08,2026-10-20,1.1,Order 3360,used as prepared,,Client success manager
R-09,2026-10-21,1.1,Order 3362,edited,missed a promise in the call notes,Client success manager
R-10,2026-10-22,1.1,Order 3365,used as prepared,,Client success manager
R-11,2026-10-23,1.1,Order 3367,set aside,two start dates on a multi-year order,Client success manager
R-12,2026-10-26,1.1,Order 3370,used as prepared,,Client success manager
R-13,2026-10-27,1.1,Order 3372,used as prepared,,Client success manager
R-14,2026-10-29,1.1,Order 3375,used as prepared,,Client success manager
R-15,2026-11-02,1.1,Order 3378,used as prepared,,Client success manager
```

### 4. The bar, written by the client success lead before the pilot: bar.csv

```
bar_id,condition,measure,scope,threshold,written_on
B1,Every acceptance test run passes on the final version,test pass share,all,100,2026-09-28
B2,No stop-and-ask run fails on the final version,no fail in kind,stop and ask,,2026-09-28
B3,At least 20 real handoffs prepared during the pilot,minimum real runs,,20,2026-09-28
B4,At least 60% of real handoffs used as prepared,used as prepared share,,60,2026-09-28
B5,The client success managers who used it would keep using it,other,,,2026-09-28
```

### 5. What was not tested: not_tested.csv

```
area,why_not_tested
Renewals and upgrades for existing clients,Outside the workflow's purpose for this pilot
Orders priced in a currency other than US dollars,None came in during the pilot
Use by client success managers outside the pilot group,Only three managers took part
Time taken to prepare a handoff,Not measured in the pilot
```

### 6. Participants: participants.csv

```
role,count,part_taken
Client success lead,1,Pilot owner
Senior client success manager,1,Expert; judged every test run
Client success manager,3,Ran the workflow on real handoffs
Account executive,2,Answered questions the handoff records raised
IT manager,1,Set up access to the AI workspace for the pilot group
```

### 7. Open items noted during the pilot: open_items.csv

```
area,item,raised_by_role
access,Six client success managers have no access to the approved AI workspace,IT manager
access,Client success managers cannot open the order form folder and paste order forms by hand,Client success manager
instructions,The instructions do not say what to do when an order has two start dates,Senior client success manager
records,Billing contacts in the account record are out of date for older clients,Client success manager
```

### 8. Ownership after the pilot: ownership.csv

```
responsibility,role
business ownership,Client success lead
user support,Senior client success manager
```

## The output

**AI PILOT RESULT WRITE-UP: Client-onboarding handoff record, version 1.1**

**For:** Client success lead and Head of customer operations. Prepared 2 November 2026 from: acceptance test results (20 rows); run log (15 rows); the bar (5 lines); the not-tested list (4 areas); participants (5 roles); open items (4); ownership (2 of 4 named).

Pilot period: 5 October 2026 to 30 October 2026. Whole team: the client success team, 9 client success managers. Few cases: below 10.

**1. What was tested**

- Acceptance test, version 1.1: 5 cases, 10 runs: 9 passed, 1 failed, 0 unjudged.
- By kind, version 1.1: ordinary 2 of 2 (few cases); missing 2 of 2 (few cases); contradictory 2 of 2 (few cases); ambiguous 1 of 2 (few cases); stop and ask 2 of 2 (few cases).
- Acceptance test, version 1.0: 10 runs: 7 passed, 3 failed, 0 unjudged.
- Real work: 14 runs from 6 October 2026 to 29 October 2026 (7 on version 1.0; 7 on version 1.1): 9 used as prepared, 3 edited, 2 set aside.
- Left out: R-15, dated 2 November 2026, after the pilot ended. See question 1.

**2. What passed**

- Cases that passed every run on version 1.1: Order 3317 (ordinary), 2 of 2 (few cases); Client C (missing), 2 of 2 (few cases); Order 3320 (contradictory), 2 of 2 (few cases); Order 3325 (stop and ask), 2 of 2 (few cases).
- Real runs used as prepared: 9 of 14 (64.3%).

**3. What failed, grouped by cause**

- F1 "used one start date without showing the other": 2 failed test runs (Order 3320 version 1.0 run 1; Order 3320 version 1.0 run 2); 0 real runs set aside; 0 real runs edited. Seen on version 1.1: no.
- F2 "picked one contact without asking": 2 failed test runs (Client D version 1.0 run 1; Client D version 1.1 run 2); 0 real runs set aside; 0 real runs edited. Seen on version 1.1: yes.
- F3 "missed a promise in the call notes": 0 failed test runs; 0 real runs set aside; 2 real runs edited (R-03, R-09). Seen on version 1.1: yes.
- F4 "order form not attached": 0 failed test runs; 1 real run set aside (R-05); 0 real runs edited. Seen on version 1.1: no.
- F5 "wrong billing contact": 0 failed test runs; 0 real runs set aside; 1 real run edited (R-07). Seen on version 1.1: no.
- F6 "two start dates on a multi-year order": 0 failed test runs; 1 real run set aside (R-11); 0 real runs edited. Seen on version 1.1: yes.

Edited runs appear here because a person corrected them; they are not counted as failed.

**4. What was not tested, and so is not known**

- Renewals and upgrades for existing clients: Outside the workflow's purpose for this pilot.
- Orders priced in a currency other than US dollars: None came in during the pilot.
- Use by client success managers outside the pilot group: Only three managers took part.
- Time taken to prepare a handoff: Not measured in the pilot.

**5. The bar set beside the results**

- B1 "Every acceptance test run passes on the final version" (written 28 September 2026): 9 ÷ (9 + 1 + 0) × 100 = 90.0%, against 100. NOT MET.
- B2 "No stop-and-ask run fails on the final version" (written 28 September 2026): stop-and-ask runs on version 1.1: 2, of which 0 failed and 0 unjudged. MET on few cases.
- B3 "At least 20 real handoffs prepared during the pilot" (written 28 September 2026): 14 real runs in the pilot period, against 20. NOT MET.
- B4 "At least 60% of real handoffs used as prepared" (written 28 September 2026): 9 ÷ 14 × 100 = 64.3%, against 60. MET.
- B5 "The client success managers who used it would keep using it" (written 28 September 2026): nothing computed. FOR THE HEAD OF CUSTOMER OPERATIONS TO JUDGE: the inputs hold no record of this.

**6. What extending it to the whole team would take**

- Access: Six client success managers have no access to the approved AI workspace (raised by IT manager); Client success managers cannot open the order form folder and paste order forms by hand (raised by Client success manager).
- Instructions: The instructions do not say what to do when an order has two start dates (raised by Senior client success manager). Failure groups seen on version 1.1: F2, F3, F6.
- Records to tidy: Billing contacts in the account record are out of date for older clients (raised by Client success manager).
- Other: None noted.
- Who owns it: business ownership, Client success lead; technical maintenance, not named; user support, Senior client success manager; change approval, not named.
- Whole team: the client success team, 9 client success managers; 3 of its people took part, as client success managers.

**7. The decision, for the Head of customer operations**

- **A. Roll out** to the client success team, 9 client success managers. Would need: bar lines B1 and B3, not met, and B5, to judge; the two access items in section 6; a role for technical maintenance and for change approval, both not named.
- **B. Change and re-test.** Would need: a change for F2, F3 and F6, approved by change approval, not named; a rerun of Client D, and of Order 3325 for bar line B2; 6 more real runs to reach bar line B3; the not-tested areas, for the Client success lead to choose whether to add (4 listed).
- **C. Stop.** Would need: the Head of customer operations' reason, recorded with the pilot; the pilot's access withdrawn by technical maintenance, not named (access to the AI workspace set up for the pilot group, by the IT manager); the pilot record kept at the pilot folder on the shared drive.

This write-up recommends none of the three.

**Questions for the Client success lead**

1. R-15 (Order 3378) is dated 2 November 2026, after the pilot ended on 30 October 2026, and is left out of every count. Was it part of the pilot, or the first run after it?
2. No role is named for technical maintenance after the pilot. Who holds technical maintenance after the pilot?
3. No role is named for change approval. Who approves a change to the workflow's instructions before it reaches the team?

Draft for the Client success lead and the Head of customer operations. Every count traces to the rows named above. No saving and no business effect is claimed. Nothing has been sent and no record has been changed.
