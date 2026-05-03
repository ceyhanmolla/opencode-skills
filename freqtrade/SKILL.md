# Freqtrade Skill

## Overview

This skill provides comprehensive knowledge for using and understanding the Freqtrade cryptocurrency trading bot. Freqtrade is an open-source Python-based crypto trading bot that supports all major exchanges and can be controlled via Telegram or WebUI.

## What Freqtrade Does

Freqtrade enables you to:

- **Strategy Development**: Write your own trading strategies in Python
- **Data Download**: Download historical market data from exchanges
- **Backtesting**: Test strategies on historical data
- **Optimization (Hyperopt)**: Find optimal parameters using machine learning
- **Telegram Control**: Manage your bot via Telegram
- **WebUI**: Monitor and control via web interface

## Getting Started

For basic operation concepts, see: [Bot Basics](./reference/bot-basics.md)

## Strategy Development

Learn how to develop strategies: [Strategy 101](./reference/strategy-101.md)

### Strategy Methods

- `populate_indicators()`: Calculate technical indicators
- `populate_entry_trend()`: Create entry signals
- `populate_exit_trend()`: Create exit signals

### Signal Types

| Signal | Description |
|--------|-------------|
| `enter_long` | Open long position |
| `enter_short` | Open short position |
| `exit_long` | Close long position |
| `exit_short` | Close short position |

## Configuration

For configuration settings: [Configuration](./reference/configuration.md)

### Key Parameters

- `max_open_trades`: Maximum open trades limit
- `stake_currency`: Stake currency (e.g., USDT)
- `stake_amount`: Amount per trade
- `minimal_roi`: Minimum return on investment
- `stoploss`: Stoploss percentage

## Testing and Optimization

### Backtesting

Learn about backtesting: [Backtesting](./reference/backtesting.md)

```bash
freqtrade backtesting --strategy MyStrategy
```

### Hyperopt

Learn about parameter optimization: [Hyperopt](./reference/hyperopt.md)

```bash
freqtrade hyperopt --strategy MyStrategy --hyperopt-loss SharpeHyperOptLossDaily -e 500
```

## Bot Management

### Telegram Commands

For Telegram bot control: [Telegram](./reference/telegram-usage.md)

Key commands:
- `/start` - Start the bot
- `/stop` - Stop the bot
- `/status` - Show status
- `/balance` - Show balance
- `/profit` - Show profit/loss

### WebUI

```bash
freqtrade UI
```

## Running the Bot

### Start Bot

```bash
# Dry-run (simulation)
freqtrade trade --config config.json --strategy MyStrategy

# Live trading
freqtrade trade --config config.json --strategy MyStrategy --dry-run false
```

### Download Data

```bash
freqtrade download-data --exchange binance --pairs BTC/USDT ETH/USDT --timeframe 5m
```

### Backtesting

```bash
freqtrade backtesting --strategy MyStrategy --timerange 20210101-
```

### Hyperopt

```bash
freqtrade hyperopt --strategy MyStrategy --spaces roi stoploss -e 500
```

## Supported Exchanges

### Spot Exchanges
- Binance, BingX, Bitget, Bitmart, Bybit, Gate.io, HTX, Kraken, OKX, Hyperliquid

### Futures Exchanges
- Binance, Bitget, Bybit, Gate.io, Hyperliquid, OKX, Kraken

## Technical Indicators

Popular indicators (using talib):

```python
import talib.abstract as ta

# RSI
dataframe['rsi'] = ta.RSI(dataframe, timeperiod=14)

# MACD
macd = ta.MACD(dataframe)
dataframe['macd'] = macd['macd']
dataframe['macdsignal'] = macd['macdsignal']

# EMA/SMA
dataframe['ema20'] = ta.EMA(dataframe, timeperiod=20)
dataframe['sma50'] = ta.SMA(dataframe, timeperiod=50)

# Bollinger Bands
bb = ta.BBANDS(dataframe, timeperiod=20)
dataframe['bb_upper'] = bb['upperband']
dataframe['bb_middle'] = bb['middleband']
dataframe['bb_lower'] = bb['lowerband']
```

## Important Warnings

> **DISCLAIMER**: This software is for educational purposes only. Do not risk money which you are afraid to lose. USE THE SOFTWARE AT YOUR OWN RISK. THE AUTHORS AND ALL AFFILIATES ASSUME NO RESPONSIBILITY FOR YOUR TRADING RESULTS.

> Always start by running a trading bot in Dry-run mode and do not engage money before you understand how it works.

## Additional Reference

For more details on specific topics:

### Getting Started
- [Installation](./reference/installation.md): Installation guide
- [Docker Quickstart](./reference/docker_quickstart.md): Docker installation
- [Bot Basics](./reference/bot-basics.md): Bot operation basics
- [Bot Usage](./reference/bot-usage.md): Running the bot

### Strategy Development
- [Strategy 101](./reference/strategy-101.md): Strategy basics
- [Strategy Advanced](./reference/strategy-advanced.md): Advanced strategy techniques
- [Strategy Callbacks](./reference/strategy-callbacks.md): Custom callbacks
- [Strategy Customization](./reference/strategy-customization.md): Customizing strategies
- [Strategy Analysis Example](./reference/strategy_analysis_example.md): Strategy analysis
- [Strategy Migration](./reference/strategy_migration.md): Migrating strategies

### Configuration
- [Configuration](./reference/configuration.md): Configuration settings
- [Exchanges](./reference/exchanges.md): Exchange-specific settings
- [Leverage](./reference/leverage.md): Trading with leverage
- [Plugins](./reference/plugins.md): Plugins and pairlists

### Testing and Optimization
- [Backtesting](./reference/backtesting.md): Historical testing
- [Advanced Backtesting](./reference/advanced-backtesting.md): Advanced backtesting
- [Hyperopt](./reference/hyperopt.md): Parameter optimization
- [Advanced Hyperopt](./reference/advanced-hyperopt.md): Advanced hyperopt
- [Lookahead Analysis](./reference/lookahead-analysis.md): Lookahead analysis
- [Recursive Analysis](./reference/recursive-analysis.md): Recursive analysis
- [Plotting](./reference/plotting.md): Plotting results
- [Data Analysis](./reference/data-analysis.md): Data analysis

### Risk Management
- [Stoploss](./reference/stoploss.md): Stoploss configuration

### Bot Management
- [Telegram](./reference/telegram-usage.md): Telegram commands
- [FreqUI](./reference/freq-ui.md): Web interface
- [REST API](./reference/rest-api.md): REST API
- [Webhook](./reference/webhook-config.md): Webhook configuration
- [Utils](./reference/utils.md): Utility commands

### Data
- [Data Download](./reference/data-download.md): Downloading data
- [Trade Object](./reference/trade-object.md): Trade object
- [SQL Cheatsheet](./reference/sql_cheatsheet.md): SQL queries

### Advanced Topics
- [Advanced Setup](./reference/advanced-setup.md): Advanced setup
- [Advanced Orderflow](./reference/advanced-orderflow.md): Order flow
- [Producer Consumer](./reference/producer-consumer.md): Producer/Consumer mode

### Other
- [FAQ](./reference/faq.md): Frequently asked questions
- [Updating](./reference/updating.md): Updating Freqtrade
- [Deprecated](./reference/deprecated.md): Deprecated features
- [Developer](./reference/developer.md): Developer guide

## More Information

- Official documentation: https://www.freqtrade.io
- GitHub: https://github.com/freqtrade/freqtrade
- Discord: https://discord.gg/p7nuUNVfP7
- Strategy examples: https://github.com/freqtrade/freqtrade-strategies