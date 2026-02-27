# Transformer-based Transfer Learning for Breast Cancer Detection via Digital Breast Tomosynthesis

## Table of Contents

- [Description](#description)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Usage](#usage)

## Description

This project investigates the application of Transformer and CNN architectures via Transfer Learning for Breast Cancer Detection, specifically on Digital Breast Tomosynthesis (DBT) images. The dataset used was obtained from the [Cancer Imaging Archive](https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=64685580).

## Getting Started

These instructions will guide you on how to set up and run the project on your local machine.

### Prerequisites

- Python (version 3.8.13)

### Installation

1. Clone the repository:

```
git clone https://github.com/mikeadimech/Breast_Cancer_Detection_DBT.git
```

2. Navigate to the project directory:
```
cd Breast_Cancer_Detection_DBT
```

3. Install the required dependencies:
```
pip install -r requirements.txt
```

### Usage

You must first download the dataset from the [Cancer Imaging Archive](https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=64685580) and store it in `/data/images`. Then, run the `preprocessing.ipynb` notebook.

To run the main training script, use the following command:
```
python src/main.py --model MaxViT --image_size 512
```

For hyperparameter tuning:
```
python src/hyperparameter_tuning.py --model MaxViT --trials 100
```

For model evaluation (provided that you have a trained model stored in `/models`):
```
python src/evaluate.py --model MaxViT
```

Replace `MaxViT` and `512` with your desired values for the following arguments:

- `--model`: Model architecture. Possible options: `MaxViT` (default), `ConvNeXt`
- `--image_size`: Image input size for the model. Possible options: `224`, `384`, `512` (default)
- `--verbose`: For verbose output.
- `--trials`: Number of trials for hyperparameter tuning.
