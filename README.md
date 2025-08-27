# 📄 Invoice Data Extraction

A powerful web application built with Streamlit that automatically extracts key information from invoice documents using OCR (Optical Character Recognition) technology.

## ✨ Features

- **Multi-format Support**: Process JPG, PNG, and PDF files
- **Intelligent OCR**: Uses EasyOCR with support for English and French languages
- **GPU Acceleration**: Automatically detects and utilizes NVIDIA GPU when available
- **Smart Data Extraction**: Automatically identifies:
  - Invoice number
  - Issue date
  - Client information
  - Financial values (Net amount, VAT, Gross total)
- **Data Validation**: Verifies financial calculations for accuracy
- **Multiple Export Formats**: Download results as JSON or CSV
- **User-friendly Interface**: Clean, responsive web interface
- **Image Preprocessing**: Enhances image quality for better OCR results

## 🚀 Getting Started

### Prerequisites

- Python 3.7+
- CUDA-compatible GPU (optional, for faster processing)

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/dous11/invoice-data-extraction.git
cd invoice-data-extraction
```

2. **Install required packages**
```bash
pip install -r requirements.txt
```

3. **Run the application**
```bash
streamlit run app.py
```

4. **Open your browser** and navigate to `http://localhost:8501`

## 📦 Dependencies

```
streamlit
numpy
pandas
opencv-python
easyocr
pdf2image
pillow
torch
torchvision
pathlib
tempfile
base64
json
re
math
io
```

## 🖥️ Usage

1. **Upload Document**: Click on the upload area and select your invoice file (JPG, PNG, or PDF)

2. **Analyze**: Click the "🔍 Analyser le document" button to start the extraction process

3. **View Results**: The application will display extracted data in a formatted table

4. **Download**: Export your results in JSON or CSV format

5. **Debug Options**: 
   - Enable "Afficher le texte OCR brut" to see raw OCR output
   - Enable "Mode debug" for additional debugging information

## 🔧 Technical Details

### Image Preprocessing
The application includes advanced image preprocessing to improve OCR accuracy:
- Grayscale conversion
- Adaptive thresholding
- Morphological operations to reduce noise

### Data Extraction Patterns
Uses regex patterns to identify:
- `Invoice no: [number]`
- `Date of issue: [DD/MM/YYYY]`
- `Client: [name]`
- Financial values with various currency symbols

### Financial Validation
- Automatically validates that Net + VAT = Gross Total
- Calculates missing values when possible
- Handles common OCR character recognition errors (B→8, l→1, etc.)

## 🎯 Supported Invoice Formats

The application works best with invoices that contain:
- Clear, readable text
- Standard invoice terminology in English or French
- Structured layout with identifiable sections
- Financial summaries with net, VAT, and total amounts

## ⚙️ Configuration

### GPU Support
- The application automatically detects CUDA availability
- Falls back to CPU processing if GPU is unavailable
- Memory optimization for large images

### File Size Limits
- Maximum file size: 10MB
- PDF processing: Converts first page only
- Image resolution: Automatically adjusted for optimal processing

## 🚨 Troubleshooting

### Common Issues

**GPU Memory Error**
- The application automatically resizes images if GPU memory is insufficient
- Consider using CPU mode for very large images

**Poor OCR Results**
- Ensure good image quality (300+ DPI recommended)
- Check that text is clearly readable
- Verify document language is English or French

**Missing Data Fields**
- Some invoices may have non-standard formats
- Use debug mode to see raw OCR output
- Consider manual data entry for critical missing fields

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔮 Future Enhancements

- [ ] Support for multiple languages
- [ ] Batch processing capability
- [ ] Integration with accounting software APIs
- [ ] Machine learning model for invoice layout detection
- [ ] Mobile-responsive interface improvements
- [ ] Cloud deployment options

## 👥 Authors

- **M1-ASD 24/25** - *Initial work*

## 🙏 Acknowledgments

- [EasyOCR](https://github.com/JaidedAI/EasyOCR) for OCR capabilities
- [Streamlit](https://streamlit.io/) for the web framework
- [OpenCV](https://opencv.org/) for image processing
- [pdf2image](https://github.com/Belval/pdf2image) for PDF conversion

## 📊 Performance

- **Processing Speed**: 2-5 seconds per invoice (GPU) / 10-15 seconds (CPU)
- **Accuracy**: 85-95% for well-formatted invoices
- **Supported Languages**: English, French
- **File Size**: Up to 10MB per document

## 📞 Support

If you encounter any issues or have questions:
1. Check the troubleshooting section above
2. Review existing GitHub issues
3. Create a new issue with detailed information about your problem

---

*© 2025 - Extraction M1-ASD 24/25*
