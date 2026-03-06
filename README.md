# Audio-Cogito: Towards Deep Audio Reasoning in Large Audio Language Models

This is the official repository 👑 for **Audio-Cogito**, a fully open-source solution that elicits deep audio reasoning capabilities in LALMs without reliance on proprietary APIs.

---

## Features
- We propose Audio-Cogito, built on Qwen3-Omni-Thinking, which utilizes self-distillation to substantially enhance the deep reasoning capabilities of LALMs.
- We introduce Cogito-Pipe, a fully open-source four-stage pipeline for constructing high-quality and diverse audio reasoning data.
- We release a large-scale audio reasoning dataset with 545k high-quality samples spanning multiple audio domains.
- Audio-Cogito achieves top-tier performance in the Interspeech 2026 Audio Reasoning Challenge and sets new SOTA results among open-source models on the MMAR benchmark, even surpassing several proprietary systems.

## Dataset

### Dataset Download

**To comply with the double-blind review policy, the complete dataset and download links are currently withheld to maintain anonymity.**

All data will be fully open-sourced upon the completion of the review process.

### Statistics of Dataset

| Domain | Dataset Source | Main Skills Learning | Quantity | Ratio (%) |
| --- | --- | --- | --- | --- |
| 🔊 **Sound** | AudioSet | General Audio Event | 179k | 32.53 |
|  | Clotho | Audio Captioning | 6k | 1.14 |
|  | AudioCaps | Audio Captioning | 40k | 7.20 |
|  | ComplexAudio | Complex Audio | 37k | 6.66 |
| 🗣️ **Speech** | MELD | Speech Emotion | 24k | 4.50 |
|  | CoVoST2 | Speech Translation | 56k | 10.10 |
|  | DailyTalk | Spoken Dialogue | 9k | 1.64 |
| 🎵 **Music** | MusicBench | General Music | 88k | 16.04 |
|  | FMA | Music Genre | 76k | 13.81 |
|  | Medley-solos-DB | Instrument Analysis | 35k | 6.38 |

## Main Results

# MMAR Benchmark Results

| Models | Size | Sound | Music | Speech | S-M | S-S | M-S | S-M-S | Avg (%) | Rubrics | CRS |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **LALMs** | | | | | | | | | | | |
| SALMONN | 7B | 30.90 | 29.60 | 34.40 | 9.10 | 37.60 | 28.10 | 37.50 | 32.80 | - | - |
| Audio Flamingo | 2.2B | 32.70 | 21.80 | 24.80 | 18.20 | 30.30 | 24.40 | 25.00 | 26.60 | - | - |
| Qwen2-Audio-Instruct | 8.4B | 33.30 | 24.30 | 32.30 | 9.10 | 31.20 | 30.50 | 25.00 | 30.00 | - | - |
| GPT-4o mini Audio | - | 38.80 | 35.90 | 58.80 | 45.50 | 60.10 | 57.30 | 60.00 | 50.60 | - | - |
| **GPT-4o Audio** | - | 53.90 | 51.00 | **70.40** | 63.60 | **72.50** | 62.20 | **75.00** | **63.50** | - | - |
| **OLMs** | | | | | | | | | | | |
| Qwen2.5-Omni | 10.7B | 58.80 | 40.80 | 59.90 | 54.50 | 61.90 | 67.10 | 58.30 | 56.70 | - | - |
| Gemini 2.5 Flash | - | 60.00 | 53.40 | 77.20 | 63.60 | 76.20 | 69.50 | 75.00 | 68.40 | - | - |
| **Gemini 2.5 Pro** | - | **67.30** | **56.80** | **82.00** | **100.0** | **84.90** | **80.50** | 66.70 | **74.40** | - | - |
| **LARMs** | | | | | | | | | | | |
| Step-Audio-R1 | 33B | 32.52 | 32.52 | 68.71 | 45.22 | 72.02 | 62.20 | 72.02 | 58.60 | 46.55 | 0.79 |
| Qwen3-Omni-Thinking | 30B | 64.24 | 50.00 | 79.25 | 54.55 | 72.48 | 69.51 | 70.83 | 68.00 | 57.97 | 0.85 |
| **Audio-Cogito** 🟢 | 30B | **66.67** | **53.40** | **79.25** | **90.91** | **79.90** | **76.83** | **79.17** | **71.70** | **62.22** | **0.87** |

## Cogito-Pipe

The Cogito-Pipe consists of four stages: (1) Data Collection from multi-domain audio sources spanning sound, speech, and music; (2) QA Construction to synthesize diverse and challenging QA pairs; (3) CoT Construction to produce detailed step-by-step reasoning traces; and (4) Quality Verification to enforce consistency between QA pairs and CoT rationales while filtering out hallucinated or low-quality samples.

<p align="center">
  <img src="cogito_pipe.svg" width="800" alt="Cogito-Pipe">
</p>
