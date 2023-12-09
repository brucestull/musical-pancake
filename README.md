# Investment Tracker

## Project Description

This is a web application that allows users to track their investments. Users can create an account, add investments to their portfolio, and view their portfolio's performance over time.

- Track market data over time.
- Track portfolio P/L over time.
- Track individual trade P/L.
- Retrieve market data from an API. Specifically, the greeks for options.
- Store market data in a database.

## Table of Contents

## Screenshots and GIFs

## Technologies Used

- Django
- Python
- PostgreSQL
- HTML
- Bootstrap
- CSS
- JavaScript
- requests
- pandas
- matplotlib
- numpy
- black
- flake8
- isort

## Features

### Current Features

- User can create an account.
- Administrator can create, read, update, and delete users.
- Administrator can update users' `registration_accepted` status.

### Future Features

- User can create, read, update, and delete Positions.
  - In trading, a position can refer to the state of owning (long position) or owing (short position) a particular stock.
- Anaylyze portfolio performance over time.
  - Calculate portfolio P/L over time.
  - Track individual trade P/L.
  - Track the greeks for options.
  - Track corrolations between the greeks in positive P/L and negative P/L trades.

## Applications and Models

- PLTracker (p_l_tracker)
  - `User`
  - `Portfolio`
    - `user`: ForeignKey to User
    - `name`: CharField
    - `description`: TextField
    - `created_at`: DateTimeField
    - `updated_at`: DateTimeField
    - `option_contracts`: ManyToManyField to `OptionContract`
  - `OptionContract`
    - `portfolio`: ForeignKey to `Portfolio`
    - `symbol`: CharField
    - `option_type`: CharField with choices `CALL` and `PUT` and `BOTH`
    - `expiration_date`: DateField
    - `strike_price`: DecimalField
    - `contract_size`: IntegerField
    - `premium`: DecimalField
    - `position_type`: CharField with choices `LONG`, `SHORT`, and `BOTH`
  - `Trade`
    - `option_contract`: ForeignKey to `OptionContract`
    - `portfolio`: ForeignKey to Portfolio
    - Greeks Values
      - Delta
      - Gamma
      - Theta
      - Vega
      - Rho
    - Implied Volatility
  - Stock
  - ETF
  - Currency
  - Position
    - Stock, Option, Currency, ETF, etc.
  - Trade
- Portfolio
  - PortfolioPosition

## Known Issues and Areas for Improvement

## Setup and Installation

## Usage

## License

## Acknowledgements

## Contact Information
