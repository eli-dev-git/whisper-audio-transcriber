# Whisper Audio Transcriber

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME/blob/main/Whisper_Audio_Transcriber.ipynb)

A simple open-source audio transcription tool powered by **OpenAI Whisper** and **Google Colab**.

Upload an audio file, let Whisper transcribe it, and automatically download a `.txt` transcript using the **same base filename** as the original audio.

> Example: `Middleton Rd 7 2.m4a` → `Middleton Rd 7 2.txt`

---

## Start Transcribing

Click the button below:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME/blob/main/Whisper_Audio_Transcriber.ipynb)

Then:

1. In Colab, select **Runtime → Change runtime type → T4 GPU** if available.
2. Run the installation cell.
3. Run the GPU-check cell.
4. Run the transcription cell.
5. Upload your audio file.
6. Watch the timestamped transcription progress.
7. Download your transcript automatically when processing finishes.

No local Python installation is required.

---

## Features

- Runs entirely in Google Colab
- No local Python setup required
- Supports MP3, M4A, WAV, MP4, and other FFmpeg-compatible formats
- Automatically preserves the original audio filename
- Downloads the finished transcript as `.txt`
- Shows timestamped transcription output while Whisper is working
- Reports total processing time
- Supports Colab GPU acceleration
- Easy to fork, modify, and redistribute
- Open source under the MIT License

---

## Example

Upload:

```text
VoiceOver School_2_2.mp3
```

The notebook automatically creates:

```text
VoiceOver School_2_2.txt
```

Another example:

```text
Middleton Rd 7 2.m4a
```

becomes:

```text
Middleton Rd 7 2.txt
```

You do not need to edit the filename in the code.

---

## Whisper Model

The notebook uses the `base` Whisper model by default:

```python
MODEL_NAME = "base"
```

You can change it to:

| Model | Speed | Accuracy | Compute |
|---|---|---|---|
| `tiny` | Fastest | Lower | Very low |
| `base` | Fast | Good | Low |
| `small` | Moderate | Better | Moderate |
| `medium` | Slower | High | Higher |
| `large` | Slowest | Highest | High |

For most users, `base` is a good starting point.

If you have access to a Colab T4 GPU and want better transcription quality, try:

```python
MODEL_NAME = "small"
```

---

## GPU Acceleration

For long recordings, enable a GPU in Google Colab:

**Runtime → Change runtime type → T4 GPU → Save**

The notebook includes a GPU check:

```python
import torch

print("GPU available:", torch.cuda.is_available())

if torch.cuda.is_available():
    print("GPU:", torch.cuda.get_device_name(0))
```

A successful GPU result may look like:

```text
GPU available: True
GPU: Tesla T4
```

If the notebook runs on CPU, transcription will still work, but it can take much longer.

---

## Supported Audio

Whisper uses FFmpeg, so common formats include:

- `.mp3`
- `.m4a`
- `.wav`
- `.mp4`
- `.mpeg`
- `.mpga`
- `.webm`

Other FFmpeg-compatible audio formats may also work.

---

## How It Works

```text
GitHub
   ↓
Open notebook in Google Colab
   ↓
Upload audio
   ↓
Whisper transcribes the recording
   ↓
Transcript keeps the original filename
   ↓
Download .txt
```

GitHub hosts the open-source notebook.

Google Colab provides the Python environment and CPU/GPU resources when each user runs it.

This means the repository owner does **not** need to operate a transcription server for every user.

---

## Privacy

The audio file is uploaded into the user's Google Colab runtime for processing.

This project does not include a separate backend server or database.

Users should still review Google's Colab privacy practices and avoid uploading sensitive recordings unless they are comfortable processing them in that environment.

---

## Requirements

Users only need:

- A web browser
- A Google account for Google Colab
- An audio file

No local Python installation is necessary.

---

## Repository Setup

After uploading these project files to GitHub, edit the two Colab button links in this README.

Replace:

```text
YOUR_GITHUB_USERNAME
```

with your GitHub username.

Replace:

```text
YOUR_REPOSITORY_NAME
```

with your repository name.

For example, if your GitHub username were:

```text
janedoe
```

and your repository were:

```text
whisper-audio-transcriber
```

the Colab URL would become:

```text
https://colab.research.google.com/github/janedoe/whisper-audio-transcriber/blob/main/Whisper_Audio_Transcriber.ipynb
```

After that change, the **Open in Colab** button will take users directly from your GitHub README into the working notebook.

---

## Project Files

```text
Whisper_Audio_Transcriber.ipynb
README.md
LICENSE
.gitignore
```

---

## Contributing

Contributions are welcome.

You can fork the repository, improve the notebook, fix bugs, add features, and submit a pull request.

Potential future improvements include:

- Multiple-file batch transcription
- `.srt` subtitle export
- `.vtt` caption export
- Speaker identification
- Language selection
- Translation
- Transcript cleanup
- Automatic summaries

---

## License

This project is released under the **MIT License**.

You are free to use, modify, distribute, and build on it under the terms of the license.
