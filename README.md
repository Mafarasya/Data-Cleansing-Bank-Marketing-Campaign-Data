# Bank Marketing Data Processing

![Piggy Bank](piggy_bank.jpg)

## Overview
This repository contains cleaned and reformatted data from a bank marketing campaign dataset. The data has been split into three CSV files: `client.csv`, `campaign.csv`, and `economics.csv`. Each file has been processed according to specific requirements to ensure it is ready for use in a PostgreSQL database.

## File Summaries

### client.csv

**Description**: This file contains cleaned and reformatted client data.

**Columns and Data Types**:
- **client_id**: integer
  - Client ID.
- **age**: integer
  - Client's age in years.
- **job**: object
  - Client's type of job (replaced "." with "_" in job titles).
- **marital**: object
  - Client's marital status.
- **education**: object
  - Client's level of education (replaced "." with "_" and "unknown" with `NaN`).
- **credit_default**: boolean
  - Whether the client's credit is in default (1 if "yes", otherwise 0).
- **mortgage**: boolean
  - Whether the client has an existing mortgage (1 if "yes", otherwise 0).

**Cleaning Requirements**:
- Replace "." with "_" in `job` titles.
- Replace "unknown" with `NaN` in `education` column.
- Convert `credit_default` and `mortgage` columns to boolean values:
  - 1 if "yes", otherwise 0.

### campaign.csv

**Description**: This file contains cleaned and reformatted campaign data.

**Columns and Data Types**:
- **client_id**: integer
  - Client ID.
- **number_contacts**: integer
  - Number of contact attempts to the client in the current campaign.
- **contact_duration**: integer
  - Last contact duration in seconds.
- **previous_campaign_contacts**: integer
  - Number of contact attempts to the client in the previous campaign.
- **previous_outcome**: boolean
  - Outcome of the previous campaign (1 if "success", otherwise 0).
- **campaign_outcome**: boolean
  - Outcome of the current campaign (1 if "yes", otherwise 0).
- **last_contact_date**: datetime
  - Last date the client was contacted (formatted as "YYYY-MM-DD", created from day, month, and a newly added year column with value 2022).

**Cleaning Requirements**:
- Convert `previous_outcome` and `campaign_outcome` columns to boolean values:
  - 1 if "success" or "yes", otherwise 0.
- Create `last_contact_date` from day, month, and a year column (2022).

### economics.csv

**Description**: This file contains cleaned and reformatted economic indicator data.

**Columns and Data Types**:
- **client_id**: integer
  - Client ID.
- **cons_price_idx**: float
  - Consumer price index (monthly indicator).
- **euribor_three_months**: float
  - Euro Interbank Offered Rate (euribor) three-month rate (daily indicator).

**Cleaning Requirements**:
- No additional cleaning or reformatting required beyond ensuring correct data types.

## How to Use
1. **Load Data**: Use these CSV files to populate your PostgreSQL database.
2. **Data Integration**: The cleaned data is ready for integration into data analysis and reporting systems.

## Files
- `client.csv`: Contains client data.
- `campaign.csv`: Contains campaign data.
- `economics.csv`: Contains economic indicators.


Source: https://projects.datacamp.com/projects/1613
