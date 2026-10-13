<div align="center">

# GPU OCR in C++ — Verified on Real Hardware
## Kylin Advanced Server OS V11 + RTX 3060

**Industrial OCR · Line-scan image recognition · Wagon & container number reading**

![cover](images/cover-16x9.jpg)

[中文](README.md) · [English](README.en.md) · [English · US/EU](README.en-US.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Deutsch](README.de.md) · [العربية](README.ar.md) · [עברית](README.he.md) · [Українська](README.uk.md) · [繁體中文](README.zh-TW.md)

</div>

---

## Why this page exists

This repository is a **reference deployment**, not a demo. It shows one thing end to end:

> a computer-vision module running **on-premise, on a domestic Linux server OS, on a single consumer GPU**, at production throughput — with the raw terminal log to back it up.

If your team has cameras on a line and a model that will not reach production speed, this is the exact problem this work solves.

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

| # | Screen | What it shows |
|---|---|---|
| 01 | Deployment environment | `run.sh` / `run_gui.sh` one-shot launchers; `libcudart` / `libcublas` / `libnvinfer` runtimes in place; `livepredict_qt` with its `.so` dependencies |
| 02 | Startup and model loading | Qt GUI launched from `run_gui.sh`; `Linux64_ctc.so` loaded on the fly; 14 / 14 threads initialized; GPU (CUDA) and CPU backends switchable |
| 03 | Concurrent inference | 14 threads inferring simultaneously, live progress, 463 ms total, 3 ms per image |
| 04 | Recognition results | End-to-end C++ inference — wagon numbers and container codes read in one pass, with instant visual verification |
| 05 | Metrics summary | The headline numbers in one frame |

| | |
|---|---|
| ![deploy](images/01-deploy.jpg) | ![launch](images/02-launch.jpg) |
| ![concurrent](images/03-concurrent.jpg) | ![result](images/04-result.jpg) |

![metrics](images/05-metrics.jpg)

---

## Where it is used

`Railway marshalling yards` · `Port gates` · `Gantry cranes` · `Container yards` · `Industrial vision OCR`

- **Wagon-number recognition** — wagon IDs across C / P / N / G / B / L / K / X class rolling stock
- **Container-code capture** — automatic collection at port gates and during gantry-crane operations
- **General industrial OCR** — nameplates, markings, serial numbers

---

## What we deliver

Most projects fail between "the model works in a notebook" and "the model runs on the line." The deliverable here is the second half:

- **A packaged module, not a notebook** — C++ core exposing a multi-threaded DLL/SO plus a standard HTTP interface, ready to embed in an existing system
- **Cross-runtime model conversion** — PyTorch / ONNX / ncnn, with CPU–GPU heterogeneous acceleration
- **Target-specific accuracy work** — 8K line-scan images, small and dense targets, motion blur, rain, snow and backlight handling
- **Field-proven numbers** — 98.5 % recall on small surface-defect targets across three wagon faces; 97 %+ OCR accuracy under adverse conditions
- **A feasibility check first** — every engagement starts with an honest test on *your* samples, so you see the real number before you commit

---

## Engagement model

- **Independent contractor (B2B)**, remote — you define the acceptance criteria, I define the technical approach
- **No visa sponsorship required. No relocation.** Work is delivered from UTC+8 with 4–5 hours of natural overlap with European teams, and written asynchronous handover for the rest
- **Air-gap and data-sovereignty friendly** — the module runs entirely on your network; no image ever leaves your infrastructure
- **Zero employment overhead** — invoiced against defined milestones and deliverables; no payroll, benefits, equity or severance obligations on your side

Fixed-scope modules are typically delivered in **1–2 weeks**. Tightly scoped PoCs are quoted after a short call and a look at your sample images.

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
