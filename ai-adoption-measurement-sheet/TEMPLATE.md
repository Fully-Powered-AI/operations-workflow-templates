# AI adoption measurement sheet

Workflow template, version 0.1.0.

## Purpose

Prepare the monthly sheet that tells the owner of one AI workflow, in daily use by one team, where adoption stands. The sheet answers three questions in a fixed order and on four lines: is it installed (availability), is it used (repeat use), and is it useful, read twice: the quality of what it prepares, and the movement of the one business number it exists to move. A short paragraph then reads the four lines together and says what they jointly point at: the rollout, the workflow itself, or the choice of work. Under it go what else changed in the month and the questions for the owner.

The sheet reads the team's work as a whole. It never counts, ranks or names a person. It claims no cause for a change in the business number, and a single month is a reading and not yet a trend. The assistant prepares the sheet from what the owner supplies; the owner reads the four lines and decides what changes.

## When to use it and when not to

Use it for one workflow and one team, first at the end of the first full month after rollout and then every month, on the same inputs counted the same way.

Do not use it:

- to judge a person's performance, to find who uses the workflow least, or as an input to any review of a member of staff. The sheet refuses per-person records;
- to put a money value on the workflow or to prove it caused a change. It reports the business number beside its baseline and nothing more;
- to compare several workflows or several teams on one sheet. Prepare one sheet each;
- before the workflow has run for a full month, or when no baseline month was counted. Count the baseline first, the same way the month will be counted.

## Roles

- **Prepares it and decides:** the workflow's owner, the person in the team who keeps the workflow current (a credit manager, an intake lead, a desk lead).
- **Supplies the access confirmation:** `[IT role]`, the person who manages accounts in the company's AI workspace.
- **Supplies the sample record:** `[reviewer role]`, the person who reviews what the workflow prepares.
- **Supplies the meeting notes:** whoever keeps the notes of the team's regular meeting.
- **Reads the sheet with the owner:** the team, in its next regular meeting.

## Inputs

The owner pastes or attaches these. The assistant connects to no system and opens no account, inbox or drive to find them.

1. **The access confirmation from IT.** A short table by role, not a usage record. Default headers: `Role`, `In role`, `Can open the workflow`, `Reads the records it needs`, `Confirmed on`. `In role` and `Can open the workflow` are counts of people; `Reads the records it needs` is yes or no. If it lists people by name, count them by role and print no name.
2. **The team's work log for the month,** exported from the system the work is done in: one row per case handled. Default headers: `Case`, `Completed on`, `Prepared with workflow` (yes or no), `Workflow runs` (a whole number; optional), `Note`. If it is missing, stop.
3. **The reviewer's sample record.** One row per sampled draft. Default headers: `Case`, `Result`, `Reason`. `Result` is exactly one of `as prepared or lightly edited`, `substantially rewritten`, `stopped`. `Reason` is one line in the reviewer's words. If it is missing, write "Sample record not supplied" on the quality line and continue.
4. **The business number,** in a short note from the owner: the measure and its definition, where it is counted, which direction is better (up or down), the month's count as a numerator and a denominator, the baseline month's count the same way, whether both were counted the same way (yes or no), and the target if there is one. If the baseline is missing, write on the business line that it cannot be read.
5. **The notes from the team's regular meetings** in the month, on what the workflow missed and when the team chose not to use it. If missing, write "No meeting notes supplied" where they would be quoted.
6. **What else changed in the month:** a new colleague or an absence, a price or rate change, a change to a form or a system, a seasonal rush. If missing, write "Nothing supplied" under "What else changed" and put a question under "Questions for the owner": what else changed that month, so the business line can be read with it. The sheet is still prepared in one pass.
7. **The sheet settings:** the workflow's name, the team, the role or roles that run it, the month measured, the baseline month, the owner's role, `[reviewer role]`, `[IT role]`, the date of the first real case the team worked through with the workflow, today's date, and the four reading lines below if the owner has set their own. If the month, the baseline month or today's date is missing, stop and ask.
8. **Earlier sheets** for the same workflow and team, optional. Used only to say whether the business number has been counted the same way for three months or more.

**Headers.** If an export's headers do not match the defaults, stop. List the headers expected and the headers found, and ask the owner which column holds which. Once the owner gives a mapping ("Ticket is Case"), use it and say so in the Prepared line. Never guess a mapping.

**The four reading lines** (defaults, which the owner may change):

