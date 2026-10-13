<div align="center">

# Kylin Advanced Server OS V11 + RTX 3060
## GPU-OCR in C++ implementiert · Am realen System verifiziert

**NingYi AI — „Kylin V11 + RTX 3060 OCR" · Linux64_ctc.so**

![cover](images/cover-16x9.jpg)

[中文](README.md) · [English](README.en.md) · [English · US/EU](README.en-US.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Deutsch](README.de.md) · [العربية](README.ar.md) · [עברית](README.he.md) · [Українська](README.uk.md) · [繁體中文](README.zh-TW.md)

</div>

---

## Gemessene Leistung

| Kennzahl | Messwert |
|---|---|
| Durchsatz (einzelne GPU, RTX 3060) | **302 Bilder / Sek.** |
| Mittlere Inferenzlatenz | **3 ms / Bild** |
| Genauigkeit (vollständige Zeichenkette) | **99,0 %** |
| Parallele Inferenz-Threads | **14** |
| Benchmark-Umfang | 1.400 Bilder · **0 Fehler** · 463 ms Gesamtzeit |
| Konfidenzbereich | 0,9489 – 0,9998 |
| Erstes Bild | 277 ms (inkl. Initialisierung von Engine und VRAM); im Dauerbetrieb 2 – 10 ms |

> Rohes Terminal-Log (unverändert):
> `==> 并发数:14 总识别:1400 失败:0 平均MS:3 每秒:302张 总耗时MS:463`

---

## Screenshots vom laufenden System

> Umgebung: Kylin Advanced Server OS V11 auf x86 (Hygon), NVIDIA RTX 3060. Alle Aufnahmen stammen von realer Hardware — keine Rendering-Bilder.

### 01 · Bereitstellungsumgebung

Aufgenommen im Kylin-V11-Dateimanager: die Startskripte `run.sh` / `run_gui.sh`, die bereitgestellten Laufzeitbibliotheken `libcudart` / `libcublas` / `libnvinfer` sowie das Programm `livepredict_qt` mit allen `.so`-Abhängigkeiten.

![Bereitstellung](images/01-deploy.jpg)

### 02 · Start der GUI und Laden des Modells

Ein Doppelklick auf `run_gui.sh` startet die Linux-Qt-Oberfläche. `Linux64_ctc.so` wird direkt geladen, 14 / 14 Erkennungs-Threads werden initialisiert, und zwischen GPU- (CUDA) und CPU-Backend lässt sich umschalten.

![Start und Laden](images/02-launch.jpg)

### 03 · Parallele C++-Inferenz mit mehreren Threads

14 Threads rechnen gleichzeitig, der Fortschritt läuft live mit: 463 ms Gesamtzeit, 3 ms pro Bild.

![Parallele Inferenz](images/03-concurrent.jpg)

### 04 · Wagennummernerkennung in Echtzeit

End-to-End-Inferenz in C++ — Wagennummern und Containernummern werden in einem Durchlauf gelesen und sofort gegen das Quellbild geprüft.

![Erkennungsergebnis](images/04-result.jpg)

### 05 · Zusammenfassung der Messwerte

![Kennzahlen](images/05-metrics.jpg)

---

## Einsatzbereiche

`Rangierbahnhöfe` · `Hafentore` · `Portalkrane` · `Container-Terminals` · `OCR in der industriellen Bildverarbeitung`

- **Wagennummernerkennung** — Wagennummern der Baureihen C / P / N / G / B / L / K / X
- **Erfassung von Containernummern** — automatisch an Hafentoren und im Portalkranbetrieb
- **Allgemeine industrielle OCR** — Typenschilder, Markierungen, Seriennummern

---

## Vollständig selbst gehostet · bereit für Air-Gap

- Ganzheitliche Anpassung an Hardware, Betriebssystem und KI-Laufzeit
- Kompatibel mit inländischen x86-CPU-Plattformen (Hygon u. a.)
- **Keine Daten verlassen das Intranet** — keine externen API-Aufrufe, keine Cloud-Abhängigkeit

---

## Über dieses Repository

> Dieses Repository **dient ausschließlich der Präsentation der Messergebnisse und Screenshots**.
> Es enthält **keinen Quellcode, keine Modellgewichte und keine Algorithmusbibliotheken**.
>
> Das Deployment-Paket wird als Offline-`.run`-Installer geliefert und enthält die
> `Linux64_ctc.so`-Bibliothek sowie die Startskripte `run.sh` / `run_gui.sh`.

<div align="center">

### Hochformat-Cover (9:16)

![Hochformat-Cover](images/cover-9x16.jpg)

**凝逸Ai · NingYi AI**

</div>
