# Pok-mon-CAPTCHA-Solver
This project implements a deep learning-based CAPTCHA solving system
🔍 Convolutional Neural Network (CNN) - Classifies 10 Pokémon species

🧹 Convolutional Autoencoder - Removes image noise

🎨 Data Augmentation - Translation, rotation, and color jittering

The final system can:

  Receive a noisy Pokémon image

  Denoise it using the autoencoder

  Classify the Pokémon species using CNN

  Select the matching image from 9 candidate images

🏗️ Project Architecture
text
├── comp2211_pa2.py          # Main program
├── cnn_model.keras          # Trained CNN classification model
├── auto_encoder.keras       # Trained autoencoder denoising model
├── Pokemon-images.zip       # Original dataset
├── images/                  # Extracted images (includes augmented data)
└── README.md                # Project documentation
🧩 Core Features
1. Data Augmentation
Translation: Random shifts in x/y directions

Rotation: Random angle rotation (-30° ~ 30°)

Color Jittering: Adjust contrast, brightness, and saturation

Goal: Expand each Pokémon class to 200 images

2. CNN Image Classifier
text
Conv2D(32) → MaxPooling → Conv2D(64) → MaxPooling 
→ Flatten → Dense(64) → Dropout(0.5) → Dense(10, softmax)
Input: 64×64×3 RGB images

Output: Probability distribution over 10 Pokémon classes

Accuracy: ~85-95% (depending on hyperparameters)

3. Autoencoder Denoising
text
Encoder: Conv2D(32) → MaxPooling
Decoder: Conv2D(32) → UpSampling → Conv2D(3, sigmoid)
Removes Gaussian noise + Salt-and-pepper noise

Improves CNN classification accuracy on noisy images
