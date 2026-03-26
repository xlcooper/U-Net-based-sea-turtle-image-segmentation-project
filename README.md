# 海龟图像分割项目

本项目使用 U-Net 对海龟图像进行语义分割，目标是根据数据集提供的 COCO 格式标注，识别图像中的海龟及其相关区域。仓库中保留了数据探索、数据预处理、模型训练与评估所需的核心文件，适合用于理解项目流程和复现实验。

## 项目文件

- `annotations.json`
  数据集的 COCO 格式标注文件，包含图像信息、类别信息和分割标注。
- `Dataset Exploration and Masks Visualisation.ipynb`
  用于查看数据集结构、浏览样例图像，并可视化标注 mask。
- `metadata_splits.csv`
  数据划分文件，记录训练集、验证集和测试集的划分信息。
- `preprocessing.ipynb`
  数据预处理 notebook，用于读取原始图像和标注，生成训练所需的预处理数据。
- `unet_training_evaluation.ipynb`
  U-Net 模型训练与评估 notebook，用于加载预处理后的数据、训练模型并查看结果。
- `requirements.txt`
  项目依赖列表，用于安装运行 notebook 所需的 Python 库。
- `license.txt`
  数据或项目附带的许可说明。

## 环境安装

建议使用 Python 3.10 左右的环境。

安装依赖：

```bash
pip install -r requirements.txt
```

## 复现流程

建议按下面的顺序运行项目：

1. 打开 `Dataset Exploration and Masks Visualisation.ipynb`
   用于了解数据集结构、类别信息以及分割标注的可视化效果。
2. 打开 `preprocessing.ipynb`
   读取 `annotations.json` 和原始图像，根据 `metadata_splits.csv` 的划分生成训练、验证和测试数据。
3. 打开 `unet_training_evaluation.ipynb`
   加载预处理后的数据，构建并训练 U-Net 模型，然后进行评估与结果展示。

## 数据说明

本仓库中的 `annotations.json` 和 `metadata_splits.csv` 只负责描述数据和划分信息。实际复现时，还需要原始图像文件与标注文件位于 notebook 中指定的目录下；如果路径不同，请先修改 notebook 中的数据路径配置。

## 模型说明

本项目的核心模型为 U-Net。整体流程是：

- 先根据 COCO 标注生成对应的分割 mask
- 再将图像与 mask 预处理成统一尺寸的数据
- 最后使用 U-Net 完成训练与评估

## 说明

- 本项目主线是图像分割。
- 如果你在本地运行时遇到路径错误，通常只需要修改 notebook 中的数据目录即可。
- 若要进一步整理仓库，建议后续补充模型结果截图或训练说明。
