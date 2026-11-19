# Outstanding signatures follow-up list

Workflow template, version 0.1.0.

## Purpose

Prepare one follow-up list from the status export of an e-signature tool, for the person who sends documents out for signature. Every document still out is listed once with the signer it is waiting on, how long it has been with them and how long since their last activity. Where a signing order applies, the signer holding the later signers is named. Documents expiring within the team's warning window, and documents declined or expired, are set apart; a reminder is drafted for each waiting signer the team's rules say is due one; and a count ties every document and every row back to the export. The assistant prepares; it reads the export and never the documents, sends no reminder, resends, voids or corrects nothing, changes no record, and says nothing about whether a signature is valid or a document binding.

## When to use it and when not to

Use it twice a week, on the same days each week, and again in the last working days of the month. Each run starts from a status export taken that morning.

Do not use it:

- to decide whether a signature is valid, whether a signed document binds anyone, or whether work may start before a signature arrives. Those questions go to whoever in the company owns the document's terms;
- to read, summarise or compare the documents themselves. This workflow template reads the status export and nothing else;
- to send, resend, void or correct a signing request, or to change a recipient. A person does each of these in the tool;
- to chase a signer the team's rules say is never reminded from this list;
- for documents collected outside the e-signature tool, such as paper forms. They are not in the export and the count would not tie.

## Roles

- **Runs it:** the operations coordinator, the office manager or the sales operations person who sends documents out for signature.
- **Sets the follow-up rules:** the team lead, or whoever the team names; the rules are written once and changed only by that person.
- **Approves, edits and sends each reminder:** the person the rules name for that signer's role, usually the sender of the document.
- **Decides what happens to a declined or expired document:** its sender.
- **Answers questions about a document's terms or a signature's validity:** whoever in the company owns the document's terms. Never the assistant.

## Inputs

1. **The status export from your e-signature tool,** one row for each signer of each document. Default column headers: `document_id, document_name, document_type, sender, sent_at, recipient, recipient_role, signing_order, status, last_activity_at, expires_at`.
   - `sent_at` and `last_activity_at` are written `YYYY-MM-DD HH:MM`; `expires_at` is `YYYY-MM-DD` or blank for no expiry. All times are in the export's own time zone; nothing is converted.
   - `signing_order` is a whole number, 1 for the first to sign. Signers with the same number sign alongside each other. Blank on every row of a document means everyone signs alongside each other.
   - `status` is one of `sent`, `viewed`, `signed`, `declined`, `expired` or `voided`, read without regard to case or surrounding spaces.
   - `last_activity_at` is the last time anything happened on that signer's row: sent, viewed, reminded, signed or declined.
   If a header does not match, stop, show the expected and the found headers, and ask which column is which. If a status word is not one of the six, stop, list each row and the word, and ask what it means in the team's tool.
2. **The team's follow-up rules.** Default form:
   - `Reminder after: [n] days` without activity. If missing, use 3 days and say so.
   - `Urgent document types: [types]`, matched to `document_type` exactly, and `Urgent reminder after: [n] days`. If missing, treat no type as urgent and say so.
   - `Expiry window: [n] days`. If missing, use 7 days and say so.
   - `Reminders, by recipient_role:` one line per role, either `[role]: [who sends]`, where who sends is "the sender" or a named person or role, or `[role]: not reminded from this list ([reason])`. If this part is missing, draft no reminder: list each due reminder as held and ask for the rule.
3. **Today's date,** and when the export was taken. If today's date is missing, stop and ask. If the export time is missing, continue and write "export time not stated".
4. **Who runs it:** the name or role that appears on the list and in the questions.

The assistant works only from what the person supplies. It needs no connection to the e-signature tool, opens no document and never asks for a password or a login code.

## The procedure

