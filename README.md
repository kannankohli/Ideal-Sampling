# Ideal-Sampling

Aim:

To perform ideal (impulse) sampling of a continuous-time sinusoidal signal, visualize the sampled signal, and reconstruct it using Python.

Tools/Software Required:

Python Software -> Numpy Library

-> Matplotlib Library

-> Scipy Library (for signal processing)
~~~~
Program :
Impulse Sampling

import numpy as np

import matplotlib.pyplot as plt

from scipy.signal import resample

fs = 100

t = np.arange(0, 1, 1/fs)

f = 5

signal = np.sin(2 * np.pi * f * t)

plt.figure(figsize=(10, 4))

plt.plot(t, signal, label='Continuous Signal')

plt.title('Continuous Signal (fs = 100 Hz)')

plt.xlabel('Time [s]')

plt.ylabel('Amplitude')

plt.grid(True)

plt.legend()

plt.show()

t_sampled = np.arange(0, 1, 1/fs)

signal_sampled = np.sin(2 * np.pi * f * t_sampled)

plt.figure(figsize=(10, 4))

plt.plot(t, signal, label='Continuous Signal', alpha=0.7)

plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')

plt.title('Sampling of Continuous Signal (fs = 100 Hz)')

plt.xlabel('Time [s]')

plt.ylabel('Amplitude')

plt.grid(True)

plt.legend()

plt.show()

reconstructed_signal = resample(signal_sampled, len(t))

plt.figure(figsize=(10, 4))

plt.plot(t, signal, label='Continuous Signal', alpha=0.7)

plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')

plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')

plt.xlabel('Time [s]')

plt.ylabel('Amplitude')

plt.grid(True)

plt.legend()

plt.show()
~~~~
Output Waveform :

![image](https://github.com/user-attachments/assets/e47d1490-a216-4948-bb39-d67e7949371d)

![image](https://github.com/user-attachments/assets/661cc3c1-771c-4724-9630-4a58e00540ca)

![image](https://github.com/user-attachments/assets/f4db27b5-093e-4f59-9535-7078f101e643)

RESULT:

The Construction or Re-Construction of impulse or ideal sampling using python are verified
