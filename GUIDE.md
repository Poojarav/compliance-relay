# The Compliance Relay

### How much of a regulatory deadline actually reaches the engineers who must deliver?

*Version 0.5.0 · Pooja Ravichandra · Not legal advice · Licensed under CC BY 4.0*

---

## The problem

The EU Cyber Resilience Act (CRA) entered into force in December 2024. Its vulnerability reporting obligations have applied since 11 September 2026, and its essential requirements apply in full on **11 December 2027**. On paper, manufacturers had three years.

Engineers do not get three years. Inside an organization that ships software, a new obligation rarely goes straight to the people who build the product. It is read by legal, turned into policy by compliance, designed into a program by security, translated into tooling by platform teams, and only then lands in a product team's backlog. Each handoff takes time. Then the work meets the organization's calendar: planning cycles, dependencies on other teams, competing priorities, code freezes, release trains and audit seasons.

Surveys suggest the gap is real. In the OpenSSF and Linux Foundation Research *2026 CRA Awareness and Readiness Report*, only **41%** of manufacturers expected to be fully compliant by the December 2027 deadline, and **39%** were uncertain whether they could meet the requirements at all. The survey measures *whether* organizations expect to be ready; the Compliance Relay is a way to examine *why*.

The Compliance Relay is a simple, generic framework for seeing where that time goes, and for winning it back.

## The framework

A requirement travels through six kinds of constraint before and around the engineering work:

| Constraint | What it is | Examples |
| --- | --- | --- |
| **Handoffs** | The teams a requirement passes through before engineers get a ticket. Steps can run in sequence or in parallel. | Legal interpretation, compliance policy, security program design, finding the right partner teams, product intake |
| **Waiting on guidance** | Time spent waiting for standards or official guidance before decisions can be final. | Harmonised standards under the CRA standardisation request |
| **Planning** | Work that misses the current planning cycle waits for the next one. | Quarterly, half-yearly or annual planning |
| **Dependencies** | Teams that cannot start until another team delivers. | A platform, build or identity team that must ship first |
| **Capacity** | The share of the team's time actually available for this work. | Job cuts, competing regulatory work, a major launch |
| **Blocked periods** | Times when engineers cannot work on it at all. | Year-end code freezes, release crunches, audit seasons, reorganizations |

Finally, the work must be finished **before** the deadline: code complete ahead of the release that must comply, and validation and evidence ready before that release ships.

The share of the calendar that survives all of this is the **effective transition period**: the time engineers really have.

## The calculation

1. **Arrival.** Add up the handoffs. Steps that run in parallel count as the longest of them. If you are waiting on standards past that date, use the standards date instead.
2. **Start.** Move to the next planning cycle, unless compliance work can enter mid-cycle. Then wait for the longest dependency.
3. **Real deadline.** Subtract code-complete lead time and evidence preparation from the regulatory deadline. If that date falls inside a blocked period, move it to the start of that period.
4. **Working days.** Count the days from start to real deadline, minus blocked days.
5. **Work possible.** Multiply the working days by the share of the team's time available.
6. **Verdict.** Compare the work possible with the work needed.
7. **Latest start.** Count back from the real deadline by the work needed at that capacity, skipping blocked days, then subtract the dependency wait and the handoffs. That is the latest date the first handoff can begin.

## Three ways to use it

All three use the same constraints and the same math, so they give the same answer.

- **Web calculator** (`calculator/index.html`). A single file that runs in any browser, offline. Add as many handoffs, dependencies, capacity reductions and blocked periods as you need. Best for quick answers and live discussions.
- **Spreadsheet template** (`spreadsheet/compliance-relay-calculator.xlsx`). Works in Excel and Google Sheets. Edit the yellow cells. Best for sharing inside a compliance program and adapting to your organization.
- **Printable worksheet** (`worksheet/compliance-relay-worksheet.pdf`). One page with fill-in boxes. Best for workshops and leadership meetings.

The web calculator can also **copy a link to your scenario**, so a team can review the same numbers. The numbers travel inside the link itself; nothing is stored or sent anywhere.

## A worked example

These are **sample numbers**, not data from any organization.

A team starts on 29 October 2026 with a 20-week engineering estimate. The requirement passes through five handoffs totalling 15 weeks, planning is quarterly, one dependency adds 3 weeks, the team has 70% of its time available after competing work, a three-week release crunch falls in May, and the release needs 4 weeks of code-complete lead time plus 6 weeks of evidence preparation.

