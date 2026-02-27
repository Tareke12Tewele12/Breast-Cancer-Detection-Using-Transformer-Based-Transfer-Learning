````markdown
# Transformer-Based Transfer Learning for Breast Cancer Detection via Digital Breast Tomosynthesis

## Table of Contents

- [Overview](#overview)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Usage](#usage)

## Overview

This project explores the use of Transformer and CNN architectures with Transfer Learning for detecting breast cancer from Digital Breast Tomosynthesis (DBT) images. The dataset is sourced from the [Cancer Imaging Archive](https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=64685580).

## Getting Started

Follow these steps to set up and run the project locally.

### Prerequisites

- Python 3.8.13

### Installation

1. Clone the repository:

```bash
git clone https://github.com/mikeadimech/Breast_Cancer_Detection_DBT.git
````

2. Navigate to the project folder:

```bash
cd Breast_Cancer_Detection_DBT
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

### Usage

1. Download the dataset from the [Cancer Imaging Archive](https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=64685580) and place it in `/data/images`.
2. Run the preprocessing notebook:

```bash
jupyter notebook preprocessing.ipynb
```

3. Train the model:

```bash
python src/main.py --model MaxViT --image_size 512
```

4. Perform hyperparameter tuning:

```bash
python src/hyperparameter_tuning.py --model MaxViT --trials 100
```

5. Evaluate a trained model stored in `/models`:

```bash
python src/evaluate.py --model MaxViT
```

**Arguments:**

* `--model`: Model architecture (`MaxViT` default, `ConvNeXt` optional)
* `--image_size`: Input image size (`224`, `384`, `512` default)
* `--verbose`: Enable verbose output
* `--trials`: Number of hyperparameter tuning trials

```
