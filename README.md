# 🕵️ Audio Deepfake Detection: Spectral Forensics

> A Convolutional Neural Network (CNN) designed to detect AI-synthesized speech by analyzing high-frequency spectral artifacts.

[![Python](https://img.shields.io/badge/Python-3.10-blue)](https://python.org)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0-red)](https://pytorch.org)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

## 🔍 The Problem
Modern TTS models (like ElevenLabs, Vall-E) generate hyper-realistic audio, but they often leave behind mathematical "scars" (artifacts) in the frequency domain that are invisible to the human ear but visible in **Mel-Spectrograms**.

## 🛠️ Solution Architecture
* **Input:** Raw Audio (.flac/.wav)
* **Preprocessing:** Conversion to Mel-Spectrograms (128x64) using `librosa`.
* **Model:** Custom 3-Layer CNN (`ArtifactHunter`) optimized for texture detection.
* **Dataset:** ASVspoof 2019 (Logical Access Subset).

## 📊 Results
* **Accuracy:** 95% on unseen test set (subset).
* **Key Insight:** Synthetic audio exhibits distinct "checkerboard" patterns above 4kHz due to vocoder upsampling.

## 🚀 How to Run
1. Install dependencies:
   ```bash
   pip install -r requirements.txt
