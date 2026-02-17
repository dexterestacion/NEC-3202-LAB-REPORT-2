<details>
<summary>Experiment 9: FM Modulation</summary>

### Objectives
- To familiarize with Frequency modulation
- To understand the principles and theories of Frequency modulation
- To create a Frequency Modulator

### Introduction
A Frequency modulation is a technique that transmits information into a varying frequency according to its amplitude and its signal. one of the advantage of using Frequency modulation is the ability to transmit message without picking up much any electrical noise to the medium, which is one of the disadvantage of AM and oher types of Amplitude modulation such as DSBSC, SSBSC because it is a varying amplitude signal, which is more susceptive from picking up electrical noise to medium, Frequency modulation also provides high quality sound when transmitting the information. However, the disadvantage of using Frequency modulation is that its transmission is complex compared to AM, and it's also expensive to operate. An FM detector usually needs an antenna, specifically a dipole antenna, to receive the transmitted signal while AM doesn't need to; this is because FM has a high-frequency component compared to AM, which creates a shorter wavelength, making the  signal propagation performance poor.

![FM Demo](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Additional%20data/Experiment%209/FM%20Demonstration.JPG)

### Block diagram

based on the block diagram it shows that the message is a 2kHz digital masters signals, connected to the Voltage controlled Oscillator module input to the Emona which as a 10kHz carrier, the first channel of the oscilloscope will be connected directly to the Information signal, while channel 2 will be connected to the output of the VCO, basically the expected output is that the output frequency from the VCO should be directly proportional to the information signal voltage.

![FM Block diagram](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Block%20diagrams/Experiment%209/FM%20BD.JPG)

### Setup

![EMONA Telecoms trainer setup for Frequency modulation](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Setup/Experiment%209/FM%20setup.JPG)

### Output

![Signal comparison after modulation](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%209/FM%20Output%20masters.jpg)

The output of the signal shows that the carrier frequency increases when the message is at a higher voltage, and decreases when the message is low, which means its frequency is directly proportional to the information signal's voltage(it's basically how a VCO works) to create a Frequency modulation signal that is compatible with the medium.

![Signal comparison with Microphone](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%209/FM%20Output%20microphone.jpg)

Additional photo: Using a transducer such as a microphone that shows clearly the Frequency modulation.

</details>

<details>
<summary>Experiment 10: FM Demodulation</summary>

### Objectives
- To familiarize with Frequency demodulation
- To understand the principles and theories of Frequency demodulation
- To create a Frequency demodulator

### Introduction

A frequency demodulator is a type of detector used to demodulate an FM signal from the medium. The demodulation process of  an FM signal is more complex compared to AM detectors since it uses a zero-crossing detector(ZCD) and a voltage comparator circuit to demodulate and recover the information.

![FM Demodulation stages](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Additional%20data/Experiment%2010/FM%20Demodulation%20demonstration.JPG)

### Block diagram

![Block diagram of FM Modulator and demodulator](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Block%20diagrams/Experiment%2010/FM%20Demodulator%20BD.JPG)


Based on the block diagram, our information is a variable DC signal connected to the input of the VCO to create the FM signal. For the demodulation, the signal will be fed to the voltage comparator to convert FM signal into square wave, this will basically switch from positve saturation voltage of the comparator to ground based on the connection and the voltage level of its inputs, this will also reduce noise from the signal since comparator relies only in voltage level of the signal. Since FM stores information in its frequency, this can be used in comparator in order to reduce the noise from the FM signal,  the output of the comparator will then be connected to the zero-crossing detector, which will output a pulse every time the signal crosses/reached 0V, effectively converting the output of the comparator signal into an equivalent rectangular wave or basically generate a pulse, this rectangular wave varies over time since it will based on the timing of the message whenever it's crossing 0V, which means the timing of the pulse of the ZCD corresponds to the information signal, the continuous pulse coming from the zero-crossing detector will be converted by the baseband LPF into an analog voltage smoothing out the signal while also blocking the high frequency component of the FM signal and passes the low frequency component, effectively recovering the original information.

 
> ⓘ NOTE: A comparator is an electronic device used to compare 2 input voltage from the Inverting input(REF) and non-inverting input(IN), if non-inverting input voltage is greater than inverting input, the comparator switch to positive saturation voltage, if the voltage in inverting input is greater than the inverting input, then the output will switch to negative saturation or GND based on the applied connection to the negative supply of the comparator, but in our case the comparator of the telecoms trainer is connected in GND(0V). This basically converts analog signal into digital signal, hence, it is used for Analog to Digital converters.

