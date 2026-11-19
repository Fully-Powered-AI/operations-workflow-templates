---
name: "ai-pilot-result-write-up"
description: "Prepare the write-up of one AI workflow pilot at the end of its pilot period, on two pages, for the pilot owner and the leader who decides whether the workflow goes to the whole team. It sets out what was tested and on how many cases, what passed, what failed grouped by the causes people recorded, what was not tested and so is not known, the bar the owner wrote before the pilot set beside the results line by line, what extending the workflow to the whole team would take, and the decision as three options: roll out, change and re-test, or stop, each with what it would need."
license: "MIT"
metadata:
  version: "0.1.0"
  publisher: "FullyPowered AI"
  template: "AI pilot result write-up"
---

# AI pilot result write-up

This is the technical file for a FullyPowered workflow template. It carries the instructions an AI product follows. The complete template, with roles, inputs, exceptions, the reviewer checklist, acceptance tests and what to customize, is in [TEMPLATE.md](TEMPLATE.md). A worked example is in [EXAMPLE.md](EXAMPLE.md).

## Instructions

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

## Before relying on it

Decide every item under "What to customize" in TEMPLATE.md and set the limits the instructions in this file leave open, written in square brackets such as [N], to your own. Then run the acceptance tests in TEMPLATE.md on past work. A person starts this work, supplies the inputs and decides what happens with the result.
