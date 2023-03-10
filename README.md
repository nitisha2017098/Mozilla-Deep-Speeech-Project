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

Again, Searching for the solution 
ON STACK OVERFLOW
```
https://stackoverflow.com/questions/20023131/cannot-install-pyaudio-gcc-error
```
I run the command of " sudo apt-get install python-pyaudio python3-pyaudio" 
and get the results as
```
Reading package lists... Done
Building dependency tree       
Reading state information... Done
E: Unable to locate package python-pyaudio

```
Again Next command 
```
pip install pyaudio

```
Got the same error 

I issue the following command 
```
pip install -r requirements.txt
  276  sudo apt-get install portaudio19-dev
  277  pip install -r requirements.txt
  278  pip install pyaudio
  279  pip install --no-cache-dir --ignore-installed --force-reinstall https://download.lfd.uci.edu/pythonlibs/w4tscw6k/pyaudio-0.2.11-cp38-cp38-linux_x86_64.whl
  280  pip install -r requirements.txt
  281  sudo pip3 install -r requirements.txt
  282  sudo apt-get install python-pyaudio
  283  pip install -r requirements.txt
  284  curl -LO https://github.com/mozilla/DeepSpeech/releases/download/v0.9.3/audio-0.9.3.tar.gz
  285  sudo pip3 install -r requirements.txt
  286  sudo apt-get install python-pyaudio python3-pyaudio
  287  tree
  288  pip install pyaudio
  289  pip install wheel
  290  pip install ./third-party/WHEEL_FILENAME
  291  ls
  292  pip install audio-0.9.3.tar.gz
  293  pip install pyaudio
  294  sudo pip3 install -r requirements.txt
  295  sudo apt-get install libasound-dev portaudio19-dev libportaudio2 libportaudiocpp0
  296  pip install pyaudio --user
```
But I am unable to get the solution as "pip install pyaudio" is not working beyond 3.6 version.

+ got suggestion to run  "sudo apt-get install portaudio19-dev"

```
Reading package lists... Done
Building dependency tree       
Reading state information... Done
You might want to run 'apt --fix-broken install' to correct these.
The following packages have unmet dependencies:
 linux-image-5.15.0-67-generic : Depends: linux-modules-5.15.0-67-generic but it is not going to be installed
 portaudio19-dev : Depends: libasound2-dev but it is not going to be installed
                   Depends: libjack-dev
                   Depends: libportaudio2 (= 19.6.0-1build1) but it is not going to be installed
                   Depends: libportaudiocpp0 (= 19.6.0-1build1) but it is not going to be installed
E: Unmet dependencies. Try 'apt --fix-broken install' with no packages (or specify a solution).
```


### Error solved
```
This is a message from the Ubuntu package manager, indicating that there 
are some unmet dependencies when trying to install packages.

The error message suggests running the command 'apt --fix-broken install' 
to attempt to fix the issue automatically. You can try running this command 
as it may resolve the issue.

If that does not work, you may need to manually install the missing dependencies. 
In this case, the package 'linux-image-5.15.0-67-generic' requires the package 
'linux-modules-5.15.0-67-generic', which is not going to be installed. You can 
try to install this package manually using the command 'sudo apt-get install 
linux-modules-5.15.0-67-generic'.

Additionally, the package 'portaudio19-dev' has multiple unmet dependencies 
including 'libasound2-dev', 'libjack-dev', 'libportaudio2', and 'libportaudiocpp0'. 
You can try to install these packages using the command 'sudo apt-get install libasound2-dev libjack-dev libportaudio2 libportaudiocpp0'.
```

