<p align="center">
  <img src="https://avatars.githubusercontent.com/u/209633456?v=4" width="160" alt="RedTail Indicators Logo"/>
</p>

<h1 align="center">RedTail LVN Hunter</h1>

<p align="center">
  <b>A standalone Low Volume Node detector for NinjaTrader 8.</b><br>
  Identifies thin spots in the volume profile where price moved quickly — potential breakout zones and key support/resistance levels.
</p>

<p align="center">
  <a href="https://buymeacoffee.com/dmwyzlxstj">
    <img src="https://img.shields.io/badge/☕_Buy_Me_a_Coffee-FFDD00?style=flat-square&logo=buy-me-a-coffee&logoColor=black" alt="Buy Me a Coffee"/>
  </a>
</p>

---

## Overview

RedTail LVN Hunter builds an internal volume profile across a configurable lookback range, scans for local volume troughs, and draws shaded rectangles that extend across the full chart at each detected Low Volume Node. These are areas where traded volume is significantly lower than surrounding price levels — zones where price tends to move through quickly and that often act as magnets or inflection points on revisit.

This is a lightweight, standalone extraction of the LVN detection logic from the full [RedTail Volume Profile](https://github.com/3astbeast/RedTail-Volume-Profile) indicator. If you only need LVN zones without the full profile suite, this is the tool for you.

---

## How It Works

The indicator distributes volume across a configurable number of price rows (the profile resolution), proportionally allocating each bar's volume to the price levels it spans. It then scans for local minima — price rows where volume is lower than all neighboring rows within the detection window. Each detected trough is drawn as a filled rectangle spanning the full chart width.

---

## Lookback Modes

- **Fixed Bars** — Analyzes the most recent N bars (configurable from 50 to 5,000). The profile rolls forward as new bars print, dropping the oldest bar and adding the newest. Default: 500 bars.
- **Session** — Resets at the start of each trading session and builds the profile from the session open forward. Useful for seeing intraday LVNs develop in real time.

---

## Detection Settings

- **Profile Number of Rows** — Controls the granularity of the volume profile analysis. More rows (e.g., 200) produce finer, noisier LVN detection. Fewer rows (e.g., 50) produce broader, smoother zones. Default: 100. Range: 20–500.
- **LVN Detection %** — The percentage of rows used as the comparison window on each side of a candidate trough. Lower values are more sensitive and detect more LVNs; higher values are more selective. Range: 1–50%. Default: 5%.
- **Show Adjacent LVN Nodes** — When enabled, expands each detected LVN zone to include the rows immediately above and below the trough, creating wider zones that better represent the low-volume area. When disabled, only the exact trough row is drawn.

---

## Display

- **LVN Fill Color** — Fill color for LVN rectangles. Default: Gray.
- **LVN Fill Opacity** — 0 (transparent) to 100 (solid). Default: 40%.
- **LVN Border Color** — Border color for LVN rectangles. Default: Dark Gray.
- **LVN Border Opacity** — 0 (transparent) to 100 (solid). Default: 100%.

LVN rectangles extend from the leftmost bar on the chart to the current bar, giving a clear visual of where low-volume zones sit relative to current price action.

---

## Performance

The indicator is optimized for speed — it only calculates the volume profile and draws LVN rectangles on real-time bars and the last historical bar. This dramatically reduces load time when scrolling through history or loading large datasets.

---

## Installation

1. Download the `.cs` file from this repository
2. Open NinjaTrader 8
3. Go to **Tools → Import → NinjaScript Add-On**
4. Select the downloaded file and click **OK**
5. The indicator will appear in your **Indicators** list — add it to any chart

---

## Part of the RedTail Indicators Suite

This indicator is part of the [RedTail Indicators](https://github.com/3astbeast/RedTailIndicators) collection — free NinjaTrader 8 tools built for futures traders who demand precision.

---

<p align="center">
  <a href="https://buymeacoffee.com/dmwyzlxstj">
    <img src="https://img.shields.io/badge/☕_Buy_Me_a_Coffee-Support_My_Work-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black" alt="Buy Me a Coffee"/>
  </a>
</p>
