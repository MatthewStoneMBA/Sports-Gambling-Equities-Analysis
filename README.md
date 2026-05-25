# Sports Gambling Equities Analysis

A time series analysis and 2-week trading volume forecast for major sports gambling stocks, built in R. Published following the Supreme Court ruling in May 2018 that opened the door for state-level sports betting legalization.

## Background

After the Supreme Court struck down the Amateur Sports Protection Act of 1992, over two dozen states legalized sports gambling. This created a surge of interest in publicly traded companies building online sports betting platforms — DraftKings, MGM Resorts, Caesars Entertainment (CZR), Penn National Gaming (Barstool), and FanDuel (Flutter Entertainment).

This project analyzes the trading volume of each stock, identifies trends and seasonality, and forecasts volume two weeks out.

## What It Does

- Pulls live equities data using the `tidyquant` R package
- Performs exploratory data analysis (EDA) on each stock
- Decomposes time series to identify seasonality and trends (`fpp3`)
- Builds a function that automatically selects the best-fitting forecast model per stock
- Generates 2-week trading volume forecasts for each company
- Compares forecasts across all five stocks

## Key Findings

- **Highest forecasted volume:** DraftKings (DKNG) and MGM Resorts
- **Lowest forecasted volume:** FanDuel (Flutter) and Caesars Entertainment (CZR)
- Best-fit models: **ARIMA** and **ETS** (Exponential Smoothing) depending on the stock

## Stocks Analyzed

| Company | Ticker |
|---|---|
| DraftKings | DKNG |
| MGM Resorts | MGM |
| Caesars Entertainment | CZR |
| Penn National Gaming (Barstool) | PENN |
| Flutter Entertainment (FanDuel) | FLUT |

## Stack

- R
- R Markdown (`rmdformats::downcute`)
- tidyquant, fpp3, tidyverse, ggplot2, lubridate

## Files

- `Time Series Sports Gambling Equities Analysis.Rmd` — full analysis and forecast
- `Time-Series-Sports-Gambling-Equities-Analysis.html` — rendered report

