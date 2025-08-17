# Max Value Gap (MVG) Indicator

A TradingView indicator for detecting and tracking price gaps in intraday trading.

## Features

- **Gap Detection**: Automatically detects gaps between consecutive bars on the same trading day
- **Visual Tracking**: 
  - Blue rectangles for active/unfilled gaps (extend to current bar)
  - Gray rectangles for filled gaps (1 bar wide at original position)
- **Gap Fill Detection**: Tracks when price trades through the gap range
- **Statistics Table**: Shows gap fill rates (total, today, same-day fills)
- **Alerts**: Configurable alerts for gap creation and gap fills

## Settings

- **Maximum Gaps to Track**: Number of gaps to keep in memory (default: 100)
- **Show Statistics Table**: Toggle statistics display
- **Alert on Gap Fill**: Enable alerts when gaps are filled (default: on)
- **Alert on Gap Creation**: Enable alerts when new gaps are detected (default: off)
- **Table Text Size**: Adjust statistics table text size
- **Gap Rectangle Color**: Customize gap visualization color

## How It Works

1. The indicator detects gaps when:
   - Gap Up: Current bar's low > Previous bar's high
   - Gap Down: Current bar's high < Previous bar's low
   - Only counts gaps on the same trading day (excludes overnight gaps)

2. Gap is considered filled when:
   - Gap Up filled: Price trades below the gap's lower boundary
   - Gap Down filled: Price trades above the gap's upper boundary

3. Visual representation:
   - Active gaps extend rightward until filled
   - Filled gaps collapse to 1-bar width at origin

## Alert Messages

- **Gap Creation**: "Gap UP/DOWN created: X.XX% | Range: XXX.XX - XXX.XX"
- **Gap Fill**: "Gap UP/DOWN FILLED | Range: XXX.XX - XXX.XX | Bars to fill: X"

## Installation

1. Copy the contents of `mvg_indicator.pine`
2. Open TradingView and create a new indicator
3. Paste the code and save
4. Add to your chart

## Notes

- Works best on intraday timeframes (1m, 5m, 15m, etc.)
- Does not track gaps between different trading days
- Requires Pine Script v6
