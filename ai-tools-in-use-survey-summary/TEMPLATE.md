# AI tools in use: survey summary

Workflow template, version 0.1.0.

## Purpose

Turn the export of an anonymous staff survey about AI use into one summary, by team, for the person about to write the company's first AI plan: which assistants and AI features are in use and how often, what people use them for (grouped into pieces of work, in their own words), which tools the company pays for and which people pay for themselves or use free, how the seats the company pays for compare with the answers that say they use them, the answers that mention customer, personal or confidential information (set apart for the owner by response id), the pieces of work named most often as candidates for the opportunity scorecard, what people said would help, and which teams gave too few answers to report. The assistant identifies nobody, judges no one's use, decides nothing about policy or discipline, recommends no product and connects to nothing.

## When to use it and when not to

Use it once before the first AI plan is written, after the survey has closed, and again every six months with a fresh survey, so the plan starts from what people actually do.

Do not use it:

- to find out who wrote an answer, or to review one person's use of AI. The survey is answered without names and the summary keeps it that way;
- to decide whether any use breaks a rule, or what follows if it does. The owner decides that, with whoever answers for the company's obligations;
- to judge whether an assistant's terms are safe for the company's information. That needs the vendor's own pages and the person who approves data use;
- to review what software costs or which subscriptions to keep. That is software subscription and vendor spend review;
- to read whether the company's values show up in daily work. That is culture health check;
- when the survey had fewer answers than the smallest group the company reports.

## Roles

- **Runs it:** the operations lead, the office manager or the owner, whoever holds the survey export.
- **Receives the summary and decides what happens next:** the owner, or the person writing the AI plan for the owner. Section 6 is read only by the owner and by the person who ran it, who hands it to the owner; remove it before the summary goes anywhere else.
- **Supplies the subscription list:** finance.
- **Answers questions about the company's rule on information:** whoever wrote the rule, usually the owner.
- **Decides any change to tools, seats, rules or training:** the owner. Always a person.

## Inputs

1. **The response export from your survey tool.** One row per answer. Default headers: `response_id`, `team`, `role`, `tools_used`, `how_often`, `what_for`, `paid_by`, `data_types_entered`, `what_would_help`. All but `role` are required. If a required header does not match, stop and ask which supplied header stands for it; never guess a mapping. If two rows share a `response_id`, stop and ask. The survey is answered without names; if the export holds a name or email column, stop and ask for an export without it.
   - `tools_used`: the assistants and AI features the person uses, separated by semicolons, or `none`.
   - `how_often` and `paid_by`: one value for each tool, in the same order, separated by semicolons. `how_often` is daily, weekly, monthly or rarely. `paid_by` is company, self or free. Both are blank when `tools_used` is `none`.
   - `what_for`: the person's own words, pieces of work separated by semicolons.
   - `data_types_entered`: none, public information, internal documents, financial figures, customer information, personal information or confidential information, separated by semicolons.
   - `what_would_help`: the person's own words.
   - `role`: kept for the planning that follows. The summary never prints it, because inside a team a role can point to one person.
2. **The subscription list from finance.** Default headers: `tool`, `plan`, `seats`, `team`, where team is a team on the team list or `company-wide`. If missing, print "subscription list not supplied" in sections 3 and 4 and continue.
3. **The team list.** Default headers: `team`, `headcount`. If missing, stop and ask: the summary is built by team.
4. **The company's rule on what information may go into an assistant,** if it has one. If not supplied, print "No rule supplied" at the top of section 6 and continue.
5. **Settings:** the company's name or description, the date the survey closed, who receives the summary, and the smallest group the company reports. The default smallest group is 5 answers. If a number below 3 is given, stop and ask the owner to confirm it.

The assistant works from files and text a person supplies. It needs no connection to the survey tool and never asks for a password, a login code or a key.

## The procedure

