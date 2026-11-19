# Trial: Outstanding signatures follow-up list, run on its example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (claude-sonnet-5-5)
- **Date:** 2026-11-19

The inputs are the example published beside this template. No client data was used. The assistant did not write the template. It read the instructions and the two sample inputs (the status export and the team's follow-up rules with today's date, 24 November 2026) in [example.md](example.md), and produced the list before reading the example's output.

## First run: what came out

This is the record of the first run, kept as it was. In the example as it stood then, Tomas Reyner signed D-202 on 18 November 2026, so the first run's D-202 facts (Grace Ilunga with the document since 18 November, 6 days) were computed from that date. The example has since changed; see the second run below.

The list had all six sections, in order, and the closing lines.

- **Counts:** 10 documents = 6 waiting + 1 declined + 1 expired + 1 voided + 1 fully signed. Rows: 3 signed + 5 viewed + 3 sent + 1 declined + 1 expired + 1 voided = 14. Waiting signers: 6 = 3 reminders drafted + 1 not yet due + 1 not reminded + 1 held. Later signers not yet reached: 2.
- **Waiting, in order:** D-202 (urgent; Grace Ilunga, 6 days with her, 4 quiet, due), D-201 (Lena Brookfield, 12 days, 8 quiet, due), D-210 (Owen Hartley, not reminded under the rules), D-207 (Sunita Varga, role missing from the rules, held), D-209 (Tomas Reyner, due), D-203 (Ana Kowal, not yet due, next due 26 November 2026).
- **Blocked later signers, not reminded:** Henrik Salo on D-202 and Bea Thornton on D-209.
- **Expiring by 1 December 2026:** D-210 (3 days), D-202 (4 days), D-207 (6 days).
- **Declined or expired:** D-204 declined by Rhea Castellan on 13 November 2026; D-205 expired on 23 November 2026. Nobody had signed either. No recommendation made.
- **Reminder drafts:** R1 to Grace (from Maya Ostrander), R2 to Lena (from Maya Ostrander), R3 to Tomas (from Kit Alvarez), each in the fixed wording, with no link and nothing about the document's content.
- **Closed:** D-206 voided on 11 November 2026; one document fully signed (D-208).
- **Questions:** one, whether a "Client finance approver" may be reminded from this list and who sends it.

## First run: what was observed

- Every required part was produced. Nothing in the instructions told the assistant to stop, and nothing was stopped for: the headers, status words, dates and signing orders in the export were all valid, and the counts tied.
- The output matched the published example in every fact: counts, ordering, day counts, due dates, expiry list, reminder drafts and question. The differences were small wording choices only, such as whether to bold labels.
- Every fact in the output was in the inputs. The example's output adds nothing that is not in them either; its introduction (the business, the roles) is framing around the inputs.
- Where the template left room for a guess:
  1. The reminder wording has one bracketed line, "It is now your turn to sign, and [number] more [person signs / people sign] after you." The template does not say that the whole line goes when nobody signs later. The assistant read the rule "leave out a line whose fact is absent" that way, and the example does the same for R2, but a reader could keep half of it.
  2. The format writes "[n] days" in several places, and the template does not say to write "1 day" for one. The assistant used "1 day", as the example does.
  3. For a document whose signers sign alongside each other (D-207), the template says "reached on" is the sent date for "the first in the order". The assistant took everyone at the lowest order as reached on the sent date. This is a reasonable reading, not a stated one.
  4. The rule that no reminder is drafted for a held signer sits in two places (step 5 and the exceptions); the assistant found them consistent.
  5. D-205's expired row has its last activity on 2 November 2026, three weeks before its expiry date of 23 November 2026. The template says to use the expiry date, so the assistant did, and it raised no question. A reader might expect one.
- The acceptance tests in the template are still marked proposed, and only the ordinary-week case was exercised here. The stop conditions, the decline conditions and the urgent-type and signing-order edge cases were not tested by this run.
- This was one run, by one model, on the example only. It shows the instructions can be followed to the published output. It says nothing about client data or other AI products.

## Edits made after the first run

After the independent review, edits were made to the template, the profile and the example:

- The template says to drop the whole "It is now your turn" line when no one signs later, and to write "1 day" for one day.
- The template says that every signer at the lowest signing order of a document counts as first, and so does every signer when the orders are blank.
- The template notes that an expired row whose last activity is long before its expiry date raises no question.
- The profile lists who runs the list among what you supply, and the extra checks that stop the work.
- The block now says the output format is supplied with the instructions and to stop and ask if it is missing; one long line in the block was rewrapped; and the suggestion to add a mapping line to the rules was dropped, since the template stops and asks on any header mismatch.
- The example's output is now set in the same plain form as the template's output format.
- In the example, Tomas Reyner's signing of D-202 moved from 18 to 19 November 2026, so that the rule that a later signer's days count from the earlier signer's signing date shows in the example (Grace Ilunga is reached on 19 November, not on the sent date of 18 November).

## Second run, after those edits

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (claude-sonnet-5-5)
- **Date:** 2026-11-19

This second run was made by the same session that made the edits, working through the edited instructions and the edited sample inputs step by step. It was not blind: the first run's output and the example's output were in view. It was not a fresh session with a separate model.

- The counts tied as before: 10 documents = 6 waiting + 1 declined + 1 expired + 1 voided + 1 fully signed; 14 rows; 6 waiting signers = 3 reminders + 1 not yet due + 1 not reminded + 1 held; 2 later signers not yet reached. Nothing was stopped for.
- Two facts changed from the first run, both because of the moved date. D-202: Grace Ilunga has had the document since 19 November 2026 (5 days, not 6), and she has been quiet since 20 November (4 days, unchanged), so her reminder is still due under the urgent wait of 1 day. Tomas Reyner's signature on D-202 is dated 19 November 2026. R1 now says the document reached her on 19 November 2026.
- Everything else matched the first run: the order of the waiting list (D-202 first as urgent, then D-201, D-210, D-207, D-209, D-203), the expiry list, the declined and expired documents, R2 and R3, the closed documents and the one question.
- The output was set out in the plain-line form of the output format. The block's closing line and the output format were read against each other and agree.
- Still not exercised: the stop conditions, the decline conditions, and the other acceptance tests, which remain proposed. This is one self-run on the example, not a test in a client environment or in other AI products.