![Comparator photo](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Additional%20data/Experiment%2010/Comparator%20image.JPG)

![Comparator output](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Additional%20data/Experiment%2010/Comparator%20output.JPG)

> A zero voltage detector is a type of electronic circuit built in a voltage comparator, it is used to detect an AC signal whenever it passes/crosses through 0V, producing a short pulse. The EMONA netTIMS has a Zero-crossing detector built in to the trainer that can vary the width of the pulse and delay.

### Setup(Emona netTIMS online setup)
![Emona FM Demod setup](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Setup/Experiment%2010/FM%20Demodulator%20setup.JPG)

### Output

![Demodulator output](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2010/FM%20Demodulator%20Output.JPG)

https://github.com/user-attachments/assets/5fc33f9f-1f2e-48b0-972a-834664cbb214

The video shows that the DC signal is recovered when we vary the variable DC voltage knob, however, the scope's channel 2 is not configured in DC coupling, but its output whenever we vary the signal changes proportionally.

https://github.com/user-attachments/assets/8b545b04-2221-4870-9c7b-3aee45ca5166

comparison of the output of the ZCD(CH1) after filtering(CH2) 

### Observations

Since FM demodulation relies on time intervals of the message, the demodulated output should be expected as a Sine wave, even when we have information with a different waveform shape.

### Theoretical setup(Using EMONA net*TIMS Telecoms trainer online)

![EMONA TIMS Theoretical](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Additional%20data/Experiment%2010/Observations/MIXED%20SETUP.JPG)

### Output

- Sine wave
  
![FM Demodulated signal using sine wave as message](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2010/Additional%20observation%20output/FM%20Demodulation%20with%20sine%20wave%20information.JPG)
   
- Square wave
  
![FM Demodulated signal using sine wave as message](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2010/Additional%20observation%20output/FM%20Demodulation%20with%20square%20wave%20information.JPG)

- Triangular wave
  
![FM Demodulated signal using sine wave as message](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2010/Additional%20observation%20output/FM%20Demodulation%20with%20triangular%20wave%20information.JPG)

</details>

<details>
<summary>Experiment 11 - Sampling and reconstruction</summary>

### Objectives
- To be familiar with digital transmission
- To understand the principles of PAM and Quantization

### Introduction
A digital transmission is a process of conveying information into  a discrete-time signal by measuring its amplitude at regular intervals. process called sampling takes measurements of the continuous message signal time intervals into a discrete-time signal. in this experiment, we will demonstrate the 2 common sampling techniques: natural sampling and sample-and-hold sampling.

A natural sampling is a form of modulation technique that involves multiplying the analog signal to the pulse train(rectangular pulses), this will allow to follow the orignal waveform's shape during pulse duration, if the pulse is on, input signal passes through, if the pulse if off, no signal will output. A sample-and-hold(S&H) is an electronic device that takes the message's amplitude signal in each point and holds the value constant for a duration.


![Natural sampling and S&H](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Additional%20data/Experiment%2011/Sampling%20demo.JPG)

### Block diagram: Natural sampling

![Natural sampling BD](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Block%20diagrams/Experiment%2011/Natural%20sampling%20BD.JPG)

baed on the diagram, it shows that the 2kHz signal will be our information signal, connected to the input of the dual analog switch, the 8kHz digital signal will serve as the switching component or the sampling frequency that will let the input signal pass to the output whenever the control signal is in positive peak and blocks it when the control signal is in 0V, generating a Pulse amplitude modulation(Natural sampling).

### Setup: Natural sampling

![Natural sampling setup](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Setup/Experiment%2011/Natural%20sampling%20setup.jpg)

### Output

![Natural samping output](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2011/Natural%20sampling%20output.jpg)

![Natural sampling and message signal comparison](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2011/Natural%20samping%20and%20message%20comparison.jpg)

as expected, the signal will get pass through when the sampling frequency is at positive peak voltage, and blocks it when it reach the negative peak voltage, forming a Natural sampling.

### Block diagram: Sample and hold/w tunable LPF(message reconstruction)