1. **Check the inputs.** Confirm the headers, that no `response_id` repeats, that the export carries no names, and that every `team` value is on the team list (capital letters ignored). If a team value is not on the list, stop and ask which listed team it stands for. A blank team is allowed and is handled in step 3.
2. **Read each row.** Split `tools_used`, `how_often` and `paid_by` on semicolons and pair them in order. If the three lists differ in length, or a `how_often` or `paid_by` value is not one of the allowed values, the row is unreadable: count it in the answers, leave it out of the tool, frequency and paid-by counts, still read its free text, and list it by response id under data gaps. A `data_types_entered` value outside the allowed list is printed as supplied under data gaps; the row still counts. Match each tool name to the subscription list ignoring capital letters and spaces. Keep any other tool name exactly as the respondent wrote it. Never merge two names on a guess: if two names may be the same tool, list them under data gaps as a question.
3. **Decide which teams are reported.** A team is reported when it has at least the smallest group of answers. Every other team, and every answer with a blank team, is held back: counted in the company total only. Then check the held-back answers together. While they number more than zero and fewer than the smallest group, hold back the reported team with the fewest answers as well (if two tie, the one first in alphabetical order of team name), and check again. Stop as soon as the held-back answers reach the smallest group or no reported team is left. Name each team held back this way in section 9 with the reason "held back so that smaller teams cannot be worked out by subtraction". If the survey's total answers are fewer than the smallest group, stop: report the number of answers and nothing else.
4. **Count by team and for the company.** For each reported team and for the company: the answers and the headcount; for each tool, in alphabetical order, the answers naming it, split by daily, weekly, monthly and rarely; the answers naming no tool; and the tool mentions paid by the company, by the person, or free. Check that each team's paid-by counts add up to its tool mentions, and that the company's answers equal the rows. If a check fails, stop and report the figures.
5. **Paid for by the company or not.** For each tool, across the company: mentions paid by the company, by the person and free, and whether the tool is on the subscription list. List any tool that answers say the company pays for but that is not on the subscription list, and any tool on the list that no answer names. These are facts for the owner; say nothing about whether anyone should have paid.
6. **Seats against answers.** For each line of the subscription list: the tool, the plan, the team, the seats, and the answers in that team that name the tool as paid by the company. A `company-wide` line is compared with the company total. A line for a held-back team prints its seats and "answers held back". Counts only. Add one line: "[n] of [headcount] people answered, so a seat with no answer against it may belong to someone who did not answer." Never call a seat unused.
7. **Group the uses into pieces of work.** Split `what_for` on semicolons. Answers that describe the same kind of output, whatever words they use, are one piece of work (for example, minutes of any meeting). Name each piece in plain words, give the count of answers naming it and their response ids, the reported teams that named it, and "also teams held back" where any held-back answer named it. Quote each distinct phrasing once; phrasings that differ only in capital letters are one phrasing, quoted as the first of them in response id order. An answer counts once per piece of work. Order: most answers first, ties in alphabetical order of the name given to the piece of work.
8. **Remove names from quoted words.** Replace any person's name (a first name alone counts), email address or other detail that points to a person in a quoted answer with "[name removed]". Never print a role. Never guess who wrote an answer.
9. **Set apart answers that touch sensitive information.** Set apart every answer whose `data_types_entered` includes customer information, personal information or confidential information, and every answer whose own words describe such information even when it is not ticked (a client's or customer's emails, records or drawings; details about a person; contracts, fees or material the company's rule calls confidential), marked "not ticked; the answer mentions [the words]". For each, in response id order: the response id, the team or "team held back", each tool with who pays for it, the types ticked, and the person's words with names removed. Quote the company's rule once at the top of the section, word for word as supplied (line breaks may be joined into one line). Do not say whether an answer follows or breaks the rule, and do not suggest any action about a person.
10. **Candidates for the opportunity scorecard.** List every piece of work named in two or more answers, in the order of step 7, with its count and teams. Write nothing about which to choose; the owner scores them.
11. **What would help.** Group `what_would_help` the same way: themes, each with its count, the reported teams that named it and "also teams held back" where it applies. Every answer is counted in exactly one theme; check that the theme counts add up to the answers. Order as in step 7, ties alphabetical by the name given to the theme.
12. **Teams with too few answers to report.** Name each held-back team with its headcount and "fewer than [n] answers", without the exact number, and any team held back under step 3's subtraction rule with that reason. Say how many answers had no team.
13. **Return the draft** to the person who ran it, for the owner. Section 6 is marked for the owner only; the person who ran it may read it in order to hand it over, and removes it before the rest is shared. A person decides what is shared, with whom, and what follows.

## Exceptions and stop conditions

- **A required header does not match, or the team list is missing:** stop and ask.
- **Two rows share a response id:** stop and ask.
- **The export holds names or email addresses:** stop and ask for an export without them.
- **A team value is not on the team list:** stop and ask which listed team it stands for.
- **The survey's answers are fewer than the smallest group:** stop; report the count only.
- **The smallest group is set below 3:** stop and ask the owner to confirm.
- **A count check fails:** stop and report the figures.
- **A row cannot be read:** count it, leave it out of the tool counts, list it under data gaps.
- **Asked who wrote an answer, or to report a team below the smallest group:** decline.
- **Asked whether a use is allowed, whether an assistant is safe for the company's information, or which product to buy:** decline; record the question for the owner under data gaps and questions. The template gives no legal or security opinion and recommends no product.
- **Asked to contact anyone, change a subscription or send the summary:** decline. A person does that.
- **Asked to connect to the survey tool:** decline; ask for an export.

## Output format

```
AI TOOLS IN USE: SURVEY SUMMARY, [company], survey closed [date]

For: [role receiving it]. Prepared from: the response export ([n] rows), the subscription list ([n] lines / not supplied), the team list ([n] teams), the company's rule on information ([supplied / not supplied]). Smallest group reported: [n] answers.
Answers: [n] of [headcount] people. Teams reported: [n]. Teams held back: [n]. The survey was answered without names. Every figure is a count of answers, not of everyone in a team.
Check: [n] rows = [n] read + [n] unreadable.

1. By team
[Team] ([n] answers of [headcount] people)
- In use: [Tool]: [n] (daily [n], weekly [n], monthly [n], rarely [n]). [one line per tool, in alphabetical order] No tool: [n].
- Paid by: company [n], self [n], free [n] ([n] tool mentions).
Teams held back: [names], counted in the company total only (section 9). / none

2. Company total ([n] answers of [headcount] people)
- In use: [Tool]: [n] (daily [n], weekly [n], monthly [n], rarely [n]). [one line per tool, in alphabetical order] No tool: [n]. Answers naming at least one tool: [n].
- Paid by: company [n], self [n], free [n] ([n] tool mentions).

3. Paid for by the company, by people themselves, or free
- [Tool]: company [n], self [n], free [n]. On the subscription list: [yes / no].
- Said to be paid by the company but not on the subscription list: [tools / none].
- On the subscription list but named in no answer: [tools / none].
[or: subscription list not supplied]

4. Seats against answers (counts only)
- [Tool], [plan], [team / company-wide]: [n] seats; [n] answers [in that team / across the company] say they use it on the company's account. [or: answers held back]
- [n] of [headcount] people answered, so a seat with no answer against it may belong to someone who did not answer.
[or: subscription list not supplied]

5. Pieces of work, in people's own words
- [Piece of work]: [n] answers ([response ids]). Teams: [reported teams][; also teams held back / teams held back only]. Their words: "[phrasing]"; "[phrasing]".
[or: none]

6. Set apart for the owner: customer, personal or confidential information
For the owner only; remove before sharing.
The company's rule, as supplied: "[rule]" / No rule supplied.
- [Response id], [team / team held back]. [Tool] ([paid by]); [Tool] ([paid by]). Ticked: [types]. [Not ticked; the answer mentions "[words]".] Their words: "[what_for, names removed]".
[n] answers set apart. / none

7. Candidates for the opportunity scorecard
1. [Piece of work]: named in [n] answers. Teams: [reported teams][; also teams held back / teams held back only].
[or: none named in two or more answers]
The owner scores and chooses.

8. What people said would help
- [Theme]: [n] answers. Teams: [reported teams][; also teams held back / teams held back only].
[or: none]

9. Teams with too few answers to report
- [Team] ([headcount] people): fewer than [n] answers. Counted in the company total only.
[only when step 3's subtraction rule applied:] - [Team]: held back so that smaller teams cannot be worked out by subtraction.
- Answers with no team: [n].
[or: none]

10. Data gaps and questions
- [Response id or tool]: [what could not be read, a possible duplicate tool name, or a question recorded for the owner].
[or: none]

Draft for the [role receiving it]. Nobody is named, no use is judged, and nothing has been sent, bought, cancelled or changed.
```

Print every section heading. If a section has nothing to report, print "none" under it, or the alternative shown.

## Reviewer checklist

1. The rows, the answers read and the unreadable answers add up, and each team's paid-by counts equal its tool mentions. (Operations lead)
2. No team with fewer answers than the smallest group appears anywhere except section 9 and as "teams held back". (Owner)
3. No name, email address or role appears anywhere in the summary. (Owner)
4. Every answer that ticks customer, personal or confidential information is in section 6, and so is every answer whose words describe such information. (Owner)
5. Section 6 quotes the rule exactly and judges no answer against it. (Owner)
6. Every seat figure matches the subscription list, and no seat is called unused. (Finance)
7. Each piece of work's quoted words come from the export, and the counts match the response ids listed. (Operations lead)
8. No product is recommended and no use is called right or wrong. (Owner)

## Acceptance tests

Proposed tests. None has been run.

1. **Ordinary survey.** Four teams, two with at least five answers and two with fewer, the two smaller together reaching five. Expected: two teams reported, two held back and named in section 9, all counts adding up.
2. **Header does not match.** The export has "tool" where `tools_used` is expected. Expected: stops and asks which supplied header stands for it.
3. **Names in the export.** The export has an email column. Expected: stops and asks for an export without it.
4. **Held-back answers too few on their own.** One small team with three answers and every other team reported. Expected: the reported team with the fewest answers is also held back, with the subtraction reason in section 9.
5. **Too few answers overall.** Four answers with the smallest group at five. Expected: reports the count and nothing else.
6. **Unreadable row.** Two tools but one `how_often` value. Expected: counted as an answer, left out of tool counts, listed under data gaps.
7. **Sensitive words not ticked.** An answer ticks internal documents but says "rewording client emails". Expected: set apart, marked not ticked, with the words quoted.
8. **A name in free text.** An answer says "minutes for Sam". Expected: quoted as "minutes for [name removed]", because a first name alone counts as a name.
9. **Paid by the company but not on the list.** Expected: listed in section 3 as said to be paid by the company but not on the subscription list, with no comment.
10. **Asked who wrote an answer, or whether a use breaks the rule.** Expected: declines; the second is recorded as a question for the owner.
11. **Asked which assistant to buy.** Expected: declines; names no product beyond those in the answers and the subscription list.

## Instructions for the AI assistant

```
You summarize an anonymous staff survey about AI use, by team, for the
person writing the company's first AI plan. You work only from the files
the person gives you. You connect to nothing, contact nobody, and never
send, buy, cancel or change anything; a person decides and approves every
action. You never ask for a password, a login code or a key.

Inputs: the response export (default headers response_id, team, role,
tools_used, how_often, what_for, paid_by, data_types_entered,
what_would_help; role is optional); the subscription list (tool, plan,
seats, team, where team may be company-wide); the team list (team,
headcount); the company's rule on what information may go into an
assistant, if any; settings (company, survey close date, who receives it,
smallest group, default 5).

Stop and ask if: a required header does not match (never guess a
mapping); a response_id repeats; the export holds names or email
addresses; a team value is not on the team list; the team list is missing;
the smallest group is set below 3; or a count check fails. If total
answers are fewer than the smallest group, report the count only.

Allowed values: how_often daily, weekly, monthly, rarely; paid_by company,
self, free; data_types_entered none, public information, internal
documents, financial figures, customer information, personal information,
confidential information. tools_used, how_often and paid_by are lists
separated by semicolons, paired in order. If they differ in length or a
how_often or paid_by value is not allowed, the row is unreadable: count
it as an answer, leave it out of tool, frequency and paid-by counts, read
its free text, list it under data gaps.

Method:
1. A team is reported if it has at least the smallest group of answers.
   Hold back every other team and every answer with no team; they count
   in the company total only. Then, while held-back answers number more
   than zero and fewer than the smallest group, also hold back the
   reported team with the fewest answers (ties: first alphabetically by
   team name) and check again. Stop when held-back answers reach the
   smallest group or no reported team is left. Give the subtraction
   reason for each team held back this way.
2. Count, for each reported team and the company: answers and headcount;
   answers naming each tool (tools in alphabetical order), split daily,
   weekly, monthly, rarely;
   answers naming no tool; tool mentions paid by company, self, free.
   Check paid-by counts equal tool mentions and answers equal rows.
3. For each tool: company, self, free, and whether it is on the
   subscription list. List tools said to be company-paid but not on the
   list, and listed tools no answer names. Match tool names ignoring
   capitals and spaces; never merge names on a guess.
4. For each subscription line: seats against answers in that team (or the
   company, for company-wide) that name the tool as company-paid. Held-back
   team: print "answers held back". Counts only; never call a seat unused.
5. Group what_for into pieces of work by the kind of output. Give count,
   response ids, reported teams, "also teams held back" where it applies,
   and each distinct phrasing quoted once (phrasings differing only in
   capital letters are one; quote the first in response id order). Most
   answers first, ties alphabetical by the name given to the piece of work.
6. Replace any person's name (a first name alone counts) or email in quoted words with "[name
   removed]". Never print a role. Never guess who wrote an answer.
7. Set apart every answer ticking customer, personal or confidential
   information, and every answer whose words describe such information
   though not ticked (mark it "not ticked; the answer mentions ...").
   Give response id, team or "team held back", each tool with who pays,
   types ticked, and the words. Quote the company's rule once, word for word (line breaks may be
   joined).
   Never say whether an answer follows or breaks the rule.
8. Candidates for the opportunity scorecard: every piece of work named in
   two or more answers, in step 5's order. Choose nothing.
9. Group what_would_help into themes, every answer in one theme; check
   the counts add up. Order as in step 5, ties alphabetical by theme name.
10. Name held-back teams with headcount and "fewer than [n] answers",
    never the exact number.

Never identify anyone, judge anyone's use, decide anything about policy
or discipline, give a legal or security opinion, or recommend a product.
Name products only as the answers and the subscription list name them.
If asked to do any of these, decline and record the question for the
owner under data gaps and questions.

Use the output format exactly. Print every section heading, and "none"
(or the alternative shown) under an empty one. Mark section 6 for the
owner only. End with: "Draft for the [role receiving it]. Nobody is
named, no use is judged, and nothing has been sent, bought, cancelled or
changed."
```

## What to customize

- The smallest group your company reports, if five is too small for you. Never below three.
- Your survey's questions and the column headers your survey tool exports. Keep a short list of what each header stands for.
- The allowed values for how often, who pays and the kinds of information, if your survey offers different choices. Change them here and in the instructions together.
- Your team list and headcounts, as of the day the survey closed.
- Your rule on what information may go into an assistant, if you have one, written in a sentence or two.
- Who receives the summary, and who sees section 6 (the owner, and the person who runs it to hand it over).
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 19 November 2026. Written by FullyPowered AI from its own published guidance on planning AI use, with no third-party text. Editorially reviewed. Tried on its example on 19 November 2026 in one run, published with it; later edits to tie order, repeated phrasings, the small-team rule, who reads section 6, the order of tools, how the company's rule is quoted and first names have not been run again. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
