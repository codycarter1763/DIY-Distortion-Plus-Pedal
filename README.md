# DIY Distortion Plus Guitar Pedal
<p align="center">
  <img src="https://github.com/user-attachments/assets/eb79bd0e-b545-4e69-9dc6-9a60619b5c46" width=40% height=40%>
</p> 

# About
<h6>
  &emsp; The MXR Distortion Plus was considered the first commercially successful distortion pedals ever released. Known for it's aggressive "hard clipping" sound used by the likes of Randy Rhoads of Ozzy Osbourne, Jerry Garcia of the Grateful Dead, Slash of Guns N Dave Murray of Iron Maiden,and countless more. The pedal is very simple with its two output and distortion controls only, making for a very easy setup.  

<p align="left">
  <img src="https://github.com/user-attachments/assets/13ae04e0-7f42-4653-af45-4e35a568afed" width="50%" height="50%" alt="Left Image">
  <img src="https://github.com/user-attachments/assets/1275ab4f-a38a-4812-8082-a9e7b05f59b2" width="48%" height="48%" alt="Right Image">
</p>  
</h6>

# Parts List
This list is for the stock circuit without any mods.

- 1 LM741 Op Amp
- 2 1nF Capacitor
- 1 10nF Capacitor
- 1 47nF Capacitor
- 2 1uF Capacitors
- 4 1MΩ Resistors
- 1 4.7KΩ Resistor
- 2 10KΩ Resistors
- 1MΩ Log Potentiometer
- 10KΩ Log Potentiometer
- 2 1N34A Germanium Diodes

# Circuit Diagrams and Mods
## Stock Circuit Diagram
![MXR Distortion Plus Schematic](https://github.com/user-attachments/assets/8a0bd349-39b4-4854-b804-345cb848d750)

## Circuit Diagram with Common Mods
Here are some common mods from Brian Wampler of Wampler Pedals, feel free to add mods to your design.
- Compression switch to add or decrease compression
- Change R3 and C3 to 1K and 0.22uF for more gain with similar tone
- Wire a toggle switch to add in 1N34A and 1N4001 clipping diodes for a smoother distortion sound
- Wire a six pin toggle switch to add 1n4001 diodes in series with 1N34A diodes for more volume and dynamics
- Change C5 to a 2.2nF capacitor and add a 1M audio taper potentiometer for a tone control
![MXR Distortion Plus Mods](https://github.com/user-attachments/assets/688128e7-7240-4ff0-953b-2da6ff297045)

# Circuit Analysis and Effect of Mods
The stock circuit is very simple yet effective. It uses just a single operational amplifier and a pair of germanium diodes to make the first commercially successful distortion pedals ever released.

## OP Amp Stage
![Screenshot 2025-02-21 230755](https://github.com/user-attachments/assets/1f3b2574-f1f2-4dc1-b12c-27e2e4ed4e9a)
### Input Impedance
Z<sub>VGround</sub> = R6 // R7 = 1M // 1M = 500K <br> 
Z<sub>Input</sub> = R1 + (Z<sub>Amp</sub> // R2) + Z<sub>VGround</sub> = 10K + (2M // 1M) + 500K = 1176K or 11.7Meg
<br> <br>
A high input impedance prevents the circuit from drawing too much current from the guitar signal, preventing tone sucking and allows the full frequency range to go through.
<br>
<br>
### Gain
As observed below through an LTSpice simulation, you can see that the MXR Distortion Plus has a very considerable amount of gain peaking at about 40dB throughout the distortion range. 
![MXR Distortion Plus Frequency Response Across Distortion Range](https://github.com/user-attachments/assets/4497a413-785b-42fc-9a62-6bc733217a6c)
<br> <br>

### Input Frequency Response
The input frequency response is governed by the RC networks leading into the OP amp inputs.
<br>
For the response of the positive OP amp input, the effective impedance not considering the OP amp internal impedance is needed for accurate measurement.
<br>
- Considering the OP amp effect for non-inverting amps, Z<sub>effGround</sub> = Z<sub>in+</sub> x A<sub>V</sub> = 343K x 2 = 686K
- Where Z<sub>in+(gain)</sub> = R2 // (Z<sub>VGround</sub>) = 1M // 500K = 333K + R1 = 333K + 10K = 343K <br>
- Where A<sub>V(gain)</sub> = 1 + (R6/R2) = 1 + (1M/1M) = 2
<br>

#### F<sub>c+</sub> Cutoff Frequency Using 1 / 2piRC
F<sub>c+</sub> = 1 / (2pi(686K)(10nF)) = 23.2 Hz <br>
This attentuates lower frequencies to prevent overloading and tone from being fuzzy
<br>
#### F<sub>c-</sub> Cutoff Frequency Max Gain
F<sub>c-</sub> = 1 / (2pi(4.7K)(47nF)) = 720 Hz <br>
  As distortion is turned up, the peak frequency shifts as viewed below
<br>
#### F<sub>c-</sub> Cutoff Frequency Low Gain
F<sub>c-</sub> = 1 / (2pi(1.0047Meg)(47nF)) = 3.37 kHz

## Clipping Stage
![Screenshot 2025-02-25 155303](https://github.com/user-attachments/assets/da495717-dbbc-4ecf-9ffa-c56469f78fc8)

This stage contains two 1N270 germanium diodes that add a hard clip distortion to the amplified output. Germanium diodes are known for their softer distortion sound and more compression since voltages are clipped above 0.25V. In my case, I used 1N34A diodes, but tonality all germanium will sound similar.

![MXR Distortion Plus Output Waveform 1N34A](https://github.com/user-attachments/assets/fd67ff92-7d99-4f47-873c-9c89efcff932)
<br>
### Output Frequency Response
#### F<sub>cdiode</sub> 
F<sub>cdiode</sub> = 1 / 2pi(10K)(1nF) = 15.9K
This attentuation of high frequencies helps with less harmonic amplification and warmer tone
<br>
## 1N4001 Silicon Diode Switch Mod
Using a 6 pin switch, you can add 1N4001 Silicon diodes in series to the germanium diodes for higher headroom and more dynamics since signals above 0.45V get clipped instead of 0.3.
![MXR Distortion Plus Output Waveform 1N34A and 1N4001](https://github.com/user-attachments/assets/0db49670-29b4-4caf-acdf-eb388f843390)
<br>
## Compression Mod
Adding in a switch and 1nF capacitor in parallel to the 10nF input capacitor allows more bass to enter the OP amp. This leads to more comrpession and warmer tone.
F<sub>cinputcap</sub> = 1 / 2pi(686K)(11nF) = 21.09Hz
<br>
## More Gain Mod
Switching R3 and C3 out for a 1K resistor and 0.22uF capacitor leads to a higher gain potential of 48dB max gain with similar frequency response.
![MXR Distortion Plus Gain Mod Frequency Response](https://github.com/user-attachments/assets/92870e6a-fbf2-4575-a58a-743161e95ddd)

<br>

# Circuit Board and Design
This is a 3D render of the original circuit design, gerber files can be found above.
![MXR Distortion Plus 3D Render](https://github.com/user-attachments/assets/c574a7f0-d2c5-405c-947a-842e6ecb2f95)
<br>
# Closing
Hope you got someting out of this guide for building the MXR Distortion Plus pedal. I'll update this repository as I find new information. 
