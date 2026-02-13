# Song Mashup Generator

A simple command-line app that automatically creates a mashup by:

1. Searching YouTube for a query
2. Downloading multiple results
3. Converting them to MP3
4. Trimming each track to a fixed duration
5. Merging them into a single audio file

Built with Python using yt-dlp and FFmpeg.

---

## Features

- Search-based YouTube audio downloading
- Automatic audio conversion to MP3
- Fixed-length trimming per track
- Batch merging into one mashup file
- Fully automated CLI workflow

---

## How It Works

1. Uses `yt-dlp` to search YouTube with `scsearchN:<query>`
2. Downloads the best available audio format
3. Converts `.opus` or `.ogg` files to `.mp3`
4. Trims each track to a user-defined duration
5. Concatenates all trimmed MP3 files into one final output file

The result is a fast, raw mashup created by stitching audio segments together.

---

## Requirements

- Python 3.8+
- FFmpeg installed and available in PATH
- yt-dlp

Install Python dependency:

```bash
pip install yt-dlp
```

Install FFmpeg:

Mac:

```bash
brew install ffmpeg
```

Ubuntu:

```bash
sudo apt install ffmpeg
```

Windows:
Download from the official FFmpeg website and add it to your PATH.

---

## Usage

```bash
python 102303244.py "search query" N duration output_file_name
```

### Parameters

| Argument           | Description                                                   |
| ------------------ | ------------------------------------------------------------- |
| `search query`     | YouTube search term                                           |
| `N`                | Number of videos to download. Must be greater than 10         |
| `duration`         | Length in seconds to trim each track. Must be greater than 20 |
| `output_file_name` | Final merged MP3 filename                                     |

---

## Example

```bash
python 102303244.py "Boy in Space" 15 30 mashup.mp3
```

This will:

- Download 15 search results
- Trim each to 30 seconds
- Merge them into `mashup.mp3`

---

## Output Structure

```
output/
├── videos/
│   ├── original downloads
├── audio/
│   ├── trimmed mp3 files
│   ├── final merged file
```

Final mashup location:

```
output/audio/<your_output_file_name>
```

---

> [!IMPORTANT]
> N must be greater than 10
> Duration must be greater than 20 seconds

If these constraints are not met, the script will exit.

If no audio files are successfully processed, the script will terminate safely.

---
