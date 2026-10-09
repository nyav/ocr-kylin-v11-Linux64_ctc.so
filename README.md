<div align="center">

# 银河麒麟高级服务器操作系统 V11 + RTX 3060
## C++ 部署 GPU AI 文字识别 · 车号识别实测

**凝逸Ai《银河麒麟服务器V11+RTX3060 OCR》 · Linux64_ctc.so**

![cover](images/cover-16x9.jpg)

[中文](#实测指标) · [English](#english) · [Metrics](#measured-performance)

</div>

---

## 实测指标

| 指标 | 实测值 |
|---|---|
| 单卡吞吐 | **302 张 / 秒** |
| 平均单张推理耗时 | **3 ms** |
| 整串识别准确率 | **99.0 %** |
| 并发识别线程 | **14 路** |
| 压测规模 | 1400 张 · **0 失败** · 总耗时 463 ms |
| 置信度区间 | 0.9489 ~ 0.9998 |
| 首张耗时 | 277 ms（含引擎与显存初始化），稳态 2 ~ 10 ms / 张 |

> 终端实测原始日志（原样保留）：
> `==> 并发数:14 总识别:1400 失败:0 平均MS:3 每秒:302张 总耗时MS:463`

---

## 实机运行截图

> 运行环境：银河麒麟高级服务器操作系统 V11（海光 x86 架构），RTX 3060，全部为实机录制，非效果图。

### 01 · 国产化部署环境

银河麒麟 V11 文件管理器实拍：`run.sh` / `run_gui.sh` 一键启动脚本，`libcudart` / `libcublas` / `libnvinfer` 运行时就位，`livepredict_qt` 主程序与 `.so` 依赖齐全。

![部署环境](images/01-deploy.jpg)

### 02 · 图形界面启动与模型加载

双击 `run_gui.sh` 启动 Linux Qt 图形界面，`Linux64_ctc.so` 动态库即载即用，识别线程加载 14 / 14，GPU(CUDA) 与 CPU 双后端可切换。

![启动加载](images/02-launch.jpg)

### 03 · C++ 多线程并发推理

14 路并发线程同时推理，进度实时滚动，总耗时 463 ms，平均 3 ms/张。

![并发推理](images/03-concurrent.jpg)

### 04 · 实时车号识别

端到端 C++ 推理，车号 / 集装箱箱号一次读出，图片预览即时校对。

![识别结果](images/04-result.jpg)

### 05 · 实测性能指标汇总

![性能指标](images/05-metrics.jpg)

---

## 适用场景

`铁路编组站` · `港口闸口` · `龙门吊` · `堆场管理` · `工业视觉 OCR`

- 车号识别：C / P / N / G / B / L / K / X 等车种车厢号
- 集装箱箱号采集：港口闸口、龙门吊作业自动采集
- 通用工业文字识别：铭牌、标记、编号

---

## 全栈自主可控 · 纯私有化部署

- 硬件 / 操作系统 / AI 框架全栈适配
- 兼容海光 x86 等国产 CPU 平台
- 数据不出内网，满足信创合规与数据主权要求

---

## 关于本仓库

> 本仓库**仅用于展示实测结果与运行截图**，
> **不包含任何源码、模型权重与算法库文件**。
>
> 部署包以 `.run` 离线安装包形式提供，含 `Linux64_ctc.so` 动态库与
> `run.sh` / `run_gui.sh` 启动脚本。

<div align="center">

### 竖屏版封面（视频号 / 抖音 9:16）

![竖屏封面](images/cover-9x16.jpg)

</div>

---
---

<div align="center">

<a id="english"></a>

# English

# Kylin Advanced Server OS V11 + RTX 3060
### GPU OCR in C++ · Verified on Real Hardware

**NingYi AI — "Kylin V11 + RTX 3060 OCR" · Linux64_ctc.so**

</div>

## Measured Performance

<table>
<tr><th>Metric</th><th>Measured</th></tr>
<tr><td>Peak throughput (single GPU, RTX 3060)</td><td><b>302 images / sec</b></td></tr>
<tr><td>Average inference latency</td><td><b>3 ms / image</b></td></tr>
<tr><td>Full-string accuracy</td><td><b>99.0 %</b></td></tr>
<tr><td>Concurrent inference threads</td><td><b>14</b></td></tr>
<tr><td>Benchmark scale</td><td>1,400 images · <b>0 failures</b> · 463 ms wall time</td></tr>
<tr><td>Confidence range</td><td>0.9489 – 0.9998</td></tr>
<tr><td>First image</td><td>277 ms (engine + VRAM warm-up), steady state 2 – 10 ms</td></tr>
</table>

> Raw terminal output (unmodified):
> `==> concurrency:14 total:1400 failures:0 avg:3ms per-sec:302 total-time:463ms`
> (`==> 并发数:14 总识别:1400 失败:0 平均MS:3 每秒:302张 总耗时MS:463`)

---

## What the screenshots show

> Environment: Kylin Linux Advanced Server V11 on x86 (Hygon), NVIDIA RTX 3060. All footage captured on real hardware — no mock-ups.

| # | Screen | Description |
|---|---|---|
| 01 | Deploy environment | `run.sh` / `run_gui.sh` one-shot launchers; `libcudart` / `libcublas` / `libnvinfer` runtime libraries in place; `livepredict_qt` binary with its `.so` dependencies |
| 02 | Startup & model loading | `run_gui.sh` launches the Linux Qt GUI; `Linux64_ctc.so` loads on the fly; 14 / 14 recognition threads initialized; GPU (CUDA) and CPU backends switchable |
| 03 | Concurrent inference | 14 threads running inference simultaneously, live progress, 463 ms total, 3 ms per image |
| 04 | Recognition results | End-to-end C++ inference — wagon numbers and container codes read in one pass, with instant visual verification |
| 05 | Metrics summary | The four headline numbers in one frame |

| | |
|---|---|
| ![deploy](images/01-deploy.jpg) | ![launch](images/02-launch.jpg) |
| ![concurrent](images/03-concurrent.jpg) | ![result](images/04-result.jpg) |

![metrics](images/05-metrics.jpg)

---

## Use cases

`Railway marshalling yards` · `Port gates` · `Gantry cranes` · `Container yards` · `Industrial vision OCR`

- **Wagon-number recognition** — wagon IDs for C / P / N / G / B / L / K / X class rolling stock
- **Container-code capture** — automatic collection at port gates and gantry-crane operations
- **General industrial OCR** — nameplates, markings, serial numbers

---

## Fully self-hosted · Air-gap ready

- Full-stack adaptation across hardware, operating system and AI runtime
- Compatible with domestic (Hygon and other) x86 CPU platforms
- **No data leaves your intranet** — no external API calls, no cloud dependency

---

## About this repository

> This repository is a **showcase of measured results and on-device screenshots only**.
> It contains **no source code, no model weights and no algorithm libraries**.
>
> The deployment package ships as an offline `.run` installer containing the
> `Linux64_ctc.so` library plus the `run.sh` / `run_gui.sh` launchers.

<div align="center">

### Portrait cover (9:16)

![portrait cover](images/cover-9x16.jpg)

**凝逸Ai · NingYi AI**

</div>
