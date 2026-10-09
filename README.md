# Sales & Marketing Performance Analysis

An Excel analysis of 20 months of order data (January 2025 to September 2026) for a subscription business. The goal was to answer the questions a sales manager would actually ask: where is the ad budget going, is it paying off, who are the customers, and how is this year compared to last year.

## What is in this repo

| `Sales-Marketing_dataset.xlsx` | The workbook: raw data, cleaned data, analysis (pivot tables) and the dashboard |
| `Sales_Marketing_Executive_Summary(1).pdf` | A two-page summary written for a stakeholder |

## Business questions

1. How much are we spending on ads per platform, and is that spend paying off?
2. Do new or returning customers make up more of our orders?
3. Which region generates the most revenue?
4. Which products generate the most revenue, and is that because of demand or price?
5. Is 2026 ahead of or behind 2025?

## Key findings

- **Total revenue** was ₦18,179,600 from 450 orders, with an average order value of ₦40,399.
- **Total ad spend** was ₦573,456, giving an overall return on ad spend (ROAS) of about 31.7x.
- **Instagram** led on ad spend, revenue and ROAS (about 24.8x). Facebook was close behind.
- **Google Ads** had the lowest ROAS of the paid channels and was the only channel where returning customers outnumbered new ones (35 vs 33). It may be working more as a retention channel than an acquisition channel.
- **New customers** made up 54% of orders and returning customers 46%.
- **Lagos** generated the most revenue (₦6,171,750), followed by Abuja and Ibadan.
- **Products** had almost the same number of orders (86 to 95 each), but revenue differed by more than 12x. That gap comes from price, not from customers preferring one plan.
- **2026 vs 2025:** over the same eight complete months (January to August), 2026 is slightly ahead, ₦7,521,600 against ₦7,391,200. The lead is small and not consistent every month.

## How the data was cleaned

The raw file had 470 rows. Cleaning was done by hand in Excel:

- Removed 17 exact duplicate rows.
- Found 6 duplicate order IDs with conflicting quantities and kept the row whose revenue matched unit price x quantity x (1 - discount).
- Trimmed whitespace and fixed inconsistent spelling and casing in region, channel, sales rep and customer type.
- Standardised four different date formats into real Excel dates.
- Labelled missing values instead of deleting rows: unknown regions as "Unknown", unattributed channels as "Unknown-Organic" or "Unknown-Paid" depending on whether ad spend existed, and missing sales reps as "N/A - Self-Serve." or "Rep Not Recorded".
- Recalculated revenue from price, quantity and discount, and checked it against the original values.

450 records remained.

## Limitations

- **Cleaning is manual.** Pivot tables and charts refresh when rows are added to the data table, but new rows are not cleaned automatically. Moving the cleaning into Power Query is the planned next step.
- **No customer ID.** Orders cannot be linked to the same customer, so questions such as "do add-ons sell more to Premium customers?" could not be answered.
- **Estimated ad spend.** Four missing ad spend values were filled with estimates instead of recorded amounts. This affects ad spend and ROAS totals by roughly 0.2%.
- **Unattributed channels.** Seven orders have no recorded marketing channel. They are included in totals but not in channel comparisons.

## Tools

Microsoft Excel (pivot tables, calculated fields, charts, formulas) for analysis and the dashboard.


## Next steps

- Rebuild the cleaning steps in Power Query so new data is cleaned on refresh.
- Add a consistency analysis (how steady each channel's revenue is month to month).
- Repeat the analysis in SQL.
