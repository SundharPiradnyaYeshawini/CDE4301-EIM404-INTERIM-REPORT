this readme contains the code since I'm still learning how to push from VScode to github
the below code is the first part with the aim of generating mel spectrogram from .wav audio file

import librosa
import librosa.display
import IPython.display as ipd
import matplotlib.pyplot as plt

#loading audio files with librosa
scale_file = "Piradnya-when-290126-800Hz.wav" #path to the audio file

#ipd.Audio(scale_file)  #play the audio of the realtive file path
#to scale the audio file. sr=None preserves the original sampling rate. y becomes a numpy array containing the audio signals.
y, sr = librosa.load(scale_file, sr=None)
ipd.Audio(y, rate=sr)  #play the audio

#Extraxcting Short Time Fourier Transform (STFT)
FRAME_SIZE = 2048
HOP_SIZE = 512
S_scale = librosa.stft(y, n_fft=FRAME_SIZE, hop_length=HOP_SIZE)
#shape of STFT
S_scale.shape #bideminsianl array (frequency bins, time frames)
