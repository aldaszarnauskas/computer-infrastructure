# Computer Infrastructure

### Author

**Aldas Zarnauskas**

---

## Table of Contents

* [Overview](#project-overview)
* [Data Source](#data-source)
* [Preprocessing](#preprocessing)
* [Analysis and Figures](#analysis-and-figures)
* [Requirements](#requirements)
* [License](#license)

---

## Project Overview

This project demonstrates how to build an automated GitHub Actions workflow designed to fetch and visualize financial data for the FAANG companies: **Facebook (Meta)**, **Apple**, **Amazon**, **Netflix**, and **Google (Alphabet)**. Every Saturday, a scheduled GitHub Action automatically executes the script **faang.py**, which downloads the hourly closing prices for the previous five days and generates corresponding plots.

The workflow configuration is defined in [`.github/workflows/faang.yml`](.github/workflows/faang.yml). Once executed, the workflow stores the generated datasets and figures in dedicated directories within the repository:

* **`/plots/`** – Contains all automatically generated visualizations.
* **`/data/`** – Contains the datasets used to produce each plot.
* **`faang.py`** – The main Python script responsible for fetching data, cleaning it, and creating the final plots.
* **`.github/workflows/faang.yml`** – Defines when and how the automated workflow runs.
* **`problems.ipynb`** – A notebook documenting the development process, illustrating intermediate steps, and explaining how each component of the GitHub Action works.

**A curious person:** Why did you create this project?
**Aldas:** I created this project to deepen my understanding of GitHub Actions and how automation can streamline repetitive tasks. It also serves as my submission for the *Computer Infrastructure* module at Atlantic Technological University.

---

## Data Source

All FAANG stock data is retrieved using the `download` function from the **yfinance** Python package, ensuring a reliable and programmatic way to access financial time series data.

---


## Analysis and Figures

Here is an example of the plot of the FAANG hourly closing stock prices for the last five days.

![An example](/plots/20251116-084022.png)

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
