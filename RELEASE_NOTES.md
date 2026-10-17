# v2.0.0 — 2026-10-17

**简体中文** · [English](#english)

---

## 简体中文

**K线手绘编辑器** —— 不用导入行情数据，在画布上亲手拖出一根根 K 线。
画完立刻看到它在 MACD、RSI、均线和多周期聚合下是什么样子，并能导出高清图片与逐根回放的动画视频。

完全离线运行，不联网、不传数据、不需要账号。

### 下载

| 文件 | 说明 |
|---|---|
| `KLinePainter-v2.0.0-win64.exe` | Windows 10/11 x64 单文件版，39.7 MiB，免安装 |

> 首次运行若被 SmartScreen 拦截：点「更多信息」→「仍要运行」。

### 这一版有什么

- **手绘手感**：空白处按住左键直接拖出一根 K 线，拖到画面边缘视野自动跟随，从 100 画到 5000 都不用手忙脚乱
- **四段精修**：`Shift` 抓端点调影线、`Ctrl` 整根平移、右键上下拖改最高最低、`Alt` 吸附最近刻度
- **日 / 周 / 月 / 年多周期**：日线是数据本体，周月年实时聚合，切过去切回来数据不丢
- **技术指标**：MACD(12,26,9)、RSI(6,12,24)、MA5/10/20、成交量与均量，全部实时重算
- **多周期分析窗**（`Ctrl+E`）：涨跌分布、收盘+均线、量能、MACD、RSI、累计涨跌六张图 + 四周期统计报告，一键复制
- **截图识图**：从行情截图或期货通截图识别 K 线导进来，`Ctrl+V` 可直接粘剪贴板
- **导出动画视频**：MP4 / GIF，可调帧率、每根帧数、清晰度，右侧标注累计涨幅
- **每根 K 线独立备注**：图上打菱形标记、数据表高亮、存进工程文件、导进 CSV
- **完整撤销栈**：识图导入、批量影线速改也是 `Ctrl+Z` 一步还原
- **深色 / 浅色双主题**：高 DPI 屏（125% / 150% / 4K）逐档适配，窗口不越界、切换不跳动

### 安装与运行

1. 下载上面的 exe
2. 放到任意目录（建议单独建个文件夹），双击运行
3. 不需要安装 Python、不需要联网

**导出的 MP4** 需要系统里有 `ffmpeg`；没有时会自动降级为 GIF，功能不受影响。

### 系统要求

- Windows 10 / 11，64 位
- 无需管理员权限
- 工程文件（`.kln`）是纯文本 JSON，可直接备份、迁移

### 已知限制

- 仅支持 Windows（用到了分层窗口与 DPI API）
- 截图识图对深色底、清晰、无遮挡的截图效果最好；读不到的成交量会填 0
- 程序内附的 AI 剧情为实验特性，需自备 GGUF 模型文件，默认不启用

---

## English

**K-Line Painter** — a hand-drawn candlestick workbench for Windows.
No market data import: drag on the canvas and draw each candle yourself, then read it through
MACD, RSI, moving averages and multi-timeframe aggregation. Export clean PNGs or a frame-by-frame
animation of the whole structure.

Runs entirely offline — no network, no telemetry, no account.

### Download

| File | |
|---|---|
| `KLinePainter-v2.0.0-win64.exe` | Windows 10/11 x64, single file, 39.7 MiB, no installer |

> If SmartScreen blocks the first launch: **More info → Run anyway**.

### What's in this release

- **Drawing that feels right** — press the left button on empty space and drag out a candle; the view follows your cursor past the edge, so any price range is reachable without fighting the canvas
- **Four-way refinement** — `Shift` grabs an endpoint to shape a wick, `Ctrl` moves the whole candle, right-drag sets high/low, `Alt` snaps to the nearest tick
- **Daily / weekly / monthly / yearly** — daily bars are the source of truth; the other timeframes are aggregated live and survive round-trips
- **Indicators** — MACD (12,26,9), RSI (6,12,24), MA5/10/20, volume with its average, all recalculated live
- **Analysis window** (`Ctrl+E`) — six charts plus a four-timeframe statistical report, copyable in one click
- **Import from screenshot** — detect candles from a chart image, or paste straight from the clipboard with `Ctrl+V`
- **Animation export** — MP4 / GIF with adjustable fps, frames per candle and resolution, cumulative return labelled
- **Per-candle notes** — marked with a diamond on the chart, highlighted in the table, saved in the project and exported to CSV
- **Full undo stack** — screenshot imports and batch wick edits are all single-step undoable
- **Dark and light themes** — HiDPI aware across 125% / 150% / 4K, no window overflow, no layout jump

### Install and run

1. Download the exe above
2. Put it in any folder and double-click — no Python, no network needed
3. Exporting MP4 additionally needs `ffmpeg` on PATH; without it the app falls back to GIF

### Requirements

- Windows 10 / 11, 64-bit, no admin rights needed
- Project files (`.kln`) are plain-text JSON — easy to back up and move

### Known limitations

- Windows only (layered windows and DPI APIs)
- Screenshot detection is most reliable on clean, dark, unobstructed charts; unreadable volume is filled with 0
- The bundled narrative engine is experimental and needs your own GGUF model file; disabled by default

---

<sub>Source, tests and documentation: [github.com/nainai520/kline-editor](https://github.com/nainai520/kline-editor)</sub>
