---
layout: help
category: help
mirrorid: pytorch-pip
---
## pytorch-pip 软件仓库镜像使用帮助
本仓库镜像仅支持使用 pip 安装 Pytorch

如果您需要使用 conda 安装 Pytorch 请移步至 [pytorch-conda](https://mirrors.qlu.edu.cn/pytorch-conda/) 仓库

### 使用镜像安装Pytorch

#### Linux

- ##### CUDA 11.6

​		`pip3 install torch torchvision torchaudio --extra-index-url https://mirrors.qlu.edu/pytorch-pip/cu116`

- ##### ROCm 5.1.1

​		`pip3 install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/rocm5.1.1`

- ##### CPU

​		`pip3 install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cpu`

#### Windows

- ##### CUDA 11.6

​		`pip3 install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu116`

- ##### CPU

  `pip3 install torch torchvision torchaudio`