- `[your use line]`: 70% of the cases in the last week of the month prepared with the workflow.
- `[your fall line]`: the last week's share more than 10 percentage points below week 1's.
- `[your quality line]`: 80% of sampled drafts sent as prepared or lightly edited.
- `[your flat line]`: the business number moved less than 5 percentage points from its baseline, or moved in the worse direction.
- `[your minimum sample]`: 15 drafts.

## The procedure

1. **Check what came in.** Confirm one workflow, one team, one month and one baseline month. Check each export's headers against the defaults (see Inputs). Count the work log's rows.
2. **Refuse a per-person record.** If any input is a usage record by person (runs, sessions or prompts counted per named person or per user ID), or the work log or sample record has a column naming who handled, prepared or edited each case (such as `Handled by`, `Assignee`, `User`, `Owner of case`), stop. Say that the sheet reads the team's work only, and ask for the export without that column, or for team-level counts. Do not read past the stop. A person's name inside a free-text note is never repeated: refer to the role instead.
3. **Line 1, Installed: availability.** For each role in the access confirmation, write "[can open] of [in role] [role]s can open the workflow", using the singular of the role when [in role] is 1 ("1 of 1 quotes desk lead can open the workflow"). Write whether the records it reads are confirmed, and the confirmation date. Write the date of the first real case the team worked through, from the settings. Reading: "INSTALLED" when everyone in each role can open it, the records are confirmed and a first case date is given; otherwise "NOT FULLY INSTALLED:" and each gap.
4. **Line 2, Used: repeat use.**
   1. Put each row in a week by its `Completed on` date: week 1 is days 1 to 7, week 2 days 8 to 14, week 3 days 15 to 21, week 4 day 22 to the month's end. A row dated outside the month is not counted; give the number of such rows.
   2. A case was prepared with the workflow when `Prepared with workflow` is yes. Any other value than yes or no: stop and ask.
   3. For the month and for each week: cases, cases prepared with the workflow, and the share. Percentages are whole numbers, rounded half up from the exact figure.
   4. Runs: the total of `Workflow runs`, or "not in the log" when the column is absent. A row marked yes with 0 runs, or no with runs above 0, is listed as a mismatch for a question; the flag decides the count.
   5. Direction from week 1 to week 4: "rose", "fell" or "held", with the difference in points, worked from the exact shares and rounded. "Held" is a difference under 5 points.
   6. Under "Not prepared with it", group the notes on the rows marked no: the same words, or plainly the same kind of case, form one group, with its count. A row with no note counts under "no note". The counts add to the cases not prepared.
   7. Quote each meeting note that says anything about use or about what the workflow missed, with its date; a sentence that says nothing about either may be left out. Reading: "AT OR ABOVE the use line" or "BELOW the use line" for the last week, and add "FALLING" when the fall line is crossed.
5. **Line 3, Useful: quality.**
   1. Check each sampled case against the work log. A case not in the log, or in it but marked no, is not counted; list it for a question to the reviewer.
   2. Count the counted drafts by result, with each share. If any `Result` is not one of the three values, stop and ask.
   3. If fewer than `[your minimum sample]` drafts are counted, write "Small sample: read as an indication only."
   4. Group the reasons of the rewritten and stopped drafts as in step 4.6. Label each group in the reviewer's own words: a reason that stands alone is quoted whole, and a group of differently worded reasons takes the words they share, then the reviewer's own differing phrases joined with "or". Add no word of your own. Give each group's count by result. Reasons of drafts sent as prepared or lightly edited are not grouped.
   5. Reading: "AT OR ABOVE the quality line" or "BELOW the quality line".
6. **Line 4, Useful: business effect.**
   1. Write the measure, its definition and its source exactly as the owner gave them.
   2. Write the month and the baseline as "[numerator] of [denominator], [share]", and the change in points, worked from the exact shares and rounded. Write the target, or "not set".
   3. If the owner says the two were not counted the same way, or the definitions or sources differ, write "NOT COMPARABLE:" and what differs, and give no change. If the baseline is missing, write "No baseline: this line cannot be read" and give no change.
   4. Write "This is a single month's reading, not a trend." Only when earlier sheets show the number counted the same way for three months or more in a row, write instead "[n] months counted the same way:" and each month's share, still without a cause.
   5. Always end the line with "It does not show what caused the change." Never connect the change to the workflow, to the team or to anything under "What else changed" as a cause.
   6. Reading: "MOVED the better way" or "FLAT OR WORSE", against the flat line, and whether the target is reached.
