---
visibility: restricted
---
# Rizom Financial Model 2026–2028 — Workbook Spec

Canonical definition of the driver-based model. The interactive HTML (`rizom-financial-model.html`) and the Excel workbook (`rizom-financial-model.xlsx`) are renders of this spec — where they disagree, this spec wins. All amounts EUR thousands. Companion to [[rizom-financial-projections-20262028]] and [[investor-one-pager]].

## Structure

A monthly engine over 30 months, **Jul 2026 through Dec 2028**. Four sheets:

1. **Inputs** — every driver, three scenario columns (Conservative / Base / Growth) plus an **Active** column the reader edits. All formulas reference Active only.
2. **Monthly** — 30 rows, one per month; all revenue, cost, cash and commons math lives here.
3. **Annual** — 2026 H2 / 2027 / 2028 rollups of the monthly sheet, plus the headline tiles (net per year, cash trough, hire gates, Ghost line, commons balance).
4. **Validation** — the published figures from the projections note next to the workbook's computed values, with a PASS/FAIL delta check.

## Inputs

Yearly triples are 2026 H2 / 2027 / 2028.

### Engagements

| Driver | Conservative | Base | Growth |
|---|---|---|---|
| Builds per year | 1 / 2 / 2 | 2 / 4 / 4 | 3 / 6 / 6 |
| Avg build price | 15 / 25 / 35 | 15 / 25 / 35 | 15 / 28 / 35 |
| Retainers at year-end | 1 / 2 / 3 | 2 / 3 / 4 | 3 / 5 / 7 |
| Avg retainer per month | 4 / 5 / 7 | 4 / 5.5 / 7 | 4 / 5.5 / 7 |
| Knowledge Sessions per year | 1 / 2 / 2 | 1 / 3 / 3 | 2 / 5 / 5 |
| Session price | 5 | 5 | 5 |
| Co-delivery share (0–1) | 0 / 0.2 / 0.4 | 0 / 0.3 / 0.5 | 0 / 0.4 / 0.5 |

### Partners

| Driver | Conservative | Base | Growth |
|---|---|---|---|
| Certification months | 2028-01 | 2027-07, 2028-01, 2028-05, 2028-09 | 2027-03, 2027-07, 2027-11, 2028-01, 2028-03, 2028-05, 2028-07, 2028-09, 2028-10, 2028-11 |
| Commons per partner per month (full) | 5 | 5 | 5 |
| Ramp-up months | 6 | 6 | 6 |
| Certification fee (one-off) | 10 | 10 | 10 |

### Hosting

| Driver | Conservative | Base | Growth |
|---|---|---|---|
| Brains at year-end | 2 / 10 / 45 | 4 / 25 / 80 | 6 / 60 / 170 |
| Price per brain per month | 0.3 | 0.3 | 0.3 |
| Hosting COGS (share of hosting revenue) | 0.3 | 0.3 | 0.3 |

### Costs & hires

| Driver | Conservative | Base | Growth |
|---|---|---|---|
| Founder draw per month | 5 / 5 / 5.5 | 5 / 5 / 6 | 5 / 6 / 6.7 |
| Overhead per month | 1.2 | 1.2 | 1.5 |
| Programs/growth spend per year | 0 / 0 / 10 | 0 / 15 / 40 | 0 / 50 / 130 |
| Delivery costs (share of own B.V. revenue) | 0.03 | 0.03 | 0.03 |
| Hire 1 start (platform ops) | 2027-07 | 2027-01 | 2026-11 |
| Hire 1 cost per month (net of WBSO) | 7.5 | 7.5 | 7.5 |
| Hire 2 start (onboarding/DX) | — | 2028-07 | 2027-07 |
| Hire 2 cost per month (net of WBSO) | 7.9 | 7.9 | 7.9 |

### Friends & family round

| Driver | Conservative | Base | Growth |
|---|---|---|---|
| Amount (0 = none) | 75 | 75 | 75 |
| Received in | 2026-10 | 2026-10 | 2026-09 |

## Monthly sheet — row formulas

