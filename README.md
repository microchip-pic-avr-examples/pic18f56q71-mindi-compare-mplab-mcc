<!-- Please do not change this logo with link -->

[![MCHP](images/microchip.png)](https://www.microchip.com)

# Comparing Simulation to Reality with PIC18F56Q71

This code example contains the code and analog simulation models for the upcoming video "Comparing Simulation to Reality with PIC18F56Q71". This video will compare an analog simulation to the performance of a real device. 

## Related Documentation

- [Maximizing the Signal: How to Use and Understand Embedded Operational Amplifiers (AN3110)](https://www.microchip.com/en-us/application-notes/an3110)

## Simulation Software

- [MPLAB Mindi&trade; Analog Simulator](#)
- PIC18F56Q71 Mindi Model

See *Mindi Model Installation* for details on installing.

## Development Software

- [MPLAB® X IDE v6.0.5 or newer](#)
- [MPLAB XC8 v2.40.0 or newer](#)
- MPLAB Code Configurator v5.2.2

## Hardware Used

- PIC18F56Q71 Curiosity Nano
- Oscilloscope
- 10x Oscilloscope Probe (with hook adapter)
- Function Generator
- BNC T-Junction (female to 2x male)
- BNC-BNC Cable (female to female)
- BNC (female) to Mini-Hooks Cable

## Hardware Setup

**Warning: Do not apply voltages outside of the absolute maximum ratings to the I/O of the microcontroller. This may cause permanent damage to the device, the Curiosity Nano, and/or the connected computer!**

### Test Setup

*Note: These instructions assume the nano has been programmed. If it has not, make the sure the nano can be connected to a computer for programming after all cables are attached.*

Setup the function generator waveform output. The configured waveform should always remain within the absolute maximum ratings of the microcontroller. (By default, the Curiosity Nano runs at 3.3V.)

For the video, the following waveform settings were used:

| Setting | Value 
| ------- | ----- 
| Waveform | Sine 
| Frequency | 1 kHz 
| Amplitude | 1 Vpp 
| Offset | 500 mV
| Load | Hi-Z

*With the output OFF*, connect the function generator output to the BNC T-Junction. Then, use a BNC-BNC cable to connect one side of the T-junction to your oscilloscope. **After connecting, make sure this oscilloscope channel is set to 1x mode.**

Next, use the BNC to Mini-Hooks cable to connect from the other side of the T-junction to the Curiosity Nano. Connect the ground hook to a GND point or pin, and connect the signal to RB1. Then, connect your 10x oscilloscope probe to RA1 on the nano. For the oscilloscope ground, connect to a ground point or pin on the nano. The gold-plated holes on the USB-side can be used for grounding - but be beware of any electronic components nearby. Alternatively, a female-to-male wire can be used on a ground pin for a suitable connection.

If the nano has been programmed, plug the nano into any USB power supply or port. Finally, enable the output of the function generator to view the OPAMP output.

If the nano has NOT been programmed, connect the nano to the USB of a computer, and perform *Drag-and-Drop programming*, described below. (Alternatively, you can compile from source and program in MPLAB X IDE).

### Drag-and-Drop Programming  

1. On the Github page for this example, go to the Releases section on the right-side of the screen.  
![Github Releases](./images/releases.PNG)  
2. Download and unzip the hex files for the example.
3. Select one of the provided hex files and drag-and-drop the file over the Curiosity Nano icon in the File Explorer. (Both hex files will function identically on device, difference is in memory usage.)  
![Curiosity Icon](./images/curiosityLocation.PNG)
4. If programming is successful, the yellow LED should start blinking.

### Microcontroller I/O Summary

| Pin | Description 
| --- | -----------
| RA1 | OPAMP Output (to oscilloscope)
| RB1 | Analog Input (from function generator)
| RC7 | Blinking LED Indicator

## Mindi Model Installation
1. Download and install MPLAB Mindi.
2. Download the Mindi model for the PIC18F56Q71 family of microcontrollers from Microchip.
3. Drag and drop the model file into the *Command Shell* of Mindi.  
![Mindi Command Shell](./images/commandShell.PNG)
4. There will be a prompt to install the model.  
![Mindi Install Prompt](./images/installPrompt.PNG)  
5. This model can now be found within Mindi.

## Operation

This example implements a simple non-inverting operational amplifier with a gain of 2, as shown below.

// TODO: Image

To compare, a Mindi schematic of this same configuration is provided.

## Summary
This example provides the source code and documentation for the video.