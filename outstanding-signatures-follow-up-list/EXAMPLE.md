# Outstanding signatures follow-up list: an example

*Illustrative example with sample data.* The business, its clients, the people, the documents and every date below are illustrative. Company A is an illustrative 45-person commercial cleaning business. Its clients appear as Client B to Client M. Kit Alvarez, the sales operations coordinator, sends service orders and renewals out for signature for the two account managers, Maya Ostrander and Joel Pemberton; Tomas Reyner, the operations director, approves some orders before the client signs. Every person named is illustrative.

On the morning of Tuesday 24 November 2026, a week before month end, Kit exported the status of every open signing request and ran the list. The inputs come first, in full, so the workflow template can be run on them. The draft list it returned follows.

## The inputs

### 1. The status export from your e-signature tool: signature_status.csv

One row for each signer of each document, with the columns document_id, document_name, document_type, sender, sent_at, recipient, recipient_role, signing_order, status, last_activity_at and expires_at.

```
document_id,document_name,document_type,sender,sent_at,recipient,recipient_role,signing_order,status,last_activity_at,expires_at
D-201,"Service order, Client B, office cleaning 2027",Service order,Maya Ostrander,2026-11-12 10:05,Lena Brookfield,Client signer,1,viewed,2026-11-16 14:20,2026-12-12
D-202,"Renewal order form, Client C",Renewal order form,Maya Ostrander,2026-11-18 09:00,Tomas Reyner,Internal approver,1,signed,2026-11-19 11:40,2026-11-28
D-202,"Renewal order form, Client C",Renewal order form,Maya Ostrander,2026-11-18 09:00,Grace Ilunga,Client signer,2,viewed,2026-11-20 16:05,2026-11-28
D-202,"Renewal order form, Client C",Renewal order form,Maya Ostrander,2026-11-18 09:00,Henrik Salo,Client executive sponsor,3,sent,2026-11-18 09:00,2026-11-28
D-203,"Site access form, Client E",Site form,Joel Pemberton,2026-11-23 15:30,Ana Kowal,Client signer,1,sent,2026-11-23 15:30,
D-204,"Service order, Client F, window cleaning",Service order,Joel Pemberton,2026-11-09 11:00,Rhea Castellan,Client signer,1,declined,2026-11-13 09:12,2026-12-09
D-205,"Renewal order form, Client G",Renewal order form,Maya Ostrander,2026-10-26 10:00,Paul Ndiaye,Client signer,1,expired,2026-11-02 08:30,2026-11-23
D-206,"Price change acknowledgement, Client H",Acknowledgement,Joel Pemberton,2026-11-10 14:00,Marta Quill,Client signer,1,voided,2026-11-11 09:45,2026-12-10
D-207,"Service order, Client J, deep clean",Service order,Maya Ostrander,2026-11-16 13:00,Ivo Marchetti,Client signer,1,signed,2026-11-17 10:10,2026-11-30
D-207,"Service order, Client J, deep clean",Service order,Maya Ostrander,2026-11-16 13:00,Sunita Varga,Client finance approver,1,viewed,2026-11-19 12:00,2026-11-30
D-208,"Service order, Client K, carpet care",Service order,Joel Pemberton,2026-11-17 09:30,Ben Okafor,Client signer,1,signed,2026-11-18 16:45,2026-12-17
D-209,"Service order, Client L, floor care",Service order,Joel Pemberton,2026-11-19 08:00,Tomas Reyner,Internal approver,1,viewed,2026-11-19 09:30,2026-12-19
D-209,"Service order, Client L, floor care",Service order,Joel Pemberton,2026-11-19 08:00,Bea Thornton,Client signer,2,sent,2026-11-19 08:00,2026-12-19
D-210,"Service order, Client M, 2027 renewal",Service order,Maya Ostrander,2026-11-13 09:00,Owen Hartley,Client executive sponsor,1,viewed,2026-11-17 10:00,2026-11-27
```

### 2. The team's follow-up rules, with today's date (typed by Kit)

```
Team: Sales operations, Company A
Today: Tuesday 24 November 2026
Export: signature_status.csv, exported 24 November 2026 08:30
Runs it: Kit Alvarez, sales operations coordinator
Reminder after: 3 days
Urgent document types: Renewal order form
Urgent reminder after: 1 day
Expiry window: 7 days
Reminders, by recipient_role:
- Client signer: the sender
- Internal approver: Kit Alvarez
- Client executive sponsor: not reminded from this list (the account manager raises it in person)
```

## The output