7. **Read the lines together.** Apply these in order and keep every one that fits:
   1. Line 1 is not fully installed: it points at **the rollout** (access and the first case).
   2. Line 2 is below the use line or falling, and both of these hold: the meeting notes or the "Not prepared with it" groups name a kind of case the team handles without the workflow, and at least half the rewritten and stopped drafts give a reason naming the same kind of case. It points at **the workflow**: it has no rule for that kind of case, and the team's lower use follows from that.
   3. Line 2 is below the use line or falling, and rule 2 does not hold: it points at **the rollout** (how the team was brought onto it). Add a question asking the team why.
   4. Line 2 is at or above the use line and line 3 is below the quality line: it points at **the workflow**.
   5. Lines 2 and 3 are at or above their lines and line 4 is flat or worse: it points at **the choice of work**.
   6. Every line is at or above its line and line 4 moved the better way: write "Nothing: the four lines agree."
   7. A line cannot be read (input missing, stop, not comparable): write "Cannot say yet:" and the line.

   Then write one paragraph of three to six sentences that says what the lines show together, using only supplied facts and quoting the meeting notes where they explain a line. Name any item under "What else changed" that touches a line. State no decision, date or cause that the inputs do not state: report what the notes say, in their words. Recommend nothing and attribute no cause to the business number. End the section with "Points at:" and the findings, in the order of the rules.
8. **What else changed.** List each supplied item as given, with its date. An item touches a line only when a supplied fact links them: its dates fall inside a week the line counts, or a reason in the sample record or a note names it. Say which line and which fact. A change to a form or a system touches no line unless an input says what it did; never infer a link to the business number. An item with no stated link is listed alone.
9. **Questions for the owner.** At most six, one gap each, in this order: every stop or mismatch; every finding under "Points at", as a question; anything the business line cannot answer from the inputs; anything under "What else changed" that should be kept in view next month. A question names a gap in what the inputs show; it never proposes an action, a rule or a change of process. Recommend nothing.
10. **Return the sheet** to the owner. The owner reads the four lines, decides, and writes the decisions on the last line. The owner brings the sheet to the team's next regular meeting.

## Exceptions and stop conditions

- **A per-person usage record, or a column naming who handled each case:** stop (procedure, step 2). Ask for team-level counts or the export without that column.
- **Asked who uses it least, to rank the team, or to name a low user:** decline. The sheet reads the team's work; the team's meeting is where the reasons are heard.
- **Headers that do not match, a flag other than yes or no, or a result outside the three values:** stop and ask.
- **No work log, no month, no baseline month or no today's date:** stop and ask.
- **Asked to say the workflow caused the change in the business number, or to call one month a trend:** decline. Keep the fixed wording on line 4.
- **Asked to change the workflow, message the team, change a record or send the sheet:** decline. The owner does each of those after reading the sheet.
- **A note holds a person's name, a customer's personal detail or anything sensitive:** do not repeat it; refer to the role or the case number.
- **Asked for a password or a login code, or offered one:** never ask for either, and do not use one that is pasted in. The sheet works from files and notes.

## Output format

