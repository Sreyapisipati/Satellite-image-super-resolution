# Satellite Image Super-Resolution Using Deep Learning

## Project Overview

An end-to-end deep learning project that enhances the spatial resolution of Sentinel-2 multispectral satellite imagery using a Residual Convolutional Neural Network (CNN).

The system processes multispectral satellite data and reconstructs higher-resolution imagery while preserving spectral information. It also provides geospatial visualizations and evaluation metrics through an interactive Streamlit application.

## Problem Statement

Satellite imagery is widely used in environmental monitoring, land-use analysis, and remote sensing. However, limited spatial resolution can restrict the identification of finer geographical details.

This project explores deep learning-based super-resolution to enhance satellite imagery while maintaining spectral consistency across multiple bands.

## Technologies Used

- Python
- PyTorch
- Residual Convolutional Neural Network (CNN)
- Residual Learning
- PixelShuffle Upsampling
- Copernicus Sentinel-2 L2A
- Rasterio
- Streamlit
- MAE, RMSE, PSNR, SSIM
- NDVI

## Dataset

- **Source:** Copernicus Data Space Ecosystem
- **Satellite Product:** Sentinel-2 Level-2A (L2A)
- **Spectral Bands:** B02 (Blue), B03 (Green), B04 (Red), B08 (Near-Infrared).

### Preprocessing
- Reflectance normalization
- Band alignment
- Geospatial reprojection
- Cloud and invalid-pixel masking

## Model Architecture

Implemented a Residual CNN architecture for multispectral image super-resolution.

Key components:
- 8 Residual Blocks for feature extraction.
- Residual Learning for reconstructing high-frequency details.
- 2× PixelShuffle Upsampling for spatial resolution enhancement.
- Bicubic Interpolation as the baseline reconstruction method.

## Training Methodology

- Generated 400 georeferenced image patches.
- Training: 300 patches.
- Validation: 50 patches.
- Testing: 50 patches.
- Combined L1, spectral-consistency, and gradient loss.
- AdamW optimizer.
- Adaptive learning-rate scheduling.

## Model Evaluation

The model was evaluated against bicubic interpolation using:

- Mean Absolute Error (MAE)
- Root Mean Square Error (RMSE)
- Peak Signal-to-Noise Ratio (PSNR)
- Structural Similarity Index Measure (SSIM)

### Achieved Results

| Metric | Result |
|---|---:|
| PSNR | 44.99 dB |
| SSIM | 0.978 |

## Streamlit Dashboard

The application provides:

- High-resolution satellite image outputs.
- RGB composite visualizations.
- NDVI (Normalized Difference Vegetation Index) maps.
- Model-disagreement maps.
- Geospatial image visualization.

The inference pipeline also generates imagery on a 4 m grid.

## Project Outcomes

- Developed an end-to-end satellite image super-resolution pipeline.
- Implemented and trained a residual CNN for multispectral imagery.
- Evaluated reconstruction quality against bicubic interpolation.
- Generated enhanced satellite imagery and remote-sensing visualizations.
- Integrated model outputs into an interactive Streamlit application.

## Future Scope

- Explore advanced deep learning architectures.
- Improve spectral and spatial reconstruction quality.
- Extend the pipeline to additional satellite datasets.
- Optimize inference performance for larger geospatial images.

---

**Project Domain:** Deep Learning | Computer Vision | Remote Sensing | Geospatial AI