```
OUTSTANDING SIGNATURES FOLLOW-UP LIST: Sales operations, Company A, Tuesday 24 November 2026

For: Kit Alvarez and each sender. Prepared from signature_status.csv (14 rows, 10 documents), exported 24 November 2026 08:30; the team's rules (as supplied).
Count: 10 documents = 6 waiting + 1 declined + 1 expired + 1 voided + 1 fully signed.
Rows: 3 signed + 5 viewed + 3 sent + 1 declined + 1 expired + 1 voided = 14 rows in the export.
Waiting signers: 6 = 3 reminders drafted + 1 not yet due + 1 not reminded under the rules + 1 held for a question. Later signers not yet reached: 2.

1. Waiting for a signature
D-202 Renewal order form, Client C (Renewal order form, URGENT). Sent by Maya Ostrander on 18 November 2026, 6 days ago. Expires 28 November 2026.
  Waiting on: Grace Ilunga (Client signer, signing order 2), viewed, with them since 19 November 2026 (5 days), no activity for 4 days.
  Blocking 1 later signer: Henrik Salo (Client executive sponsor).
  Already signed: Tomas Reyner (Internal approver), 19 November 2026.
  Reminder: due, see R1.
D-201 Service order, Client B, office cleaning 2027 (Service order). Sent by Maya Ostrander on 12 November 2026, 12 days ago. Expires 12 December 2026.
  Waiting on: Lena Brookfield (Client signer, signing order 1), viewed, with them since 12 November 2026 (12 days), no activity for 8 days.
  Reminder: due, see R2.
D-210 Service order, Client M, 2027 renewal (Service order). Sent by Maya Ostrander on 13 November 2026, 11 days ago. Expires 27 November 2026.
  Waiting on: Owen Hartley (Client executive sponsor, signing order 1), viewed, with them since 13 November 2026 (11 days), no activity for 7 days.
  Reminder: not reminded: the account manager raises it in person.
D-207 Service order, Client J, deep clean (Service order). Sent by Maya Ostrander on 16 November 2026, 8 days ago. Expires 30 November 2026.
  Waiting on: Sunita Varga (Client finance approver, signing order 1), viewed, with them since 16 November 2026 (8 days), no activity for 5 days.
  Already signed: Ivo Marchetti (Client signer), 17 November 2026.
  Reminder: held, see question 1.
D-209 Service order, Client L, floor care (Service order). Sent by Joel Pemberton on 19 November 2026, 5 days ago. Expires 19 December 2026.
  Waiting on: Tomas Reyner (Internal approver, signing order 1), viewed, with them since 19 November 2026 (5 days), no activity for 5 days.
  Blocking 1 later signer: Bea Thornton (Client signer).
  Reminder: due, see R3.
D-203 Site access form, Client E (Site form). Sent by Joel Pemberton on 23 November 2026, 1 day ago. No expiry date.
  Waiting on: Ana Kowal (Client signer, signing order 1), sent, with them since 23 November 2026 (1 day), no activity for 1 day.
  Reminder: not yet due, next due 26 November 2026.

2. Expiring by 1 December 2026 (within 7 days)
D-210 Service order, Client M, 2027 renewal: expires 27 November 2026, in 3 days. Still to sign: Owen Hartley (Client executive sponsor).
D-202 Renewal order form, Client C: expires 28 November 2026, in 4 days. Still to sign: Grace Ilunga (Client signer), Henrik Salo (Client executive sponsor).
D-207 Service order, Client J, deep clean: expires 30 November 2026, in 6 days. Still to sign: Sunita Varga (Client finance approver).

3. Declined or expired: a decision for the sender
D-204 Service order, Client F, window cleaning (Service order), sent by Joel Pemberton on 9 November 2026: declined by Rhea Castellan (Client signer) on 13 November 2026. Signed before it stopped: nobody. For Joel Pemberton to decide what happens next.
D-205 Renewal order form, Client G (Renewal order form, URGENT), sent by Maya Ostrander on 26 October 2026: expired on 23 November 2026. Signed before it stopped: nobody. For Maya Ostrander to decide what happens next.

4. Reminder drafts, for approval before sending
R1. To: Grace Ilunga (Client signer). Sent by: Maya Ostrander. About: D-202.
Subject: Signature needed: Renewal order form, Client C
Hello Grace,
Maya Ostrander sent you Renewal order form, Client C for signature, and it reached you on 19 November 2026.
It is now your turn to sign, and one more person signs after you.
The signing request expires on 28 November 2026.
When you have a moment, please review and sign it,
or reply to me if anything needs to change first.
Thank you,
Maya Ostrander
R2. To: Lena Brookfield (Client signer). Sent by: Maya Ostrander. About: D-201.
Subject: Signature needed: Service order, Client B, office cleaning 2027
Hello Lena,
Maya Ostrander sent you Service order, Client B, office cleaning 2027 for signature, and it reached you on 12 November 2026.
The signing request expires on 12 December 2026.
When you have a moment, please review and sign it,
or reply to me if anything needs to change first.
Thank you,
Maya Ostrander
R3. To: Tomas Reyner (Internal approver). Sent by: Kit Alvarez. About: D-209.
Subject: Signature needed: Service order, Client L, floor care
Hello Tomas,
Joel Pemberton sent you Service order, Client L, floor care for signature, and it reached you on 19 November 2026.
It is now your turn to sign, and one more person signs after you.
The signing request expires on 19 December 2026.
When you have a moment, please review and sign it,
or reply to me if anything needs to change first.
Thank you,
Kit Alvarez

5. Closed: no follow-up
Voided: D-206 Price change acknowledgement, Client H, voided 11 November 2026.
Fully signed: 1 (D-208).

6. Questions for Kit Alvarez
1. D-207 Service order, Client J, deep clean: Sunita Varga's role, "Client finance approver", is not in the reminder rules, so no reminder was drafted. The document has been with her for 8 days with no activity for 5, and the request expires on 30 November 2026. May a client finance approver be reminded from this list, and who sends it?

Draft for Kit Alvarez and each sender. Read from the status export only; no document was opened.
Nothing has been sent, resent or voided, and no record has been changed.
```
