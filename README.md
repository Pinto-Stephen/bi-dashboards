# BI Portfolio

![Tableau](https://img.shields.io/badge/Tableau-Public-E97627)
![Power BI](https://img.shields.io/badge/Power%20BI-PBIP%20and%20TMDL-F2C811)
![DAX](https://img.shields.io/badge/DAX-measures-blue)
![Data Modeling](https://img.shields.io/badge/Data%20Modeling-star%20schema-success)

Three business analytics dashboards, each built twice, once in Tableau and once in Power BI. Building every dashboard in both tools is deliberate as it proves versatility in skill. 

Every dashboard below has a live, interactive link, so you can explore it without downloading anything. The packaged files and the documentation sit inside each folder.

## Dashboards

| Dashboard | Business question | Tableau | Key insight |
|---|---|---|---|
| Credit Card Portfolio | How revolving balances, charge offs, and delinquency vary across customer segments and geographies. | [View](https://public.tableau.com/views/CreditcardportfolioDashboard/Dashboard4?:language=en-US&:sid=&:redirect=auth&publish=yes&showOnboarding=true&:display_count=n&:origin=viz_share_link)  | The youngest age band carries both the highest revolving rate and the steepest charge off rate. |
| Airline Operations | How on time performance, load factor, and fuel cost drive route level profitability. | [View](https://public.tableau.com/views/IndigoAirlineOps/FuelCost?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link) | Three short haul routes show strong load factors, yet thin margins once fuel cost is allocated. |
| Pharma Promotion ROI | How promotional spend converts into incremental sales across channels and physician segments. | [View](https://public.tableau.com/views/pharma-dashboard/Dashboard3?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link) | Field calls outperform digital spend for high decile prescribers, the reverse holds for low decile ones. |


## Repository structure

```
bi-portfolio/
├── README.md
├── .gitignore
├── credit-card-portfolio/
│   ├── README.md
│   ├── tableau/        credit-card-portfolio.twbx
│   ├── powerbi/        CreditCardPortfolio.pbip, .Report (PBIR), .SemanticModel (TMDL), .pbix
│   ├── data/           data for the powerbi workbook to work
│   └── screenshots/    overview.png, drilldown.png
├── airline-operations/   (same structure)
└── pharma-promo-roi/     (same structure)
```

## How to open

The Tableau workbooks are packaged as .twbx files, so they open directly in Tableau Public or Tableau Desktop with the data included. The Power BI reports are saved as Power BI Project folders. Open the .pbip file in Power BI Desktop to edit, and a packaged .pbix is also included for one click viewing. Each Power BI model is stored as TMDL text and each report as PBIR text, so every measure and visual change stays readable in version control.

## Data

Each dashboard folder contains a data folder with a sample extract and a data_dictionary.md that describes every field. All datasets here are public or synthetic. No confidential data is committed.

## Skills demonstrated

Data modeling with a star schema, DAX and Tableau calculated fields, drill down and cross filtering, KPI design, executive level storytelling, and version control of BI artifacts with Git.

## About

Built by Stephen Pinto, M.Tech Aerospace at IIT Bombay. [LinkedIn](www.linkedin.com/in/stephen-pinto-b56205204).