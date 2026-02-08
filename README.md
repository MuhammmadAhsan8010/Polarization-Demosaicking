# Polarization-Demosaicking
Polarization demosaicking using Multi-level texture aware inter-channel correlation (MLTA-ICC) method .
MLTA-ICC: DoFP Polarization Image Demosaicking

This repository contains data and related resources for the paper:

Division-of-Focal-Plane Polarization Image Demosaicking Using Multi-Level Texture-Aware Inter-Channel Correlation
Ahsan Muhammad, Xiaopin Zhong, Xiaojin Zhao, Yanyan Liang, Yuanlong Deng, Yibin Tian

📌 The repository is intended to support reproducibility, benchmarking, and further research in DoFP polarization imaging.
📖 Overview

Division-of-focal-plane (DoFP) polarization sensors enable single-shot acquisition of polarization information but require accurate demosaicking to recover full-resolution polarization channels.
This work proposes MLTA-ICC, a hybrid polarization image demosaicking framework that combines:

Inter-Channel Interpolation (ICI) guided by Stokes parameters

Multi-Level Texture-Aware Guided Filtering (TAGF)

Confidence-aware multi-scale fusion

Texture-Aware Angular Guided Filtering (TA-AGF) for AoLP

Stokes-based refinement using Adam optimization

The proposed method produces physically consistent polarization images and significantly improves RMSE and SSIM over existing methods on both real and synthetic datasets.

📂 Repository Structure
├── data/
│   ├── real_world/          # Real-world DoFP images (FLIR BFS-U3-51S5P-C)
│   ├── lapray/   # Synthesized DoFP images from Lapray dataset (NIR)
│   └── README.md           # Dataset-specific details
│
├── results/
│   ├── qualitative/        # Visual comparisons (X, S0, DoLP, AoLP)
│   └── quantitative/      # RMSE / SSIM evaluation results
│
├── docs/
│   ├── figures/            # Figures used in the paper
│   └── algorithm/          # Pseudocode and method illustrations
│
├── LICENSE
└── README.md


⚠️ Note: Code may be released separately or upon request.

📊 Datasets

Two datasets are used for evaluation:

1️⃣ Real-World DoFP Dataset

Captured using FLIR BFS-U3-51S5P-C polarization camera

Image size: 2448 × 2048 × 4

Ground truth generated via downsampling full-resolution polarization channels

Outdoor scenes with real noise characteristics

2️⃣ Lapray Polarization Dataset (Synthetic DoFP)

Original dataset captured using division-of-time method

NIR images only (monochrome polarization)

Resolution: 1024 × 768 × 4

Synthesized DoFP mosaics generated using a 2×2 polarization pattern

Both datasets enable evaluation on real sensor data and fully-known ground truth data.

📈 Evaluation Metrics

The following metrics are used for quantitative comparison:

RMSE (Root Mean Square Error)

SSIM (Structural Similarity Index)

Angular RMSE (RMSEθ) for AoLP

Angular SSIM (SSIMθ) accounting for periodicity

Metrics are reported for:

Demosaicked intensity image (X)

Stokes parameters (S0)

Degree of Linear Polarization (DoLP)

Angle of Linear Polarization (AoLP)

🧪 Compared Methods

MLTA-ICC is compared against several state-of-the-art methods, including:

Bilinear interpolation

Bicubic interpolation

Newton Polynomial (NP)

ICPC

ALGPCC

Sparse Representation (SR)

BM3D

ICC

Two variants are evaluated:

MLTA-ICC-S (fast / lightweight)

MLTA-ICC-L (full optimization with Stokes refinement)

🚀 Performance Highlights

≥ 33.02% RMSE reduction

≥ 7.85% SSIM improvement

Robust performance on textured and smooth regions

Physically consistent DoLP and AoLP reconstruction

Highly parallelizable (16× GPU speedup reported in paper)

📜 Citation

If you use this dataset or method in your research, please cite:

@article{Muhammad2024MLTAICC,
  title={Division-of-Focal-Plane Polarization Image Demosaicking Using Multi-Level Texture-Aware Inter-Channel Correlation},
  author={Muhammad, Ahsan and Zhong, Xiaopin and Zhao, Xiaojin and Liang, Yanyan and Deng, Yuanlong and Tian, Yibin},
  journal={},
  year={2024}
}

📬 Contact

For questions, data usage, or collaboration:

Ahsan Muhammad
College of Mechatronics and Control Engineering
Shenzhen University
📧 Contact via corresponding author or GitHub issues
