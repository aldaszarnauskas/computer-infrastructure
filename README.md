# Creating GitHub Actions Workflow (Submission for Computer Infrastructure module)

### Author

**Aldas Zarnauskas**

---

## Table of Contents

* [Project Overview](#project-overview)
* [GitHub Actions Workflow](#github-actions-workflow)
* [The Main Folders and Files](#the-main-folders-and-files)
* [Data Source](#data-source)
* [Figures](#figures)
* [Requirements](#requirements)
* [License](#license)

---

## Project Overview

This project demonstrates how to build an automated GitHub Actions workflow (from this point onward workflow) designed to fetch and visualize financial data for the FAANG companies: **Facebook (Meta)**, **Apple**, **Amazon**, **Netflix**, and **Google (Alphabet)**. Every Saturday at 08:00 AM UTC, a scheduled GitHub Action automatically executes the script ['faang.py'](./faang.py). The script downloads, from the Yahoo Finance's servers, the hourly prices of the FAANG stocks, for the previous five days and stores it in ['./data/'](./data/) folder. Correspndingly, the script generates a plot for the hourly closing prices of the FAANG stocks for the previous five days and stores it in ['./plots/'](./plots/) folder.

---

### GitHub Actions Workflow
The GitHub Actions workflow file is located at [`.github/workflows/faang.yml`](.github/workflows/faang.yml). A GitHub Actions workflow is a feature that automates tasks in a GitHub repository. This workflow includes several functionalities and features, one of the most important being the ability to specify when it should run.
Workflows can be triggered in multiple ways, including event-based triggers, manual triggers, and scheduled triggers. The workflow described here uses a scheduled trigger, meaning it runs automatically at a predefined date and time.
When triggered, the workflow executes the instructions defined in [`.github/workflows/faang.yml`](.github/workflows/faang.yml). This file contains all the necessary steps to generate the plots of FAANG stock prices.
The script and its steps are described in detail in the [`./problems.ipynb`](./problems.ipynb) file, under the "Problem 4: Automation" section.

---

## The Main Folders and Files

* **`/plots/`** – Contains all automatically generated visualizations.
* **`/data/`** – Contains the datasets used to produce each plot.
* **`faang.py`** – The main Python script responsible for fetching data, cleaning it, and creating the final plots.
* **`.github/workflows/faang.yml`** – Defines when and how the automated workflow runs.
* **`problems.ipynb`** – A notebook documenting the development process, illustrating intermediate steps, and explaining how each component of the GitHub Action works.

---

## Data Source

All FAANG stock data is retrieved, from the Yahoo Finance's servers, using the `yfinance.download` function from the **yfinance** Python package.

---

## Figures

Here are examples of the plots of the FAANG hourly closing stock prices for the last five days.

| 20251129-081222.png                          | 20251206-081218.png                           |
| ---------------------------------------- | -------------------------------- |
| ![Plot 1](/plots/20251129-081222.png)            | ![Plot 2](/plots/20251206-081218.png)  |
| ---------------------------------------- | -------------------------------- |
| 20251213-081233.png                          | 20251220-081232.png                           |
| ---------------------------------------- | -------------------------------- |
| ![Plot 1](/plots/20251213-081233.png)            | ![Plot 2](/plots/20251220-081232.png)  |

---

## Requirements

Before running the project locally, install the necessary dependencies:

```
pip install -r requirements.txt
```

---

## License

No license.

---