| | Weeks |
| --- | --- |
| Calendar time to 11 Dec 2027 | 58.3 |
| Handoffs | 15.0 |
| Waiting for the next planning cycle | 7.0 |
| Blocked (release crunch) | 3.0 |
| Reduced capacity | 7.0 |
| Code complete ahead of release | 4.0 |
| Evidence and audit preparation | 6.0 |
| **Engineering work possible** | **16.3** |

The team needs 20 weeks of work and can do 16.3: **short by 3.7 weeks**. To finish on time, the first handoff needed to start about six weeks ago.

The constraints interact, so the order of fixes matters:

| Change | Work possible | Verdict |
| --- | --- | --- |
| Remove the 4-week legal handoff, nothing else | 16.3 weeks | Still short by 3.7: the work just waits longer for the next planning cycle |
| Let compliance work enter mid-cycle | 19.1 weeks | Short by 0.9 |
| Mid-cycle entry **and** run legal interpretation and compliance policy in parallel | 21.9 weeks | **Fits, with about 2 weeks to spare** |

Shortening handoffs alone recovers nothing here, because the next planning cycle absorbs the gain. The two changes only work together.

## Where to get your numbers

Rough numbers are fine. Run the calculator twice, with an optimistic and a pessimistic value for anything you are unsure of, and see whether the verdict changes.

| Input | How to estimate it |
| --- | --- |
| **Clock starts** | Today. To look back at how much time has already gone, use the date your organization first started work on the obligation. |
| **Engineering work** | Your team's estimate, in weeks of full team time. If you have person-weeks, divide by the number of people on the team. |
| **Handoffs** | List every team that touched the last comparable regulation or policy before engineering got a ticket. Ask each for its typical turnaround, or compare dates in past tickets: policy approved, program designed, backlog item created. |
| **Waiting on guidance** | The date you expect standards or official guidance you can build against. Leave it blank for work that will not change. |
| **Planning** | Your real planning cadence, and whether regulatory work has ever entered a plan mid-cycle. |
| **Dependencies** | For each team that must deliver first, the gap between when the requirement reaches you and their committed date. No committed date is a risk in itself. |
| **Capacity** | Start at 100% and subtract what the team actually spends elsewhere: vacation and public holidays (four to five weeks a year is about 10%), on-call and incident response, keeping existing products running, and other regulatory work. Time-tracking data or the last two sprints are a good check. |
| **Blocked periods** | Your freeze calendar, release calendar, audit calendar and any holiday shutdowns. Mark annual ones as repeating. |
| **Release and evidence** | Code-complete lead time from your release calendar. Evidence time from how long your last audit or certification took to prepare. |

## Company size: where the bottleneck may move

Every company faces the same deadline, but size may change **where** the time goes. A pattern worth testing:

- **Larger companies** may lose more time in the relay: more specialist teams, more sequential handoffs and fixed planning cycles.
- **Smaller companies** may have shorter relays and more flexible planning, but less **capacity**: a few people who also build the product and support customers, with little budget to add more.

Treat this as a pattern to test with your own numbers, not a finding: there is no public data yet on CRA timelines by company size. The calculator's size setting shows what the CRA treats differently for each size; the timing inputs are always your own.

What the CRA itself treats differently by size:

- The essential requirements and the 11 December 2027 deadline are the same for every size.
- Micro and small enterprises cannot be fined for missing the 24-hour early-warning deadline for actively exploited vulnerabilities and severe incidents (Article 64(10)). Every other obligation, and its fines, still applies.
- Member States may offer SMEs training, testing support and regulatory sandboxes, and the Commission may publish a simplified technical documentation form for micro and small enterprises (Article 33). EU funding for SME compliance also runs through the Digital Europe Programme.
- When setting a fine, authorities must take the company's size into account, with particular regard to SMEs and start-ups (Article 64(5)).
- Open-source software stewards cannot be fined under the CRA (Article 64(10)).

## The cost of being late

Two optional inputs turn the verdict into a business case:

