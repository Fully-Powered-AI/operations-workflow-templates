# AI tools in use: survey summary, an example

*Illustrative example with sample data.* The practice, its teams, the tools, the answers and the dates below are all made up for this example. The practice is an illustrative 30-person architecture and interiors practice whose operations lead ran a short anonymous survey before the owner writes the first AI plan. The assistants are called Assistant A, B and C and the meeting notes feature Meeting notes D, so that no real product's name stands in for sample data. Nothing here describes a real organization or a measured result. First come the inputs the operations lead supplied, in full, then the summary the workflow template returned.

## The inputs

### 1. Settings

```
Company: an illustrative architecture and interiors practice
Survey closed: Friday 13 November 2026
Summary goes to: the operations lead, for the owner
Smallest group reported: 5 answers
```

### 2. The response export from the survey tool

```
response_id,team,role,tools_used,how_often,what_for,paid_by,data_types_entered,what_would_help
R01,Design,Architect,Assistant A; Assistant B,daily; weekly,Drafting design narratives for planning applications; rewording client emails,company; free,internal documents; customer information,A shared set of instructions for the design narrative
R02,Design,Interior designer,Assistant A,weekly,Writing specification notes from my sketches list; rewording client emails,company,internal documents,Training on what we may put in
R03,Design,Architect,Assistant B,daily,Drafting design narratives; summarising planning policy documents,self,public information; internal documents,A company seat for Assistant B
R04,Design,Technician,none,,,,none,Someone to show me what it is good for
R05,Design,Architect,Assistant A; Meeting notes D,weekly; weekly,Notes from client meetings; drafting design narratives,company; company,customer information; confidential information,Clear rules on client drawings
R06,Design,Interior designer,Assistant A,monthly,Rewording client emails,company,customer information,Training on what we may put in
R07,Project delivery,Project manager,Assistant A,daily,Writing meeting minutes from my notes; drafting the weekly client progress report,company,customer information; internal documents,A template for the progress report
R08,Project delivery,Project manager,Assistant A; Assistant C,weekly; rarely,Drafting the weekly client progress report; checking contractor quotes against the scope,company; free,confidential information; internal documents,Know which assistant we should use
R09,Project delivery,Site coordinator,Assistant C,weekly,Writing up site meeting minutes for Sam,self,internal documents,A company seat
R10,Project delivery,Project manager,Meeting notes D,weekly,Notes from client meetings,company,customer information,A template for the progress report
R11,Project delivery,Project coordinator,none,,,,none,Know which assistant we should use
R12,Finance,Bookkeeper,Assistant B,weekly,Explaining spreadsheet formulas; drafting payment reminder emails,self,customer information; financial figures,A company seat for Assistant B
R13,Finance,Accounts assistant,Assistant C,monthly,Drafting payment reminder emails,free,customer information,Training on what we may put in
R14,Finance,Finance manager,none,,,,none,Know which assistant we should use
R15,Office,Office manager,Assistant B; Meeting notes D,daily; weekly,Drafting the staff newsletter; writing up the minutes of staff meetings,self; company,personal information; internal documents,A company seat for Assistant B
R16,Office,Receptionist,Assistant B,rarely,Rewording client emails,free,customer information,Someone to show me what it is good for
```

### 3. The subscription list from finance

```
tool,plan,seats,team
Assistant A,Team plan,8,Design
Assistant A,Team plan,4,Project delivery
Meeting notes D,Business plan,6,company-wide
```

### 4. The team list

```
team,headcount
Design,14
Project delivery,9
Finance,4
Office,3
```

### 5. The company's rule on information

```
Client drawings, contracts, fee figures and client emails go only into
Assistant A on the company's account. Nobody's personal details go into
any assistant.
```

## The output

**AI TOOLS IN USE: SURVEY SUMMARY, an illustrative architecture and interiors practice, survey closed Friday 13 November 2026**

- **For:** Operations lead, for the owner. Prepared from: the response export (16 rows), the subscription list (3 lines), the team list (4 teams), the company's rule on information (supplied). Smallest group reported: 5 answers.
- **Answers:** 16 of 30 people. Teams reported: 2. Teams held back: 2. The survey was answered without names. Every figure is a count of answers, not of everyone in a team.
- **Check:** 16 rows = 16 read + 0 unreadable.

**1. By team**

Design (6 answers of 14 people)

- In use: Assistant A: 4 (daily 1, weekly 2, monthly 1, rarely 0). Assistant B: 2 (daily 1, weekly 1, monthly 0, rarely 0). Meeting notes D: 1 (daily 0, weekly 1, monthly 0, rarely 0). No tool: 1.
- Paid by: company 5, self 1, free 1 (7 tool mentions).

Project delivery (5 answers of 9 people)

- In use: Assistant A: 2 (daily 1, weekly 1, monthly 0, rarely 0). Assistant C: 2 (daily 0, weekly 1, monthly 0, rarely 1). Meeting notes D: 1 (daily 0, weekly 1, monthly 0, rarely 0). No tool: 1.
- Paid by: company 3, self 1, free 1 (5 tool mentions).

Teams held back: Finance, Office, counted in the company total only (section 9).

**2. Company total (16 answers of 30 people)**

- In use: Assistant A: 6 (daily 2, weekly 3, monthly 1, rarely 0). Assistant B: 5 (daily 2, weekly 2, monthly 0, rarely 1). Assistant C: 3 (daily 0, weekly 1, monthly 1, rarely 1). Meeting notes D: 3 (daily 0, weekly 3, monthly 0, rarely 0). No tool: 3. Answers naming at least one tool: 13.
- Paid by: company 9, self 4, free 4 (17 tool mentions).

