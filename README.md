# Exif Remover

**Exif Remover** is a privacy-focused forensics tool designed to "sanitize" image files by stripping away all hidden metadata. By recreating the image using only raw pixel data, it ensures that sensitive information like GPS coordinates, camera serial numbers, and timestamps are permanently removed to prevent OSINT tracking.

---

## 🛡️ Features
* **Full Metadata Stripping**: Moves beyond just deleting tags by rebuilding the image from raw pixel data.
* **OSINT Prevention**: Designed specifically to neutralize tracking vectors in digital investigations.
* **Format Preservation**: Maintains the original image mode and dimensions while purging hidden data.
* **Verification Ready**: Built to work alongside `exif-extractor.py` for easy sanitization audits.

## 🛠️ Prerequisites
This tool requires the **Pillow** library for image manipulation.

```bash
pip install Pillow
```

## 📋 Usage
1. **Download** the `exif-remover.py` script.
2. **Configure your paths**: Update the `image_path` (source) and `output_path` (cleaned file) variables in the script.
   ```python
   # Define the input and output paths
   image_path = "your_image.png"
   output_path = "cleaned_your_image.png"
   ```
3. **Run the sanitizer**:
   ```bash
   python exif-remover.py
   ```

## 🔍 How it Works
Unlike standard editors that might leave "ghost" metadata, this tool performs a deep clean:
1. It extracts the raw **pixel data** (the actual colors of the image).
2. It initializes a **completely new image object** with the same dimensions and mode.
3. It maps the pixel data onto the new object and saves it, effectively leaving the metadata header behind.

## 👤 Author
* **Yel1oww**
* **Version**: 1.0

## ⚖️ License
This project is intended for privacy protection and ethical use. Always maintain backups of your original files before sanitization.
