# Tick Peek

A Python script to track and display the closing prices and daily percentage changes of major stock indices and user-defined stock positions.

## Features

- Fetches recent closing prices for major indices: Dow Jones (^DJI), S&P 500 (^SPX), NASDAQ (^IXIC), SOX (^SOX), VIX (^VIX), and VXN (^VXN)
- Calculates and displays daily percentage changes for each index
- Prints closing prices for user-specified stock tickers
- Uses [yfinance](https://github.com/ranaroussi/yfinance) for data retrieval
- Loads ticker and index lists from a `config.json` file for easy configuration
- Optional compact output showing only close prices

## Requirements

- Python 3.9+
- `yfinance`
- `numpy`
- `pandas`

Install dependencies with:

```sh
pip install -r requirements.txt
```

## Usage

1. Create a `config.json` file in the project directory with your stock tickers, indices, and fetch days, e.g.:
    ```json
    {
        "TICKER_LIST": "AAPL,MSFT,GOOGL",
        "INDEX_LIST": "^DJI,^SPX,^IXIC,^SOX,^VIX,^VXN",
        "FETCH_DAYS": 60
    }
    ```
2. Run the script to get the closing price for the latest date:
    ```sh
    python app.py
    ```
    or pass a date in YYYY-MM-DD format to get the closing price for the requested date:
    ```sh
    python app.py -d 2025-06-30
    ```
    Note that the requested date must not exceed the range defined by `FETCH_DAYS` in `config.json`.

    Use `-c` / `--compact` for compact output (close prices only):
    ```sh
    python app.py -c
    ```

## Output

The script prints the closing prices and daily changes for indices and your selected stocks in a readable format:

```
^DJI      44632.99   -0.46%
^SPX       6370.86   -0.30%
^IXIC     21098.29   -0.38%
^SOX       5739.79    0.05%
[Your stock positions' closing prices]
```

## License

MIT License
