# Change Log History of ConfluenceEA

Here is the complete **Change Log** history of the **ConfluenceEA**, tracking its evolution from a simple signal bot to the advanced structural strategy it is today.

## Phase 1: Foundation & Filters (v1.0 - v1.9)

  * **v1.0: Initial Release.** Combined **Trend A**, **SuperTrend**, **QQE MOD**, and **Order Block 3.0**. Logic was a simple "All indicators match = Trade."
  * **v1.1 - v1.2:** Added the **Dashboard** and Background Panel for visual clarity.
  * **v1.3:** Added **Push Notifications** (Mobile Alerts).
  * **v1.4:** Added **HTF SuperTrend**. The trade is only taken if the H4 trend matches the current chart trend.
  * **v1.5:** Added `ShowIndicators` input to keep charts clean.
  * **v1.6:** Switched from OrderBlock3.0 (old) to the optimized **OrderBlock** indicator (new).
  * **v1.7:** Separated visibility settings for Main Chart vs. Subwindow (QQE).
  * **v1.8:** Dashboard **Background Color** changes (Green/Red) when a trade is active.
  * **v1.9:** Fixed `PositionsTotal` logic to ensure the EA only manages trades for the **current symbol and Magic Number**.

## Phase 2: Trade Management & Safety (v2.0 - v2.9)

  * **v2.0: Major Update.** Added:
      * **Money Management:** Auto-calculation of lots based on Risk %.
      * **Trailing Stop:** Dynamic SL trailing.
      * **Break-Even:** Moves SL to entry after profit.
      * **Close on Reversal:** Exits trade if SuperTrend flips color.
  * **v2.1:** Changed default HTF SuperTrend to **H1** for faster reaction.
  * **v2.2:** Added **AvoidObstacles**. Prevents buying if price is hitting a Resistance Order Block (and vice versa).
  * **v2.3:** Added **TradeOnPullback**. EA waits for price to return to the Order Block before entering.
  * **v2.4:** Added **Dynamic Stop Loss Modes**:
      * `SL_ATR` (Volatility)
      * `SL_ORDERBLOCK` (Structure)
      * `SL_SUPERTREND` (Trend Line)
  * **v2.5:** Added `SL_TREND_A` (Ribbon) as a Stop Loss option.
  * **v2.6:** Added **Auto-Volatility Detection**. Automatically sets ATR Multiplier to 2.5 for GBP/JPY pairs and 2.0 for others.
  * **v2.7 - v2.9:** Added **CSV Journaling**. Logs entries, exits, and pullback distances to a file for analysis.

## Phase 3: Precision & Visualization (v3.0 - v4.0)

  * **v3.0:** Added **Visual Pullback Line**. A dotted line appears on the chart showing the maximum allowed entry distance.
  * **v3.1:** Enhanced Journaling to log specific **Exit Reasons** (Hard SL vs Trailing SL vs Signal Exit).
  * **v3.2:** Added **Version Number** display to the Dashboard title.
  * **v4.0:** Added **Dynamic Pullback Distance**. Instead of a fixed 300 points, the "Allowed Entry Zone" expands/contracts based on ATR volatility.

## Phase 4: Advanced Logic & Refinement (v5.0 - v5.30)

  * **v5.0:** Consolidated Pullback logic. Dashboard now shows specific states: **WAIT** (Too Far) vs **READY** (In Zone).
  * **v5.10:** Fixed compilation error regarding version definition.
  * **v5.20:** Added **Multimodal Pullback (InpPullbackMode)**:
      * Allows waiting for pullback to **Order Block** OR **Trend A Ribbon**.
  * **v5.30:** **Smart Obstacle Avoidance.** Instead of blocking *all* trades below resistance, it only blocks trades if the wall is **within ObstacleDistance** (e.g., 200 points).

## Phase 5: Market Filters (v6.0 - v7.0)

  * **v6.0:** Added **Volatility Filter**. Blocks trades if the market is "dead" (ATR below a minimum threshold).
  * **v7.0 (Current):** Added **ZigZag Breakout Filter**.
      * Requires price to **Break Structure** (break the last ZigZag High/Low) to confirm the trend before entering.

## Alternative Branch

  * **ConfluenceEA Lite v1.0:** A stripped-down version containing only the "Core 3" rules (Trend + Momentum + Safety) for faster execution without complex waiting logic.
