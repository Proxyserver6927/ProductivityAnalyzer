# Meeting Productivity Analyzer

A sophisticated application that analyzes how well meetings align with specified agendas by processing video, audio, or text inputs.

![Meeting Productivity Analyzer](https://img.shields.io/badge/Meeting-Productivity%20Analyzer-4361ee)
![Python](https://img.shields.io/badge/Python-3.11+-blue)
![Flask](https://img.shields.io/badge/Flask-3.1.0-green)
![Whisper](https://img.shields.io/badge/OpenAI-Whisper-orange)

## Overview

This Meeting Productivity Analyzer helps teams improve their meeting efficiency by quantifying how closely discussions adhere to predefined agenda topics. The application:

- Accepts video, audio, or text inputs of meetings
- Transcribes audio/video content using OpenAI's Whisper AI
- Analyzes the transcribed or uploaded text against specified agenda topics using NLP
- Provides detailed visual analytics with similarity metrics
- Generates comprehensive reports available for download

## Features

- **Multi-format Input**: Upload video (MP4, AVI, MOV), audio files (MP3, WAV, M4A), or direct text transcripts (TXT, DOCX)
- **Advanced NLP Analysis**: Measures content alignment with agenda topics
- **Interactive Dashboard**: Visualize and explore analysis results
- **Detailed Reports**: Generate and download analysis reports as Word documents
- **Visual Analytics**: View distribution charts, pie charts, and word clouds
- **Collapsible Sections**: Easily navigate through analysis results
- **Responsive Design**: Works seamlessly across devices

## Technology Stack

- **Backend**: Python, Flask
- **Frontend**: HTML, CSS, JavaScript, Chart.js, Wordcloud2.js
- **Speech Recognition**: OpenAI Whisper
- **NLP**: Sentence Transformers
- **ML**: scikit-learn (KMeans clustering for threshold determination)
- **Document Processing**: python-docx
- **Video/Audio Processing**: MoviePy

## Installation

### Prerequisites

- Python 3.11 or higher
- FFmpeg (required for video/audio processing)

### Setup Instructions

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd ProductivityAnalyzer
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows, use `.venv\Scripts\activate`
   ```

3. Install the required dependencies:
   ```bash
   pip install flask python-dotenv moviepy==1.0.3 python-docx scikit-learn numpy sentence-transformers
   ```

   For Whisper installation, install directly from GitHub:
   ```bash
   pip install git+https://github.com/openai/whisper.git
   ```

4. Install FFmpeg (if not already installed):
   - **macOS**: `brew install ffmpeg`
   - **Ubuntu/Debian**: `sudo apt install ffmpeg`
   - **Windows**: Download from [FFmpeg website](https://ffmpeg.org/download.html)

5. Create an upload directory:
   ```bash
   mkdir -p Uploads
   ```

## Running the Application

1. Start the Flask application:
   ```bash
   python APP.PY
   ```
   
   Note: The main app file is named `APP.PY` (uppercase).

2. Open your web browser and navigate to:
   ```
   http://127.0.0.1:5000
   ```

## Usage Guide

1. **Dashboard**: The landing page provides an overview and access to all features
2. **New Analysis**: 
   - Upload a video, audio, or text file
   - Enter the agenda topics for analysis
   - Submit for processing
3. **Results Page**:
   - View the overall alignment score
   - Explore visual analytics (distribution chart, pie chart, word cloud)
   - Review aligned and non-aligned content
   - Download the detailed report

## Project Structure

```
ProductivityAnalyzer/
├── APP.PY                 # Main Flask application (uppercase)
├── templates/             # HTML templates
│   ├── index.html         # Main landing page
│   ├── dashboard.html     # Dashboard page
│   ├── analyze.html       # Analysis form page
│   └── results.html       # Analysis results page
├── Uploads/               # Storage for uploaded files
├── Vid_1.mp4              # Sample video file
├── alignment_report.docx  # Sample report
└── .venv/                 # Virtual environment
```

## Dependencies

- Flask: Web framework
- MoviePy (1.0.3): Video processing
- OpenAI Whisper: Speech recognition
- NumPy: Numerical operations
- scikit-learn: Machine learning for threshold determination
- Sentence Transformers: NLP for similarity analysis
- python-docx: Document generation
- python-dotenv: Environment management
- Chart.js: Frontend visualizations
- Wordcloud2.js: Word cloud generation

## Known Issues and Limitations

- Processing large video files may take significant time
- Currently supports English language analysis only
- Requires FFmpeg installed on the system for video/audio processing
- Analysis results are stored in memory and will be lost when the server restarts

## Security Notes

- Change the app secret key in production
- Configure proper file size limits based on your server capacity
- Implement user authentication for multi-user deployments

## License

[MIT License](LICENSE)

## Acknowledgements

- [OpenAI Whisper](https://github.com/openai/whisper)
- [Sentence Transformers](https://www.sbert.net/)
- [scikit-learn](https://scikit-learn.org/)
- [Chart.js](https://www.chartjs.org/)
- [WordCloud2.js](https://github.com/timdream/wordcloud2.js)
