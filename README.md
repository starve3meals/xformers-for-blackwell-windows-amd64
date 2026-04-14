# xformers Prebuilt Wheels for Blackwell (Windows amd64)

This repository provides **prebuilt xformers wheels** specifically compiled for **NVIDIA Blackwell architecture** (SM 12.0) on Windows.

All wheels are built from source with:
- CUDA 13.0
- TORCH_CUDA_ARCH_LIST=12.0 (optimized for Blackwell / RTX 50 series)
- Windows amd64 platform

### Purpose
Since official xformers releases do not yet provide prebuilt wheels for the **PyTorch 2.11 + CUDA 13.0 + Blackwell** combination on Windows, these wheels are compiled to help users avoid the complex build process.

### Available Releases
Check the **[Releases](../../releases)** page for all available prebuilt wheels.

Current latest:
- **xformers 0.0.35** for Python 3.13 + PyTorch 2.11 + CUDA 13.0

### Installation

```bash
# 1. Install the matching PyTorch version
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu130

# 2. Install the xformers wheel
pip install xformers-0.0.35-cp313-cp313-win_amd64.whl --force-reinstall
