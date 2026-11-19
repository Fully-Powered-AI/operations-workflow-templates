# AI pilot result write-up

Workflow template, version 0.1.0.

## Purpose

Prepare the write-up of one AI workflow pilot at the end of its pilot period, on two pages, for the pilot owner and the leader who decides whether the workflow goes to the whole team. It sets out what was tested and on how many cases, what passed, what failed grouped by the causes people recorded, what was not tested and so is not known, the bar the owner wrote before the pilot set beside the results line by line, what extending the workflow to the whole team would take, and the decision as three options: roll out, change and re-test, or stop, each with what it would need.

The assistant reports; people decide. It recommends none of the three options, never turns a failed or unjudged run into a pass, reports a count on few cases as few cases, claims no time saved, no cost saved and no business effect, names roles and never people, describes nothing as tested unless a result row says so, connects to no system, and sends, posts or changes nothing.

## When to use it and when not to

Use it at the end of a pilot's agreed period, once the last acceptance test run has been judged and the run log is closed, and before the meeting where the leader decides. Run it again after the pilot owner has answered its questions, to produce the version that is kept with the pilot's record.

Do not use it:

- to prepare the acceptance test itself. That is done before the pilot, with its cases, expected behavior and pass rule;
- to measure whether a workflow already rolled out is used and is useful, or what it is worth. That comes later, on the team's adoption sheet, from weeks of use by the whole team;
- to judge whether an individual did the work well. The write-up is about the workflow, never about a person;
- to decide whether the workflow rolls out. The leader named in the settings decides; this template prepares the facts for that decision;
- while test runs are still waiting to be judged, or the pilot period has not ended.

## Roles

- **Runs it:** the pilot owner, or someone preparing it for them, such as an operations coordinator.
- **Supplies the results and answers the questions:** the pilot owner, with the expert who judged the test runs.
- **Judged each acceptance test run:** the role recorded on each result row, usually the expert or the pilot owner.
- **Decides between rolling out, changing and re-testing, or stopping:** the leader named in the settings, such as a department head or the head of operations.
- **Holds each responsibility after the pilot:** the roles named for business ownership, technical maintenance, user support and change approval, as the inputs give them.

## Inputs

All inputs are files or notes the person supplies. The assistant needs no access to any system and never asks for a password or a login code.

1. **Acceptance test results,** one row per test run. Default column headers: `case_id, case_kind, run, date, workflow_version, expected, output_summary, result, reviewer_role, cause`.
   - `case_kind` is the kind the acceptance test gave the case, such as `ordinary`, `missing`, `contradictory`, `ambiguous` or `stop and ask`.
   - `result` is exactly `pass`, `fail` or `not run`. Any other word, such as "partial" or "pass with edits": stop, show the rows, and ask the pilot owner which it is. Never map it yourself.
   - `reviewer_role` is the role that judged the run. A `pass` or `fail` with no reviewer role is **unjudged**: it is never counted as a pass.
   - `cause` is the reviewer's short label for why a run failed, in their words. A `fail` with no cause is grouped under "cause not recorded" and gets a question.
   If missing: stop and ask. Two rows with the same `case_id`, `run` and `workflow_version`: stop and ask which is right.
2. **The run log** from the pilot weeks, one row per piece of real work the workflow prepared. Default column headers: `run_id, date, workflow_version, item, outcome, cause, run_by_role`.
   - `outcome` is exactly `used as prepared`, `edited` or `set aside`. Any other word: stop and ask.
   - `cause` is the reason given for an edit or a set-aside, in the user's words. An `edited` or `set aside` row with no cause is grouped under "cause not recorded" and gets a question.
   If missing: ask whether real work was run during the pilot. If the pilot owner confirms none was, write "No real work was run in the pilot" wherever the run log is used, and continue. Two rows with the same `run_id`: stop and ask.
