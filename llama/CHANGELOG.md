# Llama Strategy Indicator Changelog

## [1.4.0] - 2025-01-17

### Added
- **Fair Value Gaps (FVGs)**: Automatic detection and display of FVGs from 15-minute timeframe
  - FVGs detected on 15-minute candles regardless of current chart timeframe
  - Bullish FVGs shown in purple semi-transparent boxes
  - Bearish FVGs shown in pink/fuchsia semi-transparent boxes
  - Midpoint lines in white dotted style
  - Configurable maximum display count and minimum size
- **FVG Mitigation**: FVGs disappear when price fully passes through the gap
- **FVG Midpoint Breach**: Boxes stop extending right when midpoint is breached

### Changed
- **Label Format**: Price values now show in decimal format (e.g., "1.23456") instead of formatted price

## [1.3.0] - 2025-01-17

### Added
- **Price Values in Labels**: All level labels now display the actual price value in format "Label (Price)"
- **Configurable Label Distance**: User can adjust how far labels appear from current bar (default: 50)
- **Gray Breach Labels**: Breached session lines now show gray labels that continue moving with other labels

### Changed
- **Full Label Names**: Changed from abbreviations to full descriptive names for better readability
- **Label Management**: Breached lines keep their labels but turn gray instead of disappearing
- **Line Origins**: All lines now properly extend from their actual origin points in the chart

### Fixed
- **Bar Index Limitations**: Fixed "too far from current bar" errors by limiting lookback to 500 bars
- **Label Consistency**: All labels now behave consistently whether breached or active

## [1.2.0] - 2025-01-17

### Added
- **50% Midpoint Lines**: Added midpoint levels for all high/low pairs
- **Previous Month Levels**: New triad for previous month High/Low/50%
- **London Session Levels**: High/Low with breach detection
- **Toggleable Triads**: Each set of levels (High/Low/50%) can be toggled as a group
- **Unified Color Scheme**: Teal for standard levels, Purple for session levels

### Changed
- **Breach Detection**: Now only applies to Asia and London session levels
- **Color Standardization**: All non-session levels now use teal color
- **Session Lines**: Asia and London levels now use purple color
- **Improved Organization**: Level lines grouped into triads with parent toggles

## [1.1.0] - 2025-01-17

### Added
- **Level Lines**: 12 different horizontal support/resistance levels
  - Current Day Open (6pm ET)
  - True Day Open (12am ET)
  - Previous Day High/Low
  - Previous Week High/Low
  - Current Week High/Low
  - Yearly High/Low
  - Asia Session High/Low
- **Breach Detection**: Lines automatically terminate when price crosses them
- **Dotted Line Style**: All level lines use dotted style for clear identification
- **Configurable Display**: Individual toggles and colors for each level type

## [1.0.0] - 2025-01-17

### Initial Release

#### Features
- **Session Tracking**: Tracks Sydney (6pm-3am ET), Asia (8pm-5am ET), and London (3am-12pm ET) sessions
- **Session Boxes**: Visual boxes showing high/low ranges for each session
- **Fibonacci Retracement**: Automatic Fibonacci levels drawn after Asia session ends
  - Uptrend: Draws from Sydney low to Asia high
  - Downtrend: Draws from Sydney high to Asia low
  - Levels: 0.236, 0.786, -0.236, -0.786
- **Auto-cleanup**: All session boxes and Fibonacci lines reset at 6pm ET (new forex day)
- **Customizable Display**: Toggle individual sessions, labels, and Fibonacci levels
- **Floating Labels**: Fibonacci level text floats at the right edge of the chart

#### Technical Details
- Pine Script v6 compatible
- Max 500 boxes for proper rendering
- Eastern Time (ET) timezone for all calculations
- Sydney session hidden by default per trading strategy requirements
- Gold-colored Fibonacci lines with customizable width
- Alert conditions for session starts and new day