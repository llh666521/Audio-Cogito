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

## Cogito-Pipe

The Cogito-Pipe consists of four stages: (1) Data Collection from multi-domain audio sources spanning sound, speech, and music; (2) QA Construction to synthesize diverse and challenging QA pairs; (3) CoT Construction to produce detailed step-by-step reasoning traces; and (4) Quality Verification to enforce consistency between QA pairs and CoT rationales while filtering out hallucinated or low-quality samples.

<p align="center">
  <img src="cogito_pipe.svg" width="800" alt="Cogito-Pipe">
</p>

### Data Collection
### QA Construction
### CoT Generation
### Quality Verification
