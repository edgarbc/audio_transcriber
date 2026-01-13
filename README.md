# Audio Transcriber

An audio transcription web application that leverages OpenAI's Whisper model to convert audio files into text with high accuracy.

## Overview

Audio Transcriber is a modern web application designed to make audio transcription simple and accessible. The application features:

- **Backend**: FastAPI-based REST API for handling audio processing and transcription
- **Frontend**: FastHTML-based user interface for intuitive interaction
- **Transcription Engine**: OpenAI Whisper for accurate speech-to-text conversion
- **Architecture**: Spec-driven development approach ensuring well-documented and maintainable code

## Project Objective

The goal of this project is to provide a user-friendly web application that allows users to:

1. Upload audio files in various formats (MP3, WAV, etc.)
2. Transcribe audio content using OpenAI's Whisper model
3. View transcription results in a scrollable output area
4. Download transcription results as text files
5. Process audio files locally without requiring cloud services

## Current Status

**Note**: The project is currently in the planning and specification phase. The existing Jupyter notebook (`my_audio_transcriber_whisper.ipynb`) serves as a proof of concept for the transcription functionality using Google Colab.

## Planned Repository Structure

```
audio_transcriber/
├── backend/                    # FastAPI backend application
│   ├── app/
│   │   ├── __init__.py
│   │   ├── main.py            # FastAPI application entry point
│   │   ├── api/               # API endpoints
│   │   ├── models/            # Data models
│   │   ├── services/          # Business logic (transcription service)
│   │   └── utils/             # Utility functions
│   ├── requirements.txt       # Python dependencies
│   └── README.md             # Backend-specific documentation
│
├── frontend/                   # FastHTML frontend application
│   ├── app/
│   │   ├── __init__.py
│   │   ├── main.py            # Frontend entry point
│   │   ├── components/        # Reusable UI components
│   │   ├── pages/             # Application pages
│   │   └── static/            # Static assets (CSS, JS)
│   ├── requirements.txt       # Python dependencies
│   └── README.md             # Frontend-specific documentation
│
├── docs/                       # Project documentation
│   ├── spec/                  # Specifications
│   │   ├── agents.md          # Agent and task descriptions
│   │   └── architecture.md    # System architecture
│   ├── api/                   # API documentation
│   └── user-guide.md          # End-user documentation
│
├── tests/                      # Test suite
│   ├── backend/               # Backend tests
│   └── frontend/              # Frontend tests
│
├── scripts/                    # Utility scripts
│   └── setup.sh               # Setup and installation script
│
├── my_audio_transcriber_whisper.ipynb  # Original PoC notebook
├── LICENSE                     # Project license
└── README.md                   # This file
```

## Features

### Supported Features (Planned)

- **File Upload**: Support for multiple audio file formats (MP3, WAV, M4A, FLAC, OGG)
- **Audio Transcription**: High-quality speech-to-text using OpenAI Whisper
- **Multiple Model Support**: Choice of Whisper model sizes (tiny, base, small, medium, large)
- **Scrollable Output**: View transcription results in an easy-to-read format
- **Download Results**: Export transcriptions as text files
- **Progress Tracking**: Real-time feedback during transcription
- **Error Handling**: Clear error messages and recovery options

### Current Implementation

The existing Jupyter notebook demonstrates:
- Loading audio files from Google Drive
- Audio file slicing for large files
- Transcription using Whisper base model
- Saving transcriptions to text files
- Basic Gradio interface example

## Setup and Running Instructions

### Prerequisites

- Python 3.8 or higher
- FFmpeg (required by Whisper for audio processing)
- GPU support recommended for faster transcription (optional)

### Installation

**Note**: The following instructions will be applicable once the web application is implemented.

1. **Clone the repository**:
   ```bash
   git clone https://github.com/edgarbc/audio_transcriber.git
   cd audio_transcriber
   ```

2. **Install FFmpeg** (if not already installed):
   - Ubuntu/Debian: `sudo apt-get install ffmpeg`
   - macOS: `brew install ffmpeg`
   - Windows: Download from [ffmpeg.org](https://ffmpeg.org/download.html)

3. **Set up virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

4. **Install dependencies**:
   ```bash
   # Backend dependencies
   pip install -r backend/requirements.txt
   
   # Frontend dependencies
   pip install -r frontend/requirements.txt
   ```

### Running the Application

**Backend**:
```bash
cd backend
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

**Frontend**:
```bash
cd frontend
python app/main.py
```

Access the application at `http://localhost:8000` (or the configured port).

### Using the Current Notebook

To use the existing Jupyter notebook:

1. Open in Google Colab: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/edgarbc/audio_transcriber/blob/main/my_audio_transcriber_whisper.ipynb)

2. Mount your Google Drive (where audio files are stored)

3. Update the `data_dir` and `sound_file` variables with your file paths

4. Run the cells sequentially

## Development Approach

### Spec-Driven Development

This project follows a specification-driven development approach:

1. **Requirements Gathering**: Clear feature specifications are documented before implementation
2. **Agent-Based Tasks**: Development tasks are broken down and assigned to specialized agents
3. **Documentation First**: API contracts and interfaces are defined before coding
4. **Iterative Development**: Features are built incrementally with continuous testing

For more details on the development methodology and agent assignments, see [docs/spec/agents.md](docs/spec/agents.md) (to be created).

## Project Management

### Issues and Tasks

- **GitHub Issues**: Track bugs, feature requests, and enhancements at [github.com/edgarbc/audio_transcriber/issues](https://github.com/edgarbc/audio_transcriber/issues)
- **Project Board**: View development progress on the [GitHub Projects board](https://github.com/edgarbc/audio_transcriber/projects)
- **Milestones**: Major releases and feature sets are organized into milestones

### Agent Assignments

Development tasks are distributed among specialized agents based on expertise:
- Backend development agents
- Frontend/UI agents
- Testing and QA agents
- Documentation agents

Detailed agent roles and current assignments can be found in the [Agent Specification](docs/spec/agents.md) (to be created).

## Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [OpenAI Whisper](https://github.com/openai/whisper) for the transcription model
- [FastAPI](https://fastapi.tiangolo.com/) for the backend framework
- [FastHTML](https://fastht.ml/) for the frontend framework

## Contact

Edgar Bermudez - edgar.bermudez@gmail.com

Project Link: [https://github.com/edgarbc/audio_transcriber](https://github.com/edgarbc/audio_transcriber)

---

**Status**: 🚧 Under Development - Transitioning from notebook to web application
