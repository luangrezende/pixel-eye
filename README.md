# Pixel-Eye

![Status](https://img.shields.io/badge/Status-In%20Development-yellow)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-brightgreen)
![License](https://img.shields.io/badge/License-MIT-green)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-lightgrey)

A **real-time computer vision system for game interface analysis**, designed to extract structured information from on-screen elements and react to visual events with deterministic, configurable logic.

Pixel-Eye focuses on **perception, signal extraction, and event-driven responses**, treating the game as a black box and relying exclusively on visual input.

---

## Overview

Pixel-Eye monitors game windows in real time and processes HUD elements such as health, resources, alerts, and contextual signals.

Core goals:
- Real-time visual perception using screen capture
- Deterministic detection of HUD states and events
- Configurable alerting and response mechanisms
- Clear separation between capture, processing, and reaction layers

The project prioritizes **engineering discipline and system clarity** over automation gimmicks.

---

## Capabilities

### Implemented
- Screen capture and region-of-interest management
- OpenCV-based image preprocessing
- Deterministic pixel and pattern analysis
- Configurable thresholds and detection rules
- Event-driven alert pipeline (visual/audio hooks)

### In Progress
- OCR-based text extraction for dynamic HUD elements
- Overlay rendering for diagnostics and feedback
- Data recording for post-match analysis
- ML-based detectors for complex visual patterns

---

## Architecture

```
pixel-eye/
├── core/               # Capture and processing primitives
│   ├── capture.py
│   ├── processor.py
│   └── detector.py
│
├── modules/            # Domain-specific logic
│   ├── hud_reader.py
│   ├── alerts.py
│   └── analytics.py
│
├── utils/              # Configuration and helpers
│   ├── config.py
│   └── helpers.py
│
├── tests/              # Validation and diagnostics
└── main.py             # Application entry point
```

The architecture enforces **strict separation of concerns**, allowing individual modules to evolve independently.

---

## Technology Stack

- **Python 3.8+**
- **OpenCV** — real-time image processing
- **NumPy** — pixel-level analysis
- **Pillow** — image manipulation
- **PyAutoGUI** — window detection and capture
- **Tesseract OCR** — text extraction (optional)
- **PyTorch** — ML-based detectors (optional)
- **pygame** — debug rendering and overlays

---

## Installation

```bash
git clone https://github.com/your-username/pixel-eye.git
cd pixel-eye

python -m venv venv
source venv/bin/activate    # Linux / macOS
venv\Scripts\activate     # Windows

pip install -r requirements.txt
```

Optional OCR dependency:
- Windows: https://github.com/UB-Mannheim/tesseract/wiki
- Linux: `sudo apt install tesseract-ocr`

---

## Usage Example

```python
from pixel_eye import PixelEye

eye = PixelEye(game_window="Game Name")

eye.set_roi(x=100, y=50, width=800, height=600)

eye.start(
    detect_health=True,
    health_threshold=30,
    enable_overlay=True
)
```

All thresholds, regions, and behaviors are configurable.

---

## Use Cases

- Assistive systems for accessibility
- Automated detection of game states (e.g. end-of-match)
- Competitive analysis and performance feedback
- Vision-based environments for AI research

---

## Scope and Intent

This project is not intended as:
- A cheat engine
- An input automation framework
- A plug-and-play competitive advantage tool

It is intended as:
- A real-time perception layer for interactive systems
- A reference architecture for vision-driven agents
- A foundation for experimentation in applied computer vision

---

## Roadmap

- ROI auto-calibration
- Robust OCR pipelines
- Overlay customization
- ML-assisted pattern detection
- Cross-game configuration profiles
- External event integration (API/hooks)

---

## Disclaimer

This software is provided for **educational, research, and accessibility purposes**.  
Usage must comply with the terms of service of any third-party software it interacts with.

---

## License

MIT License.
