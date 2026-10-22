# MediScan AI — Next-Generation Clinical Radiology & AI Diagnostic Suite

[![Flutter CI](https://github.com/mediscan/xray_ai/actions/workflows/flutter_ci.yml/badge.svg)](https://github.com/mediscan/xray_ai/actions/workflows/flutter_ci.yml)
[![Backend Python CI](https://github.com/mediscan/xray_ai/actions/workflows/backend_ci.yml/badge.svg)](https://github.com/mediscan/xray_ai/actions/workflows/backend_ci.yml)
[![Compliance](https://img.shields.io/badge/Compliance-ACR--TID%201500%20%7C%20HIPAA-0D9488)](docs/SECURITY.md)
[![License](https://img.shields.io/badge/License-Proprietary%20Healthcare-0284C7)](LICENSE)

MediScan AI is an enterprise-grade medical imaging application and Clinical Decision Support (CDS) platform designed for thoracic radiograph analysis, DICOM-SR structured reporting, radiologist workstation workflows, telemedicine consultation, and clinical guidelines scoring.

---

## Key Features

- **Multi-Architecture Deep Learning Ensemble**: Real PyTorch DenseNet-121 (CheXNet), ResNet-50, EfficientNet-B4, and Vision Transformer (ViT-B/16) consensus engine.
- **Explainable AI (XAI)**: High-resolution Grad-CAM++ thermal heatmaps highlighting pathology activation contours.
- **Conformal Prediction & Uncertainty**: Finite-sample coverage bounds ($90\%$ confidence) and Bayesian epistemic uncertainty quantification.
- **ACR-TID 1500 Structured Reporting**: Automatic generation of DICOM Structured Reporting documents with digital cryptographic verification.
- **Clinical Guidelines Calculator Suite**:
  - Fleischner Society 2017 Pulmonary Nodule Follow-up Guidelines
  - CURB-65 Pneumonia Severity Score & Level-of-Care Triage
  - Wells' Criteria for Pulmonary Embolism (PE)
  - Cardiothoracic Ratio (CTR) Morphometry & Cardiomegaly Calipers
  - Framingham 10-Year Cardiovascular Disease (CVD) Risk Profile
- **Modern Medical Workstation**: Zero pure black clinical sapphire and slate palette (`#0F172A`), multi-touch pan, zoom, inverted contrast, and measurement calipers.
- **HIPAA-Compliant Cryptographic Audit Ledger**: Tamper-evident, Merkle-linked audit trail recording report generation, doctor reviews, and ledger verification.
- **Telemedicine Collaboration Hub**: Second-opinion exchanges, interactive tele-collaboration boards, and secure physician chat.
- **Gamified Diagnostic Training**: Daily clinical case challenges for radiology residents and fellows.

---

## Architecture & Technology Stack

- **Frontend**: Flutter 3.10+ / Dart 3.10+ with Riverpod state management, Material 3, and responsive adaptive layouts (mobile, tablet, desktop).
- **Backend**: Python 3.10+ FastAPI service running PyTorch inference engines with CPU and CUDA GPU support.
- **Persistence & Cloud**: Firebase Authentication, Cloud Firestore, Firebase Storage, with an encrypted local SQLite/in-memory fallback for offline resilience.

---

## Documentation

Comprehensive architecture, setup, security, and deployment guides are available in the `docs/` folder:

- [Project Audit & Roadmap](docs/PROJECT_AUDIT.md)
- [System Architecture Specification](docs/ARCHITECTURE.md)
- [Firebase Production Integration Guide](docs/FIREBASE_SETUP.md)
- [FastAPI Backend Setup Guide](docs/BACKEND_SETUP.md)
- [AI Model Architecture & Provenance](docs/AI_MODEL_SETUP.md)
- [Security, Privacy & HIPAA Compliance](docs/SECURITY.md)
- [Cloud Deployment (Cloud Run / Docker)](docs/DEPLOYMENT.md)

---

## Quick Start

### 1. Start the Python Backend

```bash
# 1. Create and activate virtual environment
python -m venv .venv
source .venv/bin/activate  # Or on Windows: .venv\Scripts\Activate.ps1

# 2. Install dependencies
pip install -r backend/requirements.txt

# 3. Start Uvicorn server
python -m uvicorn backend.main:app --host 0.0.0.0 --port 8000 --reload
```

For Android physical device testing via USB:
```bash
adb reverse tcp:8000 tcp:8000
```

### 2. Run the Flutter Mobile Application

```bash
# 1. Install Flutter dependencies
flutter pub get

# 2. Verify static analysis and tests
flutter analyze
flutter test

# 3. Run on connected device or emulator
flutter run
```

---

## Building the Release APK

To generate an optimized, tree-shaken Android Release APK:

```bash
flutter build apk --release
```

Output location:
`build/app/outputs/flutter-apk/app-release.apk`

To install directly to a connected Android phone via USB:
```bash
adb install -r build/app/outputs/flutter-apk/app-release.apk
```

---

## Regulatory & Clinical Disclaimer

> [!WARNING]
> MediScan AI is intended as a **Clinical Decision Support (CDS) Prototype** to assist qualified medical professionals. It is **NOT** cleared or certified as an autonomous diagnostic device. All AI-generated findings must be independently validated and digitally signed by a licensed radiologist or physician before making medical treatment decisions.
"# Mediscane_AI" 
