# Visual Cryptography in TouchDesigner

## Component 1: Blending

Using Blending to learn the concepts of Visual Encryption

## Component 2: Encryption Algorithm

This project implements a real-time visual cryptography system in TouchDesigner using GLSL. It encrypts a black-and-white image into two visually noisy shares:

- **Share A (OTP)**: A one-time pad composed of random 2×2 pixel patterns
- **Share B (Cipher)**: The encrypted output that uses the same or inverted pattern depending on the input image's pixel value

When perfectly overlaid, the two shares reveal the original image. Any misalignment results in pure noise, preserving the secrecy of the original content.

## 🔧 Features
- Pixel-perfect 2×2 block encryption
- Supports white-on-black input images
- Noise-based randomization via `iTime` uniform
- Dynamic regeneration of the OTP and Cipher every second
- Clean reveal using standard `Minimum` blend mode in TouchDesigner

## 💻 How to Use
1. Input a black-and-white image (mono, 8-bit fixed, no anti-aliasing).
2. Feed it into the provided GLSL TOP.
3. The output is a side-by-side image:
   - Left half: OTP
   - Right half: Cipher
4. Use `Crop TOP` to split the image into two shares.
5. Overlay the two using `Composite TOP → Operation: Minimum`.
6. Align perfectly to reveal the hidden image.

## 🧪 Controls
- `iTime` (float): Drives time-based pattern changes (e.g., updates every second).
- Optional: Use a slider to manually shift shares — message only appears at exact alignment.

## 📦 Dependencies
- TouchDesigner 2022.20000 or newer
- GLSL TOP (2D texture input)
- `8-bit fixed (Mono)` pixel format recommended

## 📄 License
MIT License — use freely with attribution.

---

