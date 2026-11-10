# Changelog

## Unreleased

- Survey questions: new optional questions 11–13 on prior regimes (RED Delegated Act / EN 18031, IEC 62443-4-1 and others), what carried over, and whether the same team is doing the CRA work. Suggested by Dishanth Chinnappa in [#1](https://github.com/Poojarav/compliance-relay/issues/1).

## 0.5.0

Prompted by feedback at the OpenSSF Global Cyber Policy Working Group (9 November 2026).

- **Company size.** Choose Micro, Small, Medium or Large (EU definitions) to see what the CRA treats differently for that size (Articles 33 and 64). The guide explains how size tends to move the bottleneck, as a pattern to test with your own numbers. Every timing input remains your own; no size-based assumptions are filled in.
- **Cost of being late.** Optional inputs for worldwide turnover and the product's EU revenue show the maximum CRA fine (€15M or 2.5% of turnover, whichever is higher) and the estimated EU sales at risk from the delay. Added to the spreadsheet too.
- Survey questions: new organization-size question so answers can be compared by size.
- The verdict now says "Just fits" instead of "Short by 0 weeks" when the work fits exactly.
- The printable worksheet is unchanged; size and cost are optional additions.

## 0.4.2

- Calculator: share a scenario as a link (the numbers stay inside the link; nothing is stored or sent), a "Start the clock today" button, and a jump link to the results
- Calculator: the sample now matches the guide's worked example exactly (clock starting 29 Oct 2026), so every format gives the same answer
- Calculator: results clear properly when the deadline is not after the clock start
- Clearer guidance on vacation, public holidays, on-call and holiday shutdowns, in the calculator, spreadsheet, worksheet and guide
- Guide: new "Where to get your numbers" section; corrected the worked example's recovery scenario (mid-cycle entry plus parallel interpretation gives 21.9 weeks) and added a table showing how the fixes interact; corrected the wording of the 39% survey figure
- Standards guidance no longer cites a specific draft deadline, since those dates have moved
- New SURVEY-QUESTIONS.md: a reusable question set for readiness surveys

## 0.4.1

- Re-release to register the archived, citable version on Zenodo. No changes to the framework or math.

## 0.4.0 (first public release)

- Web calculator, spreadsheet and one-page worksheet using the same constraints and math
- Guide with a worked CRA example and recovery practices
- New guidance on three practitioner-reported constraints: earliest checkpoint, mid-period capacity changes, and upstream release cadence
- Licenses: Apache 2.0 for code, CC BY 4.0 for documentation
- Issue templates for feedback and anonymized timeline data

## Planned next

- A conformity assessment step, for products that need a notified body, with the route and time as your inputs
- A checklist of CRA work areas to help estimate the engineering work
- Comparing two scenarios side by side
- Calculator inputs for an earlier checkpoint, capacity changes during the window, and upstream release cadence
