# Fannie Mae Mortgage Default Analysis: 2007 vs. 2019

This project explores what drove mortgage loan defaults at Fannie Mae by comparing two very different periods in the U.S. housing market — Q4 2007, the peak of the financial crisis, and Q4 2019, a stable period just before COVID-19. The goal was to identify which borrower and loan characteristics were most associated with default, and whether those patterns shifted between the two periods.

All analysis was done in R using ggplot2, plotly, and the tidyverse.

---

## Project Structure

```
fannie-mae-default-analysis/
│
├── Fannie_Mae_Default_Analysis.Rmd   # Main R Markdown analysis file
├── Fannie_Mae_Default_Analysis.html  # Knitted HTML output (open in browser)
│
├── data/
│   ├── data_sample_2007Q4.rds        # 50,000 Fannie Mae loans — Q4 2007 sample
│   ├── data_sample_2019Q4.rds        # 50,000 Fannie Mae loans — Q4 2019 sample
│   └── default_rate_ts.csv           # Quarterly default rate time series, 2000–2023
│
└── README.md
```

---

## Data Source

All data used in this project was sourced from Fannie Mae's publicly available Single-Family Loan Performance dataset, accessible via the [Fannie Mae Data Dynamics portal](https://datadynamics.fanniemae.com/data-dynamics/#/reportMenu;category=HP). The two sample `.rds` files are random draws from the full quarterly releases for Q4 2007 and Q4 2019. The default rate time series was computed from the complete dataset.

A full description of every variable in the original Fannie Mae data is available in the official [Glossary and File Layout document](https://www.fanniemae.com/media/9066/display).

---

## How to Run

1. Clone or download this repository
2. Open `Fannie_Mae_Default_Analysis.Rmd` in RStudio
3. Make sure the following R packages are installed:

```r
install.packages(c("tidyverse", "plotly", "scales", "bookdown"))
```

4. Place all three data files in the same folder as the `.Rmd` file (or update the file paths inside the script)
5. Click **Knit** in RStudio to generate the HTML report

---

## Key Findings

- Loans to borrowers with FICO scores below 620 in 2007 defaulted at rates above 25%, compared to under 2% for scores above 780
- Cash-out refinances defaulted at roughly double the rate of purchase loans in 2007
- Investor-owned properties had default rates nearly twice as high as primary residences during the crisis
- Loans with both high LTV and high DTI were strongly concentrated among the defaulted loans in 2007
- By 2019, all of these risk indicators had improved substantially, reflecting post-crisis underwriting reforms

---

## Tools Used

- **Language:** R
- **Packages:** tidyverse, ggplot2, plotly, scales, bookdown
- **Output:** R Markdown rendered to HTML

---

## References

- Fannie Mae. (2023). *Single-Family Loan Performance Data*. https://datadynamics.fanniemae.com
- Fannie Mae. (2023). *Glossary and File Layout*. https://www.fanniemae.com/media/9066/display
- Federal Housing Finance Agency. (2012). *Report to Congress 2011*. https://www.fhfa.gov
