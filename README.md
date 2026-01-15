![AN2DL_final](https://github.com/user-attachments/assets/7159efe2-6ce7-44ac-948f-30c1b172e43f)


# Submission Guide

This folder gathers every notebook and artifact needed to review our image-classification project: data cleaning, experiments, synthetic data attempts, final training, and the ensemble used for the submission.

## How to Navigate
- Start with `c2_final.ipynb` to see the full training pipeline for the pretrained models that produced the final checkpoints and predictions.
- Open `ensemble.ipynb` to follow the majority-vote fusion of the six model predictions stored in `ensemble_predictions/`.
- Browse `model_experiments/` to inspect the exploratory runs that informed the final choices (CNN, VGG, Inception with Ranger optimizer).
- Check `data_processing/` for the outlier-removal passes run on the dataset.
- Review `synthetization_experiments/` to see the attempt at generating extra training images.
- Use the file notes below to jump directly to any artifact.

## File and Folder Map
- `c2_final.ipynb` — Final end-to-end pipeline: dataset loading, preprocessing/augmentation, fine-tuning of pretrained models, evaluation, and export of predictions.
- `ensemble.ipynb` — Loads the six prediction CSVs below and performs majority voting to build the final ensemble submission.
- `data_processing/`
  - `booger_detection.ipynb` — Outlier detection and removal pass for the dataset (focused on problematic images containing “boogers”).
  - `shrek_detection.ipynb` — Complementary outlier pass targeting additional noisy samples (“shrek” images in the tissue shape).
- `model_experiments/`
  - `FL+cnn+ranger.ipynb` — Baseline CNN trained with the Ranger optimizer; logs training curves and metrics.
  - `FL+vgg16+ranger.ipynb` — VGG16 fine-tuning experiment with Ranger.
  - `FL+vgg19+ranger.ipynb` — VGG19 fine-tuning experiment with Ranger.
  - `inception.ipynb` — Inception-based experiment exploring hyperparameters and performance.
- `synthetization_experiments/`
  - `synthetic.ipynb` — Trials for synthesizing new training images (augmentations/generation) and assessing their impact. To download generated images, access the linked Google Drive folder: https://drive.google.com/drive/folders/1FRURBWotBOZ-hc_-xMsz9rbB6HguwUgp?usp=sharing
- `ensemble_predictions/` — Prediction CSVs from the six models used in the ensemble (file names indicate architecture/optimizer):
  - `inceptionv3_ranger.csv`
  - `resnet50_ranger.csv`
  - `vgg16_adam.csv`
  - `vgg16_adam_synthetic.csv`
  - `vgg16_ranger.csv`
  - `vgg19_ranger.csv`

