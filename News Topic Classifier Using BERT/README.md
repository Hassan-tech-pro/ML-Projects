# 📰 News Topic Classifier Using BERT

A fine-tuned BERT model for classifying news articles into four categories: **World, Sports, Business, and Science/Technology**. This project includes model training, evaluation, and an interactive Gradio web interface for real-time predictions.

## Project Overview

This project demonstrates:
- Fine-tuning a pre-trained BERT model on the AG News dataset (120,000 articles)
- Evaluating model performance with accuracy and F1-score metrics
- Building an interactive classification interface with Gradio
- Deploying the model for real-world use

## Dataset

- **Source**: AG News Classification Dataset (120,000 news articles)
- **Classes**: 
  - World
  - Sports
  - Business
  - Science/Technology
- **Features**: Article Title + Description

## Project Structure

```
.
├── news_classifier.ipynb        # Model training and evaluation notebook
├── gradio_app.ipynb             # Interactive Gradio application
├── README.md                    # This file
├── .gitignore                   # Git ignore rules (excludes model folder)
├── config.json                  # Model configuration
├── model.safetensors            # Trained model weights
├── tokenizer_config.json        # Tokenizer configuration
├── tokenizer.json               # Tokenizer vocabulary
└── saved_bert_news_model/       # Complete saved model (NOT in repo - see below)
```

## Model Download

⚠️ **Important**: The `saved_bert_news_model` folder is **not included in this repository** due to size constraints. 

### How to Download the Model

1. Download the model from Google Drive: [Download Link](https://drive.google.com/file/d/1F4Smz37WBZZvz9HNYO5XbqxhIsc93YP9/view?usp=sharing)
2. Extract the contents to the project root directory
3. The folder should be named `saved_bert_news_model`

The `.gitignore` file has been configured to exclude this folder from version control:
```
saved_bert_news_model/
```

## Installation

### Prerequisites
- Python 3.8+
- pip

### Setup

1. Clone the repository:
```bash
git clone <your-repo-url>
cd <repo-directory>
```

2. Install required dependencies:
```bash
pip install pandas evaluate accelerate numpy transformers torch kagglehub gradio
```

Or install individually:
```bash
pip install transformers torch
pip install pandas
pip install evaluate accelerate
pip install numpy
pip install kagglehub
pip install gradio
```

3. Download the pre-trained model (see "Model Download" section above)

## Usage

### 1. Training the Model (Optional)

To train a new model from scratch:

1. Open `news_classifier.ipynb` in Jupyter Notebook or VS Code
2. Run all cells in sequence:
   - Install dependencies
   - Load and explore the AG News dataset
   - Initialize BERT tokenizer and model
   - Prepare and tokenize the data
   - Configure training arguments
   - Train the model
   - Evaluate performance
   - Save the model

**Note**: Training takes approximately 30-60 minutes depending on your hardware.

### 2. Running the Interactive Classifier

1. Download the pre-trained model (link above)
2. Open `gradio_app.ipynb` in Jupyter Notebook or VS Code
3. Run all cells to launch the Gradio interface
4. The app will be available at `http://localhost:7860`

Or run directly from terminal:
```bash
jupyter notebook gradio_app.ipynb
```

### 3. Making Predictions

Once the Gradio interface is running, you can:
- Enter any news headline or article text
- Get instant predictions with confidence scores
- Try the provided examples or your own text

Example predictions:
- "The championship game went into overtime..." → **Sports** (confidence %)
- "New quantum computing breakthroughs..." → **Sci/Tech** (confidence %)
- "The central bank raised interest rates..." → **Business** (confidence %)

## Model Performance

The trained model achieves:
- **Accuracy**: ~95%
- **F1 Score**: ~0.95 (weighted average)
- **Training epochs**: 3
- **Learning rate**: 2e-5
- **Batch size**: 16

## Architecture

- **Base Model**: BERT (bert-base-uncased)
- **Task**: Multi-class text classification
- **Number of classes**: 4
- **Max sequence length**: 128 tokens

## Files Description

| File | Description |
|------|-------------|
| `news_classifier.ipynb` | Complete training pipeline with data loading, preprocessing, model training, and evaluation |
| `gradio_app.ipynb` | Interactive web interface for making predictions |
| `config.json` | BERT model configuration |
| `model.safetensors` | Pre-trained model weights (from Google Drive) |
| `tokenizer_config.json` | BERT tokenizer configuration |
| `tokenizer.json` | BERT tokenizer vocabulary |
| `.gitignore` | Git configuration to exclude large model folder |

## Troubleshooting

### Model loading fails
- Ensure the `saved_bert_news_model` folder is in the project root
- Verify the folder contains: `config.json`, `model.safetensors`, `tokenizer.json`, `tokenizer_config.json`

### CUDA/GPU issues
- The model works on CPU but will be slower
- For GPU support, ensure CUDA-compatible PyTorch is installed: `pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118`

### Out of memory errors
- Reduce batch size in `news_classifier.ipynb`
- Reduce max_length in tokenization step

## Technologies Used

- **PyTorch**: Deep learning framework
- **Transformers**: BERT model and utilities
- **Hugging Face**: Model and dataset hosting
- **Gradio**: Web interface
- **Pandas**: Data manipulation
- **NumPy**: Numerical computing

## License

This project is open source and available under the MIT License.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Contact

For questions or issues, please open an issue on the GitHub repository.

---

**Last Updated**: May 2026