1. **Check the export.** Confirm the headers and the status words as set out under Inputs. Stop and ask when: two rows share the same `document_id` and `recipient`; a date or time cannot be read; the rows of one document disagree on `document_name`, `document_type`, `sender`, `sent_at` or `expires_at`; a document mixes blank and numbered `signing_order`, or an order is not a whole number; a `last_activity_at` is earlier than its `sent_at`. Count the rows and the distinct `document_id` values.
2. **Give each document one state,** taking the first that applies: **voided** if any row is voided; **declined** if any row is declined; **expired** if any row is expired; **fully signed** if every row is signed; otherwise **waiting**. Check that waiting + declined + expired + voided + fully signed equals the number of documents, and that the rows by status add up to the rows in the export. If either does not tie, stop and show the difference.
3. **Find whose turn it is,** for each waiting document. The waiting signers are the unsigned rows with the lowest `signing_order` among the unsigned rows; when the orders are blank, every unsigned row. Unsigned rows with a higher order are later signers not yet reached: they get no reminder, whatever their status says. If a row is signed at a higher order while a lower one is unsigned, keep the lowest unsigned as the turn and raise a question.
4. **Count the days,** in whole calendar days from the date part of each time to today's date:
   - days since sent: today − `sent_at`;
   - reached on: `sent_at` for the first in the order (every signer at the lowest `signing_order` among all of the document's rows counts as first, and so does every signer when the orders are blank); for a later signer, the latest `last_activity_at` among the signed rows with a lower order;
   - days with this signer: today − reached on;
   - quiet since: the later of reached on and the signer's own `last_activity_at`; days quiet: today − quiet since.
5. **Decide each waiting signer's reminder,** in this order:
   - the rules say the role is not reminded from this list: "not reminded", with the reason the rules give;
   - the role is not in the rules, or the reminder part of the rules is missing: "held", and a question;
   - the document's `expires_at` is before today: "held", and a question (see step 6);
   - days quiet is at or above the wait (the urgent wait for an urgent document type, otherwise the ordinary wait): "due", and a draft under step 8;
   - otherwise: "not yet due", with the next due date, which is quiet since + the wait.
6. **Find the expiries.** A waiting document whose `expires_at` falls from today to today + the window, both included, goes under Expiring, with the days left and every signer still to sign, reached or not. A waiting document whose `expires_at` is before today is listed there as "past its expiry date but not shown as expired", with a question; no reminder is drafted for it.
7. **Set out declined and expired documents** for their sender: who declined and on which date (that row's `last_activity_at`), or the expiry date (`expires_at`, or the latest `last_activity_at` when it is blank), and who signed before it stopped. Recommend nothing: the sender decides whether to correct and resend, replace or close it. An expired row whose last activity is long before its expiry date raises no question; use the dates as the export gives them.
8. **Draft each due reminder** in the fixed wording of the output format, from the export's facts only: the signer's first name as the export gives it, the document's name, its sender, the date it reached the signer, the number of later signers in words, and the expiry date if there is one. Leave out a line whose fact is absent: when no one signs later, drop the whole "It is now your turn" line. The person who sends it is the one the rules name for the role, and "the sender" means the document's `sender`. Add nothing about the document's content, what signing commits anyone to, or what happens if they do not sign. Include no signing link.
9. **List the closed documents:** each voided document with the date of its voided row's `last_activity_at`, and the number of fully signed documents with their ids.
10. **Write the questions,** numbered, facts first, for the person who runs it: each signer held for a missing rule; each document past its expiry date but not shown as expired; each signature out of order. Recommend nothing.
11. **Order and return the list.** Waiting documents: urgent types first, then by days with the current signer, longest first, then by `document_id`. Expiring: soonest first. Number the reminder drafts R1, R2 in the order their documents appear under Waiting. Return the draft to the person who ran it; each reminder goes to the person who sends it for approval.

## Exceptions and stop conditions

- **A header that does not match, a status word that is not one of the six, no today's date, a repeated document and recipient, a date or time that cannot be read, rows of one document that disagree, an unreadable signing order, or activity dated before sending:** stop, show what was found, and ask.
- **The counts do not tie to the export:** stop and show the difference; never leave a row out to make them tie.
- **Asked to send, resend, void or correct a request, change a recipient, or update the export:** decline; a person does each of these in the tool.
- **Asked to open, read or summarise a document, or to pull a signing link from it:** decline; this workflow template reads the status export only.
- **Asked whether a signature is valid, whether a document binds anyone, or whether work can start before signing:** decline, and record it as a question for whoever owns the document's terms.
- **Asked to make a reminder firmer, add a deadline the export does not show, or say what happens if the signer does not sign:** decline; a reminder states only facts from the export, and the sender may change it before sending.
- **Asked to remind a signer the rules say is never reminded from this list, or to remind a later signer not yet reached:** decline, and show the rule or the signing order.
- **The export holds a password, a login code, an access link with a token, or personal details beyond a name and role:** do not repeat them; tell the person to remove them from the file.

## Output format

```
OUTSTANDING SIGNATURES FOLLOW-UP LIST: [team], [weekday date]

For: [who runs it] and each sender. Prepared from [file] ([n] rows, [n] documents), exported [date time / export time not stated]; the team's rules ([as supplied / defaults used for: [rules]]).
Count: [n] documents = [n] waiting + [n] declined + [n] expired + [n] voided + [n] fully signed.
Rows: [n] signed + [n] viewed + [n] sent + [n] declined + [n] expired + [n] voided = [n] rows in the export.
Waiting signers: [n] = [n] reminders drafted + [n] not yet due + [n] not reminded under the rules + [n] held for a question. Later signers not yet reached: [n].

1. Waiting for a signature
[document_id] [document_name] ([document_type][, URGENT]). Sent by [sender] on [date], [n] days ago. [Expires [date]. / No expiry date.]
  Waiting on: [recipient] ([recipient_role][, signing order [n]]), [status], with them since [date] ([n] days), no activity for [n] days.
  [Blocking [n] later [signer / signers]: [recipient] ([recipient_role])[, ...].]
  [Already signed: [recipient] ([recipient_role]), [date][, ...].]
  Reminder: [due, see R[n] / not yet due, next due [date] / not reminded: [reason from the rules] / held, see question [n]].
/ Nothing is waiting for a signature.

2. Expiring by [date] (within [n] days)
[document_id] [document_name]: expires [date], in [n] days. Still to sign: [recipient] ([recipient_role])[, ...].
[document_id] [document_name]: past its expiry date of [date] but not shown as expired. See question [n].
/ Nothing waiting expires by [date].

3. Declined or expired: a decision for the sender
[document_id] [document_name] ([document_type][, URGENT]), sent by [sender] on [date]: [declined by [recipient] ([recipient_role]) on [date] / expired on [date]]. Signed before it stopped: [recipient] ([recipient_role])[, ...] / nobody. For [sender] to decide what happens next.
/ Nothing was declined or has expired.

4. Reminder drafts, for approval before sending
R[n]. To: [recipient] ([recipient_role]). Sent by: [who sends under the rules]. About: [document_id].
Subject: Signature needed: [document_name]
Hello [first name],
[sender] sent you [document_name] for signature, and it reached you on [date].
[It is now your turn to sign, and [number in words] more [person signs / people sign] after you.]
[The signing request expires on [date].]
When you have a moment, please review and sign it,
or reply to me if anything needs to change first.
Thank you,
[who sends]
/ No reminder is due.

5. Closed: no follow-up
Voided: [document_id] [document_name], voided [date][; ...]. / Voided: none.
Fully signed: [n] ([document_ids]). / Fully signed: none.

6. Questions for [who runs it]
[n]. [The facts.] [The question.]
/ None.

Draft for [who runs it] and each sender. Read from the status export only; no document was opened.
Nothing has been sent, resent or voided, and no record has been changed.
```

When several signers sign alongside each other and more than one is still to sign, give each its own "Waiting on" line followed by its own "Reminder" line. Write dates in words, such as "24 November 2026", and keep the export's own form only when naming a value in it. Write every day count as a whole number of days, and write "1 day" for one.

## Reviewer checklist

1. The count line ties: every document and every row of the export is accounted for, and the waiting signers add up. (Person who runs it)
2. Each waiting document names the right signer, and in a signing order the later signers are listed as blocked, not reminded. (Person who runs it)
3. Every day count matches the export's dates and today's date. (Person who runs it)
4. Every reminder goes to a role the rules allow, from the person the rules name, and states nothing the export does not show. (Each sender)
5. Every expiring document is on the list, and anything past its expiry date is a question, not a reminder. (Person who runs it)
6. Every declined or expired document has a decision from its sender. (Each sender)
7. No reminder is sent, and nothing is resent or voided, until its sender has approved it. (Each sender)
8. No line gives a view on whether a signature is valid or a document binding. (Team lead)

## Acceptance tests

Proposed tests. None has been run.

1. **Ordinary week.** Five single-signer documents, two due a reminder. Expected: two drafts, three "not yet due" with their next due dates, and the counts tie.
2. **Renamed column.** The export says `signer_email` in place of `recipient`. Expected: stops, shows expected and found headers, asks; nothing drafted.
3. **Unknown status word.** One row says `delivered`. Expected: stops, lists the row and the word, asks.
4. **Signing order.** Three signers; the first has signed, the second has viewed, the third shows `sent`. Expected: waiting on the second, the third listed as blocked, one reminder only, to the second.
5. **Reached date.** The second signer was reached when the first signed. Expected: days with this signer counted from the first signer's signing date, not from the sent date.
6. **Urgent type.** An urgent document quiet for two days, urgent wait 1 day, ordinary wait 3. Expected: due, and marked URGENT at the top of Waiting.
7. **Role missing from the rules.** Expected: no draft, "held", and a question.
8. **Role never reminded.** Expected: "not reminded", with the reason from the rules; no draft.
9. **Expiry inside the window.** Expected: listed under Expiring with the days left and every signer still to sign.
10. **Past its expiry date but still waiting.** Expected: listed as past its expiry date, a question, no reminder.
11. **Declined and expired documents.** Expected: under Declined or expired with who and when, and who signed before; no recommendation.
12. **Asked to send the reminders.** Expected: declines; a person sends each one.
13. **Asked whether a signed document is binding.** Expected: declines and records the question for whoever owns the document's terms.

## Instructions for the AI assistant

```
You prepare one outstanding signatures follow-up list from an
e-signature tool's status export, for the person who sends documents
out for signature. You prepare; people decide and act. You read the
status export only, never the documents. You never send a reminder,
resend, void or correct a signing request, change a recipient or
change any record: a person approves and does each of these in the
tool. You give no view on whether a signature is valid or a document
binding. You never ask for a password or a login code and need no
connection to any tool.

The user will supply: the status export (document_id, document_name,
document_type, sender, sent_at, recipient, recipient_role,
signing_order, status, last_activity_at, expires_at); the team's
follow-up rules (reminder wait in days, urgent document types and
their wait, expiry window, and for each recipient_role who sends its
reminder or that it is not reminded from this list); today's date;
the export time; and who runs it. Status is one of sent, viewed,
signed, declined, expired, voided. If a header does not match, stop,
show expected and found, and ask; never guess a column. If a status
word is not one of the six, stop, list the rows, and ask. Stop and
ask if today's date is missing, a document and recipient repeat, a
date cannot be read, rows of one document disagree on name, type,
sender, sent_at or expires_at, signing_order mixes blank and numbers
or is not a whole number, or last_activity_at is before sent_at.
Missing waits: reminder 3 days, expiry window 7 days, no urgent
types; say defaults were used. Missing reminder rules: draft nothing,
hold each due reminder and ask.

1. State per document, first that applies: voided, declined,
   expired, fully signed, else waiting. The states must add up to the
   documents and the statuses to the rows; if not, stop and show it.
2. Whose turn: unsigned rows at the lowest signing_order among the
   unsigned (all unsigned when orders are blank). Higher unsigned rows
   are later signers not yet reached: never reminded. A signature at a
   higher order than an unsigned row: question.
3. Days, whole calendar days from the date part to today: since sent;
   reached on = sent_at for the first in order (everyone at the
   lowest signing_order of the document counts as first, and so does
   everyone when orders are blank), else the latest
   last_activity_at of signed rows at a lower order; with this signer
   = today - reached on; quiet since = later of reached on and the
   signer's last_activity_at; days quiet = today - quiet since.
4. Reminder per waiting signer, first that applies: role not
   reminded under the rules -> "not reminded" with the reason; role
   not in the rules or rules missing -> "held" and a question;
   expires_at before today -> "held" and a question; days quiet at or
   above the wait (urgent wait for urgent types) -> "due" and a draft;
   else "not yet due" with next due = quiet since + wait.
5. Expiring: waiting documents with expires_at from today to today +
   window, both included, with days left and every signer still to
   sign. Past expires_at but waiting: "past its expiry date but not
   shown as expired", a question, no reminder.
6. Declined or expired: who declined and when, or the expiry date,
   and who signed before; the sender decides; recommend nothing. An
   expired row whose last activity is long before expires_at raises
   no question.
7. Drafts in the fixed wording only, from the export's facts: first
   name, document name, sender, reached-on date, later signers in
   words, expiry date if any. Drop a line whose fact is absent: with
   no later signer, drop the whole "It is now your turn" line. Write
   "1 day" for one day. Sent by the person the rules name; "the
   sender" means the document's sender. Nothing about the content,
   what signing commits anyone to or what happens if they do not
   sign. No signing link.
8. Closed: voided documents with their date; fully signed count and
   ids.
9. Questions numbered, facts first, for whoever runs it.
10. Order: waiting by urgent type first, then days with the current
    signer, longest first, then document_id; expiring soonest first;
    drafts R1, R2 in the order of Waiting.
11. Use the output format supplied with these instructions exactly
    (if it was not supplied, stop and ask for it), every section in
    order, printing a section's "none" line when it is empty. Write
    dates in words. End with the two closing lines.

If asked to send, resend, void or correct anything, decline: a
person does it in the tool. If asked to open or summarise a
document, decline. If asked whether a signature is valid or a
document binding, decline and record it as a question for whoever
owns the document's terms. If asked to make a reminder firmer or add
a deadline the export does not show, decline. Never remind a later
signer or a role the rules exclude. Do not repeat a password, login
code, tokened link or personal details beyond name and role found in
the export; tell the user to remove them. Check every count and day
against the export before you return the list.
```

## What to customize

- Your export's column headers and status words, if your e-signature tool names them differently. The assistant stops and asks on any mismatch, so rename the columns in the file before you supply it, or say in the run which column is which.
- The reminder wait, the urgent document types and their wait, and the expiry warning window.
- For each signer role, who may remind them and who sends it, and which roles are never reminded from this list.
- The reminder wording: keep it to facts the export shows, in your own team's voice.
- The days of the week it runs, and the extra run before month end.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 19 November 2026. Written by FullyPowered AI as original work, with no third-party text. Editorially reviewed. Tried on its invented example on 19 November 2026; the record is published with it, with the small edits made after the first run and a second run on the edited example by the editing session, not a blind run. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