**3. Paid for by the company, by people themselves, or free**

- Assistant A: company 6, self 0, free 0. On the subscription list: yes.
- Assistant B: company 0, self 3, free 2. On the subscription list: no.
- Assistant C: company 0, self 1, free 2. On the subscription list: no.
- Meeting notes D: company 3, self 0, free 0. On the subscription list: yes.
- Said to be paid by the company but not on the subscription list: none.
- On the subscription list but named in no answer: none.

**4. Seats against answers (counts only)**

- Assistant A, Team plan, Design: 8 seats; 4 answers in that team say they use it on the company's account.
- Assistant A, Team plan, Project delivery: 4 seats; 2 answers in that team say they use it on the company's account.
- Meeting notes D, Business plan, company-wide: 6 seats; 3 answers across the company say they use it on the company's account.
- 16 of 30 people answered, so a seat with no answer against it may belong to someone who did not answer.

**5. Pieces of work, in people's own words**

- Meeting minutes and notes: 5 answers (R05, R07, R09, R10, R15). Teams: Design, Project delivery; also teams held back. Their words: "Notes from client meetings"; "Writing meeting minutes from my notes"; "Writing up site meeting minutes for [name removed]"; "writing up the minutes of staff meetings".
- Rewording client emails: 4 answers (R01, R02, R06, R16). Teams: Design; also teams held back. Their words: "rewording client emails".
- Drafting design narratives: 3 answers (R01, R03, R05). Teams: Design. Their words: "Drafting design narratives for planning applications"; "Drafting design narratives".
- Drafting payment reminder emails: 2 answers (R12, R13). Teams: teams held back only. Their words: "drafting payment reminder emails".
- Drafting the weekly client progress report: 2 answers (R07, R08). Teams: Project delivery. Their words: "drafting the weekly client progress report".
- Checking contractor quotes against the scope: 1 answer (R08). Teams: Project delivery. Their words: "checking contractor quotes against the scope".
- Drafting the staff newsletter: 1 answer (R15). Teams: teams held back only. Their words: "Drafting the staff newsletter".
- Explaining spreadsheet formulas: 1 answer (R12). Teams: teams held back only. Their words: "Explaining spreadsheet formulas".
- Summarising planning policy documents: 1 answer (R03). Teams: Design. Their words: "summarising planning policy documents".
- Writing specification notes: 1 answer (R02). Teams: Design. Their words: "Writing specification notes from my sketches list".

**6. Set apart for the owner: customer, personal or confidential information**

For the owner only; remove before sharing.

The company's rule, as supplied: "Client drawings, contracts, fee figures and client emails go only into Assistant A on the company's account. Nobody's personal details go into any assistant."

- R01, Design. Assistant A (company); Assistant B (free). Ticked: internal documents, customer information. Their words: "Drafting design narratives for planning applications; rewording client emails".
- R02, Design. Assistant A (company). Ticked: internal documents. Not ticked; the answer mentions "client emails". Their words: "Writing specification notes from my sketches list; rewording client emails".
- R05, Design. Assistant A (company); Meeting notes D (company). Ticked: customer information, confidential information. Their words: "Notes from client meetings; drafting design narratives".
- R06, Design. Assistant A (company). Ticked: customer information. Their words: "Rewording client emails".
- R07, Project delivery. Assistant A (company). Ticked: customer information, internal documents. Their words: "Writing meeting minutes from my notes; drafting the weekly client progress report".
- R08, Project delivery. Assistant A (company); Assistant C (free). Ticked: confidential information, internal documents. Their words: "Drafting the weekly client progress report; checking contractor quotes against the scope".
- R10, Project delivery. Meeting notes D (company). Ticked: customer information. Their words: "Notes from client meetings".
- R12, team held back. Assistant B (self). Ticked: customer information, financial figures. Their words: "Explaining spreadsheet formulas; drafting payment reminder emails".
- R13, team held back. Assistant C (free). Ticked: customer information. Their words: "Drafting payment reminder emails".
- R15, team held back. Assistant B (self); Meeting notes D (company). Ticked: personal information, internal documents. Their words: "Drafting the staff newsletter; writing up the minutes of staff meetings".
- R16, team held back. Assistant B (free). Ticked: customer information. Their words: "Rewording client emails".

11 answers set apart.

**7. Candidates for the opportunity scorecard**

1. Meeting minutes and notes: named in 5 answers. Teams: Design, Project delivery; also teams held back.
2. Rewording client emails: named in 4 answers. Teams: Design; also teams held back.
3. Drafting design narratives: named in 3 answers. Teams: Design.
4. Drafting payment reminder emails: named in 2 answers. Teams: teams held back only.
5. Drafting the weekly client progress report: named in 2 answers. Teams: Project delivery.

The owner scores and chooses.

**8. What people said would help**

- A company seat: 4 answers. Teams: Design, Project delivery; also teams held back.
- Clear rules and training on what may go in: 4 answers. Teams: Design; also teams held back.
- Know which assistant to use: 3 answers. Teams: Project delivery; also teams held back.
- Shared instructions or templates for a piece of work: 3 answers. Teams: Design, Project delivery.
- Someone to show what it is good for: 2 answers. Teams: Design; also teams held back.

**9. Teams with too few answers to report**

- Finance (4 people): fewer than 5 answers. Counted in the company total only.
- Office (3 people): fewer than 5 answers. Counted in the company total only.
- Answers with no team: 0.

**10. Data gaps and questions**

- none

Draft for the operations lead, for the owner. Nobody is named, no use is judged, and nothing has been sent, bought, cancelled or changed.
