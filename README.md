# Data for online Gaussian count budget estimation

This repository contains the locally captured multiview scene and numerical measurements used in the study of Gaussian count estimation within a single 3D Gaussian Splatting training run.

## Contents

- `data/data-lite/images/` contains the 75 JPEG images for the local bottle scene. Image filenames and bytes are preserved.
- `data/data-lite/sparse/0/` contains the COLMAP calibration and sparse point cloud used for that scene.
- `measurements/paired_runs.csv` contains 27 training-arm records from three scenes and three paired rounds each. Time is the complete training-process wall time. Memory is the CUDA allocator peak for that process. PSNR is the mean held-out score at the loaded training-image resolution.
- `measurements/demand_traces/` contains the nine online runs' event-level demand and population records.
- `measurements/heldout_stored_resolution.csv` contains per-view PSNR, SSIM and VGG LPIPS for the screening-round model from each arm. These scores were computed at the original stored image dimensions for the local scene and at the stored images_4 dimensions for the two outdoor scenes.

The two outdoor scenes, treehill and flowers, are from the Mip-NeRF 360 dataset and are available from the original [dataset page](https://jonbarron.info/mipnerf360/).

The CSV identifies each model by its SHA-256 checksum. Model PLY files and the original training environment are not included in this repository. The historical source and binary versions are recorded in the original experimental manifests; rebuilding an identical environment has not been verified. The high-resolution rendering scores cover the first round for each scene.

Scene and round names follow the paper. A screening round is followed by two confirmation rounds. The budgeted control is named `static` for outdoor scenes and `v8` for the local scene.
