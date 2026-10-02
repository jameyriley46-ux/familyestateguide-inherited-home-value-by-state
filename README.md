# Inherited Home Value by State: Median Value of Homes Owned by Householders 65+

Median and mean value of owner-occupied homes headed by someone 65+, homeownership and mortgage-free rates, for 50 states + DC (Census ACS 2024 1-year, with 2020-2024 5-year check).

**Live page:** https://familyestateguide.com/estate-planning-data/inherited-home-value-by-state/  
**Publisher:** Family Estate Guide (https://familyestateguide.com)  
**Version:** 1.0.0 (2026-10-02)  
**License:** CC BY 4.0 (data). See LICENSE.

> Not legal, tax, financial or medical advice. Figures are estimates with sampling error; legal rules change. Verify anything important with the original source or a qualified professional.

## Files

| File | Rows | Contents |
|---|---|---|
| `data/inherited_home_value_states_acs2024.csv` | 51 | 51 rows (50 states + DC). |
| `data/inherited_home_value_us_acs2024.csv` | 1 | 1 row, United States. |

Blank cells mean not available, not published or not applicable; they are never zero.

## Data dictionary

### `data/inherited_home_value_states_acs2024.csv`

| Column | Description |
|---|---|
| `name` | Geography name as published by the Census Bureau. |
| `state_fips` | Two-digit state FIPS code. |
| `median_value_65plus_householder_usd` | Median value, owner-occupied units with householder 65+, USD (S0103_C02_098E). |
| `median_value_65plus_moe_usd` | 90% MOE of median_value_65plus_householder_usd (S0103_C02_098M). |
| `median_value_all_owner_homes_usd` | Median value, all owner-occupied units, USD (S0103_C01_098E). |
| `gap_65plus_vs_all_owners_usd` | median_value_65plus_householder_usd minus median_value_all_owner_homes_usd. |
| `owner_homes_65plus` | Owner-occupied units with householder 65+ (B25007_009E-011E). |
| `households_65plus` | Occupied units (owner + renter) with householder 65+ (B25007 009-011 + 019-021). |
| `homeownership_rate_65plus_pct` | owner_65plus as % of households_65plus. |
| `homeownership_rate_65plus_moe_pct` | Approximate 90% MOE of the 65+ homeownership rate, percentage points (delta method, owners and renters treated as independent). |
| `pct_65plus_owner_homes_no_mortgage` | Share of 65+ owner-occupied units with no mortgage, % (B25027 016-017 vs 008-009). |
| `mean_value_per_65plus_owner_home_usd` | aggregate_value_65plus_usd (B25079_005E) / owner_homes_65plus. |
| `aggregate_value_65plus_usd` | Aggregate value of owner-occupied units with householder 65+, USD (B25079_005E). |
| `median_value_65plus_acs5_2020_2024_usd` | Median value, 65+ householder, ACS 2020-2024 5-year S0103 (more stable for small states). |
| `median_value_65plus_acs5_moe_usd` | 90% MOE of the 5-year median. |
| `rank_median_value_65plus` | Rank by median_value_65plus_householder_usd, 1 = highest. |
| `rank_homeownership_65plus` | Rank by homeownership_rate_65plus_pct, 1 = highest. |

### `data/inherited_home_value_us_acs2024.csv`

| Column | Description |
|---|---|
| `name` | Geography name as published by the Census Bureau. |
| `median_value_65plus_householder_usd` | Median value, owner-occupied units with householder 65+, USD (S0103_C02_098E). |
| `median_value_65plus_moe_usd` | 90% MOE of median_value_65plus_householder_usd (S0103_C02_098M). |
| `median_value_all_owner_homes_usd` | Median value, all owner-occupied units, USD (S0103_C01_098E). |
| `gap_65plus_vs_all_owners_usd` | median_value_65plus_householder_usd minus median_value_all_owner_homes_usd. |
| `owner_homes_65plus` | Owner-occupied units with householder 65+ (B25007_009E-011E). |
| `households_65plus` | Occupied units (owner + renter) with householder 65+ (B25007 009-011 + 019-021). |
| `homeownership_rate_65plus_pct` | owner_65plus as % of households_65plus. |
| `homeownership_rate_65plus_moe_pct` | Approximate 90% MOE of the 65+ homeownership rate, percentage points (delta method, owners and renters treated as independent). |
| `pct_65plus_owner_homes_no_mortgage` | Share of 65+ owner-occupied units with no mortgage, % (B25027 016-017 vs 008-009). |
| `mean_value_per_65plus_owner_home_usd` | aggregate_value_65plus_usd (B25079_005E) / owner_homes_65plus. |
| `aggregate_value_65plus_usd` | Aggregate value of owner-occupied units with householder 65+, USD (B25079_005E). |

## Sources

- U.S. Census Bureau, American Community Survey (ACS) 2024 1-year, table(s) S0103 (population 65+; C02_098 median value), B25007 (tenure by age), B25027 (mortgage status by age), B25079 (aggregate value by age), via the Census Data API (https://api.census.gov/data/2024/acs/). Public domain.
- U.S. Census Bureau, American Community Survey (ACS) 2020-2024 5-year, table(s) S0103, via the Census Data API (https://api.census.gov/data/2024/acs/). Public domain.

## Methodology

- ACS has no detailed B-table median value by age of householder, so the subject-table median S0103_C02_098E is the primary measure. Mean = B25079 aggregate / B25007 count.
- Homeownership MOE uses the delta method for A/(A+B).

## Limitations

- A median home value is not an inheritance amount: value is owner-reported, gross of mortgage, primary homes only, and the householder may not be the sole owner.
- DC vs. California (#2/#3) and Massachusetts vs. Washington (#4/#5) are tied within MOE.
- ACS 2025 1-year delayed; 2024 is the latest single-year release.

## Rights review and exclusions

Family Estate Guide publishes here only its own compiled data and U.S. government public-domain data (Census, BLS, CMS, DOL), plus third-party data that is under CC BY or a compatible open license, with attribution. Third-party copyrighted or non-commercial-licensed data is excluded.

- None. All columns derive from Census public-domain data.

## How to cite

Family Estate Guide (2026). *Inherited Home Value by State: Median Value of Homes Owned by Householders 65+* (Version 1.0.0) [Data set]. https://familyestateguide.com/estate-planning-data/inherited-home-value-by-state/ . GitHub: https://github.com/jameyriley46-ux/familyestateguide-inherited-home-value-by-state

A Zenodo DOI will be added here once version 1.0.0 is released and archived. Machine-readable citation: `CITATION.cff`.

Please link to the live page when you use the data.

## License

Data in this repository is licensed under the Creative Commons Attribution 4.0 International license (CC BY 4.0). Underlying U.S. government data is public domain; third-party CC BY data keeps its original attribution requirements (see Sources).
