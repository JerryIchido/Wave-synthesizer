Sine Wave, .wav File Generator
I. Introduction and Program Usage
The project is written for my final project of the Circuits and System course. The Readme file is converted from the original writeup that I submitted. There are other better synthesizers out there written by other fellow UCSD students, but I still dedicated lots of time into the project and is willing to share it. 

The waveform generator can add up to 5 sine waves and generate a wave file with frequency, amplitude, sampling rate and length of file at your discretion. This is a good option for showing the characteristics of sine waves and they combined (Beats, etc.). 

After opening the Wave Generator.exe, a command line interface will pop up. 

First, enter the desired sampling frequency. Enter an integer like 44100. This should be at least 2*biggest frequency you want to put in. 

Then input the desired file length. Longer times will lead to longer generating time and lags --- This is normal. Higher sampling frequency will lead to higher processing times. (44.1kHz is already too high to be necessary! High frequency improves little to quality!)

Then input the frequencies and relative amplitudes (0-100) of the sine waves. Bit depths is fixed as 16 bits, and all amplitude are relative based on a sum of 100. This means 5 waves with 100 amplitude will sound the same as 5 waves with 20 amplitude. (They will be standardized so that they sum to 100!) However, if sum of amplitude is less than 100, you will be able to hear quieter sounds. 

Note: If you want less than 5 waves to be summed, leave the unwanted waves¡¯ frequency and amplitude to 0. 

Hitting enter will start the processing of the wave file. It will be outputted to the same directory of the exe file. 


II. Important Acknowledgements
The code of generating a wave file with a single sine wave was done following the instructions of https://www.youtube.com/watch?v=qqjvB_VxMRM. The source code can be found here: https://github.com/Thrifleganger/audio-programming-youtube/blob/master/wav-file-format/main.cpp . One fellow student of the course Ashwin helped me debug the code. Thank for his help.


III. Background Knowledge: How Wave Files Work
I followed the instructions from https://www.youtube.com/watch?v=qqjvB_VxMRM to generate a wave file. The video shows how we write a wave file that contains a single sine wave with fixed duration, frequency, and amplitude. I spent days learning how the data of a wave file is stored and how does the header work in .wav files, but I will try to make the explanation short by pasting a picture here: http://soundfile.sapp.org/doc/WaveFormat/wav-sound-format.gif
The sound waves the program generate follows that format. It is in PCM format, 1 channel, with 16 bits per sample. The data is not compressed and lossless, leading to very big files and lags when the duration of the file increases. More information can be found at http://soundfile.sapp.org/doc/WaveFormat/ .

IV. Some more Tips
Though the program supports very high sampling rates (like 44.1kHz, 192 kHz), the sound quality doesn¡¯t get better with the sampling rate (according to the sampling theorem.) Theoretically, more than twice of the maximum frequency shall be enough. In practice we usually raise the limit to 2.5x to provide some buffer for the filter. The quality of audio depends predominately on the bit depth, which is 16 bits here (CD quality). (We don¡¯t expect quality from sine wave sounds, though.)
It is also advised that you don¡¯t generate waves with too high amplitudes or frequencies. Also, use speakers instead of headphones. Simple sine waves sound horrible and MAY CAUSE DAMAGE to hearing and speakers. Lower your volume before testing. A wave with frequency around 440 Hz should be fine. 



