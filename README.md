# Image Tester CNN — CIFAR-10 Classifier

A PyTorch image classification model that fine-tunes pretrained ResNet models on the CIFAR-10 dataset to detect and classify images into 10 categories.

## Classes
`airplane` · `automobile` · `bird` · `cat` · `deer` · `dog` · `frog` · `horse` · `ship` · `truck`

## Project Structure
```
Image-tester-cnn-project/
├── notebook/           # Jupyter notebook with full training code
├── model/              # Saved model weights (not tracked by git)
├── Test image/         # Sample images for inference
├── requirements.txt
└── .gitignore
```

> **Dataset:** This repo does not include the CIFAR-10 dataset. It will be downloaded automatically the first time you run the notebook via `torchvision.datasets.CIFAR10`. You can also download it manually from [https://www.cs.toronto.edu/~kriz/cifar.html](https://www.cs.toronto.edu/~kriz/cifar.html)

## Models

### Model 1 — ResNet18 ✅
| Setting | Value |
|---|---|
| Base model | ResNet18 (pretrained on ImageNet) |
| Output layer | Linear(512 → 10) |
| Epochs | 5 |
| Test Accuracy | **~80%** |

### Model 2 — ResNet50 ✅
| Setting | Value |
|---|---|
| Base model | ResNet50 (pretrained on ImageNet) |
| Output layer | Linear(2048 → 10) |
| Epochs | 15 |
| Test Accuracy | **~83%** |
| Loss | 0.0953 |

## Example Output

Input image fed to the model, and the predicted label printed below:

```
Model predicted: cat
```

<img width="667" height="696" alt="image" src="https://github.com/user-attachments/assets/c373a1e5-2099-40b9-9101-9ae6d1a424a8" />



## Setup

```bash
git clone https://github.com/YOUR_USERNAME/Image-tester-cnn.git
cd Image-tester-cnn
pip install -r requirements.txt
```

## Usage

Open the notebook inside the `notebook/` folder and run all cells. The dataset will be downloaded automatically on first run.

To test on your own image, update the `img_path` variable in the last cell:

```python
img_path = "Test image/your_image.jpg"
```

## Notes
- Model weights (`.pth`) and the `data/` folder are excluded from git due to file size
- Trained on macOS with Apple MPS acceleration
