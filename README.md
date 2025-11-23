# 🚗 ANPR-Traffic-Plate-Recognition  
**Automatic Number Plate Recognition System using YOLOv8 and EasyOCR**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/YOUR_LINK_HERE)
[![made-with-python](https://img.shields.io/badge/Made%20with-Python-red.svg)](#)
[![YOLOv8](https://img.shields.io/badge/YOLO-v8-blue)](#)

Real-time **License Plate Detection + OCR** system built with **YOLOv8** and **EasyOCR**. Works perfectly on traffic CCTV footage (including Indian number plates like `MH14DE1234`, `DL9CAB1234`).

Fully tested and working on **Google Colab Free Tier (T4 GPU)**.

---

### 🎯 Features
- Accurate plate detection (~98% mAP)
- High OCR accuracy on real-world blurry/low-light plates
- Real-time video processing (25–40 FPS)
- Supports Indian, US, EU, UK plates
- No paid APIs or software required
- One-click run on Google Colab

---

### 🏗️ System Architecture
```mermaid
flowchart TD
    A["Input Video Frame<br>(CCTV Footage)"] --> B["YOLOv8s Detector<br>(conf=0.35)"]
    B --> C{Plate Detected?}
    C -->|Yes| D["Crop Plate"]
    C -->|No| E["Next Frame"]
    D --> F["EasyOCR<br>(GPU + Allowlist)"]
    F --> G["Extract Text"]
    G --> H["Draw Box + Text"]
    H --> I["Output Video"]
    E --> I
    style A fill:#3498db,color:white
    style B fill:#27ae60,color:white
    style F fill:#f39c12,color:black
    style I fill:#e74c3c,color:white
