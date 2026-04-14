# xformers Prebuilt Wheel for Python 3.13 + PyTorch 2.11 + CUDA 13.0 (Blackwell)

这是一个专为 **Windows x64** 预编译的 xformers wheel，专为以下环境优化构建：

- **Python**: 3.13 (cp313)
- **PyTorch**: 2.11 + cu130
- **CUDA Toolkit**: 13.0
- **GPU 架构**: Blackwell (SM 12.0)
- **操作系统**: Windows 10 / Windows 11

由于官方目前没有提供这个组合的预编译包，我从源码编译并分享给大家，省去 Windows 下编译 xformers 的繁琐过程。

### 下载

请在 [Releases](../../releases) 页面下载wheel 文件。

### 安装步骤

```bash
# 1. 安装匹配的 PyTorch（必须严格对应）
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu130
```

```bash
# 2. 卸载旧版xformers（如果有的话）
pip uninstall xformers
```

```bash
# 2. 安装 xformers wheel（推荐使用 --force-reinstall）
pip install xformers-0.0.35-cp313-cp313-win_amd64.whl --force-reinstall
```

### 验证安装

```python
import torch
import xformers
import xformers.ops as xops

print(f"PyTorch version : {torch.__version__}")
print(f"CUDA available  : {torch.cuda.is_available()}")
print(f"CUDA version    : {torch.version.cuda}")
print(f"xformers version: {xformers.__version__}")

# 测试 xformers.ops 是否可用
print("xformers.ops 导入成功！")
print(f"Memory Efficient Attention 支持: {xops.memory_efficient_attention is not None}")
```
