# CS4048 Assignment 2: Cleaned Datasets (v1.0)

Cleaned versions of two datasets produced for CS4048 Data Science, Assignment 2 (Exploratory Data Analysis), FAST-NU Lahore. These exact files are the input for Assignment 3.

| File | Rows x Columns | Version |
|---|---|---|
| `23L_0976_A2_netflix_cleaned.csv` | 8,806 x 24 | v1.0 |
| `23L_0976_A2_supermarket_cleaned.csv` | 1,000 x 25 | v1.0 |

**Date:** 18 October 2026

## Sources
- **Netflix Movies and TV Shows** by Shivam Bansal, Kaggle: https://www.kaggle.com/datasets/shivamb/netflix-shows (original: 8,807 rows x 12 columns). Credit to the original author; see the Kaggle page for licence terms.
- **Supermarket Sales**: `supermarket_Sales.csv` as provided by the course instructor (1,000 rows x 17 columns).

## Changes made: Netflix
- Removed one exact duplicate record (show_id s6530, identical to s3372 apart from a trailing space in the title).
- Moved three durations that were typed into `rating` back into `duration`; their rating is set to "Unknown".
- Missing `rating` set to "Unknown"; "UR" merged into "NR".
- Missing `director`, `cast`, `country` filled with "Unknown".
- Stripped whitespace and stray commas in multi-valued fields (`country`, `listed_in`, `cast`).
- `date_added` converted to a date (YYYY-MM-DD); 10 missing dates left empty.
- No outliers removed.
- Added columns: `year_added`, `month_added`, `lag_years`, `added_before_release`, `movie_minutes`, `seasons`, `n_countries`, `n_genres`, `n_cast` (0 = unknown for counts), `primary_country`, `audience`, `release_decade`.

## Changes made: Supermarket Sales
- No missing values, duplicates or inconsistent labels were found, so no rows or values were changed.
- `Date` converted to YYYY-MM-DD format.
- Added columns: `datetime`, `hour`, `weekday`, `weekday_num` (0 = Monday), `month`, `is_weekend`, `time_of_day`, `high_total_flag` (9 IQR outliers in Total, kept).
- Note: `City` duplicates `Branch`; `Cost of goods sold`, `Tax 5%`, `Total`, `Gross income` are derived from `Unit price` x `Quantity`; `Gross margin percentage` is constant.

## Versioning
v1.0 is the version used in Assignment 2. Any later change will be published as a new version; v1.0 will not be overwritten.
