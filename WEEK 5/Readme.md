In this lab, we implemented a baseline encoder–decoder CNN for CIFAR-10 image reconstruction. The encoder compresses a 32×32 RGB image into a 256×4×4 latent feature representation using convolutional layers. The decoder reconstructs the image using transposed convolutions. We trained the model using L1 loss and Adam optimizer for 10 epochs. The reconstruction works but produces blurry images due to pixel-wise loss.

### Dataset Used

CIFAR-10 dataset

- 32 × 32 RGB images
- 3 channels (Red, Green, Blue)
- 50,000 training images

Important:

- We are NOT doing classification
- We are doing image reconstruction

Images are normalized to [-1, 1] because final layer uses Tanh activation.

### MODEL ARCHITECTURE

Encoder → Bottleneck → Decoder

#### ENCODER (Compression Part)
Purpose: Reduce image size and extract features.

#### DECODER (Reconstruction Part)
Purpose: Rebuild original image.

### ACTIVATION FUNCTIONS

#### ReLU

Formula: `f(x) = max(0, x)`

Purpose:
- Adds non-linearity
- Removes negative values
- Helps learning complex patterns

#### Tanh

Used because:
Input images are normalized to [-1,1]