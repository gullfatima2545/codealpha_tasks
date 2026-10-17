# Real Estate Market Trends Pakistan Property Hotspots
## CodeAlpha Task 3 | Power BI | Gull Fatima
### Business Question
Where are Pakistan's property market hotspots? What do homes typically cost across cities and neighborhoods, what rental yields can investors expect, and which areas deserve a closer look?
### Dataset
191,393 real property listings scraped from Zameen.com (Pakistan's largest property portal), covering 5 cities:
Karachi (60,484) · Lahore (58,736) · Islamabad (40,195) · Rawalpindi (22,898) · Faisalabad (9,080)
Each listing carries: price, purpose (For Sale / For Rent), property type, bedrooms, bathrooms, area (sqft), location, city, latitude/longitude, and listing date. ~72% of listings were collected in Jun–Jul 2019 (a scraping wave, not a market event, see findings).
### Approach
- Star schema (like Task 1): a LocationDim table with one row per area (1,538 areas, average lat/long each), related 1: to the listings fact table via a loc_key, so every slicer and the map filter consistently.
- DAX measures: Avg Sale Price (sale-only via CALCULATE, sale prices and monthly rents must never be averaged together), Total Listings, and Rental Yield % = (median monthly rent × 12) ÷ median sale price, computed per area only where 10+ sales AND 10+ rentals exist (thin-data areas are hidden, not faked).
- Two report pages: Market Overview (KPIs, slicers, trends) and Hotspots & Yields (Azure Map bubble map + top-15 yield ranking).
### Key Findings
1. Two Pakistans in one market. Average sale price is PKR 24.7M, but the median is only 13.5M, luxury listings drag the average up. Islamabad is priciest (31.3M avg), Faisalabad most affordable (14.1M): a 2.2x gap.
2. Houses cost ~2.6x flats. Houses average 29.2M vs flats 11.2M; farmhouses top the ladder at 64.4M.
3. Hotspots are branded. The map's biggest price bubbles sit on DHA and Bahria Town societies in every major city, branded developments command the premium.
4. Commercial corridors win on yield. Shahra-e-Faisal (Karachi) ~19%, PWD Road and Tarnol (Islamabad) ~11%, well above the 3.1% median yield across areas. Pure residential pockets lag.
5. The July 2019 "boom" is a mirage. The listing-activity spike marks when the scraper ran, not a market surge, a reminder to question spikes before reporting them.
6. Sample-size discipline matters. An early version of the yield chart showed a 63% yield built on a handful of listings; the 10+10 guardrail removed every such artifact.
### Recommendations
- Target mid-tier 7–9% yield areas (e.g. Eden Villas Lahore, Amin Town) for the best risk-adjusted profile.
- Verify outliers on the ground extreme yields often mix property types (shops vs houses) within one area label.
- Weight branded developments for capital growth; weight commercial corridors for rental income they play different roles in a portfolio.
- Refresh before deciding this data is 2018–2019 vintage; re-run the analysis on current listings before committing capital.
### Files in this submission
- Real_Estate_Market_Trends.pbix: the interactive Power BI report (2 pages)
- Real_Estate_Trends.pdf: browser-viewable export of the report
- zameen_listings.zip: source dataset (191,393 Zameen.com listings)
- README.md: this write-up
