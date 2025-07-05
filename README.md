# 🖼️ Image Synthesis using SRGAN

This project implements **Single Image Super-Resolution (SISR)** using the **SRGAN (Super-Resolution Generative Adversarial Network)** architecture. SRGAN enhances the resolution of low-quality images, producing high-resolution (HR), photo-realistic outputs that preserve fine textures and details.

## 📌 Objective

Given a low-resolution image, the goal is to generate a high-resolution version that is perceptually close to real HR images. Unlike traditional models that optimize for pixel-wise similarity (MSE), SRGAN focuses on **visual quality** using a **perceptual loss**.

---

## 🚀 Key Features

- Deep **ResNet-based Generator** with residual blocks
- GAN architecture for photorealistic synthesis
- Perceptual loss using **VGG feature maps** and **adversarial loss**
- Trained and tested on standard datasets (Set5, Set14, BSD100)
- MOS (Mean Opinion Score) evaluation for perceptual quality

---

## 🏗️ Architecture Overview

### Generator (G)
- Based on deep **ResNet**
- Contains residual blocks with BatchNorm and PReLU
- Uses **sub-pixel convolution layers** for upsampling

### Discriminator (D)
- Inspired by DCGAN architecture
- Uses **LeakyReLU**, no max-pooling
- Classifies real vs. fake HR images

### Loss Function
- **Content Loss**: Perceptual loss using VGG19 feature maps
- **Adversarial Loss**: Encourages outputs that fool the discriminator
- **Total Loss**\[
  \ell_{SR} = \ell_{content} + 10^{-3} \cdot \ell_{adversarial}
  \]

---
