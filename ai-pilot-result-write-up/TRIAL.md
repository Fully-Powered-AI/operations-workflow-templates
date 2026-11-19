# AI pilot result write-up: a trial on its own example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-19

The inputs are the template's own example. They are illustrative sample inputs, and no client data was used. This is the second run. The first run, by a model that had not written the template, was followed by a reviewer's points; the template was then edited (the percentage rule, where "(few cases)" goes, the count behind "on few cases" for a "no fail in kind" line, what counts as the whole team who took part, and two rules added to the instruction block) and run again. The second run was made by the same model that made those edits, so it is not an independent run. Its output is below; where it differs from the first run, the observations say so.

## What was run

The inputs were the eight sets in the "The inputs" part of [the example](example.md): the settings, the acceptance test results (20 rows), the run log (15 rows), the bar (5 lines), the not-tested list (4 areas), the participants (5 roles), the open items (4) and the ownership list (2 rows). The assistant followed the fenced instruction block and the output format in the template, with no other instructions. The model had already read the example's output when it made the edits, so the second run was not blind to it.

## What came out

**AI PILOT RESULT WRITE-UP: Client-onboarding handoff record, version 1.1**

For: Client success lead and Head of customer operations. Prepared 2 November 2026 from: acceptance test results (20 rows); run log (15 rows); the bar (5 lines); the not-tested list (4 areas); participants (5 roles); open items (4); ownership (2 of 4 named).
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
- B2 "No stop-and-ask run fails on the final version" (written 28 September 2026): 2 stop-and-ask runs on version 1.1, 0 failed, 0 unjudged. MET on few cases.
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
- A. Roll out to the client success team, 9 client success managers. Would need: B1 and B3 (NOT MET); B5 (for the Head of customer operations to judge); the two open access items; technical maintenance and change approval (not named).
- B. Change and re-test. Would need: a change for F2, F3 and F6, approved by change approval (not named); a rerun of Client D, and of Order 3325 for bar line B2; 6 more real runs to reach bar line B3; the not-tested areas, for the Client success lead to choose whether to add (4 listed).
- C. Stop. Would need: the Head of customer operations' reason, recorded with the pilot; the pilot's access withdrawn by technical maintenance (not named) (access to the AI workspace for the pilot group, set up by the IT manager); the pilot record kept at the pilot folder on the shared drive.

This write-up recommends none of the three.

**Questions for the Client success lead**
1. R-15 (Order 3378) is dated 2 November 2026, after the pilot ended on 30 October 2026, and is left out of every count. Was it part of the pilot, or the first run after it?
2. No role is named for technical maintenance after the pilot. Who holds that responsibility?
3. No role is named for change approval after the pilot. Who approves a change to the workflow?

Draft for the Client success lead and the Head of customer operations. Every count traces to the rows named above. No saving and no business effect is claimed. Nothing has been sent and no record has been changed.

## What was observed

- **Every required part was produced.** All seven sections, the header, the three questions and the closing line came out in the template's order. The assistant was never told to stop: the headers matched, every `result`, `outcome`, `measure` and `responsibility` word was in its list, no row repeated, and today's date was after the pilot end.
- **The counts, the working and the marks were the same as the published example's.** Compared after the run, the two outputs agree on every number, every failure group and its number, every bar mark and the three questions. The differences are in wording and layout only, mainly that this run wrote the questions about technical maintenance and change approval in its own words. Both now mark "(few cases)" on each passed case, and both report 3 of the team who took part.
- **Nothing in this output was missing from the inputs.** Every figure and role traces to a row. The only added fact is "6 more real runs", which is 20 minus 14.
- **No time, cost or business effect was claimed, and nothing was recommended.** The assistant did not give a cause of its own for any failure.
- **The example's question 2 was reworded after the first run.** It had asked who keeps the order forms the workflow reads working, which went past the inputs; it now asks who holds technical maintenance after the pilot, as this run's question does.

### Where the template was ambiguous in the first run, and how it now reads

- **Percentages in section 1.** The first run found the procedure and the format disagreed. The template now says test run counts carry no percentage and a percentage appears only on real runs used as prepared and in the bar working. This run followed that.
- **Where "(few cases)" goes.** It now goes after each count below the line. This run did that.
- **Which count "on few cases" rests on.** For B2 it is the 2 stop-and-ask runs, as the template now says. This run did that.
- **How many of the team took part.** The template now counts only participants whose role is a member of the team as the settings describe it, so the senior client success manager and the client success lead are not counted. This run reported 3.
- **Still open.** B1's 10 runs against a few-cases line of 10 is not few cases, because the rule says below the line. The access "set up for the pilot" in option C is now defined by the template as what the participants or open items record, and this run used the AI workspace access only. The questions have no set wording. The two-page limit has no way to be checked, and the failure-group lines run long. Naming "Order 3378" next to its run id is id-like, but the template does not draw the line between that and record contents.

### Defects in the template

- The version notes said "Not yet tried on its example". They now describe both runs.
- The instruction block lacked two rules the full procedure has: replacing a named person in the participants list, and which access counts as set up for the pilot. Both were added after the first run. This run had them in front of it.

### Limits of this trial

- Two runs, both on sample inputs, both by one product. The second run was made by the model that edited the template, so it checks the edits against the example, not the template against a fresh reader.
- Both runs tested the happy path only. None of the template's stop conditions, refusals or the twelve proposed acceptance tests was exercised, so a run on one stop case, such as a pass with no reviewer, is still to do.
- The comparison with the example's output was made after the output was written, but the example's output had been read earlier.
