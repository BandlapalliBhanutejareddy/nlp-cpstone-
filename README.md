# Explainable Text Intelligence System

A comprehensive Flask-based web application for advanced text analysis, summarization, and NLP processing. This system provides multiple modules for understanding and processing textual data with detailed insights and visualizations.

## Features

### 📄 Text Input & Processing
- Support for multiple file formats: **TXT**, **PDF**, and **DOCX**
- Direct text input via web interface
- Automatic text extraction and preprocessing

### 📊 Text Summarization
- Intelligent sentence importance ranking using TF-IDF vectorization
- Automated summary generation from top-ranked sentences
- Sentence-level analysis with importance scores, keyword extraction, and length metrics

### 😊 Sentiment Analysis
- Tone detection (Positive, Negative, Neutral)
- Sentiment polarity scoring
- Visual tone indicator in dashboard

### 🏷️ Part-of-Speech (POS) Tagging
- Complete POS tag analysis
- Distribution visualization with bar charts
- Grouped word tagging for linguistic analysis

### 🌳 Parse Tree Generation
- Constituency parsing with custom grammar rules
- Hierarchical sentence structure visualization
- Semantic unit extraction (NP, VP, PP, S)

### 🎯 Named Entity Recognition (NER)
- Automatic extraction of proper nouns and named entities
- Entity-based text analysis
- Integration with summarization pipeline

### 🌐 Multi-Language Translation
- Real-time translation to 100+ languages
- Semantic similarity scoring between original and translated text
- Translation history tracking

### 🔊 Text-to-Speech
- Native language audio generation
- Support for multiple languages
- Audio playback in browser

### 📈 Comprehensive Dashboard
- Real-time analytics and metrics
- POS tag distribution charts
- Tonality and confidence scoring
- Summary statistics and insights

### 📋 Report Generation
- PDF report export with full analysis
- Includes original text, summary, translations, and visualizations
- Professional formatting with charts and statistics

## Installation

### Prerequisites
- Python 3.8+
- pip

### Setup

1. **Clone or download the project:**
   ```bash
   cd t5_summarizer
   ```

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv venv
   venv\Scripts\activate  # On Windows
   # or
   source venv/bin/activate  # On macOS/Linux
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **NLTK Data Download:**
   The application automatically downloads required NLTK packages on first run:
   - `punkt` (tokenizer)
   - `averaged_perceptron_tagger` (POS tagger)
   - `stopwords` (common words list)

## Usage

### Running the Application

1. **Start the Flask server:**
   ```bash
   python app.py
   ```

2. **Access the web interface:**
   - Open your browser and navigate to `http://localhost:5000`

### Workflow

1. **Module 0 - Text Input**
   - Enter text directly or upload a file (TXT, PDF, DOCX)
   - Click "Analyze" to process

2. **Module 1 - Analysis**
   - View sentence importance rankings
   - See tone analysis and top-ranked sentences
   - Explore parse tree structure

3. **Module 2 - Translation**
   - Select a language for translation
   - View translated summary
   - Check semantic similarity score
   - Explore extracted entities

4. **Dashboard**
   - Comprehensive overview of all analyses
   - POS tag distribution chart
   - Tone and confidence metrics
   - Download PDF report

## Technical Stack

- **Backend:** Flask (Python web framework)
- **NLP Libraries:** NLTK, TextBlob, scikit-learn
- **File Processing:** PyPDF2, python-docx
- **Translation:** Google Translate API (googletrans)
- **Visualization:** Matplotlib, Graphviz
- **Text-to-Speech:** gTTS
- **Report Generation:** ReportLab
- **Frontend:** HTML5, CSS3, JavaScript

## API Endpoints

| Route | Method | Description |
|-------|--------|-------------|
| `/` | GET, POST | Home page - text input and file upload |
| `/analysis` | GET | Sentence analysis and parsing results |
| `/translation` | GET, POST | Multi-language translation interface |
| `/dashboard` | GET | Comprehensive analytics dashboard |
| `/speak_native` | GET | Text-to-speech audio generation |
| `/download_report` | GET | Generate and download PDF report |

## File Structure

```
t5_summarizer/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── README.md             # This file
├── templates/            # HTML templates
│   ├── base.html
│   ├── module0.html      # Input module
│   ├── module1.html      # Analysis module
│   ├── module2.html      # Translation module
│   └── dashboard.html    # Dashboard
├── static/               # Static assets
│   └── style.css
├── fonts/                # Font files
└── uploads/              # Temporary file uploads
```

## Configuration

The application runs in debug mode by default. For production, modify the last line in `app.py`:

```python
if __name__ == "__main__":
    app.run(debug=False)  # Set to False for production
```

## Troubleshooting

**Issue:** NLTK data not found
- **Solution:** The app automatically downloads on first run. If issues persist, manually run:
  ```python
  import nltk
  nltk.download('punkt')
  nltk.download('averaged_perceptron_tagger')
  nltk.download('stopwords')
  ```

**Issue:** Graphviz not found
- **Solution:** Install Graphviz from https://graphviz.org/download/

**Issue:** Google Translate API errors
- **Solution:** Check internet connection; rate limiting may apply with heavy usage

## License

This project is provided as-is for educational and research purposes.

## Author

Created as an Explainable AI and NLP learning project.

---

**Last Updated:** February 2026
