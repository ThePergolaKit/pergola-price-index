---
title: Pergola Price Index
description: 'Quarterly published summaries of advertised US pergola kit prices by
  roof type and size. Q4 2026: 272 aggregate rows from 8,494 prices at 73 companies.'
datapackage:
  profile: tabular-data-package
  name: pergola-price-index
  title: Pergola Price Index
  description: 'Quarterly published summaries of advertised US pergola kit prices
    by roof type and size. Q4 2026: 272 aggregate rows from 8,494 prices at 73 companies.'
  version: 1.0.0
  homepage: https://thepergolakit.com/pergola-price-index/
  created: '2026-09-28T00:00:00Z'
  keywords:
  - pergola
  - prices
  - economics
  - US
  - quarterly
  - home improvement
  licenses:
  - name: CC-BY-4.0
    title: Creative Commons Attribution 4.0 International
    path: https://creativecommons.org/licenses/by/4.0/
  contributors:
  - title: The Pergola Kit
    role: author
    path: https://thepergolakit.com/
  - title: Anthony Woodland
    role: maintainer
    email: hello@thepergolakit.com
  sources:
  - title: Pergola Price Index, Q4 2026 (baseline edition)
    path: https://thepergolakit.com/pergola-price-index/2026-q4/
  - title: Figshare archived edition
    path: https://doi.org/10.6084/m9.figshare.34018230
  resources:
  - profile: tabular-data-resource
    name: pergola-price-index-2026-q4
    title: Q4 2026 baseline edition
    description: 272 published summaries; captures 24–27 September 2026. Price units
      depend on the table column. Counts overlap across summaries.
    path: data/pergola-price-index-2026-q4.csv
    format: csv
    mediatype: text/csv
    encoding: utf-8
    bytes: 24112
    lastModified: '2026-09-28'
    schema:
      fields:
      - name: table
        type: string
        description: Summary table and units.
      - name: row
        type: string
        description: Roof category or category plus family.
      - name: size_or_band
        type: string
        description: Nominal size or covered-area band.
      - name: median
        type: number
        description: 'Median: USD per kit for typical-price-at-size rows; otherwise
          USD per square foot.'
      - name: p25
        type: number
        description: 25th percentile in the row units.
      - name: p75
        type: number
        description: 75th percentile in the row units.
      - name: min
        type: number
        description: Published minimum in the row units.
      - name: max
        type: number
        description: Published maximum in the row units.
      - name: companies
        type: integer
        description: Reported company count for this summary.
      - name: families
        type: integer
        description: Reported product-family count for this summary.
      - name: price_points
        type: integer
        description: Reported price-point count for this summary.
      - name: label
        type: string
        description: Sample, suppression or benchmark comparison notes.
      missingValues:
      - ''
---

# Pergola Price Index

