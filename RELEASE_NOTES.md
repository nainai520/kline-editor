# v3.1.0 — 2026-10-24

**简体中文** · [English](#english)

---

## 简体中文

**K线手绘编辑器** —— 不用导入行情数据，在画布上亲手拖出一根根 K 线。
画完立刻看到它在 MACD、RSI、均线和多周期聚合下是什么样子，并能导出高清图片与逐根回放的动画视频。

这一版开始**提供正式安装包**：双击 setup 就装好，免管理员、带快捷方式、能正常卸载。

完全离线运行，不联网、不传数据、不需要账号。

### 下载

| 文件 | 说明 |
|---|---|
| `KLinePainter-v3.1.0-Setup-win64.exe` | Windows 10/11 x64 安装包，72.4 MiB |

> 首次运行若被 SmartScreen 拦截：点「更多信息」→「仍要运行」。
> 旧版本（v2.0.0 / v3.0.0）的下载已下架，请使用 v3.1.0。

### 安装

1. 双击 `KLinePainter-v3.1.0-Setup-win64.exe`
2. 默认装到 `%LOCALAPPDATA%\Programs\K线手绘编辑器` —— **不需要管理员权限**，也可以改到 D 盘等其它位置
3. 勾选桌面 / 开始菜单快捷方式（可选），完成后可直接启动
4. 想卸载：控制面板 →「程序和功能」→ 卸载，会清掉文件、快捷方式和注册项；**你的工程文件和练习记录不会被删**

### 这一版有什么

**📦 正式安装包（全新）**

- 自研安装向导，深色界面与主程序同款，带进度条和深色标题栏
- 装到用户目录免提权；安装前会预检目录可写性，装到 Program Files 会提前提示换目录，不会装一半才报错
- 采用 onedir 结构：启动不用解压、不占 `%TEMP%`、卸载能把整个目录删干净

**🎮 练习：杠杆上限 100 → 1000×**

- 1000 倍反向 0.1% 就打爆保证金，爆仓闸照旧在，权益不会变成负数

**🚦 涨跌幅限制扩到影线**

- 以前只夹收盘价，影线能随便拖出界；现在拖影线、右键改高低、面板填值、表格改 h/l、单根随机影线
  五个入口全部受限，而且不会把影线夹进实体里

**📐 区间统计**

- 「识图」旁边的按钮：点起点、点终点，直接出一份报告 —— 区间涨跌、最高最低（带日期）、振幅、
  最大回撤、阳阴平根数、最长连涨连跌、单根涨跌、平均实体与上下影、成交量合计与均值

**✂️ 一键去影线**

- 影线速改里新增第 5 个按钮：整张图的影线一次收成实体，整批只压一个撤销点

**🐞 修复**

- **随机生成的起始价不生效**：周/月/年分支忽略了起始价；对话框默认值恒为 0，会冲掉手画的首根开盘；
  而且提问顺序是「起始价 → 保留并追加？」，默认按钮是"追加"，认真填完一路回车反而落进追加分支被忽略。
  现在先问模式，只有「替换」才问起始价，填 0 表示沿用现有第一根开盘价。

### 系统要求

- Windows 10 / 11，64 位
- 无需管理员权限、无需安装 Python、无需联网
- 导出 MP4 需要系统里有 `ffmpeg`；没有时会自动降级为 GIF
- 工程文件（`.kln`）是纯文本 JSON，练习记录在 `~/.kline_practice_records.json`，都不上传

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

This version ships a **proper installer**: double-click the setup and you are done — no admin rights,
shortcuts included, uninstalls cleanly.

Runs entirely offline — no network, no telemetry, no account.

### Download

| File | |
|---|---|
| `KLinePainter-v3.1.0-Setup-win64.exe` | Windows 10/11 x64 installer, 72.4 MiB |

> If SmartScreen blocks the first launch: **More info → Run anyway**.
> Downloads for v2.0.0 / v3.0.0 have been retired — please use v3.1.0.

### Install

1. Run `KLinePainter-v3.1.0-Setup-win64.exe`
2. Defaults to `%LOCALAPPDATA%\Programs\K线手绘编辑器` — **no admin rights needed**, and you can pick another drive
3. Desktop / Start-menu shortcuts are optional; launch right after finishing
4. To remove it: Settings → Apps → uninstall. Files, shortcuts and registry entries are cleaned up;
   **your project files and practice records are kept**

### What's in this release

**📦 A real installer (new)**

- Custom dark wizard matching the app, with a progress bar and a dark title bar
- Installs into your user folder without elevation; the target directory is checked for write access first,
  so choosing Program Files warns you up front instead of failing halfway
- onedir layout: no unpacking at launch, nothing left in `%TEMP%`, and the whole folder is removed on uninstall

**🎮 Practice: leverage cap 100 → 1000×**

- At 1000× a 0.1% adverse move wipes the margin; the liquidation check stays in place so equity never goes negative

**🚦 Price-move limit now covers wicks**

- Previously only the close was clamped and wicks could be dragged past the limit. Now dragging a wick,
  right-dragging high/low, typing in the panel, editing the h/l columns and randomising a single wick are all
  clamped — without pushing the wick inside the body

**📐 Range statistics**

- The button next to **识图**: click the start candle, click the end candle, and get a report — change over
  the range, high/low with dates, amplitude, max drawdown, up/down/flat counts, longest streaks, per-candle
  moves, average body and wicks, total and average volume

**✂️ Remove all wicks**

- A fifth button in the wick panel collapses every wick into its body across the chart, as one single undo step

**🐞 Fixed**

- **Random generation ignored the starting price**: the weekly/monthly/yearly branch dropped it entirely, the
  dialog defaulted to 0 and overwrote a hand-drawn first open, and the question order was
  *starting price → keep and append?* with "append" as the default button — so filling in a price and pressing
  Enter landed in the append branch where it is ignored. The mode is now asked first, the starting price is
  only asked for "replace", and 0 means "reuse the current first open".

### Requirements

- Windows 10 / 11, 64-bit; no admin rights, no Python, no network
- Exporting MP4 needs `ffmpeg` on PATH; without it the app falls back to GIF
- Project files (`.kln`) are plain-text JSON; practice records live in `~/.kline_practice_records.json` — neither is uploaded

### Known limitations

- Windows only (layered windows and DPI APIs)
- Screenshot detection is most reliable on clean, dark, unobstructed charts; unreadable volume is filled with 0
- The bundled narrative engine is experimental and needs your own GGUF model file; disabled by default

---

<sub>说明与下载：[github.com/nainai520/kline-editor](https://github.com/nainai520/kline-editor)</sub>
