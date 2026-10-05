# Financial Chart Pattern Image Dataset

**Version:** 1.0.0  
**Release date:** 2026-10-05  
**Dataset creator:** Mahdi Mohammadiha  
**Affiliation:** Computer Engineering Department, Imam Khomeini International University, Qazvin, Iran  
**Status:** Private / Research Collaboration

## Overview

The **Financial Chart Pattern Image Dataset** is a curated image dataset designed for research on financial chart-pattern recognition using machine learning and deep learning methods.

Version 1.0.0 contains **1,200 candlestick chart images** distributed equally across four financial chart-pattern classes:

| Class | Images |
|---|---:|
| Double Top | 300 |
| Double Bottom | 300 |
| Head and Shoulders | 300 |
| Inverse Head and Shoulders | 300 |
| **Total** | **1,200** |

The dataset was created and curated independently by **Mahdi Mohammadiha**.

## Dataset Construction

The dataset was constructed from publicly available Forex financial time-series data. The raw time-series data were obtained from:

**TheSnowGuru — Stocks-Futures-Financial-Time-series-Tick-Bar-Data**

Source repository:
https://github.com/TheSnowGuru/Stocks-Futures-Financial-Time-series-Tick-Bar-Data

The source repository provides historical financial data in CSV format across multiple instruments and timeframes. Its README states that the data are made available under the MIT License and that appropriate attribution should be provided.

The construction process for this dataset consisted of:

1. Obtaining the required Forex time-series CSV files from the source repository.
2. Processing the time-series data using Python.
3. Implementing four rule-based algorithms, one for each target chart pattern.
4. Using the algorithms to detect candidate pattern instances.
5. Rendering candidate instances as 224 × 224 pixel candlestick chart images.
6. Manually reviewing the generated candidates.
7. Selecting 300 high-quality and correctly identified examples for each pattern class.

Therefore, the dataset construction combines **algorithmic pattern detection** with **manual verification and curation**.

## Pattern Classes

The four classes included in this release are:

- Double Top
- Double Bottom
- Head and Shoulders
- Inverse Head and Shoulders

Pattern identification was based on established definitions of the respective financial chart patterns. Rule-based detection algorithms were developed according to these definitions, followed by manual review to correct or remove erroneous detections.

The evaluation of the patterns primarily considers **open and close price behavior**. Candlestick shadows/wicks are present in the rendered images, but they were not used as the primary criterion for determining whether an instance belongs to a target pattern class.

## Source Financial Data

The dataset was derived from Forex time-series data covering the following 18 currency pairs:

- AUDCAD
- AUDUSD
- EURUSD
- EURCAD
- EURCHF
- EURGBP
- EURJPY
- EURNZD
- EURAUD
- GBPAUD
- GBPCAD
- GBPCHF
- GBPJPY
- GBPUSD
- NZDUSD
- USDCAD
- USDCHF
- USDJPY

Four timeframes were used for each currency pair:

- 1D
- 4H
- 1H
- 15M

This results in **72 currency-pair/timeframe combinations**.

The original source repository documents its timestamps as GMT/Greenwich Mean Time.

## Image Characteristics

Each dataset sample is a **224 × 224 pixel** candlestick chart image.

The charts contain:

- Green and red candlesticks.
- Open and close price information represented by the candlestick bodies.
- High and low price information represented by candlestick shadows/wicks.

The images do **not** include volume, technical indicators, or other auxiliary indicators.

The 224 × 224 images were generated directly during the dataset-generation process; they were not subsequently resized from a larger image.

## Software and Tools

The dataset-generation and pattern-detection workflow was implemented in **Python** and executed in the **marimo** computational environment.

The development workflow used, among other components:

- NumPy
- pandas
- re
- zipfile
- dataclasses
- pathlib
- Matplotlib
- Pillow (PIL)
- SciPy
- `scipy.signal.find_peaks`

The dataset itself is an output of the processing and curation workflow rather than a redistribution of the original CSV time-series files.

## Intended Use

The primary intended use of this dataset is academic and research-oriented work, including:

- Machine learning experiments.
- Deep learning experiments.
- Financial chart-pattern recognition.
- Image classification.
- Benchmarking and evaluation of pattern-recognition approaches.
- Research publications.

At the time of version 1.0.0, the dataset is **not publicly released**. It may be provided to research collaborators under the terms specified in `TERMS_OF_USE.md`.

## Ownership and Attribution

The dataset creator and curator is:

**Mahdi Mohammadiha**

Affiliation:

**Computer Engineering Department  
Imam Khomeini International University  
Qazvin, Iran**

The creator claims authorship and ownership of the original dataset-specific work, including the selection, processing, algorithmic detection workflow, manual verification, curation, and organization of the image dataset.

This statement does **not** claim ownership of the underlying third-party raw financial time-series data. The raw financial data remain subject to the terms and rights applicable to their original source.

## Collaboration

The dataset was created solely by Mahdi Mohammadiha. No collaborator is listed as a dataset creator or contributor for version 1.0.0.

The dataset may subsequently be used by research collaborators for machine learning/deep learning experiments and research evaluation. Such use does not by itself confer authorship, ownership, or contributor status regarding the dataset.

## Current Access Status

This version is maintained as a **private research dataset**.

Do not redistribute, publish, upload, mirror, sell, sublicense, or otherwise make the dataset publicly available without written permission from the dataset creator.

See `TERMS_OF_USE.md` for the applicable research-collaboration terms.

## Versioning

This dataset follows semantic-style versioning.

### v1.0.0 — 2026-10-05

Initial version containing:

- 4 chart-pattern classes.
- 300 images per class.
- 1,200 images in total.
- 18 Forex currency pairs.
- 4 timeframes per currency pair.
- 72 currency-pair/timeframe combinations.
- 224 × 224 pixel candlestick chart images.

Future versions may expand the number of pattern classes, samples, source instruments, timeframes, or other dataset characteristics.

## Citation

If you use this dataset in research, please cite it as specified in `CITATION.cff`.

Until a DOI or public repository URL is assigned, the recommended citation is:

> Mohammadiha, M. (2026). *Financial Chart Pattern Image Dataset* (Version 1.0.0).

## Contact

**Mahdi Mohammadiha**

University email: mahdi.mohammadiha@edu.ikiu.ac.ir  
Personal email: m.mohamadiha81@gmail.com

## Important Note

This dataset contains derived visual representations of financial time-series data. It is intended for research and educational purposes and is not financial advice, a trading signal, or a guarantee of financial performance.
