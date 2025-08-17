# Llama Strategy Indicator Changelog

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