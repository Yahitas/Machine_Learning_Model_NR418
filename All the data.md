# Data Inventory
This document lists all files provided for the land cover classification. Files are organized by folder. 

---
## Project Folder Summary

| Folder | File Count | Description |
|--------|------------|-------------|
| `full_textures/` | ~35 files | GLCM texture layers, vegetation indices, full_test.tif |
| `og_tif_files/` | 3 files | Original raster (og_merge.tif), testr.tif, valdr.tif |
| `pca_results/` | ~12 files | PCA layers (pca_1 through pca_6 + extras) |
| `output_tifs/` | 3 files | mother_labels.tif, left_classified.tif, child_stack.tif |
| `polygons/` | 8 subfolders | Training polygon shapefiles (6 classes + 2 point sets) |
| `rds_outputs/` | 5 files | Saved R model objects and data frames |

---

## full_textures/

Contains all GLCM texture layers (21), vegetation index layers (8+), and the full_test.tif raster stack. 

| File | Size | Description |
|------|------|-------------|
| `GLCM_Blueglcm_contrast.tif` | 435.1 MB | GLCM contrast, blue band |
| `GLCM_Blueglcm_correlation.tif` | 647.6 MB | GLCM correlation, blue band |
| `GLCM_Blueglcm_dissimilarity.tif` | 385.5 MB | GLCM dissimilarity, blue band |
| `GLCM_Blueglcm_entropy.tif` | 640.9 MB | GLCM entropy, blue band |
| `GLCM_Blueglcm_homogeneity.tif` | 600.2 MB | GLCM homogeneity, blue band |
| `GLCM_Blueglcm_mean.tif` | 453.9 MB | GLCM mean, blue band |
| `GLCM_Blueglcm_variance.tif` | 674.1 MB | GLCM variance, blue band |
| `GLCM_Greenglcm_contrast.tif` | 440.1 MB | GLCM contrast, green band |
| `GLCM_Greenglcm_correlation.tif` | 649 MB | GLCM correlation, green band |
| `GLCM_Greenglcm_dissimilarity.tif` | 389.9 MB | GLCM dissimilarity, green band |
| `GLCM_Greenglcm_entropy.tif` | 641.8 MB | GLCM entropy, green band |
| `GLCM_Greenglcm_homogeneity.tif` | 615 MB | GLCM homogeneity, green band |
| `GLCM_Greenglcm_mean.tif` | 456.3 MB | GLCM mean, green band |
| `GLCM_Greenglcm_variance.tif` | 677.3 MB | GLCM variance, green band |
| `GLCM_Redglcm_contrast.tif` | 443.6 MB | GLCM contrast, red band |
| `GLCM_Redglcm_correlation.tif` | 650.4 MB | GLCM correlation, red band |
| `GLCM_Redglcm_dissimilarity.tif` | 392.9 MB | GLCM dissimilarity, red band |
| `GLCM_Redglcm_entropy.tif` | 642.4 MB | GLCM entropy, red band |
| `GLCM_Redglcm_homogeneity.tif` | 624.9 MB | GLCM homogeneity, red band |
| `GLCM_Redglcm_mean.tif` | 457.7 MB | GLCM mean, red band |
| `GLCM_Redglcm_variance.tif` | 679.2 MB | GLCM variance, red band |
| `glcm_200_blue_all_bands.tif` | 4.27 GB | All 7 blue GLCM metrics (multi-band) |
| `glcm_200_green_all_bands.tif` | 4.3 GB | All 7 green GLCM metrics (multi-band) |
| `glcm_200_red_all_bands.tif` | 4.32 GB | All 7 red GLCM metrics (multi-band) |
| `EXG_200.tif` | 116.5 MB | Excess Green Index |
| `EXG_norm_200.tif` | 142.9 MB | Excess Green (normalized 0–1) |
| `EXGR_200.tif` | 272.5 MB | Excess Green-Red Index |
| `GLI_200.tif` | 541.9 MB | Green Leaf Index |
| `NGRDI_200.tif` | 531.7 MB | Normalized Green-Red Difference Index |
| `RGBVI_200.tif` | 675.1 MB | RGB Vegetation Index |
| `TGI_200.tif` | 283.8 MB | Triangular Greenness Index |
| `VARI_200.tif` | 507.2 MB | Visible Atmospherically Resistant Index |
| `VEG_200.tif` | 570.3 MB | Vegetation Index |
| `full_test.tif` | 11.68 GB | Right-half raster stack (35 bands) for teacher model |

---

## og_tif_files/

Original RGB drone rasters. `og_merge.tif` is the full merged orthomosaic. `testr.tif` right side and `valdr.tif` left side.

