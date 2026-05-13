# 🏠 Multimodal ML – Housing Price Prediction Using Images + Tabular Data

A sophisticated machine learning project that combines **computer vision** and **tabular data** to predict house prices in Southern California. This demonstrates the power of multimodal learning by leveraging both image features from property photos and numerical/categorical features from structured data.

## Project Overview

This end-to-end multimodal machine learning project demonstrates:
- Loading and preprocessing both image and tabular data
- Building a hybrid neural network combining CNN and MLP branches
- Training on multi-input data (images + tabular features)
- Evaluating performance with real estate price prediction
- Scaling and optimization techniques for better convergence

## Dataset

- **Source**: House Prices and Images - SoCal (Southern California)
- **Data Type**: Multimodal
  - **Images**: Property photos (PNG format, 64x64 resolution)
  - **Tabular Data**: Numerical and categorical features
- **Target**: House price in dollars
- **Size**: 1,000 samples used in this project

## Project Structure

```
Multimodal ML – Housing Price Prediction Using Images + Tabular Data/
├── Multimodal ML.ipynb    # Complete multimodal pipeline
└── README.md              # This file
```

## Architecture

### Model Design

The project implements a **dual-branch neural network**:

1. **CNN Branch (Image Processing)**
   - Input: 3-channel images (64×64)
   - Conv2d layers with ReLU activation
   - MaxPooling layers for dimensionality reduction
   - Outputs: 16-dimensional feature vector

2. **MLP Branch (Tabular Data)**
   - Input: Numerical/categorical features (one-hot encoded)
   - Dense layers with ReLU activation
   - Outputs: 8-dimensional feature vector

3. **Fusion & Output Layer**
   - Concatenate CNN and MLP outputs
   - Dense layers for price prediction
   - Output: Single-value house price prediction

### Loss Function & Optimization
- **Loss**: Huber Loss (robust to outliers)
- **Optimizer**: Adam (learning rate: 0.0005)
- **Epochs**: 60
- **Batch Processing**: Full dataset (1,000 samples)

## Installation

### Prerequisites
- Python 3.8+
- pip

### Setup

1. Clone the repository:
```bash
git clone https://github.com/Hassan-tech-pro/ML-Projects.git
cd "Multimodal ML – Housing Price Prediction Using Images + Tabular Data"
```

2. Install required packages:
```bash
pip install pandas numpy scikit-learn opencv-python torch torchvision torchaudio
pip install kagglehub
```

Or install all at once:
```bash
pip install pandas numpy scikit-learn opencv-python kagglehub --pre torch torchvision torchaudio --index-url https://download.pytorch.org/whl/nightly/cpu
```

## Usage

### Run the Complete Pipeline

1. Open `Multimodal ML.ipynb` in Jupyter Notebook or VS Code
2. Run all cells in sequence:
   - Install dependencies
   - Download dataset from Kaggle
   - Load and preprocess images (resize to 64×64)
   - Prepare tabular features (one-hot encoding)
   - Build multimodal model
   - Train on combined data
   - Evaluate performance

```bash
jupyter notebook "Multimodal ML.ipynb"
```

### Cell-by-Cell Breakdown

1. **Installation** - Install required packages
2. **Data Download** - Fetch dataset from Kaggle Hub
3. **Data Loading** - Load CSV and images from disk
4. **Image Preprocessing** - Resize images to 64×64 and normalize
5. **Tabular Preprocessing** - One-hot encode categorical variables
6. **Model Definition** - Create multimodal neural network
7. **Data Preparation** - Convert to PyTorch tensors
8. **Training** - Train model with Huber loss
9. **Evaluation** - Calculate MAE, MSE, RMSE on predictions

## Performance Metrics

The trained model achieves the following evaluation metrics:

- **Mean Absolute Error (MAE)**: Typical error in dollars
- **Mean Squared Error (MSE)**: Penalizes large errors
- **Root Mean Squared Error (RMSE)**: Error in original dollar units

See the notebook for specific metric values after training.

## Key Features

✅ **Multimodal Learning** - Combines images and structured data  
✅ **CNN for Vision** - Extracts spatial features from property photos  
✅ **MLP for Tabular Data** - Processes numerical/categorical features  
✅ **Fusion Architecture** - Intelligently combines both modalities  
✅ **Robust Loss Function** - Huber loss handles outliers in price data  
✅ **Real-world Application** - Practical use case in real estate pricing  

## Technologies Used

- **PyTorch**: Deep learning framework
- **OpenCV (cv2)**: Image processing and resizing
- **Pandas**: Data manipulation and loading
- **NumPy**: Numerical computing
- **Scikit-learn**: Data splitting and preprocessing
- **Kaggle Hub**: Dataset downloading
- **Jupyter**: Interactive notebook environment

## Troubleshooting

### Image Loading Fails
- Verify image directory path is correct
- Check image files exist with .png extension
- Ensure images are in RGB format

### Memory Issues
- Reduce batch size (currently processes all at once)
- Reduce image resolution below 64×64
- Use a smaller subset of data for testing

### Poor Convergence
- Adjust learning rate (currently 0.0005)
- Increase number of epochs
- Try different loss functions (MSE, L1Loss)
- Scale target values appropriately

### Dataset Not Found
- Ensure Kaggle credentials are configured
- Check internet connection
- Verify dataset name is still available on Kaggle

## Future Improvements

- 📊 Add data augmentation for images (rotation, flipping)
- 🔍 Implement cross-validation for better generalization
- 📈 Add attention mechanisms for feature importance
- 🎯 Create separate test/validation sets
- 🚀 Deploy model as API endpoint
- 📉 Implement learning rate scheduling
- 🎨 Visualize learned CNN filters

## Dataset Citation

Dataset: House Prices and Images - SoCal  
Source: Kaggle (ted8080)  
Link: https://www.kaggle.com/datasets/ted8080/house-prices-and-images-socal

## Learning Outcomes

This project teaches:
- How to work with multimodal data in deep learning
- CNN architecture for image feature extraction
- Combining different neural network branches
- Hyperparameter tuning and optimization
- Working with PyTorch for custom models
- Real-world ML applications

## License

This project is open source and available under the MIT License.

## Contributing

Contributions are welcome! Please:
- Report issues on GitHub
- Suggest improvements
- Submit pull requests with enhancements

## Contact

For questions or feedback, please open an issue on: [Hassan-tech-pro/ML-Projects](https://github.com/Hassan-tech-pro/ML-Projects)

---

**Last Updated**: May 2026  
**Project Type**: Multimodal Deep Learning  
**Framework**: PyTorch  
**Application**: Real Estate Price Prediction
