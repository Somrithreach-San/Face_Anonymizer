# Face Anonymizer

Privacy-first image and video anonymization using OpenCV and a simple Flask web UI.

## Quick Start

1. Install Python 3.
2. Install ffmpeg and ensure `ffmpeg` is on your PATH (for video audio).
3. Create a virtual environment and install dependencies:

   - Windows (PowerShell):
     ```powershell
     py -m venv .venv
     .\.venv\Scripts\Activate.ps1
     pip install -r requirements.txt
     ```
   - macOS / Linux:
     ```bash
     python3 -m venv .venv
     source .venv/bin/activate
     pip install -r requirements.txt
     ```

4. Run the web app:

   - Windows:
     ```powershell
     python web_app.py
     ```
   - macOS / Linux:
     ```bash
     python3 web_app.py
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
- The web UI uses Tailwind via CDN — no Node or build step is required.

## Requirements
- Python 3.x
- OpenCV (installed via `opencv-python-headless` in `requirements.txt`)
- NumPy
- Flask
- ffmpeg (for preserving audio in anonymized videos)

## CLI (optional)
You can also process videos via the CLI:
```bash
python anonymizer.py process input.mp4 output.mp4 --method blur --intensity 30
# Quick scan without producing a video:
python anonymizer.py probe input.mp4 --max-frames 120
```
