
<details>
<summary>Experiment 9</summary>

### Objectives
- To familiarize with Frequency modulation
- To understand the principles and theories of Frequency modulation
- To create a Frequency Modulator

### Introduction
A Frequency modulation is a  technique that transmits information into a varying frequency according to its amplitude and its signal. one of the advantage of using Frequency modulation is the ability to transmit message without picking up much any electrical noise to the medium, which is one of the disadvantage of AM and oher types of Amplitude modulation such as DSBSC, SSBSC because it is a varying amplitude signal, which is more susceptive from picking up electrical noise to medium, Frequency modulation also provides high quality sound when transmitting the information. However, the disadvantage of using Frequency modulation is that its transmission is complex compared to AM, and it's also expensive to operate. An FM detector usually needs an antenna, specifically a dipole antenna, to receive the transmitted signal while AM doesn't need to; this is because FM has a high-frequency component compared to AM, which creates a shorter wavelength, making the  signal propagation performance poor.

![FM Demo](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Additional%20data/Experiment%209/FM%20Demonstration.JPG)

### Block diagram

based on the block diagram it shows that the message is a 2kHz digital masters signals, connected to the Voltage controlled Oscillator module input to the Emona which as a 10kHz carrier, the first channel of the oscilloscope will be connected directly to the Information signal, while channel 2 will be connected to the output of the VCO, basically the expected output is that the output frequency from the VCO should be directly proportional to the signal when the signal is at the positive peak.

![FM Block diagram](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Block%20diagrams/Experiment%209/FM%20BD.JPG)

### Setup

![EMONA Telecoms trainer setup for Frequency modulation](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Setup/Experiment%209/FM%20setup.JPG)

### Output

![Signal comparison after modulation](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%209/FM%20Output%20masters.jpg)

The output of the signal shows that the carrier frequency increases when the message is at a higher voltage, and decreases when the message is low, which means it's frequency is directly proportional to the information signal(its basically how a VCO works) to create a Frequency modulation signal that is compatible with the medium.

![Signal comparison with Microphone](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%209/FM%20Output%20microphone.jpg)

Additional photo: Using a transducer such as a microphone that shows clearly the Frequency modulation.

## Theories

</details>

<details>
<summary>Experiment 10</summary>

### Objectives
- To familiarize with Frequency demodulation
- To understand the principles and theories of Frequency demodulation
- To create a Frequency demodulator

### Introduction

A frequency demodulator is a type of detector used to demodulate an FM signal from the medium. The demodulation process of  an FM signal is more complex compared to AM detectors since it uses a zero-crossing detector(ZCD) and a voltage comparator circuit to demodulate and recover the information.

### Block diagram

Based on the block diagram, our information is a Variable DC signal connected to the input of the VCO to create the FM signal. For the demodulation, the signal will be fed to the voltage comparator to convert FM signal into square wave, or basically clipping off the sinusoidal peak into square wave, and the output will be connected to the zero-crossing detector, which will output a pulse every time the signal crosses 0V, effectively converting the output of the comparator signal into an equivalent rectangular wave, this rectangular wave varies over time since it will based on the timing of the message whenever it's crossing 0V, which means the timing of the pulse of the ZCD will corresponds to the information, This will then be fed into the baseband LPF to filter out the high-frequency signals under Baseband frequency, effectively recovering the original information

### Setup

### Output


## Theories

Since FM demodulation relies on time intervals of the message, the demodulated output should be expected as a Sine wave, even when we have information with a different waveform shape.

## Theoretical setup(Using EMONA TIMS Telecoms trainer simulation)
https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Additional%20data/Experiment%2010/Theories/MIXED%20SETUP.JPG

## Output

- Sine wave
  !
- Square wave
- Triangular wave




</details>

<details>
<summary>Experiment 11</summary>
In progress.
</details>

<details>
<summary>Experiment 12</summary>
In progress.
</details>

<details>
<summary>Experiment 13</summary>
In progress.
</details>

<details>
<summary>Experiment 14</summary>
In progress.
</details>


<details>
<summary>Reference</summary>
  
### Experiment 9
  
  - https://blog.truegeometry.com/api/exploreHTML/42c699040c9d7b230a38fff56c680c96.exploreHTML
  - https://electronicscoach.com/frequency-modulation.html




  
### Experiment 10
  -
### Experiment 11
  -
### Experiment 12
  -
### Experiment 13
  -
### Experiment 14
  -
### Experiment 15
  -
### Experiment 16
  -
  
</details>
