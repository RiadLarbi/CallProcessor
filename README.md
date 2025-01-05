# Call Transcriber
A Python-based system that transcribes phone calls with speaker detection, generates summaries, and saves both audio and transcriptions.

## 📋 Features
- Audio call transcription using OpenAI's Whisper
- Speaker diarization (detection of different speakers)
- Call summarization
- Automatic saving of both audio files and transcriptions
- Timestamps and speaker labels in transcriptions
- Detailed call metadata

## 🔧 Project Structure
```
call-transcriber/
├── src/
│   ├── __init__.py
│   ├── processor.py        # Main CallProcessor class
│   └── utils/
│       ├── __init__.py
│       └── audio_utils.py  # Audio processing utilities
├── tests/
│   ├── __init__.py
│   ├── test_processor.py
│   └── test_utils.py
├── examples/
│   └── basic_usage.py
├── call_records/          # Default directory for saved files
│   ├── audio/
│   └── summaries/
├── requirements.txt
├── setup.py
├── README.md
└── .gitignore
```

## 🚀 Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/call-transcriber.git
cd call-transcriber
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Get required authentication:
- Create an account on [HuggingFace](https://huggingface.co/)
- Accept the user agreement for [pyannote/speaker-diarization](https://huggingface.co/pyannote/speaker-diarization)
- Get your access token from [HuggingFace settings](https://huggingface.co/settings/tokens)

## 📖 Usage

Basic usage example:
```python
from src.processor import CallProcessor

# Initialize with HuggingFace token
processor = CallProcessor(auth_token="your_huggingface_token")

# Process a call
success = processor.process_call("path/to/your/audio.wav")
```

## 🔑 Requirements
- Python 3.8+
- PyTorch
- OpenAI Whisper
- pyannote.audio
- transformers

## 📝 License
MIT License
