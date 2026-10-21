# v3.0.0 — 2026-10-21

**简体中文** · [English](#english)

---

## 简体中文

**K线手绘编辑器** —— 不用导入行情数据，在画布上亲手拖出一根根 K 线。
画完立刻看到它在 MACD、RSI、均线和多周期聚合下是什么样子，并能导出高清图片与逐根回放的动画视频。

这一版最大的变化：**它现在可以拿来练手了**。封面多了「K线练习」入口，
在编辑器里押方向、带杠杆、算真实盈亏，一局一局练盘感。

完全离线运行，不联网、不传数据、不需要账号。

### 下载

| 文件 | 说明 |
|---|---|
| `KLinePainter-v3.0.0-win64.exe` | Windows 10/11 x64 单文件版，39.8 MiB，免安装 |

> 首次运行若被 SmartScreen 拦截：点「更多信息」→「仍要运行」。

### 这一版有什么

**🎮 K 线练习（全新）**

- 封面第二个主行动进入，界面就是编辑器本身 —— 不是另做一个玩具窗口
- 开局随机生成一段走势，只露前 40 根：`空格` / `→` 揭下一根，走到底自动结算
- `↑` 做多、`↓` 做空、`Esc` 平仓；成本 = 当根收盘，浮动收益按方向 × 涨跌幅算
- **真实资金模型**：默认 10 万（可改 1000 ~ 1 亿），**杠杆 1~100×**、**仓位 5~100%**
- **爆仓判定**：浮亏吃穿保证金就强平，100 倍反向 2% 恰好亏光本金，不会穿仓变负数
- 杠杆/仓位改完要按「确定」才生效，没按还是旧值（未确定时按钮变蓝提醒）
- 一局根数 30~600 可改；**每局起点价、波动率、趋势完全随机**，不会每局一个模子
- **练习记录**：每局收益写进本机排行榜（最多 200 局），显示共 N 局 / 平均 / 最好 / 最差，红涨绿跌
- 退出练习会原样还原你原来的工程 —— 连「已修改」状态都还回去，玩一局不会弄丢你的图

**🚦 涨跌幅限制**

- 顶部「涨跌幅」键循环 **关 / 10% / 20%**（菜单「更多 → 涨跌幅限制」同样可选）
- 拖到或输入到限制价就**停住**，右下角滑入一张 Windows 通知式卡片：
  「取消涨跌幅限制」放行并补应用原始值，「保持限制」停在限制价
- 周/月/年线按 **档位 × 交易日数**（一周 5 天）折算，不是生搬日线档位
- 面板改值、表格改值、方向键微调、鼠标拖动全部硬夹；级联派生的日线同样守限制

**🔧 其它改进**

- **截图识图会读价格轴**：截图里带价格网格时自动对齐坐标，导入不再需要手对基准
- **周/月/年视图可直接清空**：不用先切回日线
- **播放时纵轴自动取景**：K 线多的时候不再被压成一条细线

**🐞 修复**

- 编辑周/月/年线后，随机生成的下级 K 线出现**大跳空与巨柱**：
  贴边分摊与随机游走都加了位移上限，改收盘会传导到下一根开盘，相邻跳空设硬上限
  （实测边界断口 7.1% → 0）

### 安装与运行

1. 下载上面的 exe
2. 放到任意目录（建议单独建个文件夹），双击运行
3. 不需要安装 Python、不需要联网

**导出的 MP4** 需要系统里有 `ffmpeg`；没有时会自动降级为 GIF，功能不受影响。

### 系统要求

- Windows 10 / 11，64 位
- 无需管理员权限
- 工程文件（`.kln`）是纯文本 JSON，可直接备份、迁移
- 练习记录存在本机 `~/.kline_practice_records.json`，不上传

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

The big addition in this version: **it doubles as a trading drill**. A second action on the cover
opens a practice mode inside the editor — call the direction, set leverage, and see real P&L
candle by candle.

Runs entirely offline — no network, no telemetry, no account.

### Download

| File | |
|---|---|
| `KLinePainter-v3.0.0-win64.exe` | Windows 10/11 x64, single file, 39.8 MiB, no installer |

> If SmartScreen blocks the first launch: **More info → Run anyway**.

### What's in this release

**🎮 Candle practice (new)**

- Entered from the second primary action on the cover — and it *is* the editor, not a toy window
- Each run generates a random series and reveals only the first 40 bars: `Space` / `→` reveals one, the run settles automatically at the end
- `↑` goes long, `↓` goes short, `Esc` closes; cost basis is the current close, floating P&L follows direction × return
- **Real money model**: ¥100k starting capital (editable, 1k–100M), **leverage 1–100×**, **position size 5–100%**
- **Liquidation**: if floating loss eats the margin you are force-closed — at 100× a 2% adverse move wipes the margin exactly, equity never goes negative
- Leverage and position size only take effect after pressing **确定** — until then the old value is used and the button turns accent-coloured
- Run length adjustable 30–600 bars; **every run randomises start price, volatility and trend**, so no two runs look alike
- **Scoreboard**: each run's P&L is stored locally (up to 200 runs) with runs / average / best / worst, red for gains and green for losses
- Leaving practice restores your previous project exactly — even its "modified" flag — so a quick session never costs you your work

**🚦 Price-move limit**

- The top-bar **涨跌幅** key cycles off / 10% / 20% (also under **More → 涨跌幅限制**)
- Dragging or typing **stops at the limit** and a Windows-style toast slides in from the bottom-right: **取消涨跌幅限制** releases the clamp and applies the value you originally wanted, **保持限制** keeps the clamped price
- Weekly/monthly/yearly candles are clamped by **level × trading days** (5 per week) instead of the raw daily level
- Panel edits, table edits, arrow-key nudges and mouse drags are all clamped, and so are the daily bars derived by cascading down

**🔧 Also improved**

- **Screenshot import reads the price axis**: when the image carries a price grid the coordinates are aligned automatically
- **Weekly / monthly / yearly charts can be cleared directly** — no need to switch back to daily first
- **The Y axis recentres while playing**, so a long series no longer collapses into a thin band

**🐞 Fixed**

- After editing weekly/monthly/yearly candles, the randomly generated child bars showed **huge gaps and oversized bodies**: displacement caps were added to edge distribution and the random walk, closing price now propagates into the next open, and adjacent gaps are hard-capped (measured boundary gap 7.1% → 0)

### Install and run

1. Download the exe above
2. Put it in any folder and double-click — no Python, no network needed
3. Exporting MP4 additionally needs `ffmpeg` on PATH; without it the app falls back to GIF

### Requirements

- Windows 10 / 11, 64-bit, no admin rights needed
- Project files (`.kln`) are plain-text JSON — easy to back up and move
- Practice records live in `~/.kline_practice_records.json` on your machine and are never uploaded

### Known limitations

- Windows only (layered windows and DPI APIs)
- Screenshot detection is most reliable on clean, dark, unobstructed charts; unreadable volume is filled with 0
- The bundled narrative engine is experimental and needs your own GGUF model file; disabled by default

---

<sub>说明与下载：[github.com/nainai520/kline-editor](https://github.com/nainai520/kline-editor)</sub>
