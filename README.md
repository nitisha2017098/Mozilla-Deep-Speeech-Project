# Mozilla-Deep-Speeech-Project

## Introduction

Mozilla DeepSpeech is an open-source speech recognition system developed by Mozilla. It is based on deep learning techniques and uses a neural network architecture to transcribe speech to text. The system can be trained on large datasets of speech, making it highly customizable for a wide range of speech recognition tasks.

DeepSpeech is based on the TensorFlow machine learning framework and uses a neural network architecture known as a recurrent neural network with LSTM (Long Short-Term Memory) cells. The system has achieved state-of-the-art results on some benchmark datasets, including the LibriSpeech dataset, which is commonly used for evaluating speech recognition systems.

Mozilla DeepSpeech is designed to be easy to use, with pre-trained models available for download and a simple API for developers to integrate the system into their own applications. The system also supports multiple languages, including English, French, German, Spanish, and Mandarin.

Overall, Mozilla DeepSpeech is a promising open-source speech recognition system that has the potential to be a valuable tool for a wide range of applications, including voice assistants, transcription services, and more.


**Step 1**
+ make a directory named ProjectDeepspeech

+ and inside it, download the file https://github.com/mozilla/DeepSpeech/releases/download/v0.9.3/deepspeech-0.9.3-models.pbmm
+ Another one to download https://github.com/mozilla/DeepSpeech/releases/download/v0.9.3/deepspeech-0.9.3-models.scorer
+ Now under example folder - there is a folder name mic_vad_streaming ( For Microphone)
+ Now copy the example repo and clone it.

**Step 2**
+ Now issue command "ls", you have three file inside it
+ go into DeepSpeech-examples repo, here again issue command "ls" and see what is there 
+ now go inside the mic_vad_streaming 
In this folder , we got a python folder that we actually need for this file
+ Issue command "vim mic_vad_streaming.py" and see the program inside it.

