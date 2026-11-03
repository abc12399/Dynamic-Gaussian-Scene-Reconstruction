<div align="center">

# Dynamic Gaussian Scene Reconstruction from Unsynchronized Videos

**AAAI 2026**

Zhixin Xu · Hengyu Zhou · Yuan Liu · Wenhan Xue · Hao Pan · Wenping Wang · Bin Wang

[![arXiv](https://img.shields.io/badge/arXiv-2511.11175-B31B1B?style=for-the-badge&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2511.11175)
[![Paper PDF](https://img.shields.io/badge/Paper-PDF-5146DC?style=for-the-badge)](https://arxiv.org/pdf/2511.11175)
[![Code status](https://img.shields.io/badge/Code-Coming_Soon-697386?style=for-the-badge&logo=github&logoColor=white)](#timeline)

</div>

## Timeline

- **2025-11-14** — Paper released on arXiv.
- **Code: Coming Soon.**

## ✨ Overview

We reconstruct dynamic Gaussian scenes from **unsynchronized multi-view videos**. A coarse-to-fine alignment module estimates each camera's time shift, reducing the blur and ghosting caused by temporal misalignment.

- **Frame-level initialization.** Find reliable temporal offsets through foreground feature matching.
- **Sub-frame refinement.** Learn continuous time corrections jointly with the scene representation.
- **Flexible integration.** Evaluated with SC-GS, 4DGaussians, and RT4DGS.

## 🧩 Method

<p align="center">
  <img src="assets/method-overview.png" alt="Coarse temporal alignment with LoFTR and RANSAC, followed by learnable fine temporal refinement." width="100%" />
</p>

1. **Match the moving foreground.** Use LoFTR and foreground masks to establish correspondences across views.
2. **Estimate coarse offsets.** Search integer-frame shifts and select the offsets with the most RANSAC inliers.
3. **Refine during reconstruction.** Optimize a continuous per-camera residual offset together with the Gaussian scene using photometric supervision.

## 🖼️ Results

<p align="center">
  <img src="assets/qualitative-results.png" alt="Ground truth, 4DGaussians and RT4DGS baselines, and results enhanced by our temporal alignment module." width="100%" />
  <br />
  <sub>Novel-view comparisons on DyNeRF. Temporal alignment reduces blur and ghosting in dynamic regions.</sub>
</p>

On six DyNeRF scenes with offsets of up to 10 frames at 15 FPS, our module improves **4DGaussians' mean PSNR from 29.60 to 31.16 dB** (averaged from Table 1). See the [paper](https://arxiv.org/html/2511.11175v1#Sx5.T1) and [full PSNR / SSIM / LPIPS results](assets/results.csv) for details.

## Citation

```bibtex
@misc{xu2025dynamicgaussian,
  title         = {Dynamic Gaussian Scene Reconstruction from Unsynchronized Videos},
  author        = {Zhixin Xu and Hengyu Zhou and Yuan Liu and Wenhan Xue and
                   Hao Pan and Wenping Wang and Bin Wang},
  year          = {2025},
  eprint        = {2511.11175},
  archivePrefix = {arXiv},
  primaryClass  = {cs.CV},
  url           = {https://arxiv.org/abs/2511.11175}
}
```