3. **The bar,** written by the pilot owner before the pilot: what has to be true for the workflow to go to the whole team. Default column headers: `bar_id, condition, measure, scope, threshold, written_on`.
   - `measure` is one of: `test pass share` (test runs passed on the final version, as a percentage, at least the threshold); `no fail in kind` (no failed or unjudged run on the final version among cases of the kind named in `scope`); `minimum real runs` (run log rows in the pilot period, at least the threshold); `used as prepared share` (run log rows used as prepared, as a percentage, at least the threshold); `set aside share` (run log rows set aside, as a percentage, at most the threshold); or `other` (anything else, such as what the users say, which a person judges).
   - `scope` is `all` or a case kind; it applies to the test measures only.
   - `written_on` is the date the line was written.
   If missing: ask whether a bar was written before the pilot. If the pilot owner confirms none was, write "No bar was written before the pilot" in its section, and never write one now. If a header does not match: stop and ask.
4. **The not-tested list:** what was deliberately not tested. Default column headers: `area, why_not_tested`. If missing: ask once. If the pilot owner says nothing was left out, write "The pilot owner states that nothing was left out of the test"; if they do not answer, write "Not supplied" and raise a question.
5. **The participants,** by role. Default column headers: `role, count, part_taken`. A row that gives a person's name instead of a role: use "[a named person]", and tell the person to replace the name with a role in the source.
6. **Open items noted during the pilot.** Default column headers: `area, item, raised_by_role`, where `area` is `access`, `instructions`, `records` or `other`. If missing: write "none noted" under each heading in section 6.
7. **Ownership after the pilot,** one row per responsibility. Default column headers: `responsibility, role`, where `responsibility` is one of `business ownership`, `technical maintenance`, `user support` and `change approval`. A responsibility with no row is "not named" and gets a question.
8. **The settings:** the workflow's name; the final workflow version; the pilot start and end dates; the pilot owner's role; the deciding leader's role; the whole team the workflow would go to, as the owner describes it, saying whether the pilot owner and the expert belong to it; the few-cases line (default 10); where the pilot's record is kept; and today's date. If the final version, the pilot dates, the pilot owner's role or the deciding leader's role is missing: stop and ask.

For every export, if a header does not match the defaults: stop, show the expected and the found headers, and ask which column is which. Never guess a column.

## The procedure

1. **Check the inputs.** Confirm the headers, the fixed words in `result`, `outcome`, `measure` and `responsibility`, and the repeated-row rules, stopping as set out under Inputs. Confirm the final version appears in the test results; if it does not, stop and ask. Confirm today is on or after the pilot end date; if it is not, stop: the pilot has not ended.
2. **Sort the rows.** Test rows are sorted by version: the final version, and each earlier version. Run log rows dated inside the pilot period are used; a row dated outside it is left out and listed under "Left out", with a question. Rows marked `not run` are listed, never counted as passed or failed.
3. **Count what was tested.** For each version: test runs, passed, failed and unjudged. For the final version, the same count for each case kind. For the run log: rows used, by version, and the number used as prepared, edited and set aside.
4. **Write every count as "n of m".** Counts of test runs in sections 1 and 2 carry no percentage. A percentage, to one decimal place, is shown only on the real runs used as prepared in section 2 and in the working for a share line in section 5, and only when m is at or above the few-cases line; below it, write "(few cases)" after the count and give no percentage. In every section, "(few cases)" goes after each count whose m is below the line, not once at the end of a list. A percentage is never shown on its own.
5. **List what passed.** The cases that passed every one of their runs on the final version, each with its kind and its count, and the run log rows used as prepared. A case with any failed or unjudged run on the final version is not listed here.
6. **Group what failed by cause.** Take every failed or unjudged test run on any version, every `set aside` run log row and every `edited` run log row. Group them by `cause` exactly as written; two causes are one group only when their words are the same, ignoring case. Unjudged runs form the group "unjudged: no reviewer recorded". Rows with no cause form the group "cause not recorded". Number the groups F1, F2 and so on, by the number of rows in each, largest first, and in order of first appearance where two are equal (test results before the run log). For each group, list the failed test runs (case, version, run), the real runs set aside and the real runs edited, by id, and say whether the cause was seen on the final version. Edited runs are shown in this section because a person corrected them; they are never counted as failed. Never give a cause of your own, never merge groups whose words differ, and never say a cause was fixed: a later version is described only by its own rows.
7. **List what was not tested,** from the not-tested list, each with its reason as written. Add nothing of your own.
8. **Set the bar beside the results.** For each bar line, in its order: quote the condition as written; work out its measure on the rows it names, with the working; and mark it:
   - `test pass share`: passed runs on the final version in scope ÷ (passed + failed + unjudged runs in scope) × 100. MET when the unrounded figure is at or above the threshold, NOT MET below it;
   - `no fail in kind`: the failed and unjudged runs of that kind on the final version; the count it rests on, for "on few cases", is the runs of that kind, not all final-version runs. MET when there are none and at least one run of that kind; NOT SHOWN when there is no run of that kind; NOT MET otherwise;
   - `minimum real runs`: run log rows in the pilot period. MET at or above the threshold;
   - `used as prepared share`: used-as-prepared rows ÷ run log rows × 100. MET at or above the threshold;
   - `set aside share`: set-aside rows ÷ run log rows × 100. MET at or below the threshold;
   - `other`: compute nothing. Mark it "FOR THE [deciding leader] TO JUDGE", and say "the inputs hold no record of this" unless a supplied row is named in the condition itself.
   Apply the few-cases rule to every count in this section, and add "on few cases" after the mark when the count it rests on is below the few-cases line. If a line's `written_on` is after the pilot start date, add "written after the pilot began" and raise a question. Never change a threshold, add a line or call a line met that the working does not meet.
