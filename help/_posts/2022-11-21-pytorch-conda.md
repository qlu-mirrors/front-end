---
layout: help
category: help
mirrorid: pytorch-conda
---
## pytorch-conda 软件仓库镜像使用帮助
本仓库镜像仅支持使用 conda 安装 Pytorch

如果您需要使用 pip 安装 Pytorch 请移步至 [pytorch-pip](https://mirrors.qlu.edu.cn/pytorch-pip/) 仓库

### 临时使用
`conda install pytorch torchvision torchaudio cudatoolkit=11.0 -c https://mirrors.qlu.edu.cn/anaconda/cloud/pytorch/`

### 永久添加到 Conda Channel
`conda config --add channels https://mirrors.qlu.edu.cn/anaconda/cloud/pytorch/` 