Published summaries of advertised pergola kit prices for US buyers, produced by [The Pergola Kit](https://thepergolakit.com/pergola-price-index/).

The **Q4 2026 baseline edition** contains **272 summary rows**, derived from **8,494 kit-size prices across 73 companies**, captured **24–27 September 2026** and published **28 September 2026**. This repository distributes the published aggregate CSV as a quarterly series. It does not contain 8,494 individual product records or the underlying captured pages.

- [Price Index report](https://thepergolakit.com/pergola-price-index/)
- [Permanent Q4 2026 edition](https://thepergolakit.com/pergola-price-index/2026-q4/)
- [All editions, downloads and column guide](https://thepergolakit.com/pergola-price-index/data/)
- [Full methodology](https://thepergolakit.com/pergola-price-index/methodology/)
- [Figshare record and DOI](https://doi.org/10.6084/m9.figshare.34018230)

## Contents

The CSV is one UTF-8, long-format table with 12 columns. The `table` field identifies the summary represented by each row:

| Summary (`table` value) | Rows | Price units |
| --- | ---: | --- |
| `category $/sq ft` | 50 | USD per square foot |
| `family $/sq ft (category too small for a median)` | 6 | USD per square foot |
| `typical price at size (USD)` | 165 | USD per kit |
| `$/sq ft by size band` | 48 | USD per square foot |
| `marketplace benchmark vs brand-direct, size-matched ($/sq ft)` | 3 | USD per square foot |

These summaries include category comparisons and alternative groupings; rows can describe overlapping sets of products. Do not sum their counts to obtain a market total.

## Files and editions

| File | Description |
| --- | --- |
| `data/pergola-price-index-2026-q4.csv` | Unmodified published Q4 2026 aggregate data; 272 rows, 24,112 bytes. |
| `README-source-2026-q4.txt` | Original accompanying documentation, preserved unchanged. |
| `LICENSE` | Creative Commons Attribution 4.0 International licence text. |

The index is scheduled quarterly. Q4 2026 is the only edition in this upload. Future editions should be added as separate dated files and configurations, preserving previous releases. See the source website for edition updates and correction notices.

## Column definitions

| Column | Type | Meaning |
| --- | --- | --- |
| `table` | string | Summary table and price units. |
| `row` | string | Roof category or category plus product family. |
| `size_or_band` | string | Nominal size, such as `12x12`, or covered-area band; blank where inapplicable. |
| `median` | number, nullable | Published median in the units specified by `table`. |
| `p25` | number, nullable | Published 25th percentile. |
| `p75` | number, nullable | Published 75th percentile. |
| `min` | number, nullable | Published minimum where provided. |
| `max` | number, nullable | Published maximum where provided. |
| `companies` | integer, nullable | Company count as reported for the summary. |
| `families` | integer | Product-family count as reported for the summary. |
| `price_points` | integer, nullable | Price-point count as reported for the summary. |
| `label` | string | Limited-sample notes, reasons for withheld medians, or benchmark comparisons. |

Empty numeric cells are missing, withheld or inapplicable values, **not zero**. Read the `label` and the source table for context. Count fields describe each published comparison and should not be interpreted as independent observations. Price columns in `typical price at size (USD)` use dollars per kit; other tables use dollars per square foot.

## Collection and methodology

The source study records publicly advertised, purchasable kit prices for US buyers, including sale prices available during the capture window. It groups products by roof type first and frame material second, and treats multiple colours or listings of the same design as one product family.

Where a required component has a public price, the cost of completing a usable kit is included. Quote-only products and products without a readable qualifying price are excluded. The methodology documents additional product exclusions, naming rules, seller coverage, verification and sample thresholds.

For the core comparisons, each product family first receives its own median price per nominal covered square foot. Published category figures summarize those family medians, reducing the influence of product lines with many sizes. Size tables and marketplace comparisons have their own groupings and coverage rules. Amazon and Walmart best-sellers are a separate benchmark rather than part of the headline brand-direct figures.

Prices are kit prices, not installed costs or completed transactions. Tax, installation, foundations, permits and electrical work are excluded. Shipping is generally excluded or separately described; some sellers bundle freight into their advertised price without itemizing it. Refer to the [full methodology](https://thepergolakit.com/pergola-price-index/methodology/) and [edition report](https://thepergolakit.com/pergola-price-index/2026-q4/) for the applicable rules and sensitivity comparisons.

## Suggested uses and limitations

Useful for descriptive price comparisons, reference tables, visualizations, research and reproducible examples of aggregate tabular analysis.

- This release is a single historical snapshot. It cannot establish price changes over time or support time-series forecasting on its own.
- The downloadable data contains aggregates, not individual product prices. It cannot reproduce every calculation from the original study or support product-level prediction by itself.
- Coverage is a purposive collection of publicly priced products, not a random or sales-weighted sample of the entire US market. Quote-only suppliers and inaccessible sources are not represented in the priced sample.
- Some categories have small samples; medians may be withheld. Preserve the accompanying counts and labels when reusing a figure.
- Nominal covered dimensions, product mix, sale timing and bundled freight affect comparisons.
- The publisher operates a commercial pergola comparison website and discloses affiliate commissions. The documentation and CSV provide source attribution and research documentation.
- The uploaded aggregate CSV contains no consumer-level records or personal identifiers.

No separate training, validation or test partition, prediction target, or benchmark score is supplied.

## Load the data

Download [the Q4 2026 CSV](data/pergola-price-index-2026-q4.csv) and read it with any CSV tool. After downloading this repository locally:

```python
import pandas as pd

df = pd.read_csv("data/pergola-price-index-2026-q4.csv")
category_prices = df[df["table"] == "category $/sq ft"]
kit_prices = df[df["table"] == "typical price at size (USD)"]
```

## Licence and citation

Maintainer: Anthony Woodland, [hello@thepergolakit.com](mailto:hello@thepergolakit.com).

The dataset is distributed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). Credit **The Pergola Kit, Pergola Price Index**, link to the source edition and licence, and indicate changes when adapting the data.

Suggested citation:

> The Pergola Kit (2026). *Pergola Price Index, Q4 2026 (baseline edition).* https://thepergolakit.com/pergola-price-index/2026-q4/ . DOI: https://doi.org/10.6084/m9.figshare.34018230

```bibtex
@misc{thepergolakit2026pergolapriceindex,
  author = {{The Pergola Kit}},
  title = {Pergola Price Index, Q4 2026 (baseline edition)},
  year = {2026},
  url = {https://thepergolakit.com/pergola-price-index/2026-q4/},
  doi = {10.6084/m9.figshare.34018230}
}
```

## Source integrity

The CSV is mirrored byte-for-byte from the [original edition download](https://thepergolakit.com/pergola-price-index/2026-q4/pergola-price-index-2026-q4.csv).

SHA-256: `5b32dba0db2215e173b462f811ec0335d86796543b71b47d0e6423081b9c3289`

For questions or corrections, use [The Pergola Kit contact page](https://thepergolakit.com/contact/).
