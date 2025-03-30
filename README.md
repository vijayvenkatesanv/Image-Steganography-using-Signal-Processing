# Image Steganography using Signal Processing

## 📝 Overview
This project implements image steganography using signal processing techniques, specifically Discrete Wavelet Transform (DWT) and Singular Value Decomposition (SVD). It enables hiding a secret image within a cover image and later extracting it securely.

## 🔄 Process

### 1️⃣ Reading and Preprocessing Images
- The cover image and the secret image to be hidden are loaded.
- Images are converted to RGB format for processing.

### 2️⃣ Discrete Wavelet Transform (DWT)
- The cover and secret images undergo DWT to extract four coefficient matrices:
  - Approximation (cA)
  - Horizontal Detail (cH)
  - Vertical Detail (cV)
  - Diagonal Detail (cD)
- This process is applied to each RGB channel separately.

### 3️⃣ Singular Value Decomposition (SVD)
- SVD is performed on the approximation coefficient (cA) of both cover and secret images.
- It decomposes the matrix into three components:
  - Left singular vectors (P)
  - Singular values (D)
  - Right singular vectors (Q)

### 4️⃣ Embedding the Secret Image
- A scaling factor is used to embed the secret image’s singular values (D1) into the cover image’s singular values (D).
- The modified singular values are reconstructed back into an image using inverse SVD.
- This forms a new approximation coefficient (cA) containing the hidden data.

### 5️⃣ Inverse DWT to Generate Stego Image
- The modified cA, along with unchanged detail coefficients (cH, cV, cD), undergo inverse DWT.
- The result is a steganographic image visually similar to the cover image but containing hidden information.

### 6️⃣ Decoding Process
- The receiver applies DWT to extract coefficients from the stego image.
- SVD is performed on the approximation coefficient (cA) to retrieve singular values.
- The secret image is reconstructed by subtracting the original cover image’s singular values from the stego image’s singular values.
- Inverse DWT is applied to fully reconstruct the secret image.

## 🔒 Security Measures
- Password authentication ensures only authorized users can decode the hidden image.

## 🛠️ Tools & Libraries Used
- Python
- OpenCV
- NumPy
- PyWavelets (pywt)
- Matplotlib

## 💡 Applications
- 🔐 Secure transmission of confidential images
- 🌊 Digital watermarking
- 🕵️ Stealth communication

## 🚀 Future Improvements
- Implement encryption before embedding for enhanced security.
- Optimize computation for large image processing.


