# MEGA.dev S01E03 · what it shows

This repository contains the support KB export and the date-cause analysis for ticket #4471.

The export has 427 rows but 412 unique report IDs; 15 rows are repeated export overlaps. Using
each tenant's locale, booking form, and report channel to identify the cause, the unique reports
split into:

- **379 parser reports**: the shared parser reads month first for day-first tenants.
- **33 form-hint reports**: booking-v3 shows `MM/DD/YYYY` to day-first tenants on form submissions.

The `intakeTag` is an intake guess, not the cause. The signed KB page uses the export's
`CauseTable` component so report totals remain computed from the deduplicated data.

## Deliverables

- GitHub issues for the parser and form-hint problems, with report counts.
- `support-kb/src/routes/kb/incidents/4471-causes/+page.svx`, the signed KB page.
- `support-kb/rendered/4471-causes.html`, a static rendered view of that page.
- `support-kb/`, the supplied KB export, including its report data and components.