9. **Set out what extending it would take.** Under Access, Instructions, Records to tidy and Other, list each open item with the role that raised it. Under Instructions, also list the failure groups seen on the final version by their numbers. Under Who owns it, give the role for each of the four responsibilities, or "not named". Then the whole team as the settings describe it, and how many of its people took part, from the participants. Count only participants whose role is a member of the whole team as the settings describe it; the pilot owner and the expert are not counted unless the settings say they belong to it. Take every line from the inputs; propose no fix, no access change and no owner.
10. **Lay out the decision.** Three options, always in this order, each with what it would need, taken from the sections above:
    - **A. Roll out** to the whole team: every bar line that is NOT MET, NOT SHOWN or for the leader to judge; every open access item; every responsibility not named. If there are none, write "Nothing outstanding in the inputs".
    - **B. Change and re-test:** the failure groups seen on the final version; who approves a change (the change approval role, or "not named"); a rerun of every case behind a failed or unjudged run on the final version, and of every case of a kind named in a `no fail in kind` bar line; the real runs still short of any `minimum real runs` line; and the not-tested areas, for the pilot owner to choose whether to add.
    - **C. Stop:** the deciding leader's reason, recorded with the pilot; the access set up for the pilot, as the participants or open items record it, withdrawn by the technical maintenance role (or "not named"); and the pilot's record kept where the settings say.
    Rank nothing, weigh nothing and recommend nothing. End the section with "This write-up recommends none of the three."
11. **Write the questions,** numbered, for the pilot owner: each row left out; each failure group with no cause recorded and each unjudged run; each bar line written after the pilot began; each responsibility not named; a missing not-tested list; each value that had to be read as a role. Give the facts, then the question.
12. **Keep it to two pages.** One line per item. Name cases and runs by their ids, never by copying record contents; in a question, the item reference as written in the run log may follow a run id, so the run can be found. Return the draft to the person who ran it, for the pilot owner and the deciding leader.

## Exceptions and stop conditions

- **A header that does not match, a result, outcome, measure or responsibility word outside its fixed list, a repeated row, or a date that cannot be read:** stop, show what was found, and ask.
- **No test results, no final version, no pilot dates, no pilot owner or no deciding leader:** stop and ask.
- **The pilot has not ended, or test runs are still waiting to be judged:** stop and ask whether to wait; a write-up on part of the pilot would mislead.
- **Asked which option to choose, or whether the workflow is ready:** decline; the deciding leader decides. Lay out the three options as they stand.
- **Asked to count a failed or unjudged run as passed, to drop a row, to lower a threshold, to add a bar line after the fact, or to round a figure up to the bar:** decline, and show the working.
- **Asked how much time or money the workflow saves, or what it will do for the business:** decline. The pilot's rows do not show it; it is measured later, on the adoption sheet, from the whole team's use.
- **Asked to describe something as tested that no result row shows:** decline; it belongs under what was not tested.
- **Asked to send the write-up, post it, change a test result, grant access or update a record:** decline; a person does each of these.
- **An input names a person, rates someone's work, or holds client records, personal details, a password or a login code:** do not repeat them; refer to people by role only, and tell the person to remove such details from the source. Never rate or blame an individual.

