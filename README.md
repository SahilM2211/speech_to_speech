
# Project Title
End-to-End AI Voice Assistance Pipeline

Overview:

This project provides a pipeline that converts an audio file to text using Whisper, generates a response based on the text using a transformer model, and then converts the response back into audio using Edge TTS. The generated audio can then be played directly in your notebook.

Installation:

Before using the project, ensure that the required packages are installed:


pip install git+https://github.com/openai/whisper.git
pip install torch
pip install transformers
pip install pydub
pip install edge-tts
pip install nest_asyncio
pip install ipython



How to Use:

Transcription: Convert your audio file (.m4a) to text using Whisper.

Response Generation: Generate a response from the transcribed text using a "Lamini-Prompt-Enchance-Long" pre-trained transformer model.

Text-to-Speech: Convert the response text into an audio file using Edge TTS.

Audio Playback: Play the generated audio file.

Example:

Here's an example of how to use the pipeline:

1. Transcription:

# Load and transcribe your audio file using Whisper
result = model.transcribe("/path/to/audio/file.m4a")
print(result["text"])


2. Generate a Response:

# Generate a response based on the transcribed text
response_text = generate_response(result["text"])
print("LLM Response:", response_text)


3. Convert to Speech:

# Convert the response text to speech
await text_to_speech(response_text, "output_audio.mp3")

4. Play the Audio:

# Play the generated audio
play_audio("output_audio.mp3")

