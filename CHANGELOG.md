# Changelog

All notable changes to Operator Stack Lab are recorded here.

## 0.8.1 — 2026-09-27

- 「白黒点 / クリップ」を「白黒点 / レベル」に変更。
- 黒点以下を 0、白点以上を 1 にし、その間を 0–1 へ線形再マップする Levels 型の動作に修正。
- 数学的な「クランプ / クリップ」は従来どおり `clip(x, lo, hi)` として分離。

## [0.8.0] - 2026-09-27

### Added

- Japanese-first interface for building an ordered image/signal operation stack
- Drag handle and highlighted insertion zones for reordering operations
- Slider controls with numeric entry for common editing parameters
- Local image preview processed entirely in the browser
- Gaussian Noise with adjustable sigma and fixed seed
- Gaussian Blur with adjustable sigma
- Pointwise transfer-curve visualization
- First- and second-derivative analysis for the pointwise portion of the stack
- Relative cost units and per-pixel operation breakdown
- Big-O notation as a secondary complexity indicator

### Notes

- When spatial or stochastic operators are present, the plotted transfer curve and derivatives describe only the pointwise portion of the stack.
- Color management is not yet implemented.
