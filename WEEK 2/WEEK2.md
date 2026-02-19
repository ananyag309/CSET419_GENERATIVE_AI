# CSET419 -- Generative AI Fundamentals

## Lab Experiment 02

# Training a Generative Adversarial Network (GAN) for Digit Generation

------------------------------------------------------------------------

## 1. Objective

In this lab, I implemented a basic GAN using TensorFlow to generate handwritten digits from MNIST. The generator learns to create images from random noise, while the discriminator learns to classify real vs fake images. Through adversarial training over 30 epochs, the generator improved significantly. However, classifier evaluation showed mode collapse, indicating limited diversity in generated samples.

------------------------------------------------------------------------

## 2. Dataset Description

-   Dataset Name: MNIST Handwritten Digits
-   Source: TensorFlow / Keras Built-in Dataset
-   Image Size: 28 × 28 pixels
-   Color Mode: Grayscale
-   Number of Classes: 10 (Digits 0--9)

The dataset contains labeled handwritten digit images used for training
and evaluation.

------------------------------------------------------------------------

## 3. Hyperparameters Used

-   Dataset: MNIST
-   Epochs: 30
-   Batch Size: 128
-   Latent Space Dimension: 100
-   Learning Rate: 0.0002
-   Image Save Interval: Every 5 epochs

These hyperparameters were selected to ensure stable adversarial
training while maintaining computational efficiency.

------------------------------------------------------------------------

## 4. Model Architecture

### 4.1 Generator Network

The Generator transforms a random noise vector into a synthetic image.

Architecture: - Input: 100-dimensional random noise vector - Dense
(Fully Connected) Layers - Activation: LeakyReLU - Output Layer
Activation: Sigmoid - Output Shape: 28 × 28 image

Objective: To generate realistic handwritten digit images capable of
fooling the Discriminator.

------------------------------------------------------------------------

### 4.2 Discriminator Network

The Discriminator acts as a binary classifier.

Architecture: - Input: 28 × 28 image (real or fake) - Dense Layers with
LeakyReLU - Output: Single neuron (probability) - Activation: Sigmoid

Objective: To distinguish between real MNIST images and generated
images.

------------------------------------------------------------------------

## 5. Training Procedure

The GAN training follows an adversarial strategy:

Step 1: Train the Discriminator - Real images labeled as 1 - Generated
images labeled as 0

Step 2: Train the Generator - Generate fake images - Attempt to fool the
Discriminator - Update Generator weights through backpropagation

This alternating training process continues for 30 epochs.

Loss values for both models were monitored throughout training.

------------------------------------------------------------------------

## 6. Experimental Outputs

### 6.1 Training Logs

-   Generator loss per epoch
-   Discriminator loss per epoch
-   Observed convergence behavior

### 6.2 Intermediate Generated Samples

Directory: generated_samples/ - Images saved every 5 epochs - Each image
contains 25 generated samples (5 × 5 grid)

### 6.3 Final Generated Images

Directory: final_generated_images/ - Total images generated: 100 - Used
for qualitative evaluation

### 6.4 Diversity Analysis

-   A pre-trained digit classifier was used
-   Generated images were evaluated
-   Predicted label distribution analyzed to check diversity

------------------------------------------------------------------------

## 7. Observations

-   Early epochs produced noisy and unclear outputs
-   Image clarity improved gradually
-   Generator and Discriminator losses showed competitive behavior
-   Final outputs resembled realistic handwritten digits
-   Diversity analysis confirmed multi-class generation

------------------------------------------------------------------------

## 8. Conclusion

The experiment successfully demonstrated the working principles of
Generative Adversarial Networks. Through adversarial learning, the
Generator improved its ability to synthesize realistic handwritten
digits. This lab provided practical understanding of:

-   Latent space representation
-   Adversarial optimization
-   Synthetic data generation
-   Model convergence analysis

------------------------------------------------------------------------

## 9. Tools and Technologies Used

-   Python 3
-   TensorFlow / Keras
-   NumPy
-   Matplotlib
-   Google Colab

------------------------------------------------------------------------

