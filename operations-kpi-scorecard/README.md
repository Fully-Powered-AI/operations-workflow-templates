# Operations KPI scorecard

Get one red-amber-green page each month for the measures that run the operation, with the working shown. You set the measures and decide the actions.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** This is a template, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See Operations KPI scorecard on our website](https://fullypowered.ai/workflows/operations-kpi-scorecard/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard). Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Quick start**

1. Read EXAMPLE.md to see what a good result looks like.
2. Copy all of TEMPLATE.md into your assistant, then give it your own inputs, or the sample ones from EXAMPLE.md.
3. Read what comes back. It marks what it checked and what is left for you.

*Workflow template · Operations and process improvement · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/operations-kpi-scorecard/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard)*

## The outcome

The monthly review starts from one page everybody trusts. Every measure is written down once, with its definition, its formula, a target, a red level and one named owner, so nobody argues about what a number means. Each value comes with its working, so anyone can follow it back to the export it came from.

No red sits unanswered from one month to the next. The page shows every red beside the action agreed for it, with an owner and a date. A red with nothing open against it becomes a question for the operations manager, and so does an action past its due date.

Your people choose the measures, set the targets and agree the actions. The AI assistant reads the exports, does the arithmetic, applies your rules and lays out the page. It invents no reason for a move, proposes no action unless asked, rates no individual and sends nothing.

## Who starts the work, and when

The operations manager, or an analyst or coordinator working for them, runs it once a month after the month's exports are out. A first run before the operations review shows where the reds are and which have no action yet. A second run, after the review has agreed the actions and they are in the action list, gives the scorecard that is kept and shared.

## What they supply

- **The measure sheet:** ten measures at most, each with a definition, a formula, the export it reads, a target, a red level, which direction is good, one owner, and whether it signals trouble ahead or reports results already in.
- **The month's exports:** from the warehouse, production, transport, stock or service systems, as summary rows or line by line.
- **The scorecard history:** earlier months' values and statuses, for the trend.
- **The action list:** what was agreed at this and earlier reviews, with owners, dates and statuses.
- **A short note from each owner** on why their measure moved.

## What comes out

One scorecard in a fixed order: the overall count of reds, ambers and greens; every measure with its value, status, three-month trend and owner; the working for every value; what moved and why, in the owner's words; each red with its agreed actions; each amber with its distance from target and from red; last month's actions with the overdue ones marked; checks on the measure sheet itself; and numbered questions for the operations manager.

When data for a measure is missing, the page says so and asks; it never reads a missing month as zero. When an export's columns do not match what the measure sheet expects, the work stops and asks which column is which.

See the worked example in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Operations and process improvement](https://fullypowered.ai/functions/operations-and-process-improvement/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard), which owns the measures that show whether the operation is running well and what to fix next.
- [Analytics and reporting](https://fullypowered.ai/functions/analytics-and-reporting/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard), where the same numbers are produced the same way every month from the same exports.
- [Manufacturing](https://fullypowered.ai/industries/manufacturing/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard), where output, scrap, downtime and on-time delivery decide the month.
- [Logistics and trade](https://fullypowered.ai/industries/logistics-and-trade/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard), where dispatch, picking accuracy and first-time delivery are watched every day.
- [Ecommerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard), where orders shipped on time, stock-outs and returns shape what customers come back for.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard), where the monthly numbers live in several systems and one person's spreadsheet.
- [Growth and scaling](https://fullypowered.ai/situations/growth-and-scaling/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard), when volume grows faster than anyone's feel for whether the operation is keeping up.

## What has to change for your company

Choose your measures with the people who own them, and write each one down: what it counts, the formula, the export it reads, the target, the red level and one owner. Keep to ten. Agree who adds owners' notes and by which day after the month ends, when the operations review is held, and who keeps the action list. Decide your action statuses and who receives the approved page. It runs in ChatGPT, Claude, Copilot or Gemini, from the exports and notes you supply; it needs no access to any system.

## What has been checked

FullyPowered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried on its example in Claude on 10 November 2026; the record of that run is published with it, and lists the small edits made afterward that have not been run again. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on two or three past months your operations manager already knows, with hard cases written in advance: a value exactly on its red level, a renamed export column, a month with no rows, a team named as an owner, a red whose only action is already done. The operations manager checks every value against its working before anyone relies on the page. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard) sets those cases up, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard) describes the record we keep.

- Written by FullyPowered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete workflow template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the workflow template drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related workflow templates

- [Incident investigation and corrective actions](../incident-investigation-and-corrective-actions/)
- [SOP exception capture](../sop-exception-capture/)
- [Budget-versus-actual variance commentary](https://fullypowered.ai/workflows/budget-versus-actual-variance-commentary/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard)

## Make it yours

This workflow template is an example and a starting point. FullyPowered AI adapts it to how your company works, proves it on real work and rolls it out to the roles that use it. We can also build any other workflow for your company, including one that runs several steps, in a Workflow Sprint or a scoped implementation. [Talk with us](https://fullypowered.ai/contact/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=operations-operations-kpi-scorecard&from=gh-operations-operations-kpi-scorecard).
