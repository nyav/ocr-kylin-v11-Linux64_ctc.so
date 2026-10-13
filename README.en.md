<div align="center">

# Kylin Advanced Server OS V11 + RTX 3060
## GPU OCR Deployed in C++ · Verified on Real Hardware

**NingYi AI — "Kylin V11 + RTX 3060 OCR" · Linux64_ctc.so**

![cover](images/cover-16x9.jpg)

[中文](README.md) · [English](README.en.md) · [English · US/EU](README.en-US.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Deutsch](README.de.md) · [العربية](README.ar.md) · [עברית](README.he.md) · [Українська](README.uk.md) · [繁體中文](README.zh-TW.md)

</div>

---

## Measured performance

| Metric | Measured |
|---|---|
| Peak throughput (single GPU, RTX 3060) | **302 images / sec** |
| Average inference latency | **3 ms / image** |
| Full-string accuracy | **99.0 %** |
| Concurrent inference threads | **14** |
| Benchmark scale | 1,400 images · **0 failures** · 463 ms wall time |
| Confidence range | 0.9489 – 0.9998 |
| First image | 277 ms (engine + VRAM warm-up); steady state 2 – 10 ms |

> Raw terminal output, unmodified:
> `==> concurrency:14 total:1400 failures:0 avg:3ms per-sec:302 total-time:463ms`
> (`==> 并发数:14 总识别:1400 失败:0 平均MS:3 每秒:302张 总耗时MS:463`)

---

## Screenshots from the live system

> Environment: Kylin Advanced Server OS V11 on x86 (Hygon), NVIDIA RTX 3060. Every frame was captured on real hardware — no mock-ups.

### 01 · Deployment environment

Captured in the Kylin V11 file manager: `run.sh` / `run_gui.sh` one-shot launchers, the `libcudart` / `libcublas` / `libnvinfer` runtimes in place, and the `livepredict_qt` binary with all of its `.so` dependencies.

![deploy](images/01-deploy.jpg)

### 02 · Startup and model loading

Double-clicking `run_gui.sh` launches the Linux Qt GUI. `Linux64_ctc.so` loads on the fly, 14 / 14 recognition threads are initialized, and the GPU (CUDA) and CPU backends are switchable.

![launch](images/02-launch.jpg)

### 03 · Concurrent C++ inference

14 threads inferring simultaneously with live progress: 463 ms total, 3 ms per image.

![concurrent](images/03-concurrent.jpg)

### 04 · Live wagon-number recognition

End-to-end C++ inference — wagon numbers and container codes read in a single pass, with instant visual verification against the source image.

![result](images/04-result.jpg)

### 05 · Metrics summary

![metrics](images/05-metrics.jpg)

---

## Use cases

`Railway marshalling yards` · `Port gates` · `Gantry cranes` · `Container yards` · `Industrial vision OCR`

- **Wagon-number recognition** — wagon IDs across C / P / N / G / B / L / K / X class rolling stock
- **Container-code capture** — automatic collection at port gates and during gantry-crane operations
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

**NingYi AI · 凝逸Ai**

</div>
