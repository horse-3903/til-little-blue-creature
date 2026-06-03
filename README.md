<div align="center">

# TIL-AI 2025 — Little Blue Creature

Competition submission for DSTA BrainHack TIL-AI 2025, tackling four AI challenges: Automatic Speech Recognition, Computer Vision, OCR, and Reinforcement Learning

[![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://docker.com)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/horse-3903/til-little-blue-creature?style=flat-square)](../../commits)

</div>

---

## Overview

This is team **Little Blue Creature**'s submission repository for [DSTA BrainHack TIL-AI 2025](https://tribegroup.notion.site/BrainHack-2025-TIL-AI-Guardian-s-Handbook-1885263ef45a80fdb547d0f22741a5ba). The competition challenges teams to build AI models across four domains — ASR, CV, OCR, and RL — each deployed as a Dockerised inference server scored on a live leaderboard.

> This repository is a fork of the official [til-ai/til-25](https://github.com/til-ai/til-25) starter template.

## Competition Challenges

| Challenge | Domain | Description |
|-----------|--------|-------------|
| `asr/` | Automatic Speech Recognition | Transcribe audio clips to text |
| `cv/` | Computer Vision | Visual perception and classification tasks |
| `ocr/` | Optical Character Recognition | Extract text from images |
| `rl/` | Reinforcement Learning | Train an agent in the TIL competition environment |

Each challenge directory contains:
- `src/` — Model manager (`*_manager.py`) and inference server (`*_server.py`)
- `Dockerfile` — Container definition for the submission image
- `requirements.txt` — Challenge-specific dependencies
- `README.md` — Input/output format specification

## Tech Stack

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://docker.com)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org)

## Getting Started

### Prerequisites

- Python 3.12+
- Docker with GPU support (`--gpus all`)
- conda (for environment management)
- Access to a Vertex AI Workbench instance (for competition infrastructure)

### Installation

```bash
git clone https://github.com/horse-3903/til-little-blue-creature.git
cd til-little-blue-creature

# Initialise submodules
git submodule update --init

# Create conda environment
conda create --name til python=3.12
conda activate til

# Install dev dependencies
pip install -r requirements-dev.txt
```

### Build, Test, and Submit

```bash
# Navigate to a challenge directory
cd asr/

# Build the Docker image
docker build -t TEAM_ID-asr:TAG .

# Test locally
docker run -p PORT --gpus all -d TEAM_ID-asr:TAG
python test/test_asr.py

# Submit for evaluation
til submit TEAM_ID-asr:TAG
```

Replace `TEAM_ID` with your assigned team ID and `TAG` with a version tag.

## Project Structure

```
.
├── asr/                   Automatic Speech Recognition challenge
├── cv/                    Computer Vision challenge
├── ocr/                   OCR challenge
├── rl/                    Reinforcement Learning challenge
├── test/                  Local testing and scoring tools
├── til-25-environment/    RL environment package (git submodule)
├── til-25-finals/         Finals code (git submodule)
└── requirements-dev.txt   Development dependencies
```

## Resources

- [Competition Wiki](https://github.com/til-ai/til-25/wiki) — Full tutorials and challenge specifications
- [Guardian's Handbook](https://tribegroup.notion.site/BrainHack-2025-TIL-AI-Guardian-s-Handbook-1885263ef45a80fdb547d0f22741a5ba) — Leaderboard and competition info
- [TIL-AI Curriculum](https://drive.google.com/drive/folders/18zP4pHt5E6YqA3usey16ETEzKNeAn5X9) — Educational materials

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.
