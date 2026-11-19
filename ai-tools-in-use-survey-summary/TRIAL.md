# AI tools in use: survey summary, tried on its own example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (claude-sonnet-5-5)
- **Date:** 2026-11-19

This is one run of the workflow template. The inputs are the template's own example: illustrative, sample inputs for a made-up 30-person architecture and interiors practice. No client data was used. The person who ran it did not write the template.

## Inputs used

The five sample inputs in [the example](example.md), under "The inputs": the settings (smallest group 5), the 16-row response export, the 3-line subscription list, the 4-team list and the company's rule on information. The example's output was not read until after this run's output was finished.

## What came out

The instruction block and the output format were followed as written. Every one of the ten sections was produced, plus the header, the check line and the closing line.

- Header: 16 rows = 16 read + 0 unreadable. 16 of 30 people answered. Two teams reported (Design 6 answers, Project delivery 5), two held back (Finance 3, Office 2). The held-back answers total 5, which is not fewer than the smallest group, so the subtraction rule did not apply.
- Section 1: Design used Assistant A (4 answers), Assistant B (2), Meeting notes D (1), with 1 answer naming no tool; paid by company 5, self 1, free 1 (7 mentions). Project delivery used Assistant A (2), Assistant C (2), Meeting notes D (1), with 1 answer naming no tool; paid by company 3, self 1, free 1 (5 mentions).
- Section 2: Assistant A 6, Assistant B 5, Assistant C 3, Meeting notes D 3; 3 answers naming no tool; 13 naming at least one. Paid by company 9, self 4, free 4 (17 mentions). All checks added up.
- Section 3: Assistants B and C are paid by people themselves or free and are not on the subscription list; nothing is said to be company-paid but missing from the list; every listed tool is named in an answer.
- Section 4: Assistant A, Design: 8 seats, 4 answers. Assistant A, Project delivery: 4 seats, 2 answers. Meeting notes D, company-wide: 6 seats, 3 answers. Plus the line "16 of 30 people answered, so a seat with no answer against it may belong to someone who did not answer."
- Section 5 (most answers first): minutes and notes of meetings 5 (R05, R07, R09, R10, R15); rewording client emails 4; drafting design narratives 3; payment reminder emails 2; weekly client progress report 2; then five single-answer pieces. The name in R09 was quoted as "[name removed]".
- Section 6: the company's rule quoted once, then 11 answers set apart (R01, R02, R05, R06, R07, R08, R10, R12, R13, R15, R16). R02 ticked only internal documents and was marked "not ticked; the answer mentions \"client emails\"". No answer was judged against the rule.
- Section 7: five candidates (minutes and notes 5, rewording client emails 4, design narratives 3, payment reminder emails 2, weekly progress report 2), with "The owner scores and chooses."
- Section 8: five themes adding up to 16 answers: a company seat 4; clear rules and training on what may go in 4; a template or shared instructions 3; know which assistant to use 3; someone to show what it is good for 2.
- Section 9: Finance (4 people) and Office (3 people), "fewer than 5 answers"; 0 answers with no team.
- Section 10: none.

## What was observed

- Nothing in the run called for a stop: no header mismatch, no repeated response id, no name or email column, no unlisted team, no unreadable row, no failed count check.
- Every required part was produced.
- The figures matched the published example exactly: every count in the header, sections 1 to 4 and 6 to 9, the 11 answers set apart, and the response ids. No fact appeared in either output that is not in the inputs.
- The differences from the published example were all about wording and order, never numbers:
  - Names of pieces of work and themes (for example "Minutes and notes of meetings" against the example's "Meeting minutes and notes"; "A template or shared instructions for a recurring document" against "Shared instructions or templates for a piece of work").
  - The order of single-answer pieces and of tied themes. The template says ties go in alphabetical order but not whether that means the name chosen, so the order depends on the names chosen.
  - How many phrasings are quoted. Where two answers differ only in a capital letter, this run treated them as one phrasing; the example is not consistent about it.
  - The company's rule was printed with its original line break. The example joins it into one line.
- Where the instructions were ambiguous and a guess was needed:
  - The order of tools within sections 1 and 2 is not stated. Alphabetical order was used, as the example does.
  - Whether "Notes from client meetings" and "minutes of staff meetings" are the same piece of work. The template's own example (minutes of any meeting) was followed, but it is a judgement.
  - Whether "Clear rules on client drawings" and "Training on what we may put in" are one theme. They were merged; keeping them apart would also have been defensible.
  - Whether the operations lead, who receives the summary, may read section 6, which is marked for the owner only. The settings say the summary goes to the operations lead for the owner, so the run printed section 6 and marked it.
  - Step 3's repeat-until rule is hard to read; it did not apply here, so it was not exercised.
- Not exercised: the ten acceptance tests other than the ordinary survey, including the stop conditions and the subtraction rule. This one run does not show them working.