![S&H with LPF BD](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Block%20diagrams/Experiment%2011/S%26H%20%20and%20reconstruction%20BD.jpg)

Based on the block diagram, the dual analog switch circuit will be replaced with Sample-and-hold circuit, the princple of S&H sampling is that it holds the first constant value until the next sampling frequency 

### Setup: Sample and hold sampling/w tunable LPF(message reconstruction)

![S&H Setup](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Setup/Experiment%2011/Sample%20and%20hold%20%20original%20message%20reconstruction%20setup.jpg)

### Output: Sample and hold sampling/w tunable LPF(message reconstruction)

- S&H Output
![Sample and hold output](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2011/Sample%20and%20hold%20output.jpg)

- Original message and S&H comparison
![S&H and message comparison](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2011/S%26H%20and%20message%20comparison.jpg)

- Reconstructed Message to Original message comaparison
![Reconstructed message and original message](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2011/S%26H%20Reconstructed%20message%20comparison.jpg)


### Observation

if the sampling frequency increased, it improved the quality of the reconstruction of the signal because it reduces aliasing and provides improves the quality when it comes to reconstructing the signal

### Setup: Natural sampling using VCO

![Natural sampling VCO setup](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Setup/Experiment%2011/Observation%20setup/Natural%20sampling%20setup.JPG)

### Output: Natural sampling using VCO

- if VCO frequency is low

![Natural sampling under low frequency](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2011/Observation%20output/Natural%20sampling%20under%20low%20frequency%20sampling.JPG)

- if VCO frequency is high

![Natural sampling under high frequency](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2011/Observation%20output/Natural%20sampling%20under%20high%20frequency%20sampling.JPG)


### Setup: S&H Sampling using VCO

![S&H Sampling with VCO setup](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Setup/Experiment%2011/Observation%20setup/S%26H%20Sampling%20VCO%20observation%20setup.JPG)

### Output: S&H Sampling using VCO

- if VCO frequency is low
  
![S&H Sampling Under low frequency sampling](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2011/Observation%20output/S%26H%20under%20low%20frequency%20sampling.JPG)


- if VCO frequency is high
  
![S&H Sampling Under high frequency sampling](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2011/Observation%20output/S%26H%20under%20high%20frequency%20sampling.JPG)
</details>

<details>
<summary>Experiment 12 - PCM encoding</summary>

### Objectives
- To familarize PCM Encoding
- Understand the basic principle of Pulse Code Modulation (PCM)
- Analyze the PCM output for 0V input and variable DC input.
- Compare and observe the relationship between the analog input voltage and the generated PCM digital data.
### Introduction

A pulse code modulation(PCM) is a type of digital modulation technique that converts analog signal into binary sequence of 1s and 0s. PCM uses sampling, quantizing, and encoding in order for analog signal to be converted into binary system. This process was developed in 1937, primarily used for telephony, space communications, and digital audio processing during the 1960s and 70s.

![PCM](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Additional%20data/Experiment%2012/PCM%20demo.JPG)

PCM contains 2 output pins:
- Frame synchronization - it is an identifier that will align to the exact beginning of the data frame of an encoded data to identify and read the PCM data from the moment the bit starts and stops.
- PCM data - this is the equivalent analog signal convered into digital data that has been decoded, in our setup, the EMONA telecoms trainer only has a 7 bit encoder.

![PCM Actual demo](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Additional%20data/Experiment%2012/PCM%20Data%20actial%20representation.jpg)
  

### Block diagram

![PCM Encoder block diagram with 0V input](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Block%20diagrams/Experiment%2012/PCM%20Encoder%20with%200V%20Input.JPG)

our input signal will be grounded and our clock signal would be 8kHz signal. the PCM encoder for EMONA combines the process of Sampling, Quantization, and encoding into a single block, making it easy to implement rather than using a separate dual analog switch for sampling and quantization.

### Setup

![PCM Encoder setup](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Setup/Experiment%2012/FS%20and%20Digital%20signal%20comparison.jpg)

Observing the output, the frame synchronization (FS) signal appeared as a periodic pulse that marked the beginning of each data frame. The 8 kHz clock signal was visible and maintained a constant frequency, which means it has a stable sampling operation

### Output

- CH1(Frame synchronization) and CH2(8kHz digital clock signal) comparison
  
![PCM Encoder output](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2012/Clock%20signal%20and%20Frame%20synchonization%20signal.jpg)

