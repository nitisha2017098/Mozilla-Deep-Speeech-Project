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


**step 3**
now installation of requirements.txt 
by issuing the command "pip install -r requirements.txt"


Getting error after this command 

```
ERROR: Command errored out with exit status 1:
   command: /usr/bin/python3 /tmp/tmpvwm1r8id build_wheel /tmp/tmpvezns7i9
       cwd: /tmp/pip-install-yytk6k2s/pyaudio
  Complete output (18 lines):
  running bdist_wheel
  running build
  running build_py
  creating build
  creating build/lib.linux-x86_64-cpython-38
  creating build/lib.linux-x86_64-cpython-38/pyaudio
  copying src/pyaudio/__init__.py -> build/lib.linux-x86_64-cpython-38/pyaudio
  running build_ext
  building 'pyaudio._portaudio' extension
  creating build/temp.linux-x86_64-cpython-38
  creating build/temp.linux-x86_64-cpython-38/src
  creating build/temp.linux-x86_64-cpython-38/src/pyaudio
  x86_64-linux-gnu-gcc -pthread -Wno-unused-result -Wsign-compare -DNDEBUG -g -fwrapv -O2 -Wall -g -fstack-protector-strong -Wformat -Werror=format-security -g -fwrapv -O2 -fPIC -I/usr/local/include -I/usr/include -I/usr/include/python3.8 -c src/pyaudio/device_api.c -o build/temp.linux-x86_64-cpython-38/src/pyaudio/device_api.o
  src/pyaudio/device_api.c:9:10: fatal error: portaudio.h: No such file or directory
      9 | #include "portaudio.h"
        |          ^~~~~~~~~~~~~
  compilation terminated.
  error: command '/usr/bin/x86_64-linux-gnu-gcc' failed with exit code 1
  ----------------------------------------
  ERROR: Failed building wheel for pyaudio
```


### While searching about the error above on ChatGPT
The error message indicates that there was a problem building the wheel for the PyAudio package during installation.

The specific error message is "fatal error: portaudio.h: No such file or directory", which means that the portaudio.h 
header file, which is required for building PyAudio, could not be found.

To fix this error, you need to install the portaudio development package on your system. You can do this by running the 
following command:

bash
```
sudo apt-get install portaudio19-dev
```
After installing the portaudio development package, try installing PyAudio again:

bash
```
pip install pyaudio
```
If the error persists, you can try installing PyAudio using a pre-built wheel file instead of building it from source:

bash
```
pip install --no-cache-dir --ignore-installed --force-reinstall https://download.lfd.uci.edu/pythonlibs/w4tscw6k/pyaudio-0.2.11-cp38-cp38-linux_x86_64.whl
```
This command downloads and installs a pre-built wheel file for PyAudio that is compatible with Python 3.8 on a Linux x86_64 platform.

If you are using a different platform or Python version, you can find the appropriate wheel file at https://www.lfd.uci.edu/~gohlke/pythonlibs/#pyaudio.


+ Got above instructions but getting same error again even by running above command.


**SOLVING THE ERROR**

I changed the command with "sudo pip3 -r requirements.txt" 
+ still getting same 

**Disaapointing!**











