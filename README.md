# AI-Powered Handwriting Digit Generator

An interactive web application that generates realistic handwritten digits (0-9) using a Conditional Variational Autoencoder (CVAE) trained on the MNIST dataset. Built with PyTorch and Streamlit.

## Features

- **Interactive Web Interface**: Easy-to-use Streamlit interface for generating digits
- **Conditional Generation**: Select any digit (0-9) to generate multiple variations
- **CVAE Architecture**: Uses a Conditional Variational Autoencoder for high-quality digit generation
- **Real-time Generation**: Generate multiple handwritten digit samples instantly
- **Adjustable Output**: Control the number of generated images (1-10)

## Technology Stack

- **Python 3.x**
- **PyTorch**: Deep learning framework for the CVAE model
- **Streamlit**: Web application framework
- **Matplotlib**: Visualization of generated digits
- **MNIST Dataset**: Training data for the model

## Prerequisites

Before running this project, make sure you have the following installed:

- Python 3.7 or higher
- pip (Python package manager)

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/NahuelBarriga/AI-powered-handwriting-digit-generator.git
   cd AI-powered-handwriting-digit-generator
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

   The required packages are:
   - `torch`: PyTorch deep learning library
   - `streamlit`: Web application framework
   - `matplotlib`: Plotting and visualization

## 💻 Running the Application Locally

1. **Start the Streamlit app**
   ```bash
   streamlit run app.py
   ```

2. **Access the application**
   - The application will automatically open in your default web browser
   - If it doesn't open automatically, navigate to `http://localhost:8501`

3. **Generate digits**
   - Select a digit (0-9) from the dropdown menu
   - Adjust the number of images to generate using the slider
   - Click the "🚀 Generate Images" button
   - View the generated handwritten digits displayed below

## Project Structure

```
AI-powered-handwriting-digit-generator/
├── app.py                      # Streamlit web application
├── model.py                    # CVAE model definition and utilities
├── cvae_mnist.pth              # Pre-trained CVAE model weights
├── cvae_mnist_train.ipynb      # Jupyter notebook for model training
├── requirements.txt            # Python dependencies
├── data/                       # MNIST dataset directory (created on first run)
└── README.md                   # Project documentation
```

## Model Architecture

The project uses a **Conditional Variational Autoencoder (CVAE)** with the following architecture:

- **Latent Dimension**: 20
- **Encoder**: 
  - Input: 784 (28×28 image) + 10 (one-hot encoded label)
  - Hidden layer: 400 neurons
  - Output: Mean (μ) and log-variance (σ²) for latent space
- **Decoder**:
  - Input: 20 (latent vector) + 10 (one-hot encoded label)
  - Hidden layer: 400 neurons
  - Output: 784 (28×28 reconstructed image)

The model is trained on the MNIST dataset and can generate new digit variations by sampling from the learned latent space.

## How It Works

1. **User Input**: Select a digit (0-9) and specify the number of images to generate
2. **Encoding**: The digit label is encoded as a one-hot vector
3. **Sampling**: Random latent vectors are sampled from a normal distribution
4. **Decoding**: The CVAE decoder generates images conditioned on both the latent vector and the digit label
5. **Display**: Generated images are displayed in grayscale

## Training Your Own Model

If you want to retrain the model:

1. Open and run the Jupyter notebook:
   ```bash
   jupyter notebook cvae_mnist_train.ipynb
   ```

2. The notebook will:
   - Download the MNIST dataset
   - Define and train the CVAE model
   - Save the trained weights to `cvae_mnist.pth`

## Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

## 📄 License

This project is open source and available for educational and research purposes.

## Author

**Nahuel Barriga**

## Acknowledgments

- MNIST Dataset: Yann LeCun, Corinna Cortes, and Christopher J.C. Burges
- PyTorch Team for the excellent deep learning framework
- Streamlit Team for the intuitive web app framework

---

**Enjoy generating handwritten digits!**