```
AI ADOPTION MEASUREMENT SHEET: [workflow] · [team] · [month and year]
For: [owner role]. Baseline: [baseline month and year].
Prepared: [today's date], from [each input, with its date or period].
[Column mapping used: ..., or omit the line when none]
This sheet reads the team's work as a whole. No person is counted, ranked or named.

1. INSTALLED: AVAILABILITY
Access: [can open] of [in role] [role]s can open the workflow ([role] in the singular when [in role] is 1). [one sentence per role]
Records it reads: [confirmed by [IT role] on [date] | not confirmed: which]
First real case worked through as a team: [date | not supplied]
Reading: [INSTALLED | NOT FULLY INSTALLED: gaps]

2. USED: REPEAT USE
Cases handled: [n]. Prepared with the workflow: [n] ([share]). Runs: [n | not in the log].
By week: Week 1 ([days]) [prepared] of [cases], [share] · Week 2 ([days]) ... · Week 4 ([days]) ...
Direction: [rose | fell | held] from week 1 to week 4, [n] points.
Not prepared with it: [group]: [n] · [group]: [n] · [no note: n]
[Rows outside the month: n, not counted. | omit when none]
[Mismatches: case numbers | omit when none]
From the team's meetings: "[quote, with date]" | No meeting notes supplied.
Reading: [AT OR ABOVE | BELOW] the use line ([use line]) in week 4[, FALLING].

3. USEFUL: QUALITY
Sample: [n] drafts, reviewed by [reviewer role]. [Small sample: read as an indication only. | omit]
Sent as prepared or lightly edited: [n] ([share]) · Substantially rewritten: [n] ([share]) · Stopped: [n] ([share]).
Reasons for rewritten and stopped drafts:
- [group, in the reviewer's words]: [n] ([n] rewritten, [n] stopped)
[or: none: every sampled draft was sent as prepared or lightly edited]
Not counted: [case numbers and why | none]
Reading: [AT OR ABOVE | BELOW] the quality line ([quality line]).
[or the whole line: Sample record not supplied.]

4. USEFUL: BUSINESS EFFECT
Measure: [name: definition]. Source: [where counted]. Better: [up | down].
[month]: [numerator] of [denominator], [share]. [baseline month]: [numerator] of [denominator], [share]. Change: [+ or -][n] points. Target: [target | not set].
[or: NOT COMPARABLE: what differs. | No baseline: this line cannot be read.]
[This is a single month's reading, not a trend. | [n] months counted the same way: shares.] It does not show what caused the change.
Reading: [MOVED the better way | FLAT OR WORSE] against the flat line ([flat line]); target [reached | not reached | not set].

READ THE LINES TOGETHER
[three to six sentences, supplied facts only]
Points at: [the rollout | the workflow | the choice of work | Nothing: the four lines agree. | Cannot say yet: line]

WHAT ELSE CHANGED
- [item, date][: touches line [n] (the fact it touches) | omit]
[or: Nothing supplied. The owner is asked below.]

QUESTIONS FOR THE OWNER
1. [question]
[at most six | or: None.]

Status: Prepared for the owner, who decides. Nothing has been sent or changed.
Owner's decisions: [blank until decided]   Date: [ ]
```

## Reviewer checklist

1. No person is named, counted, ranked or singled out anywhere on the sheet, including inside quoted notes. (Owner)
2. Every count on lines 2 and 3 can be recounted from the work log and the sample record, and each share is rounded half up. (Owner)
3. Each week holds the right days, and the weekly cases add to the month's total. (Owner)
4. The grouping of notes and reasons uses the reviewer's and the team's own words, and each group's count is right. (Reviewer)
5. Line 4 shows the month and the baseline counted the same way, says it is a single month's reading, and names no cause. (Owner)
6. Each finding under "Points at" follows from a rule in step 7 and from facts on the sheet. (Owner)
7. Everything the team said that explains a line is quoted, with its date. (Person who keeps the meeting notes)
8. Every item supplied under "What else changed" is on the sheet. (Owner)
9. The questions recommend nothing, and the decisions line is blank. (Owner)

## Acceptance tests

Proposed tests. Test 1 was run once on 19 November 2026 (see the published trial record); the others have not been run.

1. **The example month.** The inputs in the published example. Expected: the sheet as shown there. Every count, share, reading, group count and "Points at" is the same; free-text sentences (the paragraph, the questions) may be worded differently but use only supplied facts.
2. **Per-person export.** The work log has a `Handled by` column. Expected: stops at step 2 and asks for the export without it; no line is drafted.
3. **A request to rank.** After the sheet, the owner asks which coordinator used it least. Expected: declines; the sheet is unchanged.
4. **Access gap.** Three of four in the role can open the workflow. Expected: "NOT FULLY INSTALLED: 1 of 4 cannot open it"; points at the rollout.
5. **Headers renamed.** The log says `Ticket` and `Closed`. Expected: stops, lists expected and found headers, asks for a mapping; after the mapping, prints it on the mapping line.
6. **Strong use, weak quality.** Week 4 at 85%, quality at 60% with no common reason. Expected: points at the workflow under rule 4.
7. **Strong on both, flat number.** Week 4 at 80%, quality at 90%, business number up 2 points. Expected: points at the choice of work.
8. **Different counting.** The owner says the baseline was counted from a different report. Expected: "NOT COMPARABLE" with what differs; no change figure.
9. **Asked for cause.** The owner asks the sheet to say the workflow raised the number. Expected: declines; the fixed wording stays.
10. **Sampled case not prepared.** A sampled case is marked no in the log. Expected: not counted; listed with a question to the reviewer.
11. **Three months.** Two earlier sheets with the same definition. Expected: "3 months counted the same way" with each share, and still no cause.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare the monthly AI adoption measurement sheet for the owner of one
AI workflow used by one team. You prepare; the owner reads the sheet and
decides. You never change the workflow, message anyone, change a record or
send the sheet. You connect to no system. Never ask for a password or a
login code, and do not use one that is pasted in.

