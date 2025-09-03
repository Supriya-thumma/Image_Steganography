
# 🖼️ Image Steganography in Python

This project demonstrates **image-based steganography** by encoding and decoding hidden text messages inside PNG images using the **Python PIL (Pillow) library**.  
The program works exclusively with **PNG images** because JPEG compression can distort pixel values and corrupt hidden data.

## 📌 Features
- ✅ Encode secret text messages inside images.
- ✅ Decode hidden text messages from images.
- ✅ Simple command-line interface.
- ✅ Works with any PNG image (supports batch processing).

## 📂 Project Structure
```
├── encrypt/         # Folder containing original images to encode messages
├── decrypt/         # Folder containing images with encoded messages to decode
├── export/          # Folder where encoded images will be saved
├── steganography.py          # Main Python script
```

## ⚙️ Requirements
- Python 3.x
- Pillow (PIL)

Install dependencies:
```
pip install pillow
```

## ▶️ How to Use

### 1. Prepare Folders
- Place original PNG images in the `encrypt/` folder.
- Ensure you have an empty `export/` folder for saving encoded images.
- Place images with hidden messages in the `decrypt/` folder (for decoding).

### 2. Run the Script
```
python main.py
```

### 3. Choose Mode
- Encrypt (e): Encode a secret message into all PNG images in `encrypt/`.
- Decode (d): Decode hidden messages from all PNG images in `decrypt/`.

## 🔍 Example Workflow
Encoding a message:
```
Decode or encrypt? (d/e): e
Enter message to encode: Hello World
Encoded message into [image1.png]
Encoded message into [image2.png]
Finished Encoding images.
```

Decoding a message:
```
Decode or encrypt? (d/e): d
Decoded message from [image1.png]: Hello World
Finished Decoding images.
```

## ⚠️ Important Notes
- This script only works with **PNG images** due to lossless compression.
- Messages that are too long to fit in an image will raise an error.
- End of message is marked using the special sequence **127** in pixel values.

## 🛠️ How It Works
- Each character in the message is converted to its **ASCII code**.
- The ASCII value is split across the last digits of the **RGB channels** of pixels.
- A special marker (`127`) indicates the **end of the message**.
- The encoded image is saved in the `export/` directory.

## 🚀 Future Improvements
- Add **GUI** for better user interaction.
- Support for **JPEG with error correction**.
- Encrypt messages before encoding for **extra security**.

## 📜 License
This project is open-source and available under the **MIT License**.
