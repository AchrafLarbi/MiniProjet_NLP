# Medical Symptom Detection from Speech

A natural language processing project that extracts medical symptoms from speech input, supporting Arabic language detection and translation.

## Project Overview

This project creates an end-to-end pipeline that:
1. Records audio input from users
2. Transcribes speech to text (supporting Arabic)
3. Translates the content to English (if needed)
4. Extracts medical symptoms from the transcribed text
5. Organizes the symptoms into a structured format

## Features

- **Audio Recording**: Capture voice input directly through the application
- **Multilingual Support**: Works with Arabic speech input
- **Speech-to-Text Conversion**: Uses ElevenLabs API for accurate transcription
- **Translation**: Converts Arabic dialect text to English
- **Symptom Extraction**: Identifies medical symptoms from the processed text
- **Structured Output**: Returns symptoms in a clean, organized format

## Technologies Used

- **Python**: Core programming language
- **SoundDevice & SciPy**: Audio recording and processing
- **ElevenLabs API**: Speech-to-text transcription
- **OpenRouter API**: Access to GPT-3.5 Turbo for translation and symptom extraction
- **Regular Expressions**: Cleanup and formatting of extracted symptoms

## Installation

1. Clone this repository
2. Install required packages:

```bash
pip install sounddevice scipy python-dotenv elevenlabs openai
```

3. Create a `.env` file with your API keys:

```
ELEVENLABS_API_KEY=your_elevenlabs_api_key
```

## Usage

The project is implemented as a Jupyter notebook ([speech_to_text.ipynb](speech_to_text.ipynb)) that can be run step by step:

1. **Record Audio**:
   - The system records audio input for a predefined duration (default: 10 seconds)
   - Audio is saved as 'output.wav'

2. **Transcribe Speech**:
   - The ElevenLabs API converts the audio to text
   - Supports Arabic language with word-level timestamps

3. **Translate Content** (if in Arabic):
   - Translates the transcribed text from Arabic dialect to English
   - Uses GPT-3.5 Turbo via OpenRouter API

4. **Extract Symptoms**:
   - Processes the translated text to identify medical symptoms
   - Cleans the output by removing numbering and unnecessary elements
   - Stores extracted symptoms in an array

## Example Workflow

1. User speaks in Arabic: "الضهر يضرني ويوجعني. لا."
2. System transcribes the audio
3. System translates: "My back hurts and causes me pain. No."
4. System extracts the symptom: "Back pain"
5. Result is stored in the symptoms array

## Project Structure

- `speech_to_text.ipynb`: Main Jupyter notebook containing the entire workflow
- `output.wav`: Generated audio recording file
- `.env`: Environment variables file (not tracked in git)
- Various audio test files (MP3 format)
- `symbipredict_2022.csv`: Dataset possibly used for model training or validation

## Future Improvements

- Add a user-friendly interface
- Support more languages
- Integrate with a medical diagnosis system
- Expand symptom detection capabilities
- Improve accuracy with more specific medical terminology

## Contributors

Larbi Mohammed Achraf