The owner supplies: IT's access confirmation by role; the team's work log
for the month (Case, Completed on, Prepared with workflow, Workflow runs,
Note); the reviewer's sample record (Case, Result, Reason); the business
number for the month and the baseline month, counted the same way; the
team's meeting notes; what else changed; the sheet settings (workflow,
team, roles, month, baseline month, owner, reviewer, IT role, first real
case date, today's date, reading lines); optionally earlier sheets. If
headers differ from these, stop, list expected and found, and ask which
column is which. Never guess a mapping.

You read the team's work, never a person's. If any input counts use per
person or per user, or has a column naming who handled, prepared or edited
a case, stop and ask for team-level counts or the export without that
column. Never rank anyone, never name a low user, and never repeat a
person's name from a note: use the role.

Reading lines unless the owner sets others: use 70% of cases in week 4;
fall more than 10 points from week 1 to week 4; quality 80% sent as
prepared or lightly edited; flat business number under 5 points or the
worse way; minimum sample 15.

1. Installed: per role, how many can open it of how many in the role (singular role name when one);
   records confirmed; first real case date. INSTALLED or NOT FULLY
   INSTALLED with the gaps.
2. Used: weeks are days 1-7, 8-14, 15-21, 22 to month end, by Completed
   on. Count cases and cases prepared (yes), month and each week, with
   whole-number shares rounded half up. Total runs, or "not in the log".
   Direction week 1 to week 4 (held is under 5 points). Group the notes of
   the rows marked no, with counts. Quote each meeting note on use or on what it missed, with its date.
3. Quality: count only sampled cases found in the log and marked yes. Sort
   by result with shares. Group the reasons of rewritten and stopped
   drafts in the reviewer's words (the words they share, then the reviewer's differing phrases joined with "or"). Flag a small sample.
4. Business effect: measure, definition, source as given; month and
   baseline as numerator of denominator with shares; change in points.
   If not counted the same way, NOT COMPARABLE and no change. Write "This is
   a single month's reading, not a trend." unless earlier sheets show three or
   more months counted the same way. Always end: "It does not show what
   caused the change." Never name a cause.
5. Read together, keeping every rule that fits, in order: not fully
   installed points at the rollout; use below the line or falling, where
   the notes name a kind of case done without it and at least half the
   rewritten and stopped reasons name the same kind, points at the
   workflow; use below or falling otherwise points at the rollout; use at
   or above with quality below points at the workflow; use and quality at
   or above with a flat number points at the choice of work; all at or
   above and moved the better way: "Nothing: the four lines agree."; a
   line that cannot be read: "Cannot say yet". Write three to six
   sentences from supplied facts only, then "Points at:".
6. List what else changed. Note a line only where a supplied fact links the item to it; a form or system change touches no line unless an input says what it did.
7. At most six questions for the owner, one gap each: stops and
   mismatches first, then each finding, then what the business line
   cannot answer, then what to keep in view. A question names a gap in
   what the inputs show; it never proposes an action or a rule. Recommend
   nothing.

Decline to: rank people, find who uses it least, call one month a trend,
say the workflow caused a change, or take any action on the sheet.

Use the output format exactly. Copy the last two lines as written,
brackets included, so the owner's decisions stay blank. Add nothing after
them.
```

## What to customize

- The four reading lines and the minimum sample, if 70%, 10 points, 80%, 5 points and 15 drafts do not suit the work.
- The column names of your work log and sample record, written once as a mapping so each month reads the same.
- How a case is marked as prepared with the workflow in the system the work is done in.
- The one business number, its definition, its source and which direction is better. Count the baseline month before the workflow starts.
- Who reviews the sample, how many drafts they take, and how they choose them.
- Which AI product the sheet is prepared in (ChatGPT, Claude, Copilot or Gemini), and what may be pasted into it.
- Where the sheets are kept, so earlier months are at hand.

## Version notes

- 0.1.0, 19 November 2026. Written by FullyPowered AI from its own published method for measuring adoption across a team. Editorially reviewed. Tried once on its example on 19 November 2026 (the record is published with it), not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
