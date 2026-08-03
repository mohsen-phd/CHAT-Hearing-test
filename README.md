# CHAT Hearing Test

CHAT (Conversational Hearing Assessment Test) is an experimental speech-in-noise (SIN) hearing test that uses modern AI tools to generate, administer, and score hearing assessments. Instead of asking participants to repeat sentences verbatim, CHAT presents a short statement followed by a question and evaluates the participant's spoken response automatically.

This repository accompanies the paper:

> *An Automated Question-and-Answer-Based Speech-in-Noise Hearing Test Using a Large Language Model*
>
> Mohsen Fatehifar, Kevin J. Munro, Michael A. Stone, David Wong, Tim Cootes, and Josef Schlittenlacher.

## Features

- Conversational question-and-answer hearing test (CHAT)
- Adaptive Sentence List (ASL) test
- Four Alternative Auditory Feature Test (FAAF)
- Automatic speech recognition (ASR)
- Text-to-speech (TTS) synthesis
- Adaptive signal-to-noise ratio (SNR) tracking
- Practice and test modes
- Automatic logging and result saving

## Repository structure

```text
CHAT-Hearing-test/
├── main.py                  # Main entry point
├── config.yaml             # Test configuration
├── pyproject.toml          # Poetry configuration
├── Questions.txt
├── hearing_test/           # Core hearing-test logic
├── audio_processing/       # Noise generation and processing
├── get_response/           # ASR and CLI response capture
├── vocalizer/              # Speech synthesis and playback
├── stimuli_generator/      # Stimulus generation
├── media/                  # Material of the test (audio and text files)
└── records/                # Saved results
```

## Installation

This project uses Poetry.

```bash
git clone https://github.com/mohsen-phd/CHAT-Hearing-test.git
cd CHAT-Hearing-test

poetry install
poetry shell
```

## Configuration

The test configuration is stored in `config.yaml`.

Before running the project, verify:

- file paths in `config.yaml`;
- microphone and playback devices;
- locations of stimuli and noise files.

Some paths in the current configuration are machine-specific and may need to be updated.

## OpenAI API key

Before running the project, create a folder called `keys` in the project root and add a file named `openai.txt` containing your OpenAI API key:

```text
CHAT-Hearing-test/
├── keys/
│   └── openai.txt
├── main.py
├── config.yaml
└── ...
```

The `openai.txt` file should contain only your API key:

```text
sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## Running the CHAT test

Start the application:

```bash
python main.py
```

The program will ask for:

```text
Enter The ID:
Enter test number:
Enter test name:
Enter test name for showing:
Enter response capturing mode (asr or cli):
Enter vocalization mode (tts or recorded):
Enter processing mode ((n)one, (l)owpass, (m)odulation matching or (b)oth):
Enter the test mode (test or practice):
```

Example configuration for CHAT:

```text
Participant ID: 001
Test number: 1
Test name: chat
Test name for showing: CHAT
Response capturing mode: asr
Vocalization mode: tts
Processing mode: n
Test mode: test
```



## Output

Results, recordings and logs are saved in:

```text
records/<participant_id>/
```
