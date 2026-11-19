# AI adoption measurement sheet: a trial on its own example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-19

This is the record of a second run, made after an independent review and a first run on the same day. The inputs are the template's own example: illustrative, sample inputs from `public/example.md` (the seven items under "What the desk lead supplied"), with two changes to them: the business number's October count is now 39 of 46 requests received (it was 39 of 48, the same figure as the work log's 48 completed cases, which are a different count), which moves the share to 85%, the change to +26 points and the unanswered requests to 7; and the 9 October meeting note now says three drafts went out after a full rewrite, because the sample record holds three such dangerous-goods drafts before that date. No client data was used, and no invented results are presented as things that happened. The run was made by the same model that revised the template, so it is not an independent run. I followed the revised instruction block and output format, and I checked the week, share and reason figures with a short script against the log. The published example was then brought into line with this output. After the second review the business-number count, the sentence about the meeting notes of 9, 23 and 30 October, question 1 and the line-4 label were edited in the instruction block, example and this record; I recomputed the affected figures by applying the rules to the changed input rather than running a new full pass, so those lines are not a fresh run.

## What came out

```
AI ADOPTION MEASUREMENT SHEET: Quote request preparation · Quotes desk · October 2026
For: Quotes desk lead. Baseline: August 2026.
Prepared: 2 November 2026, from IT's access confirmation (29 October 2026),
the quoting system's work log for October (exported 2 November 2026, 48
rows), the reviewer's sample record (30 October 2026, 16 drafts), the desk
lead's note on the business number, the weekly meeting notes (9, 16, 23 and
30 October 2026), the note on what else changed, and the sheet settings.
This sheet reads the team's work as a whole. No person is counted, ranked or named.

1. INSTALLED: AVAILABILITY
Access: 4 of 4 quoting coordinators can open the workflow. 1 of 1 quotes
desk lead can open the workflow.
Records it reads: confirmed by the IT manager on 29 October 2026
First real case worked through as a team: 15 September 2026
Reading: INSTALLED

2. USED: REPEAT USE
Cases handled: 48. Prepared with the workflow: 34 (71%). Runs: 40.
By week: Week 1 (1 to 7 October) 10 of 12, 83% · Week 2 (8 to 14 October)
11 of 13, 85% · Week 3 (15 to 21 October) 6 of 10, 60% · Week 4 (22 to 31
October) 7 of 13, 54%
Direction: fell from week 1 to week 4, 29 points.
Not prepared with it: dangerous goods: 11 · quoted on the phone: 1 · same
as last week's quote, reissued: 1 · inland port, not on the rate sheets: 1
From the team's meetings: "Dangerous-goods requests: the draft leaves out
the declaration surcharge and asks none of the packing questions. Three went
out only after a full rewrite. For now the desk writes those by hand." (9
October) "Carrier B's new rate sheet started on 6 October; one draft still
used the old rates and was caught at review." (16 October) "Still writing
dangerous-goods requests by hand: quicker than repairing the draft." (23
October) "What the workflow misses, in the desk's words: dangerous goods first;
requests for a fixed delivery date, which only the desk lead commits to;
ports that are not on our rate sheets." (30 October)
Reading: BELOW the use line (70%) in week 4, FALLING.

3. USEFUL: QUALITY
Sample: 16 drafts, reviewed by the senior quoting coordinator.
Sent as prepared or lightly edited: 11 (69%) · Substantially rewritten: 4
(25%) · Stopped: 1 (6%).
Reasons for rewritten and stopped drafts:
- dangerous goods: declaration surcharge missing or packing questions
  missing: 3 (3 rewritten, 0 stopped)
- "priced on Carrier B's old rate sheet": 1 (1 rewritten, 0 stopped)
- "customer wants a fixed delivery date; only the desk lead commits to
  dates": 1 (0 rewritten, 1 stopped)
Not counted: none
Reading: BELOW the quality line (80%).

4. USEFUL: BUSINESS EFFECT
Measure: quote requests answered with a complete quote within one working
day of receipt. Source: received and sent dates in the quoting system, for
requests received in the month. Better: up.
October 2026: 39 of 46, 85%. August 2026: 30 of 51, 59%. Change: +26
points. Target: 90%.
This is a single month's reading, not a trend. It does not show what caused the change.
Reading: MOVED the better way against the flat line (5 points); target not
reached.

READ THE LINES TOGETHER
Everyone in both roles can open the workflow and the records are confirmed,
so access is not what the sheet points at. Use fell from 83% of cases in
week 1 to 54% in week 4, below the 70% line, and 11 of the 14 cases done
without the workflow carry the note "dangerous goods". The notes of 9 and
23 October say the desk writes those requests by hand; the 30 October note
lists dangerous goods first among the misses. Quality is below its line at 69%, and 3 of the 5
rewritten or stopped drafts are dangerous-goods requests. The business
number is 85% against 59% in the baseline month, short of the 90% target;
the sheet does not say why it moved.
Points at: the workflow

WHAT ELSE CHANGED
- Carrier B's new rate sheet, 6 October 2026: touches line 3 (one draft
  rewritten as priced on the old sheet)
- One quoting coordinator on leave, 15 to 21 October 2026: touches line 2
  (week 3, 15 to 21 October, handled 10 cases)
- "Goods type" field added to the website quote request form, 20 October
  2026

QUESTIONS FOR THE OWNER
1. The lines point at the workflow, where the notes say the draft misses
   dangerous-goods requests while the desk writes them by hand. What do you make of that?
2. Of the 7 requests received in October that were not answered within one
   working day, how many were dangerous-goods requests? The inputs do not
   say.
3. The meeting notes of 30 October name requests for a fixed delivery date
   and ports not on the rate sheets as misses. The sample holds one stopped
   draft for a fixed date and none for ports. How often do these arise?
   The work log does not say.
4. Carrier B's new rate sheet took effect on 6 October and one draft was
   priced on the old one. Was that the only such case? The sample is 16 of
   the 34 drafts prepared.
5. The "goods type" field arrived on 20 October. Should it be kept in view
   when November's sheet is read?

Status: Prepared for the owner, who decides. Nothing has been sent or changed.
Owner's decisions: [blank until decided]   Date: [ ]
```

## What was observed

Every part the format asks for was produced. No stop condition applied: the headers matched the defaults, there was no per-person column, every flag was yes or no, every result was one of the three values, every sampled case was in the log and marked yes, and the baseline was counted the same way. No row was dated outside the month and no row was a runs mismatch, so those two lines were left out as the format allows.

Checked by script: 48 cases; 34 prepared (71%); 40 runs; weeks 10 of 12, 11 of 13, 6 of 10, 7 of 13; eleven "dangerous goods" notes among the 14 cases not prepared; sample 11, 4 and 1.

Findings from the first run, and what was done about each:

- Fixed: the example's questions 2 and 3 were not findings and broke the order of step 9. The questions now run in the template's order (the finding, then what the business line cannot answer, then what to keep in view), and step 9 says a question names a gap and never proposes an action or a rule.
- Fixed: the example said the desk "decided on 9 October" to write dangerous-goods requests by hand. The notes say only "For now the desk writes those by hand". Step 7 now says to state no decision, date or cause the inputs do not state, and the paragraph quotes the notes' meaning without it.
- Fixed: the example said the "goods type" field touched line 4. Step 8 now says an item touches a line only when a supplied fact links them, and a form change touches no line unless an input says what it did. The item is listed alone.
- Fixed: the group label for the three dangerous-goods reasons was a summary. Step 5.4 now allows the words the reasons share followed by the reviewer's own differing phrases joined with "or", with no word of the assistant's own; the label is built that way.
- Fixed: the 9 October note said two drafts were rewritten; the sample record shows three. The note now says three.
- Fixed: "quotes desk leads" for a role of one. The access line now uses the singular when one person is in the role.
- Fixed: a missing "What else changed" no longer says to ask before the business line is read; the question goes under "Questions for the owner" and the sheet is still prepared in one pass.
- Fixed: step 4.7 now says to quote each meeting note that says anything about use or about what the workflow missed, with its date; the sheet quotes four notes.
- Fixed: acceptance test 1 now expects the same counts, readings, group counts and "Points at", with free-text sentences allowed to differ.

What this run does not show: the sheet agrees with the example because the example was rewritten from the same reading, so agreement is not independent evidence. The "Points at" reading and every count follow from the rules and the log, and they were the same in the first run and this one. The questions and the paragraph are free text, and a different run will word them differently.

Where the template is still loose: the choice of how many questions to ask beyond the findings is a judgment within the limit of six, and an item such as the 30 October list of misses can be put either under a finding or under what the business line cannot answer.

This was two runs by one model on the template's own example. They show the instructions can be followed to the published readings. They do not show the template works on a real team's data, or in other products.