## Output format

```
AI PILOT RESULT WRITE-UP: [workflow], version [final version]
For: [pilot owner role] and [deciding leader role]. Prepared [date] from: acceptance test results ([n] rows); run log ([n] rows / no real work was run in the pilot); the bar ([n] lines / no bar was written before the pilot); the not-tested list ([n] areas / nothing left out, as stated / not supplied); participants ([n] roles); open items ([n] / none noted); ownership ([n] of 4 named).
Pilot period: [start] to [end]. Whole team: [as the settings describe it]. Few cases: below [n].

1. What was tested
Acceptance test, version [final]: [n] cases, [n] runs: [n] passed, [n] failed, [n] unjudged[, [n] not run].
By kind, version [final]: [kind] [passed] of [runs][ (few cases)]; [...].
Acceptance test, version [earlier]: [n] runs: [n] passed, [n] failed, [n] unjudged.
Real work: [n] runs from [date] to [date] ([n] on version [v]; [n] on version [v]): [n] used as prepared, [n] edited, [n] set aside.
Left out: [id], [reason]. See question [n]. / None.

2. What passed
Cases that passed every run on version [final]: [case_id] ([kind]), [n] of [n][ (few cases)]; [...]. / None.
Real runs used as prepared: [n] of [n][ ([pct]%) / (few cases)].

3. What failed, grouped by cause
F[n] "[cause as written]": [n] failed test runs ([case_id] version [v] run [n]; ...); [n] real runs set aside ([run_ids]); [n] real runs edited ([run_ids]). Seen on version [final]: [yes / no].
Edited runs appear here because a person corrected them; they are not counted as failed.
/ No test run failed, none was unjudged, and no real run was edited or set aside.

4. What was not tested, and so is not known
[area]: [why, as written].
/ The pilot owner states that nothing was left out of the test. / Not supplied. See question [n].

5. The bar set beside the results
[bar_id] "[condition as written]" (written [date][, written after the pilot began. See question [n]]): [the working, ending in the result / nothing computed][, against [threshold]]. [MET / NOT MET / NOT SHOWN / FOR THE [deciding leader role] TO JUDGE: the inputs hold no record of this][ on few cases].
/ No bar was written before the pilot.

6. What extending it to the whole team would take
Access: [item] (raised by [role]); [...]. / None noted.
Instructions: [item] (raised by [role]); [...]. Failure groups seen on version [final]: [F ids / none].
Records to tidy: [item] (raised by [role]). / None noted.
Other: [item] (raised by [role]). / None noted.
Who owns it: business ownership, [role / not named]; technical maintenance, [role / not named]; user support, [role / not named]; change approval, [role / not named].
Whole team: [as described]; [n] of its people took part, as [roles]. / Not given.

7. The decision, for the [deciding leader role]
A. Roll out to [the whole team]. Would need: [bar lines not met, not shown or to judge, by id]; [open access items]; [responsibilities not named]. / Nothing outstanding in the inputs.
B. Change and re-test. Would need: a change for [F ids seen on version [final]], approved by [change approval role / not named]; a rerun of [case ids][, and of [case ids] for bar line [id]]; [n more real runs to reach bar line [id]]; the not-tested areas, for the [pilot owner role] to choose whether to add ([n] listed).
C. Stop. Would need: the [deciding leader role]'s reason, recorded with the pilot; the pilot's access withdrawn by [technical maintenance role / not named] ([the access the inputs record as set up for the pilot / not recorded]); the pilot record kept at [location / not given].
This write-up recommends none of the three.

Questions for the [pilot owner role]
[n]. [The facts.] [The question.]
/ None.

Draft for the [pilot owner role] and the [deciding leader role]. Every count traces to the rows named above. No saving and no business effect is claimed. Nothing has been sent and no record has been changed.
```

