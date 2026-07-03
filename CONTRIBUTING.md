# Contributing to cpa-cpe-data

## Reporting Errors

Open an issue with:
- State code
- Field that's incorrect
- Correct value
- Source URL (official state board, NASBA, etc.)

## Submitting Updates

1. Fork this repository
2. Edit the relevant `data/states/{state_code}.json` file and `data/states.json`
3. Add the source URL in your PR description
4. Submit a pull request

## Data Standards

- All hours are per cycle (not per year, unless `cycle_years` = 1)
- `null` means "no requirement" — do not use 0
- `ethics_state_specific: true` means generic NASBA ethics alone is NOT sufficient
- Source URLs should link to official state board regulations
