# cpa-cpe-data

Machine-readable JSON dataset of US CPA continuing professional education (CPE)
requirements for all 50 states + Washington, D.C.

Maintained by [Paprika Labs](https://paprika-labs.app) — the team behind
[CPETrack](https://cpe.paprika-labs.app), a free CPA CPE deadline tracker.

## Data Files

| File | Description |
|------|-------------|
| `data/states.json` | All 51 jurisdictions in one file |
| `data/states/` | One JSON file per state |

## Schema

Each record contains:

```json
{
  "state_code": "NY",
  "state_name": "New York",
  "deadline_type": "annual",
  "deadline_date": "December 31",
  "deadline_notes": "Annual CPE by December 31. Two-option system: 40hr general or 24hr concentrated.",
  "cycle_years": 1,
  "total_hours": 40,
  "annual_min_hours": 40,
  "ethics_hours": 4,
  "ethics_state_specific": false,
  "aa_hours": null,
  "aa_applies_to": null,
  "self_study_cap_pct": null,
  "carryover_hours": null,
  "technical_floor_pct": null,
  "regulatory_body": "NYSED",
  "source_url": "https://cpe.paprika-labs.app/ny-cpa-cpe-requirements-december-31.html",
  "notes": "..."
}
```

### Field Reference

| Field | Type | Description |
|-------|------|-------------|
| `state_code` | string | 2-letter USPS code (or "DC") |
| `state_name` | string | Full jurisdiction name |
| `deadline_type` | string | "annual" / "biennial" / "triennial" / "rolling" |
| `deadline_date` | string | Human-readable deadline (e.g. "December 31", "birth-month", "June 30") |
| `deadline_notes` | string | Stagger rules, split cohorts, or date caveats |
| `cycle_years` | number | Renewal cycle length in years |
| `total_hours` | number | Total CPE hours required per cycle |
| `annual_min_hours` | number\|null | Hours required each calendar year (null = no annual mandate) |
| `ethics_hours` | number\|null | Ethics hours per cycle (null = no mandate) |
| `ethics_state_specific` | boolean | true = generic NASBA ethics is NOT sufficient |
| `aa_hours` | number\|null | Accounting & Auditing hours per cycle (null = no mandate) |
| `aa_applies_to` | string\|null | "all" / "attest" / "compilation" / null |
| `self_study_cap_pct` | number\|null | Maximum % of total hours from self-study (null = no cap) |
| `carryover_hours` | number\|null | Max hours that carry forward (null = carryover not allowed) |
| `technical_floor_pct` | number\|null | Minimum % of hours that must be technical subjects |
| `regulatory_body` | string | Primary licensing board abbreviation |
| `source_url` | string | Full Paprika Labs state guide URL |
| `notes` | string | Distinctive rules not captured in structured fields |

## Quick Reference: States by Deadline

### December 31 Annual
AR, LA, MO, MT, NC, NV, NY, SC, WV, WY

### December 31 Biennial (even years)
CO, DC, MD, NE (even birth year), TN (even license#), UT

### December 31 Biennial (odd years)
GA, PA

### December 31 Triennial
IN, NJ, OH, VA, WA

### June 30 Annual
CT (completion), MI, MS (completion), ND

### June 30 Biennial
FL (even years), KS (by cert#), MA (by license#)

### June 30 Triennial
IA, MN, NH, RI

### Birth-Month
AZ (biennial), CA (biennial), NM (annual), OK (annual), TX (annual)

### Other Deadlines
AL, ME: September 30 (annual)
ID: December 31 (rolling 2-yr)
IL: September 30 (triennial)
SD: August 1 (annual)
VT: July 31 (odd years biennial)
WI: December 14 (biennial)
AK, HI: December 31 (odd years biennial — next active 2027)

## Sources & Accuracy

Data compiled from official state board websites, NASBA, and AICPA sources.
Each state has a detailed guide at [cpe.paprika-labs.app](https://cpe.paprika-labs.app)
with citations to primary regulatory sources.

**Last updated:** 2026-07-03

⚠️ CPE requirements change. Always verify against your state board's current regulations
before relying on this data for compliance purposes.

## Contributing

Found an error or a rule change? Open a PR or issue. This dataset is community-maintained.

State sources:
- [NASBA CPE Resources](https://www.nasba.org/licensure/continuingprofessionaleducation/)
- [AICPA State CPE Requirements](https://www.aicpa-cima.com/professional-insights/download/us-cpa-state-cpe-requirements)
- Individual state board websites

## License

[CC0 1.0 Universal](LICENSE) — public domain, no attribution required.

---

Built and maintained by [Paprika Labs](https://paprika-labs.app) •
Free CPE tracker: [cpe.paprika-labs.app](https://cpe.paprika-labs.app)
