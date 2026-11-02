# Crime suspects by nationality in Germany (PKS 2025)

Analysis of official German police crime statistics: how suspect counts and population-adjusted rates differ by citizenship, and whether that picture changes across offence groups such as theft, violent crime, and offences against life.

Absolute counts alone can mislead when groups differ a lot in size, so rates per 100,000 residents (approx. age 8+) are used alongside the raw totals.

## Questions

- Which nationalities dominate absolute suspect counts?
- How do those same groups look once expressed as suspects per 100k?
- Does that ranking change across selected offence groups?

## Notebooks

| File | Role |
|------|------|
| [`Part_I_notebook.ipynb`](Part_I_notebook.ipynb) | Data wrangling and exploratory charts |
| [`Part_II_notebook.ipynb`](Part_II_notebook.ipynb) | Short presentation of the main findings |
| [`data/polished_dataset.csv`](data/polished_dataset.csv) | Cleaned rates table written at the end of Part I; input for Part II |

## Data

- **BKA** (Federal Criminal Police Office): PKS 2025 suspects by nationality/offence and German vs non-German population totals (age 8+). Fetched automatically when Part I runs.
- **Destatis** (Federal Statistical Office): population by citizenship (table `12411-0009`, 31 Dec 2024). Download manually to `data/12411-0009_en.csv` (see the note in Part I). When exporting, turn off quality symbols (see [screenshot of download page](destatis-download.png)).

## How to run

1. Use a Python environment with `numpy`, `pandas`, `matplotlib`, `seaborn`, `requests`, and Excel support (`openpyxl`).
2. Put Destatis `12411-0009_en.csv` in `data/`.
3. Run Part I top to bottom (downloads BKA files, explores the data, writes `polished_dataset.csv`).
4. Run Part II for the presentation plots.

---

Sources: [BKA PKS](https://www.bka.de/DE/AktuelleInformationen/StatistikenLagebilder/PolizeilicheKriminalstatistik/pks_node.html) / [PKS 2025](https://www.bka.de/DE/AktuelleInformationen/StatistikenLagebilder/PolizeilicheKriminalstatistik/PKS2025/Polizeiliche_Kriminalstatistik_2025/Polizeiliche_Kriminalstatistik_2025_node.html), [Destatis GENESIS](https://genesis.destatis.de/datenbank/online/) (table 12411-0009). Reuse subject to those agencies' terms.