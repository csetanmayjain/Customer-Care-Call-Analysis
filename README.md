# Customer-Care-Call-Analysis
This project performs customer care call analysis by leveraging multiple technologies, including Voice Activity Detection (VAD), Automatic Speech Recognition (ASR), and Large Language Models (LLM). The system is designed to analyze stereo audio files, split the audio into channels, process it to extract meaningful insights, and analyze conversations using LLMs.

## Features
1. Stereo to Mono Conversion: Splits stereo audio into two mono tracks (one for each speaker).
2. Voice Activity Detection (VAD): Detects speech segments in the audio, extracting timestamps for each chunk of detected speech.
3. Automatic Speech Recognition (ASR): Transcribes the detected audio chunks into text.
4. Large Language Model (LLM) Integration: Analyzes transcriptions to derive insights such as problem resolution status, important keywords, agent behavior, product enhancement opportunities, and potential new product features.

## Workflow
1. Load Dependencies: The project imports essential dependencies, including:
  - Silero VAD for voice activity detection.
  - NVIDIA NeMo for ASR.
  - Groq for integrating large language models (LLMs).
    
2. Stereo to Mono Conversion: The function `split_stereo_to_mono(input_file, output_left, output_right)` splits stereo audio into two mono channels (left and right speakers). 

3. Speech Chunking and Timestamps: The function `get_chunks_timestamps(audio_file_path)`:
  -  Reads the left and right mono audio files using Silero VAD.
  - Detects speech segments and their corresponding timestamps using `get_speech_timestamps`.
  - Combines the speech timestamps from both speakers and sorts them chronologically.
  
4. ASR Model Loading: The function `load_models(asr_model_path)`:
- Loads the ASR model from the specified path using NeMo.
- Uses the ASR model to transcribe the audio chunks into text.

5. Audio Analysis using LLM: After ASR transcription, the processed text is analyzed using a large language model (LLM). This analysis provides insights into:
- Problem Resolution: Identifying whether the problem discussed in the conversation was resolved.
- Keyword Detection: Detecting important keywords or phrases from the conversation.
- Agent Behavior: Analyzing the tone and behavior of the customer service agent.
- Product Enhancement Opportunities: Identifying areas for potential product improvements.
- New Product Features: Suggesting new features based on customer feedback.

## Output
The analysis provides a summarized transcription of the call with insights such as problem resolution, keyword detection, agent behavior, and more.

## Conclusion
This project demonstrates a comprehensive approach to analyzing customer care calls using advanced technologies like VAD, ASR, and LLMs. The system effectively processes stereo audio files, performs transcription, and provides actionable insights for improving customer service operations.

## Disclaimer
This project is a proof of concept (POC) and is not intended for production use.

### License: 
  CC BY-NC