- **Maximum fine.** Non-compliance with the essential requirements, or with the obligations in Articles 13 and 14, can be fined up to €15 million or 2.5% of worldwide annual turnover, whichever is higher (Article 64(2)). Above €600 million in turnover, the 2.5% figure is the larger one. These are maximums: authorities weigh the size of the company and the severity and duration of the infringement.
- **EU sales at risk.** If the work is short, the calculator estimates how long past the deadline it will take to finish (the shortfall divided by the share of time available) and multiplies it by the product's weekly EU revenue. A product that does not meet the requirements cannot be placed on the EU market, and authorities can order it withdrawn.

In the worked example, a company with €1 billion in turnover and €52 million a year of EU sales for the product faces a maximum fine of €25 million, and about €5.3 million of sales at risk from a delay of about 5.3 weeks. These are estimates, not legal advice.

## Winning time back: a 90-day plan

Start with your biggest loss.

| If your biggest loss is… | Do this in the next 90 days |
| --- | --- |
| **Handoffs** | Form one working group with legal, compliance, security and an engineering lead. Interpret in parallel, and name the partner teams on day one. |
| **Waiting on guidance** | Build what will not change (inventory, SBOM generation, vulnerability intake) while standards settle, and design the rest to absorb them. |
| **Planning** | Reserve a standing slice of every planning cycle for regulatory work. |
| **Dependencies** | Map every team you depend on, agree dates in writing, and escalate any dependency without a committed date. |
| **Capacity** | Make the work an explicit priority with dedicated people. Stop or defer lower-value work to fund it. |
| **Blocked periods** | Put milestones before each freeze or crunch, and treat the last freeze before the deadline as your real deadline. |
| **Release lead time** | Ship compliance capabilities on an earlier release train, separate from feature releases. |
| **Evidence** | Generate SBOMs, validation results and audit records automatically in the pipeline, as you build. |

## Three things the model now asks you to check

These came from practitioners and are not yet built into the calculator. Account for them by hand until v0.5.

- **The earliest checkpoint, not the legal date.** If an internal audit, readiness review or certification step needs complete evidence before the regulatory deadline, enter that date as your deadline. In the worked example, an internal audit on 1 October 2027 cuts the work possible from 16.3 to 9.2 weeks.
- **Capacity that changes partway through.** Reorganizations, workforce reductions, incident response and on-call duty change the share of time available. Split the window at the change and run the calculator for each part.
- **Upstream release cadence.** For an open-source dependency, the upstream project's release schedule acts as a second planning calendar: a fix that misses one upstream release waits for the next. Measure your own lag as the time from an upstream fix to your shipped release, on your last three security fixes.

## Beyond the CRA

The Compliance Relay is not specific to one regulation. Enter any deadline: later CRA obligations, new standards once they are cited, an implementing act on SBOM format, or other regulations with fixed dates. The handoffs, the calendar and the capacity limits are the same every time.

## Limits

- This is a planning model, not a prediction. Its answers are only as good as the numbers you enter.
- Weeks are calendar weeks. Time off and other duties are handled through capacity, and full stops through blocked periods.
- The delay and sales-at-risk figures are simple estimates that ignore blocked periods after the deadline.
- Handoff durations vary widely, and little public data exists on them yet.
- The spreadsheet counts overlapping blocked periods twice, and its latest-start date is an approximation. The web calculator counts day by day.
- It is not legal advice and does not interpret the CRA.

## References

- Regulation (EU) 2024/2847 (Cyber Resilience Act), *Official Journal of the European Union*, 20 November 2024; Article 33 (support for SMEs) and Article 64 (penalties).
- Commission Recommendation 2003/361/EC on the definition of micro, small and medium-sized enterprises.
- European Commission, standardisation request C(2025) 618 to CEN, CENELEC and ETSI in support of the CRA, 3 February 2025.
- Linux Foundation Research and OpenSSF, *2026 CRA Awareness and Readiness Report*, June 2026. Summary: [The CRA Readiness Reality](https://www.linuxfoundation.org/blog/the-cra-readiness-reality-what-changed-and-what-didnt-between-2025-and-2026), Linux Foundation, 19 June 2026.
- Kubernetes release cycle, kubernetes.io, for an example of a public release calendar with scheduled freezes.

## Credit and license

The Compliance Relay framework, calculator, spreadsheet and worksheet were created by **Pooja Ravichandra**. Feedback and contributions are welcome.

The guide, worksheet and spreadsheet are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The calculator code is licensed under the Apache License 2.0. See `LICENSE` and `LICENSE-docs`.
