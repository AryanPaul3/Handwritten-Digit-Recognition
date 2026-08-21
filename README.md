# Handwritten Digit Recognition using Neural Network

## Project Overview
This project involves identifying handwritten digits from 0 to 9 within images or scanned documents. It implements a neural network-based solution, serving as a benchmark for evaluating models in real-world applications.

## Technology Stack
The project is built using the following libraries and frameworks:
* Python
* TensorFlow/Keras
* NumPy
* Pandas
* Scikit-learn
* Matplotlib

## Dataset Details
* The training dataset consists of 42,000 rows, where each row represents a single image.
* The first column contains the label, indicating the correct digit from 0 to 9.
* The remaining columns contain the pixel values, totaling 784 features per image (representing 28x28 pixels).

## Data Preprocessing Pipeline
Before training the neural network, the raw data undergoes several preprocessing steps:
* The data is converted to a Pandas DataFrame, cast to numeric values, and any missing values are replaced with 0.
* Pixel values are normalized to a range between 0 and 1 by dividing them by 255.0, which helps the model learn faster.
* The feature data is reshaped to include a channel dimension, resulting in a shape of (42000, 28, 28, 1) to ensure compatibility with the neural network.
* The labels are transformed using one-hot encoding into a 10-class format.
* The dataset is split into an 80% training set and a 20% validation set.

## Model Architecture
The project utilizes a feedforward neural network with the following layers:
* **Flatten Layer**: Converts the 28x28 image input into a single 1D vector of length 784.
* **First Hidden Layer**: A Dense layer with 128 neurons utilizing the ReLU activation function to introduce non-linearity.
* **Second Hidden Layer**: A Dense layer with 64 neurons, also using the ReLU activation function.
* **Output Layer**: A Dense layer with 10 neurons utilizing the softmax activation function to output predicted probabilities for each of the 10 digits.

## Training and Results
* The model is compiled using the Adam optimizer, categorical cross-entropy loss, and accuracy as the evaluation metric.
* Training is conducted over 10 epochs using a batch size of 32 samples.
* The trained model achieves approximately 96.81% training accuracy and 97.13% validation accuracy.
* These metrics indicate that the model performs well on both training and validation data, demonstrating good generalization capabilities for recognizing unseen handwritten digits.