Write dates in words, such as "19 October 2026". Keep percentages to one decimal place. Show the division behind a percentage in the working for a bar line in section 5; in section 2 the percentage follows the count it rests on.

## Reviewer checklist

1. Every test row and every run log row is counted once, left out with a reason, or listed as not run, and the counts add up to the rows in each file. (Pilot owner)
2. No failed or unjudged run appears under What passed, and no edited run is counted as failed. (Expert)
3. Every failure group uses a cause exactly as the reviewer or user recorded it, and no cause was supplied by the assistant. (Expert)
4. Every count below the few-cases line says "few cases" and carries no percentage. (Pilot owner)
5. Every bar line is quoted as written before the pilot, with its working, and none was added, lowered or reworded. (Pilot owner)
6. Nothing is described as tested that no result row shows, and the not-tested list is complete. (Expert)
7. No saving, no business effect and no recommendation appears anywhere. (Deciding leader)
8. Every line in section 6 traces to an input, and no person is named or rated. (Pilot owner)

## Acceptance tests

Proposed tests. None has been run.

1. **Clean pilot.** Every final-version run passed, every real run used as prepared, every bar line met. Expected: the failures section prints its "none" line; option A says "Nothing outstanding in the inputs"; all three options are still laid out and none is recommended.
2. **Renamed column.** The test results headed `outcome` in place of `result`. Expected: stops, shows expected and found headers, and asks.
3. **Unrecognized result word.** A row marked "pass with edits". Expected: stops and asks; does not count it as a pass.
4. **Pass with no reviewer.** Expected: counted as unjudged, not as passed, grouped under "unjudged: no reviewer recorded", with a question.
5. **Seven real runs, few-cases line of 10.** Expected: "5 of 7 (few cases)", no percentage.
6. **Bar written after the pilot began.** Expected: compared as written, marked "written after the pilot began", and a question.
7. **Asked which option to choose.** Expected: declines and lays out the three options.
8. **Asked how many hours it saves.** Expected: declines, and says that is measured later on the adoption sheet.
9. **A fail with no cause.** Expected: grouped under "cause not recorded", and a question; no cause supplied.
10. **Two causes worded differently that seem alike.** Expected: kept as two groups.
11. **A run log row dated after the pilot ended.** Expected: left out, listed, and a question.
12. **No bar supplied, and the owner confirms none was written.** Expected: "No bar was written before the pilot"; no bar written now.

## Instructions for the AI assistant

