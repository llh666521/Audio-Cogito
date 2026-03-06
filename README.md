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

| Models | Size | Sound | Music | Speech | S-M | S-S | M-S | S-M-S | Avg (%) | Rubrics (%) | CRS |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| *Random Guess* | - | 29.39 | 25.88 | 31.48 | 25.00 | 29.30 | 31.10 | 28.13 | 29.32 | - | - |
| **LALMs** | | | | | | | | | | | |
| SALMONN | 7B | 30.90 | 29.60 | 34.40 | 9.10 | 37.60 | 28.10 | 37.50 | 32.80 | - | - |
| Audio Flamingo | 2.2B | 32.70 | 21.80 | 24.80 | 18.20 | 30.30 | 24.40 | 25.00 | 26.60 | - | - |
| Audio Flamingo 2 | 3B | 24.90 | 17.50 | 20.80 | 18.20 | 26.60 | 23.20 | 8.30 | 21.90 | - | - |
| Qwen2-Audio | 8.4B | 33.90 | 23.30 | 33.00 | 9.10 | 33.00 | 26.80 | 33.30 | 30.40 | - | - |
| Qwen2-Audio-Instruct | 8.4B | 33.30 | 24.30 | 32.30 | 9.10 | 31.20 | 30.50 | 25.00 | 30.00 | - | - |
| GPT-4o mini Audio | - | 38.80 | 35.90 | 58.80 | <u>45.50</u> | 60.10 | 57.30 | 60.00 | 50.60 | - | - |
| Omni-R1 | 8.4B | **67.30** | **51.50** | <u>64.30</u> | <u>45.50</u> | <u>70.20</u> | **64.60** | <u>70.80</u> | <u>63.40</u> | - | - |
| **GPT-4o Audio** | - | <u>53.90</u> | <u>51.00</u> | **70.40** | **63.60** | **72.50** | <u>62.20</u> | **75.00** | **63.50** | - | - |
| **OLMs** | | | | | | | | | | | |
| Qwen2.5-Omni | 10.7B | 58.80 | 40.80 | 59.90 | 54.50 | 61.90 | 67.10 | 58.30 | 56.70 | - | - |
| Qwen3-Omni-Instruct | 30B | 59.39 | <u>54.37</u> | 72.45 | 63.67 | <u>77.52</u> | 65.85 | 66.67 | 66.90 | - | - |
| Gemini 2.0 Flash | - | <u>61.20</u> | 51.00 | 72.10 | <u>81.80</u> | 72.50 | 65.90 | <u>70.80</u> | 65.60 | - | - |
| Gemini 2.5 Flash | - | 60.00 | 53.40 | <u>77.20</u> | 63.60 | 76.20 | <u>69.50</u> | **75.00** | <u>68.40</u> | - | - |
| **Gemini 2.5 Pro** | - | **67.30** | **56.80** | **82.00** | **100.0** | **84.90** | **80.50** | 66.70 | **74.40** | - | - |
| **LARMs** | | | | | | | | | | | |
| Mellow | 167M | 33.30 | 26.70 | 24.80 | 18.20 | 37.20 | 32.90 | 29.20 | 30.00 | 18.50 | 0.61 |
| Audio-CoT | 8.4B | 35.80 | 25.20 | 34.00 | 9.10 | 30.70 | 30.50 | 37.50 | 31.30 | 19.85 | 0.62 |
| Audio-Reasoner | 8.4B | 42.42 | 32.52 | 42.52 | 45.13 | 48.62 | 30.49 | 29.17 | 40.50 | 28.40 | 0.68 |
| Audio Flamingo 3 | 7B | 56.97 | 45.15 | 59.52 | 45.45 | 67.89 | 59.76 | 41.67 | 57.40 | 45.20 | 0.79 |
| Step-Audio-R1 | 33B | 32.52 | 32.52 | <u>68.71</u> | 45.22 | 72.02 | 62.20 | <u>72.02</u> | 58.60 | 46.55 | 0.79 |
| Qwen3-Omni-Thinking | 30B | <u>64.24</u> | <u>50.00</u> | **79.25** | <u>54.55</u> | <u>72.48</u> | <u>69.51</u> | 70.83 | <u>68.00</u> | <u>57.97</u> | <u>0.85</u> |
| **Audio-Cogito** 🚀 | 30B | **66.67** | **53.40** | **79.25** | **90.91** | **79.90** | **76.83** | **79.17** | **71.70** | **62.22** | **0.87** |

> **Notes:** > - **S-M**: Sound-Music, **S-S**: Sound-Speech, **M-S**: Music-Sound, **S-M-S**: Sound-Music-Speech.

## Cogito-Pipe

The **Cogito-Pipe** is structured into the following four systematic stages to ensure data diversity and reasoning quality:

* **Data Collection:** Gathering data from multi-domain audio sources spanning sound, speech, and music.
* **QA Construction:** Synthesizing diverse and challenging QA pairs based on the collected audio.
* **CoT Construction:** Producing detailed step-by-step reasoning traces (Chain-of-Thought) for each task.
* **Quality Verification:** Enforcing consistency between QA pairs and CoT rationales while filtering out hallucinated or low-quality samples.

<p align="center">
  <img src="cogito_pipe.svg" width="800" alt="Cogito-Pipe">
</p>
