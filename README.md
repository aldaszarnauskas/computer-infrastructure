# FAANG Stock Tracker — Automated with GitHub Actions

*Submission for the Computer Infrastructure module, ATU*

![Workflow status](https://github.com/aldaszarnauskas/computer-infrastructure/actions/workflows/faang.yml/badge.svg)

### Author
**Aldas Zarnauskas**

---

## Table of Contents
* [Project Overview](#project-overview)
* [GitHub Actions Workflow](#github-actions-workflow)
* [The Main Folders and Files](#the-main-folders-and-files)
* [Data Source](#data-source)
* [Figures](#figures)
* [How to Run Locally](#how-to-run-locally)
* [License](#license)

---

## Project Overview

This project demonstrates how to build an automated GitHub Actions workflow (from this point onward, "workflow") designed to fetch and visualize financial data for the FAANG companies: **Facebook (Meta)**, **Apple**, **Amazon**, **Netflix**, and **Google (Alphabet)**.

Every Saturday at 08:00 AM UTC, a scheduled GitHub Action automatically executes the script [`faang.py`](./faang.py). The script downloads, from Yahoo Finance's servers, the hourly prices of the FAANG stocks for the previous five days and stores them in the [`./data/`](./data/) folder. Correspondingly, the script generates a plot of the hourly closing prices of the FAANG stocks for the previous five days and stores it in the [`./plots/`](./plots/) folder.

---

## GitHub Actions Workflow

The GitHub Actions workflow file is located at [`.github/workflows/faang.yml`](.github/workflows/faang.yml). A GitHub Actions workflow is a feature that automates tasks in a GitHub repository. This workflow includes several functionalities and features, one of the most important being the ability to specify when it should run.

Workflows can be triggered in multiple ways, including event-based triggers, manual triggers, and scheduled triggers. The workflow described here uses a scheduled trigger, meaning it runs automatically at a predefined date and time.

When triggered, the workflow carries out the following steps, as defined in [`.github/workflows/faang.yml`](.github/workflows/faang.yml):

1. Checks out the repository.
2. Sets up the Python environment.
3. Installs the required dependencies.
4. Runs [`faang.py`](./faang.py) to download the data and generate the plot.
5. Commits and pushes the new data and plot files back to the repository.

The script and its steps are described in detail in the [`problems.ipynb`](./problems.ipynb) file, under the "Problem 4: Automation" section.

---

## The Main Folders and Files

* **`/plots/`** – Contains all automatically generated visualizations.
* **`/data/`** – Contains the datasets used to produce each plot.
* **`faang.py`** – The main Python script responsible for fetching data, cleaning it, and creating the final plots.
* **`.github/workflows/faang.yml`** – Defines when and how the automated workflow runs.
* **`problems.ipynb`** – A notebook documenting the development process, illustrating intermediate steps, and explaining how each component of the GitHub Action works.

---

## Data Source

All FAANG stock data is retrieved from Yahoo Finance's servers using the `yfinance.download` function from the **yfinance** Python package.

---


## Figures

**Here are examples of the plots of the FAANG hourly closing stock prices for the last five days**

| November 29, 2025                       | December 6, 2025                        |
| --------------------------------------- | --------------------------------------- |
| ![FAANG stocks plot for week ending Nov 29, 2025](/plots/20251129-081222.png) | ![FAANG stocks plot for week ending Dec 6, 2025](/plots/20251206-081218.png) |

| December 13, 2025                       | December 20, 2025                        |
| --------------------------------------- | --------------------------------------- |
| ![FAANG stocks plot for week ending Dec 13, 2025](/plots/20251213-081233.png) | ![FAANG stocks plot for week ending Dec 20, 2025](/plots/20251220-081232.png) |

---
## How to Run Locally

Requires **Python 3.10+**.

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/yourrepo.git
   cd yourrepo
   ```
2. Install the dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Run the script:
   ```
   python faang.py
   ```

The downloaded data will be saved to `./data/` and the generated plot to `./plots/`.

---

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