| File | Size | Description |
|------|------|-------------|
| `og_merge.tif` | 721.6 MB | Full merged RGB drone raster (3 bands) |
| `testr.tif` | 370.1 MB | Right half of raster (training side) |
| `valdr.tif` | 353.3 MB | Left half of raster (validation side) |

---

## pca_results/

PCA output layers. `pca_1.tif` through `pca_6.tif` are the six principal components used by the teacher model. The PCAPC files and `PCA_PC1_to_PC6.tif` are alternative exports of the same data.

| File | Size | Description |
|------|------|-------------|
| `pca_1.tif` | 720 MB | Principal Component 1 (highest variance) |
| `pca_2.tif` | 718.2 MB | Principal Component 2 |
| `pca_3.tif` | 718.8 MB | Principal Component 3 |
| `pca_4.tif` | 720.4 MB | Principal Component 4 |
| `pca_5.tif` | 715.8 MB | Principal Component 5 |
| `pca_6.tif` | 718.6 MB | Principal Component 6 |
| `PCA_PC1_to_PC6.tif` | 4.34 GB | All 6 PCs as one multi-band raster |
| `PCAPC1.tif` – `PCAPC6.tif` | ~718 MB each | Alternate individual PC exports |

---

## output_tifs/

Model outputs: the teacher model's pixel-level labels, the student model's classification of the left side, and the student feature stack.

| File | Size | Description |
|------|------|-------------|
| `mother_labels.tif` | 22.6 MB | Teacher model classification of right side (6 classes) |
| `left_classified.tif` | 24.6 MB | Student model classification of left side (6 classes) |
| `child_stack.tif` | 10.35 GB | Student model 18-layer feature stack |

---

## polygons/

Hand-digitized training polygons (shapefiles). Each subfolder contains `.shp`, `.shx`, `.dbf`, and `.prj` files.

| Subfolder | Type | Description |
|-----------|------|-------------|
| `BG_poly_test/` | Shapefile | Bare ground training polygons |
| `DS_poly_test/` | Shapefile | Dead shrubs training polygons |
| `GRS_poly_test/` | Shapefile | Grass training polygons |
| `RT_poly_test/` | Shapefile | Russian thistle training polygons |
| `SB_poly_test/` | Shapefile | Saltbush training polygons |
| `SHD_poly_test/` | Shapefile | Shadow training polygons |
| `NO_SB_pts_test/` | Shapefile | Non-saltbush point samples |
| `NO_TS_pts_test/` | Shapefile | Non-thistle point samples |

---

## rds_outputs/

Saved R objects (`.rds`). These contain trained models and processed data frames that can be loaded with `readRDS()`.

| File | Size | Description |
|------|------|-------------|
| `rf_caret_model.rds` | 354.6 MB | Trained teacher model (Random Forest, 500 trees, 96% accuracy) |
| `child_model.rds` | 329.8 MB | Trained student model (Random Forest, 500 trees, 94.6% agreement) |
| `train_data.rds` | 464.5 MB | Full training data frame (all polygon-extracted pixels) |
| `test_set.rds` | 5.9 MB | Teacher model test set (30% held-out split) |
| `child_training_df.rds` | 16.2 MB | Student model training data (300K subsampled pixels) |

---

## QMD Script Files

Quarto Markdown files to be run in order in RStudio. Each file is numbered for sequence.

| File                          | Step      | Description                                                  |
| ----------------------------- | --------- | ------------------------------------------------------------ |
| `1_pre_processing.qmd`        | Step 1    | Compute GLCM textures and vegetation indices from raw raster |
| `2_pca.qmd`                   | Step 2    | Run PCA on the 28-layer stack to produce 6 PC layers         |
| `3_teacher_model.qmd`         | Step 3    | Train teacher model on 35 features + generate pixel labels   |
| `4_student_model.qmd`         | Step 4    | Train student model on 18 RGB features using teacher labels  |
| `5_testing_student_model.qmd` | Step 5    | Apply student model to left side (validation area)           |
| `6_FINAL_TEMPLATE.qmd`        | Last step | Apply the machine learning model to similar drone imagery    |

---

## Estimated Total Data Size

| Folder                  | Size       | Notes                         |
| ----------------------- | ---------- | ----------------------------- |
| `full_textures/`        | ~30 GB     |                               |
| `og_tif_files/`         | ~1.4 GB    | Original rasters              |
| `pca_results/`          | ~9 GB      | PCA layers                    |
| `output_tifs/`          | ~10.4 GB   | Model outputs                 |
| `polygons/`             | < 50 MB    | Training shapefiles           |
| `rds_outputs/`          | ~1.2 GB    | Model objects and data frames |
| **Total (approximate)** | **~52 GB** | Full dataset                  |