```
You prepare the two-page result write-up of one AI workflow pilot, for
the pilot owner and the leader who decides whether the workflow goes to
the whole team. You report; people decide. You never recommend roll out,
change and re-test, or stop. You never count a failed or unjudged run as
a pass, never claim a saving or a business effect, never describe
anything as tested unless a result row shows it, and never name or rate
a person. You never send, post or change anything, need no access to any
system, and never ask for a password or a login code.

The user will supply: acceptance test results (case_id, case_kind, run,
date, workflow_version, expected, output_summary, result, reviewer_role,
cause); the run log (run_id, date, workflow_version, item, outcome,
cause, run_by_role); the bar written before the pilot (bar_id,
condition, measure, scope, threshold, written_on); the not-tested list
(area, why_not_tested); participants (role, count, part_taken); open
items (area, item, raised_by_role); ownership (responsibility, role);
and the settings: workflow, final version, pilot start and end, pilot
owner role, deciding leader role, whole team, few-cases line (default
10), record location, today.

A participants row that gives a person's name: write "[a named person]"
and tell the user to put a role in the source.

Stop and ask when: a header does not match (show expected and found;
never guess a column); result is not pass, fail or not run; outcome is
not used as prepared, edited or set aside; measure or responsibility is
outside its list; a row repeats; a date cannot be read; the test
results, final version, pilot dates, pilot owner or deciding leader are
missing; the final version is not in the test results; or the pilot has
not ended. If the run log or the bar is missing, ask; if the owner
confirms there was none, say so in its section and never write one.

1. Sort test rows by version. Use run log rows dated inside the pilot
   period; list any other row as left out, with a question. List not
   run rows; never count them.
2. Count runs passed, failed and unjudged (pass or fail with no
   reviewer_role) per version, and per case kind on the final version.
   Count run log rows used as prepared, edited and set aside.
3. Write every count as "n of m". Test run counts in sections 1 and 2
   carry no percentage. A percentage to one decimal goes only on the
   real runs used as prepared and in the working of a share line in
   the bar, and only when m is at or above the few-cases line; below
   it write "(few cases)" after that count, and no percentage. Put
   "(few cases)" after each such count, not once at the end of a list.
4. What passed: cases with every final-version run passed; run log rows
   used as prepared.
5. What failed: failed and unjudged test runs on any version, set-aside
   and edited run log rows, grouped by cause exactly as written (same
   words, ignoring case). Unjudged runs: "unjudged: no reviewer
   recorded". No cause: "cause not recorded", and a question. Number
   F1, F2 by size, then first appearance. Say whether each was seen on
   the final version. Edited runs are not counted as failed. Never give
   a cause of your own or say a cause was fixed.
6. Not tested: the list as written; add nothing.
7. The bar, line by line, with the working: test pass share = passed /
   (passed + failed + unjudged) on the final version in scope x 100, MET
   at or above threshold; no fail in kind, MET with no failed or
   unjudged run of that kind and at least one run, NOT SHOWN with none;
   minimum real runs, MET at or above; used as prepared share, MET at or
   above; set aside share, MET at or below; other, "FOR THE [deciding
   leader] TO JUDGE: the inputs hold no record of this". Judge on the
   unrounded figure. Add "on few cases" when the count is below the
   line; for no fail in kind the count is the runs of that kind, not
   all final-version runs. Mark a line written after the pilot began,
   and ask.
8. Extending it: access, instructions, records to tidy and other items
   with the role that raised each; failure groups seen on the final
   version; the role for business ownership, technical maintenance,
   user support and change approval, or "not named" with a question;
   the whole team and how many of its people took part, counting only
   participants whose role is a member of the whole team as the
   settings describe it (not the pilot owner or the expert unless the
   settings say they belong to it). Only from the inputs.
9. The decision, in this order: A. Roll out, would need the bar lines
   not met, not shown or to judge, the access items and the
   responsibilities not named. B. Change and re-test, would need a
   change for the groups seen on the final version, approved by the
   change approval role, a rerun of the cases behind them and of the
   kinds a bar line names, any real runs still short, and the
   not-tested areas for the owner to choose. C. Stop, would need the
   leader's reason recorded, the pilot's access withdrawn by the
   technical maintenance role (the access the participants or open items
   record as set up for the pilot, nothing else), and the record kept. End: "This
   write-up recommends none of the three."
10. Numbered questions for the pilot owner, facts first.
11. Use the output format exactly, every section in order, printing
    the "none" line for an empty section. One line per item; ids, not
    record contents (an item reference may follow a run id in a question). Dates in words.

If asked which option to choose, decline. If asked to count a fail as a
pass, drop a row, lower a threshold, add a bar line or round up to the
bar, decline and show the working. If asked what it saves or what it
will do for the business, decline: that is measured later on the
adoption sheet. Refer to people by role only; do not repeat personal
details, client records, a password or a login code from an input, and
tell the user to remove them. Check every count against the rows before
you return the draft.
```

## What to customize

- Your export column headers, if your test record sheet or run log names them differently.
- The case kinds your acceptance tests use.
- The few-cases line: 10 by default; some teams set it higher.
- The measures your bar may use, if you write bar lines in other terms; anything outside the list is judged by a person.
- The roles: who runs it, who judged the test runs, who decides, and who holds each of the four responsibilities after the pilot.
- The whole team the workflow would go to, and where the pilot's record is kept.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 19 November 2026. Written by FullyPowered AI from its own method for piloting a workflow before the whole team uses it. Editorially reviewed. Tried on its example on 19 November 2026 in one run, published with it (`public/trial.md`). After a reviewer's points the same day, the percentage rule, the placement of "(few cases)", the count behind "on few cases" for a "no fail in kind" line, and the count of the whole team who took part were made definite, two rules were added to the instruction block, and the template was run once more on its example. That run covered the happy path only. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
