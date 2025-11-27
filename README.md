# DSBSC-PYTHON#

Aim

To implement and analyze DSBSC using Python's NumPy and Matplotlib libraries. 

Apparatus Required

1.	Software: Python with NumPy and Matplotlib libraries
2.	Hardware: Personal Computer
  
Theory

Double Sideband Suppressed Carrier (DSB-SC) is a method of transmitting information over a carrier wave by varying its amplitude in accordance with the amplitude of the input signal (message signal). In this technique, the carrier component is suppressed, and only the two sidebands containing the information are transmitted.


Algorithm

1. Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency.
2. Generate Time Axis: Create a time vector for the signal duration.
3. Generate Message Signal: Define the message signal as a cosine wave.
4.Generate Carrier Signal: Define the carrier signal as a cosine wave with the specified carrier frequency.
5. Generate DSB-SC Signal: Multiply the message signal with the carrier signal to obtain the modulated (DSB-SC) signal.
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and DSB-SC modulated signal.

Program
~~~
import numpy as np
import matplotlib.pyplot as plt

Am = 4.5
fm = 362
Ac = 9.0
fc = 3620
fs = 36200

t = np.arange(0, 2/fm, 1/fs)

m = Am * np.cos(2 * np.pi * fm * t)
plt.subplot(3, 1, 1)
plt.plot(t, m)


c = Ac * np.cos(2 * np.pi * fc * t)
plt.subplot(3, 1, 2)
plt.plot(t, c)


s1 = (Ac + m) * np.cos(2 * np.pi * fc * t)
s2 = (Ac - m) * np.cos(2 * np.pi * fc * t)
s = s1 - s2

plt.subplot(3, 1, 3)
plt.plot(t, s)
~~~
Output Waveform

<img width="559" height="413" alt="image" src="https://github.com/user-attachments/assets/04c55a50-5c4c-4b33-a013-4a79a9b5531a" />


Tabular Column

![WhatsApp Image 2025-11-27 at 19 07 18_45ab9b50](https://github.com/user-attachments/assets/f4b59a12-2ec0-4a18-90a7-8f4a527306ce)



Result
The message signal, carrier signal, and Double Sideband Suppressed Carrier (DSB-SC) signal will be displayed in separate plots. The modulated signal will show amplitude variations corresponding to the instantaneous amplitude of the message signal, while the carrier component remains suppressed.
