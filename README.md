# PBL4-MedAI4Life: TransUNet for Medical Image Segmentation

## 🎯 Project Objective

This project aims to study scientific papers, learn, and research artificial intelligence methodologies applied to healthcare and medical imaging fields.

## 🧠 What is TransUNet?

TransUNet is an advanced medical image segmentation architecture that combines **CNN (Convolutional Neural Networks)**, **Transformers**, and **U-Net**. By leveraging CNN for local feature extraction and Transformers for global contextual understanding, TransUNet builds a powerful encoder-decoder framework capable of precise biomedical image segmentation.

This repository is based on the original implementation of the paper:

**TransUNet: Transformers Make Strong Encoders for Medical Image Segmentation**  
https://arxiv.org/pdf/2102.04306.pdf

---

# 📁 Repository Structure

To clearly separate the original research code from our customized implementations, this repository is organized into three main directories:

- `/TransUNet_Original`  
  Contains the original source code and materials provided by the authors.

- `/TransUNet_DatasetSynapse`  
  Contains customized code, configurations, training, and testing pipelines for the **Synapse (BTCV)** dataset.

- `/TransUNet_DatasetACDC`  
  Contains customized code, configurations, training, and testing pipelines for the **ACDC** dataset.

---

# 📰 News (From Original Authors)

### [07/26/2024] TransUNet Published in Medical Image Analysis

TransUNet, which supports both 2D and 3D data and incorporates Transformer-based encoders and decoders, has been published in the journal *Medical Image Analysis*.

Reference:

```bibtex
@article{chen2024transunet,
  title={TransUNet: Rethinking the U-Net architecture design for medical image segmentation through the lens of transformers},
  author={Chen, Jieneng and Mei, Jieru and Li, Xianhang and Lu, Yongyi and Yu, Qihang and Wei, Qingyue and Luo, Xiangde and Xie, Yutong and Adeli, Ehsan and Wang, Yan and others},
  journal={Medical Image Analysis},
  pages={103280},
  year={2024},
  publisher={Elsevier}
}
```

Paper link:
https://www.sciencedirect.com/science/article/pii/S1361841524002056

---

### [10/15/2023] 3D TransUNet Released

The 3D version of TransUNet was released. It achieves an **88.11% Dice score on the BTCV dataset**, surpasses nn-UNet, outperforms the top-1 solution in the BraTS 2021 challenge, and secures second place in the BraTS 2023 challenge.

---

# 🚀 Usage & Workflow

## 1. Environment Setup

The primary execution environment for this project is **Google Colab**.

Prepare an environment with:

- Python 3.7
- CUDA-compatible GPU
- Required Python packages

Install dependencies using:

```bash
pip install -r requirements.txt
```

---

## 2. Download Pre-trained ViT Models

Download pre-trained Vision Transformer (ViT) checkpoints such as:

- R50-ViT-B_16
- ViT-B_16
- ViT-L_16

Example command:

```bash
wget https://storage.googleapis.com/vit_models/imagenet21k/{MODEL_NAME}.npz

mkdir -p ../model/vit_checkpoint/imagenet21k

mv {MODEL_NAME}.npz \
../model/vit_checkpoint/imagenet21k/{MODEL_NAME}.npz
```

---

## 3. Dataset Preparation

All data are available so no need to send emails for data. Please use the [BTCV preprocessed data](https://drive.google.com/drive/folders/1ACJEoTp-uqfFJ73qS3eUObQh52nGuzCd?usp=sharing) and [ACDC data](https://drive.google.com/drive/folders/1KQcrci7aKsYZi1hQoZ3T3QUtcy7b--n4?usp=drive_link).


### Google Colab Workflow (Optional)

1. Download the dataset `.zip` files to your local computer.
2. Upload the `.zip` files to your personal Google Drive.
3. Mount Google Drive in Google Colab.
4. Extract the dataset files.
5. Open the code inside either:
   - `/TransUNet_DatasetSynapse`
   - `/TransUNet_DatasetACDC`
   - ...(customize)

**Important:**  
Modify all dataset paths and directory configurations inside Python scripts to match your Google Drive directory before training or testing.

---

## 4. Training and Testing

Navigate to the desired dataset directory before running commands.

### Training

The training parameters (e.g., batch size, learning rate, and number of epochs) can be adjusted according to the experiment objectives and available hardware resources.

---

### Testing

The testing script supports both 2D slices and 3D volumes.

**Note:** Change the `--dataset` argument when using the ACDC directory.

---

# 📚 References

This implementation is built upon and references the following resources:

- Google ViT
- ViT-pytorch
- segmentation_models.pytorch

---

# 📝 Citation

If you use TransUNet in your research, please cite the original paper:

```bibtex
@article{chen2021transunet,
  title={TransUNet: Transformers Make Strong Encoders for Medical Image Segmentation},
  author={Chen, Jieneng and Lu, Yongyi and Yu, Qihang and Luo, Xiangde and Adeli, Ehsan and Wang, Yan and Lu, Le and Yuille, Alan L. and Zhou, Yuyin},
  journal={arXiv preprint arXiv:2102.04306},
  year={2021}
}
```
