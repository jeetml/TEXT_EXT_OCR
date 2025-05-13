# 📛 Image Text Extractor using PaddleOCR

This project is designed to extract textual information from images—such as invoices, receipts, or scanned documents—and save the results into a CSV file. It uses **PaddleOCR** for highly accurate Optical Character Recognition and optionally displays the results as an annotated image.

---

## 📌 Features

* Extracts text from image files using `PaddleOCR`.
* Displays each extracted text line along with confidence scores.
* Saves extracted text into a `.csv` file.
* Generates an annotated image with bounding boxes around the detected text.

---

## 🔧 Installation

Install the required dependencies:

```bash
pip install paddleocr layoutparser opencv-python matplotlib paddlepaddle pytesseract
```

> ℹ️ Note: Table detection uses `layoutparser` with Detectron2 but this README focuses only on the text extraction component.

---

## 📁 Input

Replace the `image_path` variable in the code with the path to your image:

```python
image_path = "hdfc.png"  # Replace this with your own image path
```

The supported formats include PNG, JPG, JPEG, etc.

---

## 🚀 How It Works

1. **Load Image**: The image is read and converted from BGR to RGB.
2. **OCR Inference**: The `PaddleOCR` model detects text boxes and performs text recognition with orientation classification.
3. **Text Extraction**: The recognized text and its confidence score are stored.
4. **Save to CSV**: If layout parsing fails or is not used, all extracted text is saved to a CSV file called `invoice_extracted_text.csv`.
5. **Annotated Output**: An image (`invoice_annotated.png`) is generated showing the bounding boxes and recognized text.

---

## 📂 Output

* `invoice_extracted_text.csv`: A CSV file containing all the recognized text.
* `invoice_annotated.png`: The original image annotated with red bounding boxes and blue text.

---

## 🖼️ Sample Output

**Console Output**

```
🔹 Extracted Text from Invoice:
HDFC BANK LIMITED (Confidence: 0.98)
Account Statement (Confidence: 0.96)
...
```

**CSV Format**

```csv
text
HDFC BANK LIMITED
Account Statement
...
```

**Annotated Image**
A visual representation with bounding boxes and labels.

---

## ✅ Example Use Cases

* Extracting invoice details for bookkeeping.
* Digitizing scanned printed documents.
* Preprocessing for NLP analysis.

---

## 💡 Note

This README intentionally **excludes** any explanation related to table extraction. If you want to use layout detection and table parsing, that part of the code can be enhanced separately.

---

## 📬 Contact

Created by Jeet Patel.
For queries or contributions, feel free to reach out or fork the repo!
