# The Compliance Relay

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23906178.svg)](https://doi.org/10.5281/zenodo.23906178) [![Live calculator](https://img.shields.io/badge/calculator-live-2756c9)](https://poojarav.github.io/compliance-relay/)

**A free, vendor-neutral framework for finding out how much of a regulatory deadline actually reaches your engineers, and how to win back the rest.**

Regulations like the EU Cyber Resilience Act give organizations years. But a requirement passes through legal, compliance, security and partner teams, waits for planning cycles and other teams, competes for people's time, and runs into freezes, releases and audits before engineers can deliver. The Compliance Relay makes that time visible, and shows the latest date a team must start to finish on time.

## Try it

- **Web calculator:** use it online at **https://poojarav.github.io/compliance-relay/**, or open [`calculator/index.html`](calculator/index.html) in any browser. It runs offline.
- **Spreadsheet:** [`spreadsheet/compliance-relay-calculator.xlsx`](spreadsheet/compliance-relay-calculator.xlsx) works in Excel and Google Sheets. Edit the yellow cells.
- **Worksheet:** [`worksheet/compliance-relay-worksheet.pdf`](worksheet/compliance-relay-worksheet.pdf) is a one-page printable for workshops.
- **Guide:** [`GUIDE.md`](GUIDE.md) explains the framework, the calculation, a worked example and how to win time back.

All formats use the same constraints and math, and every value is your own input.

## The six constraints

| Constraint | What it captures |
| --- | --- |
| Handoffs | The teams a requirement passes through before engineers receive work |
| Waiting on guidance | Time until standards or official guidance are stable enough to build against |
| Planning | Work that misses the current planning cycle waits for the next |
| Dependencies | Teams, or upstream projects, that must deliver first |
| Capacity | The share of team time actually available |
| Blocked periods | Freezes, release crunches and audit seasons |

Release lead time and evidence preparation come off the end of the timeline.

## A worked example (sample numbers)

A team with a 20-week engineering estimate, starting 29 October 2026 against the CRA's 11 December 2027 deadline, can fit only **16.3 weeks** of work after the constraints. Shortening handoffs alone recovers nothing, because the next planning cycle absorbs the gain. Letting compliance work enter mid-cycle **and** running interpretation in parallel brings it to **21.9 weeks**, so the work fits. See [`GUIDE.md`](GUIDE.md).

## Help calibrate it

Little public data exists on how long these steps take. If you can share rough, anonymized ranges, open an issue using the **Share anonymized timeline data** template. Never share confidential information.

## Status

Version 0.4, the first public release. This is a planning model, not a prediction, and not legal advice. It does not interpret any regulation. See [`CHANGELOG.md`](CHANGELOG.md) for what's planned next.

## Citing

Ravichandra, P. (2026). *The Compliance Relay* (Version 0.4.1) [Software]. Zenodo. https://doi.org/10.5281/zenodo.23906178

GitHub's "Cite this repository" button uses [`CITATION.cff`](CITATION.cff).

## License

- Calculator code: [Apache License 2.0](LICENSE)
- Guide, worksheet and spreadsheet: [CC BY 4.0](LICENSE-docs)

Created by Pooja Ravichandra. Contributions are welcome: see [`CONTRIBUTING.md`](CONTRIBUTING.md).
