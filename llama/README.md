# Llama Strategy Indicator

A TradingView Pine Script indicator that tracks overnight forex sessions and automatically generates Fibonacci retracement levels for intraday trading.

## Overview

The Llama Strategy indicator visualizes three major forex sessions (Sydney, Asia, London) and automatically calculates Fibonacci retracement levels based on the overnight range between Sydney and Asia sessions.

## Features

### Session Tracking
- **Sydney Session**: 6pm-3am ET (hidden by default)
- **Asia Session**: 8pm-5am ET
- **London Session**: 3am-12pm ET

### Fibonacci Retracement
After the Asia session ends, the indicator automatically draws Fibonacci retracement levels:
- **Uptrend** (Asia high > Sydney high): Retracement from Sydney low to Asia high
- **Downtrend** (Asia low < Sydney low): Retracement from Sydney high to Asia low

### Retracement Levels
- 0.236 (23.6%)
- 0.786 (78.6%)
- -0.236 (23.6% extension)
- -0.786 (78.6% extension)

## Usage

1. Add the indicator to your TradingView chart
2. Configure session visibility in the settings
3. Fibonacci levels automatically appear after Asia session closes
4. All drawings reset at 6pm ET (new forex trading day)

## Settings

### Sessions
- Toggle individual session visibility
- Customize session colors
- Show/hide session labels

### Fibonacci
- Toggle Fibonacci retracement display
- Adjust line width
- Show/hide floating level labels

### Visual
- Customize text size
- Adjust box border width
- Configure label colors

## Trading Strategy

The Llama strategy uses overnight session ranges to identify key support and resistance levels for the upcoming trading day. The Fibonacci retracement levels provide potential entry and exit points based on the overnight price action between Sydney and Asia sessions.

## Notes

- All times are in Eastern Time (ET)
- Indicator resets daily at 6pm ET
- Requires intraday timeframe for proper display
- Maximum 500 drawing objects supported