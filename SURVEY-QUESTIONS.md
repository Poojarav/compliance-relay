# Survey questions: why do organizations expect to be late?

Readiness surveys show *whether* organizations expect to meet a regulatory deadline. In the 2026 CRA Awareness and Readiness Report, only 41% of manufacturers expected full compliance by December 2027. These questions are designed to show *why*, by measuring how much of the transition period actually reaches engineering teams.

Each question maps to one constraint in the Compliance Relay, so answers can be compared across organizations and fed back into the calculator's sample values. Survey designers are welcome to use, shorten or adapt them (CC BY 4.0). Most can be answered in under five minutes.

## Core questions

0. **Organization size.** How many people work in your organization? *(Lets every other answer be compared by size.)*
   *Under 10 · 10–49 · 50–249 · 250–999 · 1,000 or more*
   → Company size

1. **Time to engineering.** Roughly how long after your organization started work on the CRA did the first CRA requirement reach an engineering team's backlog?
   *Less than 1 month · 1–3 months · 3–6 months · 6–12 months · More than 12 months · Not yet · Don't know*
   → Handoffs

2. **Handoff path.** Which functions did CRA requirements pass through before engineering received work? *(Select all that apply)*
   *Legal · Compliance · Security · Product management · Platform or tooling teams · External consultants · Other*
   → Handoffs

3. **Sequence.** Did those functions work mostly in sequence (one after another) or in parallel?
   *Mostly in sequence · Partly in parallel · Mostly in parallel · Don't know*
   → Handoffs

4. **Waiting on standards.** Are you delaying any CRA engineering decisions until harmonised standards or official guidance are available?
   *Yes, most decisions · Yes, some decisions · No · Don't know*
   → Waiting on guidance

5. **Planning.** Can regulatory work enter your engineering plans mid-cycle, or does it wait for the next planning cycle?
   *Can enter mid-cycle · Waits for the next cycle · Depends on the team · Don't know*
   → Planning

6. **Dependencies.** Is your CRA work waiting on other teams, suppliers or upstream open-source projects to deliver first?
   *Yes, significantly · Yes, somewhat · No · Don't know*
   → Dependencies

7. **Capacity.** Roughly what share of the affected engineering teams' time is available for CRA work, after other priorities, on-call and time off?
   *Under 10% · 10–25% · 25–50% · Over 50% · No dedicated time · Don't know*
   → Capacity

8. **Earliest checkpoint.** How far before 11 December 2027 must your evidence be complete for an internal audit, readiness review or certification step?
   *Same date · 1–3 months earlier · 3–6 months earlier · More than 6 months earlier · Don't know*
   → Release and evidence

9. **Biggest source of delay.** Which of these most limits your ability to meet the CRA deadline? *(Select up to two)*
   *Time to interpret and hand off requirements · Waiting for standards or guidance · Planning cycles · Dependencies on other teams or projects · Limited engineering capacity · Code freezes or release schedules · Preparing evidence for audits · Other*
   → All constraints

## Optional question on planning tools

10. **Planning the timeline.** Has your organization estimated how much engineering time remains before the CRA deadline, after these constraints?
    *Yes, formally · Yes, informally · No, but it would be useful · No, and it would not be useful · Don't know*

## Optional questions on prior regimes

Suggested by Dishanth Chinnappa ([issue #1](https://github.com/Poojarav/compliance-relay/issues/1)). Organizations that have already met an earlier product cybersecurity regime may start the CRA with part of the interpretation and handoff work done. These questions test whether that explains some of the difference between organizations.

11. **Prior regimes.** Before starting CRA work, had your organization (or the product line you're answering for) already met the requirements of any of these? *(Select all that apply)*
    *RED Delegated Act / EN 18031 · IEC 62443-4-1 · IEC 62443-4-2 · ETSI EN 303 645 · FDA premarket cybersecurity · Common Criteria or FIPS 140-3 · NIST SSDF attestation · Other · None · Don't know*
    → Handoffs, Waiting on guidance

12. **What carried over.** If so, what carried over to the CRA work most? *(Select up to two)*
    *Requirements mapping · Secure development processes · Evidence and technical documentation · People who have done it before · Little or nothing · Don't know*
    → Handoffs, Waiting on guidance

13. **Same team.** If so, is the team doing the CRA work the same team that handled the regime that carried over most?
    *Yes · Partly · No · Don't know*
    → Handoffs

## Notes for survey designers

- Questions 0, 1, 7 and 9 give the most insight if space is limited. Size (question 0) helps test whether smaller organizations are limited more by capacity, and larger ones by handoffs and planning.
- Questions 11 to 13 can be compared with question 1 (time to engineering) and question 4 (waiting on standards) to test whether prior regimes shorten handoffs and the wait for guidance. They are not expected to help much with CRA-only obligations such as vulnerability reporting, the support period or SBOMs.
- Ranges, not exact figures, keep responses anonymous and easier to answer.
- The same questions work for any regulation with a fixed deadline: replace "CRA" and the date.

Source: [The Compliance Relay](https://github.com/Poojarav/compliance-relay) by Pooja Ravichandra, https://doi.org/10.5281/zenodo.23906177. Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
