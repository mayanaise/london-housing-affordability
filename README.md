# Buying in London: Housing Affordability and Borough Trends, From 2015–2025

An analysis of how house prices and workplace earnings relate to housing affordability across London's 32 boroughs and the City of London.

## Purpose

Help potential homebuyers understand current affordability and distinguish recent improvements from longer-term trends. The project also provides historical context for people researching property investment; it does not predict returns or recommend purchases.

## Key findings

- All 33 local authorities had lower house-price-to-earnings ratios in 2025 than in 2021.
- In 19 of 33 areas, affordability improved despite rising median house prices because workplace earnings grew faster proportionally.
- Tower Hamlets recorded the largest improvement since 2021: its ratio fell by 37.13%, alongside earnings growth of approximately 39% and a median house-price decline of approximately 13%.
- Recent improvement did not reverse the longer-term deterioration everywhere: 15 areas remained less affordable in 2025 than in 2015.
- Kensington and Chelsea's ratio fell by 31.86% since 2021 but remained 25.22 in 2025. A large improvement therefore does not necessarily mean a low affordability ratio.

## Data and scope

**Source:** [Office for National Statistics: Housing affordability in England and Wales, 2025](https://www.ons.gov.uk/peoplepopulationandcommunity/housing/bulletins/housingaffordabilityinenglandandwales/2025), published 26 March 2026.

The accompanying house-price-to-workplace-based-earnings workbook contains:

| Sheet | Measure |
| --- | --- |
| 5a | Median house prices |
| 5b | Median annual workplace-based earnings |
| 5c | Median house-price-to-earnings ratios |

The source ratio table has 318 local authorities and 34 columns. Selecting 2015–2025 produces 3,498 area-year records across England and Wales; the London analysis uses 363 records covering 33 local authorities and 11 years.

The affordability ratio is median house price divided by median gross annual workplace earnings. Higher ratios indicate lower affordability relative to that earnings measure.

## Analytical questions

1. Which areas improved between 2021 and 2025 despite rising prices?
2. How did price and earnings changes relate to the improvements?
3. Did higher workplace earnings necessarily mean more affordable housing in 2025?
4. Were improvements widespread or concentrated?
5. Which areas remained less affordable than in 2015 despite improving since 2021?

## Cleaning and analysis

- Checked duplicates and unavailable-value markers before transforming data.
- Converted `[x]` markers to missing values and annual measures to numeric types.
- Retained missing values rather than estimating unsupported replacements: 10 unavailable ratios and 10 unavailable earnings values occur in the wider selected dataset, all for the Isles of Scilly. The selected London data has no missing values in these measures.
- Standardised year headings and reshaped wide tables into area-year records using `melt`.
- Joined prices, earnings and ratios using local authority code and year, validating one-to-one relationships.
- Checked unique area-year keys and consistency between calculated and published ratios; differences are within published rounding precision.
- Used `pivot`, `groupby`, filtering and percentage-change calculations to answer the questions.

Cleaning decisions, findings, chart interpretation and limitations are documented in Markdown throughout the notebook.

## Visualisations

Five selected charts use Matplotlib and Seaborn:

1. Earnings growth against house-price growth.
2. Price and earnings changes in the five areas with the largest ratio reductions.
3. Workplace earnings against affordability ratios in 2025, with marginal histograms.
4. A heatmap indexed to each area's 2021 ratio.
5. Recent versus decade-long changes in eight areas with the largest long-term deterioration.

Each chart addresses a question and is accompanied by an interpretation. The notebook also adds sourced employment context for Tower Hamlets and contrasts its findings with Bexley and Kensington and Chelsea.

## Files

| File | Purpose |
| --- | --- |
| `london-housing-affordability.ipynb` | Analysis, saved outputs, five charts, research and recommendations |
| `aff1ratioofhousepricetoworkplacebasedearnings.xlsx` | Original ONS workbook |
| `requirements.txt` | Python packages needed to run the notebook |



## Interpretation and limitations

Workplace earnings describe people working in a borough, including commuters; they do not necessarily reflect its residents or a particular buyer's income. The ratios use individual gross earnings, rather than household income, deposits or mortgage repayments.

Area medians hide variation between neighbourhoods and property types. Changes in the mix of properties sold can affect median prices. ONS also identifies limitations in earnings comparisons arising from pandemic disruption and methodological changes.

The findings describe published estimates and do not establish that office construction, regeneration or transport changes caused affordability changes. Investment assessment would require further evidence, including rental yields, financing and ownership costs.

What I found was that earnings caught up with house prices after 2021, which improved the affordability ratios. In some boroughs, falling prices helped too. But that doesn’t mean everyone found buying easier: workplace earnings don’t necessarily represent residents, mortgage costs aren’t included, and 15 areas were still less affordable than in 2015

## Tools

Python, Jupyter Notebooks, pandas, Matplotlib, Seaborn and GitHub.

Created as a Sparta Global data analysis project.