For each month *i* (Jul 2026 = month 1 of 30), with `y` its calendar year, `miy` its 1-based month within the year, and `nm` the number of active months in that year (6 in 2026, else 12):

| Row | Formula | Notes |
|---|---|---|
| Retainers (count) | `prev_year_end + (year_end − prev_year_end) × miy / nm` | Linear ramp toward the year-end count. Prior year-end is 0 for 2026. |
| Retainer revenue | `retainers × retainer_price[y]` | |
| Build revenue | `(builds[y] / nm) × build_price[y]` | Builds spread **evenly** across the year's months (fractional). The HTML model places whole builds in discrete months; annual totals are identical, intra-year cash timing differs slightly. Even spreading is the deliberate choice for the workbook — smoother and standard in driver models. |
| Session revenue | `(sessions[y] / nm) × 5` | Same even spreading. |
| **Own system revenue** | `retainer + build + session revenue` | The full engagement value, before the split. |
| **Own B.V. revenue** | `own_system × (1 − 0.60 × co_delivery_share[y])` | The B.V. books everything except the 60% delivery share on co-delivered work. |
| Partner remits | `Σ over certified partners: 5 × MIN(1, months_since_cert / 6)` | Each partner ramps to full €5k/mo commons flow over 6 months from certification. Excel: SUMPRODUCT over the certification-month list. |
| Certification fees | `10 × (number of partners certifying this month)` | |
| Hosted brains (count) | `prev_year_end + (year_end − prev_year_end) × miy / nm` | Same linear ramp as retainers. |
| Hosting revenue | `brains × 0.3` | |
| Hosting COGS | `hosting_revenue × 0.3` | |
| **Total revenue** | `own_BV + partner_remits + cert_fees + hosting_revenue` | |
| Costs | `founder_draw[y] + overhead + program_spend[y]/nm + 0.03 × own_BV + hosting_COGS + hires` | Hires: hire cost from its start month onward, per hire. |
| **Net** | `revenue − costs` | |
| **Cash** | `prior_cash + net (+ 75 in the F&F month, with-F&F track only)` | Two cash tracks: with and without the round. Trough is tracked on the **without** track — that is the insurance argument. |
| Commons inflow | `0.25 × own_system + partner_remits` | Cert fees and hosting margin are commercial, not commons. |
| Commons outflow | `overhead + hire costs` | The infra team and platform overhead are what the earmark must fund. |
| Commons balance | cumulative `inflow − outflow` | Negative = the commercial 75% is fronting the platform. |

## Derived indicators (Annual sheet)

| Indicator | Definition |
|---|---|
| Hire gate 1 / 2 | First month where trailing-12-month commons inflow ≥ **90** / ≥ **185**. With fewer than 12 months of history (minimum 6), annualize: `sum × 12 / months_available`. |
| Ghost line | First month hosted brains ≥ **73** — hosting margin alone carries 2 FTE. |
| Cash trough | Most negative cumulative cash on the without-F&F track, and the month it occurs. |

## Validation targets

From the projections note (generated by the HTML model with these presets). Annual totals must match; small intra-year deviations from the even-spreading choice are acceptable, sign and magnitude of the trough must hold.

| | 2026 H2 net | 2027 net | 2028 net | Cash end-2028 (no F&F) |
|---|---|---|---|---|
| Conservative | −3 | +27 | +166 | 190 |
| Base | +27 | +112 | +355 | 493 |
| Growth | +45 | +240 | +786 | 1,070 |

Worst trough across scenarios: **−14** (conservative, first months). 2028 base revenue composition: engagements 317, partners 173, hosting 197, costs 332.

## What the reader is invited to break

The workbook exists so a financial reader can stress the ask. The levers that matter:

- **Pilot conversion and retainer counts** — the survival lever; everything else is downstream.
- **Partner economics** — the €5k/mo per-partner commons flow is unproven until the first certification; set it to zero and see what remains.
- **Hosting attach rate** — the Ghost line (73 brains) is where the platform self-funds.
- **The F&F round itself** — set the amount to 0: the model should stay solvent in base, and the trough shows exactly what the €75k insures against.
