# S&P 500 Data Downloader & Inauguration Performance Analysis

This project uses a Jupyter notebook (`main.ipynb`) to:

- Download historical S&P 500 data from Yahoo Finance
- Store the data in a CSV file (`sp500_bulk_data.csv`)
- Resume downloading from the last known date (idempotent)
- Clean the file by removing malformed header rows
- Analyze and plot S&P 500 performance over the first 100 trading days of recent U.S. presidents

## Requirements

Install dependencies with:

```bash
pip install pandas yfinance matplotlib
```

## Usage

1. Open the notebook:

```bash
jupyter notebook main.ipynb
```

2. Run all cells. The notebook will:
   - Download or update `sp500_bulk_data.csv`
   - Remove any malformed rows (e.g., from Yahoo headers like `,^GSPC,...`)
   - Generate a line chart showing % change from Day 0 of each presidency

## Output

- `sp500_bulk_data.csv` — Daily S&P 500 index data from 2013 to today
- A matplotlib chart showing how the S&P 500 performed during the early days of:
  - Barack Obama (2013)
  - Donald Trump (2017, 2025)
  - Joe Biden (2021)

## Notes

- Data is downloaded in 90-day chunks to avoid rate limits.
- The CSV is automatically updated without duplicating existing data.
- Inauguration performance is calculated from the closing price on each president’s inauguration day.
