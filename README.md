# Face Anonymizer

Privacy-first image and video anonymization using OpenCV and a simple Flask web UI.

## Quick Start (Windows)

1. Install Python 3 (if you don’t have it yet).
2. Install ffmpeg and make sure `ffmpeg` is on your PATH (needed for video audio).
3. In this folder, create and activate a virtual environment and install deps:

```bash
py -m venv .venv
.\.venv\Scripts\pip.exe install -r requirements.txt
```

4. Run the web app:

```bash
.\.venv\Scripts\python.exe web_app.py
```

5. Open http://127.0.0.1:5000/ and:
   - Upload an image or video
   - Choose anonymization method (blur, pixelate, black bar)
   - Adjust intensity
   - Download the anonymized result

## Notes
- All processing happens locally; nothing is uploaded to external servers.
- Large or unsupported video codecs may fail with a clear error toast.
- If ffmpeg is missing or not on PATH, video anonymization will still work but the output video will not contain audio.

## Requirements
- Python 3.x
- OpenCV (installed via `opencv-python-headless` in `requirements.txt`)
- NumPy
- Flask
- ffmpeg (for preserving audio in anonymized videos)
