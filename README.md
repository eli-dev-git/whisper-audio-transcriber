# Whisper Audio Transcriber

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/eli-dev-git/whisper-audio-transcriber/blob/main/Whisper_Audio_Transcriber.ipynb)

A simple open-source audio transcription tool powered by **OpenAI Whisper** and **Google Colab**.

Upload one or multiple audio files, transcribe them with Whisper, and automatically download matching `.txt` transcripts.

## Batch transcription

Example uploads:

```text
File 1.m4a
File 2.mp3
File 3.wav
```

Outputs:

```text
File 1.txt
File 2.txt
File 3.txt
```

All completed transcripts are packaged into:

```text
transcripts.zip
```

## How to use

1. Click **Open in Colab**.
2. Optionally choose **Runtime → Change runtime type → T4 GPU**.
3. Run the installation cell.
4. Run the GPU-check cell.
5. Run the transcription cell.
6. Select one or multiple audio files.
7. Whisper transcribes each file.
8. Download `transcripts.zip` when the batch completes.

## Why batch processing instead of true parallel processing?

This notebook processes multiple files one after another using the same loaded Whisper model.

On a single Colab T4 GPU, running many Whisper jobs simultaneously can exhaust GPU memory and may reduce performance. Batch processing is more reliable while still letting users upload many files at once.

## Features

- No local Python installation required
- Runs in Google Colab
- Upload one or multiple audio files
- Supports common formats such as MP3, M4A, WAV, MP4, and WebM
- Preserves the original base filename
- Creates one `.txt` transcript per audio file
- Packages all transcripts into one ZIP file
- Shows timestamped transcription output
- Reports per-file processing time
- Reports total batch processing time
- Continues processing if one file fails
- Supports Colab GPU acceleration
- Open source under the MIT License

## Whisper model

The notebook uses:

```python
MODEL_NAME = "base"
```

You can change it to `tiny`, `small`, `medium`, or `large`.
[![Watch the demo video](https://img.youtube.com/vi/PQQEAOUaRd8/hqdefault.jpg)](https://www.youtube.com/watch?v=PQQEAOUaRd8)


## License

MIT
