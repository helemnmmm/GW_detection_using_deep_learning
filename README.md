## Acknowledgement

This project is heavily based on [GWData-Bootcamp](https://github.com/iphysresearch/GWData-Bootcamp).  
Most of the code was adapted or derived from that repository.  
We sincerely thank the original authors for their valuable contributions.

## Intro

This repository contains a deep learning framework for simulating and identifying gravitational wave (GW) signals, particularly those from binary neutron star (BNS&BBH) mergers. The project leverages signal whitening, and CNN&ResNet to distinguish GW signals from noise. More details for this project to see [here](https://helemnmmm.github.io/projects/1_project/).

## Repository Structure

- `baseline.ipynb`: Main Jupyter notebook demonstrating signal generation, preprocessing, and model inference.
- `main.py`: Contains model architecture and training pipeline.
- `utils.py`: Utility functions for visualizing training process.

## Key Features

- Simulates BNS&BBH gravitational waveforms using user-defined sampling parameters.
- Supports Gaussian LIGO noise PSD injection and data whitening.
- Implements 4 classifiers to distinguish signal from noise.
- Modular code with flexible parameters: observation time, sampling rate, SNR, etc.

## Requirements

- Python 3.7+
- PyTorch
- NumPy, Matplotlib, SciPy
- [LALSuite](https://git.ligo.org/lscsoft/lalsuite) (for waveform and PSD generation)

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/helemnmmm/GW_detection_using_deep_learning.git
cd GW_detection_using_deep_learning
```

### 2. Install dependencies

You need install the required packages using pip or conda:

```bash
!pip install [package]
```

### 3. Run the notebook

Open and run the `baseline.ipynb` file in Jupyter:

This will:

- Generate synthetic GW signals and stimulated LIGO-like noise, for different mergers type(BNS/BBH), you need choose different `baseline.ipynb` in [BNS](https://github.com/helemnmmm/GW_detection_using_deep_learning/tree/main/BNS) or [BBH](https://github.com/helemnmmm/GW_detection_using_deep_learning/tree/main/BBH).
- Whiten the data and visualize it
- Train or test the deep learning classifier on the simulated datasets, where you can choose the different models:

 ```bash
  model_type='ResNet152' #CNN,ResNet50,ResNet101,ResNet152,LSTM
 ```

### 4. Model training (optional)

If you want to train a model from scratch:

```bash
Nnoise=25
batchsize=16
train_nsample_perepoch =100
test_nsample_perepoch =100
```

See `main.py` for more training options.

