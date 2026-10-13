<div align="center">

# Kylin Advanced Server OS V11 + RTX 3060
## C++로 구현한 GPU AI 문자 인식 · 차량번호 인식 실측

**NingYi AI(凝逸Ai) 「Kylin V11 + RTX 3060 OCR」 · Linux64_ctc.so**

![cover](images/cover-16x9.jpg)

[中文](README.md) · [English](README.en.md) · [English · US/EU](README.en-US.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Deutsch](README.de.md) · [العربية](README.ar.md) · [עברית](README.he.md) · [Українська](README.uk.md) · [繁體中文](README.zh-TW.md)

</div>

---

## 실측 지표

| 지표 | 실측값 |
|---|---|
| 단일 GPU 처리량 | **초당 302장** |
| 평균 추론 지연 | **3 ms / 장** |
| 전체 문자열 인식 정확도 | **99.0 %** |
| 동시 추론 스레드 | **14개** |
| 부하 테스트 규모 | 1,400장 · **실패 0건** · 총 소요 463 ms |
| 신뢰도 구간 | 0.9489 ~ 0.9998 |
| 첫 장 처리 | 277 ms(엔진 및 VRAM 초기화 포함), 안정 상태 2 ~ 10 ms / 장 |

> 단말 실측 원본 로그:
> `==> 并发数:14 总识别:1400 失败:0 平均MS:3 每秒:302张 总耗时MS:463`

---

## 실기 동작 스크린샷

> 실행 환경: Kylin Advanced Server OS V11(Hygon x86 아키텍처), RTX 3060. 전부 실제 장비에서 촬영했으며 합성 이미지는 없습니다.

### 01 · 국산화 배포 환경

Kylin V11 파일 관리자 실제 화면: `run.sh` / `run_gui.sh` 원클릭 실행 스크립트, `libcudart` / `libcublas` / `libnvinfer` 런타임 배치, `livepredict_qt` 본체와 `.so` 의존성까지 모두 준비된 상태.

![배포 환경](images/01-deploy.jpg)

### 02 · GUI 실행 및 모델 로딩

`run_gui.sh`를 더블클릭하면 Linux Qt GUI가 실행되고 `Linux64_ctc.so`가 즉시 로드됩니다. 인식 스레드는 14 / 14로 초기화되며 GPU(CUDA)와 CPU 백엔드를 전환할 수 있습니다.

![실행 및 로딩](images/02-launch.jpg)

### 03 · C++ 멀티스레드 동시 추론

14개 스레드가 동시에 추론하며 진행 상황이 실시간으로 갱신됩니다. 총 소요 463 ms, 평균 3 ms/장.

![동시 추론](images/03-concurrent.jpg)

### 04 · 실시간 차량번호 인식

엔드투엔드 C++ 추론으로 차량번호와 컨테이너 번호를 한 번에 읽고, 원본 이미지와 즉시 대조할 수 있습니다.

![인식 결과](images/04-result.jpg)

### 05 · 실측 성능 지표 요약

![성능 지표](images/05-metrics.jpg)

---

## 적용 분야

`철도 조차장` · `항만 게이트` · `갠트리 크레인` · `컨테이너 야드` · `산업용 비전 OCR`

- **차량번호 인식** — C / P / N / G / B / L / K / X 등 차종의 차량 번호
- **컨테이너 번호 수집** — 항만 게이트와 갠트리 크레인 작업 시 자동 수집
- **범용 산업 OCR** — 명판, 마킹, 일련번호

---

## 풀스택 자체 제어 · 완전한 프라이빗 배포

- 하드웨어 / 운영체제 / AI 프레임워크 전 계층 적합
- Hygon 등 국산 x86 CPU 플랫폼 호환
- **데이터가 사내망을 벗어나지 않습니다** — 외부 API 호출도, 클라우드 의존도 없습니다

---

## 저장소 안내

> 본 저장소는 **실측 결과와 실기 스크린샷 공개만을 목적**으로 합니다.
> **소스 코드, 모델 가중치, 알고리즘 라이브러리는 일절 포함되지 않습니다.**
>
> 배포 패키지는 오프라인 `.run` 설치 파일 형태로 제공되며,
> `Linux64_ctc.so` 라이브러리와 `run.sh` / `run_gui.sh` 실행 스크립트를 포함합니다.

<div align="center">

### 세로형 커버(9:16)

![세로형 커버](images/cover-9x16.jpg)

**凝逸Ai · NingYi AI**

</div>