Afrer "sudo apt-get install libasound2-dev libjack-dev libportaudio2 libportaudiocpp0"
above command Iussed again same command 
```
sudo apt install portaudio19-dev
```
and its done with follwoing messages
```
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libfwupdplugin1 libxmlb1 linux-headers-5.15.0-46-generic linux-hwe-5.15-headers-5.15.0-46 linux-image-5.15.0-46-generic linux-modules-5.15.0-46-generic linux-modules-extra-5.15.0-46-generic
Use 'sudo apt autoremove' to remove them.
Suggested packages:
  portaudio19-doc
The following NEW packages will be installed:
  portaudio19-dev
0 upgraded, 1 newly installed, 0 to remove and 32 not upgraded.
Need to get 106 kB of archives.
After this operation, 628 kB of additional disk space will be used.
Get:1 http://in.archive.ubuntu.com/ubuntu focal/universe amd64 portaudio19-dev amd64 19.6.0-1build1 [106 kB]
Fetched 106 kB in 2s (62.7 kB/s)          
Selecting previously unselected package portaudio19-dev:amd64.
(Reading database ... 236755 files and directories currently installed.)
Preparing to unpack .../portaudio19-dev_19.6.0-1build1_amd64.deb ...
Unpacking portaudio19-dev:amd64 (19.6.0-1build1) ...
Setting up portaudio19-dev:amd64 (19.6.0-1build1) ...
```
then 
```
sudo pip3 install -r requirements.txt
```
and issue resolved!!

+ Command in between
```
  329  cd Downloads
  330  cd ProjectDeepspeech
  331  ls
  332  mv deepspeech-0.9.3-models.*DeepSpeech-examples/
  333  mv deepspeech-0.9.3-models.*DeepSpeech-examples/ls
  334  mv deepspeech-0.9.3-models.* DeepSpeech-examples/ls
  335  mv deepspeech-0.9.3-models.* DeepSpeech-examples/mic_vad_streaming/
  336  ls
  337  cd DeepSpeech-examples
  338  ls
  339  cd mic_vad_streaming
  340  ls
  341  python3 mic_vad_streaming.py -m deepspeech-0.9.3-models.pbmm -s deepspeech-0.9.3-models.scorer
  342 
```


### Finally its done and ready to listen to speech and convert it into text
```
niti@niti:~/Downloads/ProjectDeepspeech/DeepSpeech-examples/mic_vad_streaming$ python3 mic_vad_streaming.py -m deepspeech-0.9.3-models.pbmm -s deepspeech-0.9.3-models.scorer
Initializing model...
INFO:root:ARGS.model: deepspeech-0.9.3-models.pbmm
TensorFlow: v2.3.0-6-g23ad988
DeepSpeech: v0.9.3-0-gf2e9c85
2023-03-10 13:43:32.795685: I tensorflow/core/platform/cpu_feature_guard.cc:142] This TensorFlow binary is optimized with oneAPI Deep Neural Network Library (oneDNN)to use the following CPU instructions in performance-critical operations:  AVX2 AVX512F FMA
To enable them in other operations, rebuild TensorFlow with the appropriate compiler flags.
INFO:root:ARGS.scorer: deepspeech-0.9.3-models.scorer
ALSA lib pcm_dmix.c:1089:(snd_pcm_dmix_open) unable to open slave
ALSA lib pcm.c:2642:(snd_pcm_open_noupdate) Unknown PCM cards.pcm.rear
ALSA lib pcm.c:2642:(snd_pcm_open_noupdate) Unknown PCM cards.pcm.center_lfe
ALSA lib pcm.c:2642:(snd_pcm_open_noupdate) Unknown PCM cards.pcm.side
ALSA lib pcm_route.c:869:(find_matching_chmap) Found no matching channel map
ALSA lib pcm_oss.c:377:(_snd_pcm_oss_open) Unknown field port
ALSA lib pcm_oss.c:377:(_snd_pcm_oss_open) Unknown field port
ALSA lib pcm_usb_stream.c:486:(_snd_pcm_usb_stream_open) Invalid type for card
ALSA lib pcm_usb_stream.c:486:(_snd_pcm_usb_stream_open) Invalid type for card
ALSA lib pcm_dmix.c:1089:(snd_pcm_dmix_open) unable to open slave
Listening (ctrl-C to exit)...
Recognized: hello everyone
Recognized: you
```
+ It is not stable
```
Recognized: he
Recognized: i do 
Recognized: good morning
Recognized: 
Recognized: 
Recognized: 
Recognized: happy and shall
Recognized: 
Recognized: he
Recognized: 
Recognized: welcome to whom
Recognized: he composed
Recognized: come home
```

























