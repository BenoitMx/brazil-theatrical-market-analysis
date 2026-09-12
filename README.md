# Brazilian Theatrical Market Analysis

## Project Overview

This project analyzes theatrical releases in Brazil using weekly box-office data published by ANCINE.

The objective is to understand how films perform throughout their first four weeks of theatrical exploitation and identify factors associated with screen retention.

The analysis focuses on three questions:

1. What types of theatrical trajectories can be identified?
2. Is W2 screen retention more strongly associated with W1 performance or with
   competitive pressure from new major releases?
3. Does a wider initial release lead to lower admissions per screen?


## Dataset

Source: ANCINE – Brazilian theatrical market data
Period: 2009–2025

Main variables:
- Weekly admissions
- Weekly box-office revenue
- Number of screens
- Distributor
- Genre
- Production country
- Release date


## Data Preparation

The original dataset required substantial preprocessing before analysis.

In particular, theatrical weeks were reconstructed to identify the true first, second, third and fourth weeks of exploitation (W1–W4).

Brazilian theatrical weeks changed from Friday–Thursday to Thursday–Wednesday in March 2014, which was taken into account when reconstructing release weeks.

Preview screenings and extreme screen expansions were also identified as a potential source of distortion. Extreme W1–W2 screen-retention values were excluded from analyses where appropriate.


## Methodology

### SQL / BigQuery
- Data cleaning and transformation
- Reconstruction of theatrical weeks
- W1–W4 performance metrics
- Admissions and revenue per screen
- Screen-retention metrics
- Competitive-pressure indicators

### Python
- pandas
- scikit-learn
- StandardScaler
- K-Means clustering
- Plotly

Films were clustered according to their first four weeks of theatrical
performance, using release scale, revenue per screen and screen-retention
metrics.


## Key Findings

### 1. Four theatrical trajectories emerge

The clustering analysis identifies four distinct release profiles:

- Blockbusters / High-Performing Wide Releases
- Wide Releases / Standard Performers
- Limited Releases / Strong Holdovers
- Limited Releases / Fast Decliners

Films opening on similar numbers of screens can follow substantially different
trajectories during their first four weeks.

<img width="1192" height="892" alt="Four Major Release Categories in the Brasilian theatrical Market" src="https://github.com/user-attachments/assets/973bb6e7-ffcc-4c6b-b27e-bd9aaf39e1c0" />

### 2. Competitive pressure is associated with screen retention

No clear relationship emerges between W1 admissions per screen and W2 screen
retention.

By contrast, films facing more new major releases in Week 2 tend to experience
larger screen losses.

<img width="976" height="725" alt="Capture d’écran 2026-09-11 à 00 20 24" src="https://github.com/user-attachments/assets/014b9816-ac29-43ff-82a6-6eed4064e7e2" />

### 3. Wider releases do not show audience dilution

Admissions per screen remain relatively stable for films opening on 100–999
screens.

Above 1,000 screens, admissions per screen increase substantially, with the
widest releases generating the highest average W1 admissions per screen.

Rather than showing diminishing returns, the results suggest a strong selection
effect: the widest releases are allocated to films with particularly high
audience potential.

<img width="979" height="729" alt="Capture d’écran 2026-09-11 à 00 20 30" src="https://github.com/user-attachments/assets/547cdc5e-e672-4ae1-813c-24ac9d08dcbc" />


## Business Takeaway

The analysis suggests that theatrical distribution decisions should combine:

- Expected audience potential
- Initial release scale
- Competitive pressure
- Early theatrical trajectory

Opening-week performance alone does not fully explain whether a film will retain
its screens in subsequent weeks.


## Dashboard / Presentation

[View the analysis presentation](https://drive.google.com/file/d/1XVX2JsQf4DK1nA4NcwoZPA59o00f63Bz/view?usp=sharing)

[View interactive visualizations](https://datastudio.google.com/reporting/1955bd99-1ff1-46e5-97d7-fef01f3ebb6e)

## Limitations

- The dataset does not include marketing expenditure.
- Release size is not randomly assigned: distributors allocate wider releases
  to films expected to perform strongly.
- Some preview screenings cannot be perfectly identified from the available
  release-date information.
- Results therefore describe associations rather than causal relationships.

## Repository Structure

├── README.md
├── data/
├── notebooks/
│   └── clustering_analysis.ipynb
├── sql/
│   ├── data_cleaning.sql
│   ├── theatrical_weeks.sql
│   └── analysis_tables.sql
├── images/
│   ├── clusters.png
│   ├── competition.png
│   └── release_size.png
└── presentation/


## Tools

BigQuery | SQL | Python | pandas | scikit-learn | Plotly | Looker Studio


## Data Source
<div><span>https://www.gov.br/ancine/pt-br/oca/publicacoes/mercado-audiovisual-brasileiro/cinema/arquivos.csv/listagem-de-filmes-brasileiros-lancados-1995-a-2025.csv</span></div><div><span>https://www.gov.br/ancine/pt-br/oca/publicacoes/mercado-audiovisual-brasileiro/cinema/arquivos.csv/listagem-de-filmes-brasileiros-e-estrangeiros-exibidos-informacoes-por-semana-2009-a-2025.csv</span></div>