- CH1(Frame synchronization) and CH2(PCM DATA) comparison

![FS and PCM DATA Comparison](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2012/Frame%20synchronization%20and%20PCM%20output%20data.jpg)

- Reading the equivalent binary data of the PCM output
![PCM Data reading](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2012/PCM%20Data%20reading.JPG)

### Block diagram

![PCM Encoder block diagram with VDC input](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Block%20diagrams/Experiment%2012/PCM%20Encoder%20with%20Variable%20DC%20Input.JPG)


### Setup

![PCM Encoder DCV setup](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Setup/Experiment%2012/PCM%20Setup%20DCV.jpg)

Modifying the setup, this time, instead of grounded input, we use the variable dc voltage and observe the output.

### Output

![PCM Encoder output](https://github.com/user-attachments/assets/9bb37632-e221-4fab-a63e-4295a544365a)

The binary code pattern shifted based on the amplitude of the applied DC voltage. Higher DC voltages produces more binary codes corresponding to higher quantization levels, while lower DC voltages produced less binary codes.


</details>

<details>
<summary>Experiment 13 - PCM decoding</summary>


### Objectives

- To familiarize with the operation of the PCM Decoder module in the EMONA Telecommunications Trainer.
- Understand the basic principle of PCM decoding and signal reconstruction.
- To create a PCM decoder.
- Analyze and compare the reconstructed output signal with the original input signal.

### Introduction

Pulse Code Modulation (PCM) decoder is the counterpart of the PCM encoder used to convert encoded PCM data back into its original analog signal. the decoder performs the process to reconstructing the signal, it receives the PCM data along with the clock frequency and the frame synchronization signals to ensure correct timing and proper alignment of each digital word. for our experiment, we'll stole the clock frequency and the frame synchronization to the encoder to make sure that the orignal message is recovered

### Block diagram

### Setup

![PCM Decoder setup](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Setup/Experiment%2013/PCM%20Decoder%20setup.jpg)

### Output

![PCM Decoder output](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2013/PCM%20decoder%20output.jpg)

- after filtering
![PCM Output filtered](https://raw.githubusercontent.com/dexterestacion/NEC-3202-LAB-REPORT-2/refs/heads/main/Output/Experiment%2013/PCM%20decoder%20output%20after%20filtering.jpg)

### Additional Observation

Looking at the converted binary data of the PCM output at 0V, it shows that the data is not 000000 when the input is 0V. This is because most PCM coding uses a bipolar encoding scheme, where the mapping range usually from -2V to +2V across 256 steps. which means 0V is around the middle point, resulting to a minimum binary value rather than a complete 00000000 binary output, another reason is the Quantization levels where 0V may not align exactly wih the first quantization level due to the ADC dividing the total voltage span. Also, when looking at the second output where we applied a variable DC voltage, the output keeps changing even when the value of the input voltage is constant, this is probably because  the voltage is different for every sample input signal, or possibly due to small noise variation or 

</details>


<details>
<summary>Experiment 14 - BW limiting and restoring digital signals</summary>



### Objectives

### Introduction

### Block diagram

### Setup

### Output

### Observation

### Setup

### Output


 
</details>


<details>
<summary>Reference</summary>
  
### Experiment 9
  
  - https://blog.truegeometry.com/api/exploreHTML/42c699040c9d7b230a38fff56c680c96.exploreHTML
  - https://electronicscoach.com/frequency-modulation.html
  
### Experiment 10
  - https://user.eng.umd.edu/~tretter/commlab/c6713slides/ch8.pdf
  - https://ae-iitr.vlabs.ac.in/exp/voltage-comparator/theory.html
    
### Experiment 11
  - https://uomus.edu.iq/img/lectures21/MUCLecture_2025_225463.pdf
    
### Experiment 12
  - https://www.sciencedirect.com/topics/engineering/pulse-code-modulation
  - https://www.eng.auburn.edu/~troppel/courses/TIMS-manuals-r5/TIMS%20Experiment%20Manuals/Student_Text/Vol-D1/D1-11.pdf
  - https://byjus.com/physics/pulse-code-modulation/
    
### Experiment 13
  - https://www.egr.msu.edu/classes/ece458/radha/ss07Keyur/Lab-Handouts/Lab9PCM.pdf
    
### Experiment 14
  -

  
</details>
