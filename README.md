# AudioMixer (WIP)
I've been interested in analog electronics and electronic instruments for a decent chunk of my time in college so I wanted to try my hand at creating an [audio mixer](https://youtu.be/q8tmUgaXrEQ?si=oKsCojngbPTezQQb&t=1473) using a design I found online. This will be the first part of a bigger project where I hope to make a few different analog synthesizer modules and use the mixer to, well, mix them together. :)

### Table of Contents
1. [Initial Simulations](https://github.com/Jumpin-Josh/AudioMixer/blob/main/README.md#initial-simulations)
   - Audio Mixer
   - Module 1: [Wave Folder](https://github.com/Jumpin-Josh/AudioMixer/blob/main/README.md#module-1-double-wave-folder)
   - Module 2: [Distortion Module](https://github.com/Jumpin-Josh/AudioMixer/blob/main/README.md#module-2-distortion)
   - Module 3: [Voltage Controlled Filter (VCF)](https://github.com/Jumpin-Josh/AudioMixer/blob/main/README.md#module-3-vcf)
2. [Breadboard Prototyping](https://github.com/Jumpin-Josh/AudioMixer/blob/main/README.md#breadboard-prototyping)
   - Audio Mixer
   - Module 1: [Wave Folder]()
   - Module 2: [Distortion Module]()
   - Module 3: [VCF]()
3. [PCB Design and Circuit Assembly](https://github.com/Jumpin-Josh/AudioMixer/blob/main/README.md#pcb-design-and-circuit-assembly)
4. [Enclosure Design](https://github.com/Jumpin-Josh/AudioMixer/blob/main/README.md#enclosure-design)
5. [Final Product and Closing Thoughts](https://github.com/Jumpin-Josh/AudioMixer/blob/main/README.md#final-product-and-closing-thoughts)

## Initial Simulations
Cause who doesn't enjoy a little circuit simulation? It's the LT*Spice* of life!
### Audio Mixer Design
![alt text](https://github.com/Jumpin-Josh/AudioMixer/blob/main/simulations/Mixer%20Circuit.png "Initial Mixer Design in LTSpice")
All three of the 100k potentiometers are setup like voltage dividers allowing each input to be attenuated independently. The inputs are tied together and fed into two inverting buffers<sup>1</sup> to boost the resulting signal since the input pots may reduce the amplitude. The 20k potentiometer is used to tune the clipping on the mixer's output which is then fed into a non-inverting buffer. The .step directive is used to sweep through multiple potentiometer values to see how it will affect the signal.

[1]: The first inverting buffer sums the input signals while the second buffer negates the first inversion in case I want to mix in a control voltage (CV) from a low frequency oscillator (LFO) or envelope generator (I plan on building both in future).
### Signal Analysis
![alt text](https://github.com/Jumpin-Josh/AudioMixer/blob/main/simulations/Mixer%20Waveforms%201.png "Input and output signals of the mixer")
Above are the input and output waveforms of the mixer with all input pots at max "volume".
#### Closer look at the output signal
![alt text](https://github.com/Jumpin-Josh/AudioMixer/blob/main/simulations/Mixer%20Waveforms%202.png "Output signal")
Note the signal has some clipping as it reaches the supply voltages even though this is the raw output.
#### Effect of the clipping diodes
![alt text](https://github.com/Jumpin-Josh/AudioMixer/blob/main/simulations/Mixer%20Waveforms%203.png "Sweep of the cliping potentiometers")
Simulation of the output signal with no, half, and max clipping.

### Module 1: Wave Folder
Under Construction.
### Module 2: Distortion
Under Construction.
### Module 3: VCF
Under Construction.
---------------------------------------------------------------------------------------------------------------------------------------------------
## Breadboard Prototyping
Not as edible as they sound.
### Breadboard Design
![alt text](https://github.com/Jumpin-Josh/AudioMixer/blob/main/pictures/1_MixerPic.jpg "Inital Breadboard Layout")
The [workstation](https://www.ericasynths.lv/edu-diy-labor/) i'm using lets me set up jack sockets, potentiometers, switches and buttons off the breadboard so I have more space. It also has a module that can act as an osiloscope, lissajous curve plotter, spectrum analyzer, voltmeter and even tuner.

I cut out the three seperate outputs for now to simplify the wiring. I also swapped out the feedback resistor in the second amplifier for a 1M resistor so it has a gain of 10. Paired with the 250k potentiometer I put in place of the 20k, the mixer will always output a signal that can be distorted.

### Wave Analysis
Here are some highlights from my wave anylsis.

My synth has 3 oscilators that ouput either sawtooth or square waves. I had it output a single sawtooth for easier viewing.
![alt text](https://github.com/Jumpin-Josh/AudioMixer/blob/main/pictures/2_Sawtooth1.jpg "Sawtooth output")

Unclipped
![alt text](https://github.com/Jumpin-Josh/AudioMixer/blob/main/pictures/3_Sawtooth2.jpg "Sawtooth closeup")

Clipped
![alt text](https://github.com/Jumpin-Josh/AudioMixer/blob/main/pictures/4_ClippedSaw.jpg "Clipped sawtooth")

By lowering the cutoff frequency of the synth's low-pass filter I can shape the sawtooth into a sine wave.
![alt text](https://github.com/Jumpin-Josh/AudioMixer/blob/main/pictures/5_Sine.jpg "Sine wave")

And when clipped it resembles a square wave.
![alt text](https://github.com/Jumpin-Josh/AudioMixer/blob/main/pictures/6_ClippedSine.jpg "Clipped sine")

The workstation has an in built oscillator that can be adjusted from just before the upper limit of human hearing to well below it. I did some additional testing using the oscillator as an LFO and mixing it with the output of the synthesizer and found that it caused the synth's signal to sit on top of the lower frequency the same way a boat would sit atop an ocean wave.


## PCB Design and Circuit Assembly
## Enclosure Design
## Final Product and Closing Thoughts
