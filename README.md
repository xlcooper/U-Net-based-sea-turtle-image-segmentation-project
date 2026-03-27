# U-NET 海龟图像分割项目

本项目使用 U-Net 对海龟图像进行语义分割，主要流程包括数据探索、数据预处理、模型训练与结果评估。仓库当前保留的是项目的核心代码与说明文件，适合用于展示项目结构和复现实验流程。

## 目录结构

```text
U-NET/
├─ data/
│  ├─ Dataset Exploration and Masks Visualisation.ipynb
│  ├─ metadata_splits.csv
│  └─ preprocessing.ipynb
├─ src/
│  └─ unet_training_evaluation.ipynb
├─ license.txt
├─ README.md
└─ requirements.txt
```

## 文件说明

### `data/`

- `Dataset Exploration and Masks Visualisation.ipynb`
  用于查看数据集结构、类别信息，并可视化分割标注。

- `metadata_splits.csv`
  数据划分文件，记录训练集、验证集和测试集的划分信息。

- `preprocessing.ipynb`
  数据预处理 notebook，用于读取原始图像和标注信息，生成训练所需的输入数据。

### `src/`

- `unet_training_evaluation.ipynb`
  U-Net 模型训练与评估 notebook，用于加载预处理后的数据、训练模型并展示结果。

### 根目录文件

- `requirements.txt`
  项目依赖列表。

- `license.txt`
  数据或项目附带的许可说明。

- `README.md`
  项目说明文档。

## 环境安装

建议使用 Python 3.10 左右的环境。

安装依赖：

```bash
pip install -r requirements.txt
```

## 如何复现

建议按以下顺序运行：

1. 运行 `data/Dataset Exploration and Masks Visualisation.ipynb`
   先了解数据集结构、图像内容和分割标注格式。

2. 运行 `data/preprocessing.ipynb`
   根据原始图像、标注文件和 `metadata_splits.csv` 生成训练、验证、测试所需的数据。

3. 运行 `src/unet_training_evaluation.ipynb`
   加载预处理结果，构建并训练 U-Net 模型，随后进行评估。

## 关于数据文件

本仓库没有上传 `annotations.json`，因为该文件体积较大且不适合直接放入 GitHub 仓库。  
如果你希望完整复现本项目，需要额外准备：

- 原始图像数据
- `annotations.json` 标注文件

根据 SeaTurtleID2022 论文中给出的数据集入口，可以从 Kaggle 下载原始数据集：

- SeaTurtleID2022（Kaggle）  
  [https://www.kaggle.com/datasets/wildlifedatasets/seaturtleid2022](https://www.kaggle.com/datasets/wildlifedatasets/seaturtleid2022)

论文页面也明确引用了上述 Kaggle 数据集作为官方发布入口：

- SeaTurtleID2022: A long-span dataset for reliable sea turtle re-identification  
  [https://huggingface.co/papers/2311.05524](https://huggingface.co/papers/2311.05524)

下载完成后，请将原始图像和 `annotations.json` 放到 notebook 中对应的读取路径下；如果你的本地路径不同，请手动修改 notebook 里的数据路径。

## 项目说明

- 本项目的核心任务是图像分割，使用的模型是 U-Net。
- 当前仓库更适合用于展示项目主流程和代码结构；若要完整复现训练结果，仍需补充原始数据与标注文件。
