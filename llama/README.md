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

### Level Lines
The indicator draws horizontal level lines with configurable triads (High/Low/50%):

#### Standard Levels (Teal colored, no breach detection):
- **Current Day Open**: Opens at 6pm ET (forex day start)
- **True Day Open**: Opens at midnight (12am ET)
- **Previous Day Triad**: High/Low/50% from previous day
- **Previous Week Triad**: High/Low/50% from previous week
- **Previous Month Triad**: High/Low/50% from previous month
- **Current Week Triad**: High/Low/50% from current week (updating)
- **Yearly Triad**: High/Low/50% from current year

#### Session Levels (Purple colored, with breach detection):
- **Asia Session High/Low**: Terminates when price breaches
- **London Session High/Low**: Terminates when price breaches

All level lines:
- Display as dotted lines for easy identification
- Standard levels extend indefinitely to the right
- Session levels terminate at breach points but labels turn gray and continue moving
- Reset daily at 6pm ET
- Each triad is toggleable as a group
- Individual components (High/Low/50%) can be toggled within each triad
- All labels show price values in format "Label (Price)"

### Fair Value Gaps (FVGs)
The indicator automatically detects and displays Fair Value Gaps from the 15-minute timeframe:

#### FVG Features:
- **15-Minute Detection**: FVGs are detected specifically on 15-minute candles regardless of current chart timeframe
- **Bullish FVGs**: Purple semi-transparent boxes (gaps between 15min candle[2] high and candle[0] low)
- **Bearish FVGs**: Pink/Fuchsia semi-transparent boxes (gaps between 15min candle[2] low and candle[0] high)
- **Midpoint Lines**: White dotted lines showing the 50% level of each gap
- **Midpoint Breach**: Boxes stop extending right when price breaches the midpoint
- **Full Mitigation**: FVGs disappear completely when price fully passes through the gap
- **Maximum Display**: Configurable limit on number of FVGs shown (default: 20)
- **Minimum Size**: Only shows FVGs above a configurable minimum size

#### FVG Behavior:
- Initially extends to the right indefinitely
- **Midpoint Breach**: When price touches the midpoint, the box stops extending but remains visible
- **Full Mitigation**: FVG is completely removed only when price fully passes through the entire gap
  - Bullish FVG: Mitigated when price trades below the bottom of the gap
  - Bearish FVG: Mitigated when price trades above the top of the gap
- All FVGs reset at 6pm ET with new trading day

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

### Level Lines
- Toggle individual level lines on/off
- Configure colors for each level type
- Show/hide level labels
- Adjust line width

## Trading Strategy

The Llama strategy uses overnight session ranges to identify key support and resistance levels for the upcoming trading day. The Fibonacci retracement levels provide potential entry and exit points based on the overnight price action between Sydney and Asia sessions.

## Notes

- All times are in Eastern Time (ET)
- Indicator resets daily at 6pm ET
- Requires intraday timeframe for proper display
- Maximum 500 drawing objects supported