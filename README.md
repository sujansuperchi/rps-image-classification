# Rock-Paper-Scissors Image Classification

Project for the course Data Science and Management (IGM-20), Sujan Superchi.

The task is to classify photos of hand gestures (rock, paper, scissors) using the
[Rock-Paper-Scissors dataset](https://www.kaggle.com/datasets/drgfreeman/rockpaperscissors) on Kaggle
(2188 PNG images, CC BY-SA 4.0, by Julien de la Bruère-Terreault).

All photos in this dataset are taken with the same setup (green background, same camera and lighting),
so getting a high accuracy is quite easy: the author of the dataset already reports F1 around 0.98-0.99
with PCA + SVM. For this reason the project looks mainly at:

- avoiding data leakage: near-duplicate photos are kept in the same set when splitting the data
- robustness: how the models work on new photos with different backgrounds and lighting
- efficiency: a small CNN compared with a pre-trained MobileNet (accuracy, training time, model size)

## Research questions

1. How much does a small CNN improve over simple baselines (PCA + logistic regression / KNN / SVM)?
2. Does data augmentation help, on the test set and on new photos?
3. How much do the models get worse when the background and the lighting change?
4. (extra) How does MobileNet compare with the small CNN in accuracy, training time and size?

## Structure

```
notebooks/        notebooks, to run in order (01_eda, 02_split, ...)
splits/           train/validation/test assignment of every image
results/figures/  figures for the report
results/metrics/  tables and metrics saved by the notebooks
report/           report and slides
data.nosync/      dataset (not in the repository)
```

## How to run

1. Create the environment with [uv](https://docs.astral.sh/uv/) (`uv sync`) or with pip (`pip install -r requirements.txt`).
2. Download the dataset from Kaggle and unzip it in `data.nosync/rockpaperscissors/`.
3. Run the notebooks in `notebooks/` in order.
