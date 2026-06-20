# 🎛️ Unksyit Pro DTMF Analyzer

![Version](https://img.shields.io/badge/Version-1.0.0-blue.svg)
![Build](https://img.shields.io/badge/Build-Client--Side-success.svg)
![Tech](https://img.shields.io/badge/Tech-Vanilla_JS-f7df1e.svg)
![Privacy](https://img.shields.io/badge/Privacy-100%25_Offline-critical.svg)

A lightning-fast, purely client-side Dual-Tone Multi-Frequency (DTMF) telemetry analyzer. Built entirely with HTML, CSS, and Vanilla JavaScript, this tool extracts and decodes dial-pad tones directly from audio and video files without ever sending your data to a server.

## ✨ Core Features

| Feature | Description |
| :--- | :--- |
| 🎬 **Universal Media Support** | Upload standard audio (`.mp3`, `.wav`) or extract audio layers directly from video files (`.mp4`, `.mkv`) instantly. |
| ⚡ **Zero-Server Processing** | Everything happens in your browser. No uploads, no backend, 100% private and offline capable. |
| 🎚️ **Smart Normalization** | Automatically boosts quiet signals to ensure accurate detection even in poorly recorded media. |
| 💾 **Persistent Terminal** | An integrated analysis console that saves your session history locally until you explicitly clear it. |
| 📱 **Responsive UI** | A lightweight, "calm blue" interface perfectly scaled for small screens and low-DPI displays. |

---

## 🧠 How It Works: The Mechanisms Explained

This tool doesn't just guess; it uses deep signal processing mathematics to find hidden tones. Here is the humanistic breakdown of what happens under the hood when you upload a file.

### 1. 🌊 The Web Audio Extraction
> **The Prep-Work:** When you load a file, the browser's native `AudioContext` API intercepts the media. If it's a video, it effortlessly strips away the visual data and grabs just the raw audio waveform, decoding it into raw mathematical samples.

### 2. 🧮 The Goertzel Algorithm
> **The Heavy Lifting:** Instead of running a massive, CPU-heavy Fast Fourier Transform (FFT) to map every sound in the file, we use the **Goertzel Algorithm**. It acts like a highly tuned laser, ignoring background noise and searching *only* for the 8 specific frequencies used in DTMF telecom standards. 

### 3. 🛡️ The "Intel" Logic (Error Correction)
> **The Bouncer:** Just finding a frequency isn't enough. Human voices can sometimes mimic these tones. The analyzer applies strict **Twist Checks**—ensuring the "high" tone and "low" tone hit at the exact same time with similar energy levels. If the signal doesn't pass the threshold, it is dismissed as background noise.

---

## 📊 The DTMF Frequency Matrix

For the curious, here is the matrix our algorithm hunts for. A valid button press must contain exactly one Row frequency and one Column frequency:

| High Frequencies ➔ | `1209 Hz` | `1336 Hz` | `1477 Hz` | `1633 Hz` |
| :--- | :---: | :---: | :---: | :---: |
| **Low `697 Hz`** | **1** | **2** | **3** | **A** |
| **Low `770 Hz`** | **4** | **5** | **6** | **B** |
| **Low `852 Hz`** | **7** | **8** | **9** | **C** |
| **Low `941 Hz`** | **\*** | **0** | **#** | **D** |

---

## 🚀 Quick Start / Usage

Because this is a standalone Single-Page Application (SPA), installation is delightfully simple:

1. Clone or download this repository.
2. Open `Decoderpro.html` directly in any modern web browser (Chrome, Edge, Firefox, Safari).
3. Select your scan duration (e.g., First 30 seconds, 60 seconds, or Custom).
4. Click **Upload Media** and select your file.
5. Watch the real-time decoding in the terminal!

### Pro-Tips:
* **Custom Scan Length:** Use the "Custom" dropdown option to specify exact seconds to save memory on massive files.
* **Whole File Scan:** Use the "Whole File" option carefully on files larger than 10 minutes, as your browser will need to chew through millions of audio samples.

---

## 🛠️ Built With
* **Structure:** HTML5
* **Styling:** CSS3 (Custom Calm-Blue Theme)
* **Logic:** Vanilla JavaScript (ES6)
* **APIs:** Web Audio API, LocalStorage API

---

*Designed and engineered for ultra-responsive, secure, client-side execution.*
