# DIY Distortion Plus Guitar Pedal

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
The pedal uses the LM741CN to cleanly amplify the guitar signal. 
- Starting at the source, the pedal runs off of 9V and feeds into the LM741. Then runs through a voltage divider with two 1Mohm resistors along with a 1nF capacitor to divide the voltage to 4.5V and smooth out any ripples from the 9V source
- The guitar signal runs through a 1nF capacitor to ground to remove RF noise and other noise from te guitar signal. Then runs through a 10nF decoupling capacitor and 10k resistor that blocks any DC signals and attenuates the bass signals. Which then combines with the power supply impedance to feed into the non inverting op amp input.


![Screenshot 2025-02-21 230755](https://github.com/user-attachments/assets/1f3b2574-f1f2-4dc1-b12c-27e2e4ed4e9a)


# Circuit Board and Design
This is a 3D render of the original circuit design
![MXR Distortion Plus 3D Render](https://github.com/user-attachments/assets/c574a7f0-d2c5-405c-947a-842e6ecb2f95)

# Closing
Hope you got someting out of this guide for building the MXR Distortion Plus pedal. I'll update this repository as I find new information. 
