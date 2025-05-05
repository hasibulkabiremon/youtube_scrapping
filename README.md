# YouTube Video Info Downloader

This script downloads video information, comments, and thumbnails from a specified YouTube video using `yt-dlp`.

## Features
- Extracts video metadata and comments.
- Downloads video thumbnails.
- Formats and saves the data in a structured JSON format.

## Requirements
- Python 3.x
- `yt-dlp` package

## Setup
1. **Create a Virtual Environment**:
   ```bash
   python3 -m venv yt_env
   source yt_env/bin/activate
   ```

2. **Install Required Packages**:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
Run the script to download video information:
```bash
python download_video.py
```

## How It Works
1. **Download Video Info**: The script uses `yt-dlp` to download video metadata and comments without downloading the video itself.
2. **Process Data**: It processes the downloaded data to format timestamps and organize comments into a hierarchical structure.
3. **Save Data**: The formatted data is saved to a JSON file for further analysis or use.

## Subprocess Usage
- The `subprocess` module is a powerful tool in Python that allows you to spawn new processes, connect to their input/output/error pipes, and obtain their return codes.
- In this script, `subprocess.run()` is used to execute the `yt-dlp` command, which is a command-line program for downloading videos and extracting information from YouTube and other video platforms.
- The command executed by `subprocess.run()` includes several options:
  - `--write-thumbnail`: Downloads the video thumbnail.
  - `--skip-download`: Skips downloading the actual video file.
  - `--write-info-json`: Writes video metadata to a JSON file.
  - `--write-comments`: Writes comments to a JSON file.
  - `--output %(id)s`: Sets the output filename template to the video ID.
- This integration allows the script to leverage the capabilities of `yt-dlp` directly from Python, automating the process of extracting video data and comments efficiently.

## Notes
- Ensure `yt-dlp` is installed and accessible in your environment.
- The script is configured to work with a specific YouTube video URL, which can be modified in the script. 