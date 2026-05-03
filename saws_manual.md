

![Front page](https://github.com/user-attachments/assets/17847f58-f52f-4f7c-b41f-93a5e856adae){: .full-width}

* TOC
{:toc}

**Copyright** 

© 2026 Kristian Pontoppidan Larsen. All rights reserved.

### **Installation Guide**

### **Design**

Building on classic subtractive principles, the SAWS Synth is a virtual analog synthesizer featuring 8 voice polyphony, 3 oscillators, extended 8-voice unison control and a full stereo path architecture.<br>
The single-page layout displays all parameter values in plain view for the active patch.<br>
By use of classic subtractive elements the synth targets musical synth sounds, with dynamic wide stereo image, phase control and precise attack tuning. Dirt and drift noise can be added to main parameters for an analog feel.<br>
It uses a ring buffer and BLEP techniques for effective quality antialiasing with variable cutoff strength.
It features 4 fully in-house developed unconventional resonant and distorted low pass filters which covers: 1) linear phase Bessel filters, 2) a brighter lattice 12 dB and 24 dB, a CombEffect filter for pads and finallt a 12 dB Bessel filter variant with experimental distortion/drive
Selected functions targeting musical tones withing the range of virtual analog principles. Notably missing osc sync, only one lfo waveform (sine), limited phase modulation (softmod), fairly limited modulation matrix.



### **Signal path** 


![title](https://github.com/user-attachments/assets/a146ad89-db86-4a25-bab6-6f8c55adc5cd){: .medium-size}



### **Disclaimer**

This software synthesizer is provided free of charge and is currently in  _beta testing_ . It may contain bugs or unintended behaviors.

_Warning: Loud Audio Output_
This plugin is capable of generating sudden, high-volume, or unexpected sounds, including due to software errors or instability. Users should take appropriate precautions, including:  1) _Keeping monitoring levels at a safe volume_; 2) _Avoiding headphone use at high levels during testing_<br>

By using this software, you acknowledge that you do so at your own risk. This software is provided “as is”, without warranty of any kind, express or implied.<br>


### **UI overview**

![title](https://github.com/user-attachments/assets/a38e3f45-08fb-4235-9c00-2196a1c336c4){: .medium-size}

The overall organization and the signal flow logic of the UI. <br>

![title](https://github.com/user-attachments/assets/ecbc46dc-3289-4f23-bfae-de76d0bb2bf9){: .medium-size}




### **Oscillators**

<img src="https://github.com/user-attachments/assets/b8f78be1-095b-4038-ae67-7fd8e5d1fa34" >

**Type**, select waveform: Saw, Square, Triangle and Noise<br>
**Oct**, **Pitch** and **Detune** sets the oscillator tuning at respectively levels; octave, semi tones and fine tuning. <br>
**Phase** and **Ph. Rnd** set the start phase of the oscillator and the amount of randomness of the start phase. <br>
**PW / Shp** sets the pulse width of square waveform, and morph shape of the triangle (triangle-to-saw morph).<br>
**BLEP fc** sets the cutoff value of the BLEP waveform used for the fundamental antialiasing filter. Fc = 0.45 corresponds to a cutoff close to Nyquist producing bright tone, while a lower value e.g 0.25 yields a warmer sound with stronger aliasing suppression. <br>
3 special BLEP modes are found when turning the slider to 0 includes, for special BLEP lowpass filters variants that alterns the fundamental waveform sound/grit
- "**ResGrit**" using a BLEP with more resonant cutoff
- "**c64Grit**" lower cutoff and wider res peak somehow resembling HP filter gritty sound of the c64
- "**LeakyGrit**" imperfect lowpass filter with 2 extra pass band lobes

### **Unison**

<img src="https://github.com/user-attachments/assets/8f1c74c1-d3c5-42d1-ab45-3ed794a73101" >

**Voices** and **Type**. Set 1-8 unison voices. When voices is 1, the unison unit is just passed through. <br>
The "**SuperSaw**" type uses static detuned voices spread out with given detune range, amplitude and pan spread. "**ChorusLike**" unison type uses oscillating detune values spread by a phase difference (frequency set by **Ch. Freq**).<br>
**Detune** and **Distrib**, sets the maximum detune value and the distribution/ spread of the detuned voices, being wide, flat or narrow.  (see appendix for details).<br>
**St.Width** and **Distrib**, sets the stereo pan with and spread function of individual pan positions, being wide, flat or narrow. (see appendix for details).<br>
Asym, is an extra fine tuning parameter causing different effects depending on the unison mode <br>
**Ch. Freq** set the common frequency for all unison modules, affects the "ChorusLike" unision mode chorusing frequency.<br>

### **Osc mixer**

<img src="https://github.com/user-attachments/assets/3e3afdd5-9fbc-4105-95b0-d0053100a373" >

**Vol** and **Pan** mixes the output from the unision module before entering the filter.<br>
**Pre-attack** controls an attack ramp time of the signal before the filter.<br>

### **Filter routing & Mix**

<img src="https://github.com/user-attachments/assets/8986df42-800e-473c-ab17-a7d7ded75b0e" >

After the unision module, the signals can be fed through on of the two independent instances of the filter, F1 and F2. The gain before the filter, and how the oscillator signals are combined, affects the filter drive and saturation.<br>
**O1,O2,O3** to **F1** and **F2** switch board matrix sets the routing.<br>
On the F2 line, it is possible apply **Sat** before and/or after the filter.<br>

**F1 and F2 Mixer**
Final mix of the filter output.<br>

### **Amp Envelope**

<img src="https://github.com/user-attachments/assets/02a15eb2-ecc7-4549-ac74-6f384ab15a36" >

**ADSR** control of the signal.<br>
**Curve** sets the envelope curve form from round to linear.<br>
**DELTA F. ENV** sets a time delay of the AMP Envelope relative to the Filter Envelope. Can be negative or positive, when negative the filter envelope is delayed after the amp envelope. When positive the AMP envelope comes after the filter envelope.<br>

### **Master Out**


<img src="https://github.com/user-attachments/assets/e46512bf-4f24-4e74-8c50-3286a417c16c" >

**HP** and  **SHLF THRU** controls a high pass shelve filter of the final output. Shelf through level = 0 resembles a normal 1st order HP filter, increasing the shelf level represents the dry mix level. For shelve values 100% - 200% the filter suppresses the higher frequencies above HP freq, turning the filter into a low pass filter.
Vol and Meter.<br>


### **Filters**

<img src="https://github.com/user-attachments/assets/144f6baa-3157-45b0-939e-695eb80798b1" >

**Filter Types** include 5 custom developed filters:

- **LP12 Linear**. Minimum phase distortion, Bessel style, smooth low pass filter.
- **LP12 Bright**. Distorted brighter 12dB filter, good for leads and other voices that must break through the mix
- **LP24 Linear**. Cascaded LP12 minimum phase Bessel style filter.
- **CombLike**. Comb/ notch filter useful in broadband pads
- **LP12 Drive**. Alternative, non linear filter, that changes character depending on drive

Standard filter controls with **Cutoff**, **Res** and  **Contour**<br>
**Keytrack** scales the cutoff sculpting value to the keynumber. 100% scales the note freq to the cutoff. Negative key tracking values can be used to effectivly dampen the higher notes.<br>

### **Filter Envelope**


<img src="https://github.com/user-attachments/assets/d19d317a-8df8-44ef-87dd-080d737b317f" >
 
**ADSR** standard coltrols.<br>
**Pitch ENV**  sets pitch bend to the filter envelope. This is active even when sculpt is 0.<br>
**PW ENV** sets Pulse width and shape to the filter envelope. This is active even when sculpt is 0.<br>


### **Soft Mod**



<img src="https://github.com/user-attachments/assets/2fafc8d3-5957-494b-9f2b-1ca23ca1a07d" >

The SAWS Synth features a "**Soft Mod**" option, where the signal(s) routed to the F2 path (after first optional saturation and before the filter) is used for FM of the OSC1 waveform.<br>
The effect is limited to relative small amplitudes, therefore the name "soft mod". The total modulation amplitude depends on the Soft Mod value and the amplitude of signals routed to F2.<br>
Full FM effect is achieved when OSC1 is a sine waveform. For other waveforms (saw, square, triangle) the FM is limited to positive delta modulation.<br>



### **LFOs**

<img src="https://github.com/user-attachments/assets/744a0923-cfa0-449e-8864-200006925eff" >

The **Sine or Triangle** lever sets the waveform for LFO1 and LFO2 to sine or triangle.  <br>
Freq, Ph. and Att. control the frequency, start phase and attack ramp time of the LFO. In the lower settings of the frequency slider there are options to sync the LFO freq to DAW tempo. <br>
In the lower range of the phase slider, 2 special modes "Rnd" for random phase onset, and "Scene" for shared running phase of all active voices.<br>

### **LFO1 Dirt**
 

<img src="https://github.com/user-attachments/assets/dc6d77e2-67ee-495f-a99c-e4c010c61b18" >

Brownian style noise source that can be added independently to the LFO1 signal and associated matrix parameters.<br>
**Color** and  **Ampl** set the noise color and amplitude, where a higher color value has more high frequency content.<br>

### **Vibrato**


<img src="https://github.com/user-attachments/assets/6beffdfd-7616-48d7-9a0e-6af5921dd4c2" >


**Vibrato**, **pitch** and **Frequency** defines the vibrato of the voice.<br>

### **Matrix**


<img src="https://github.com/user-attachments/assets/8dc01325-8b50-4f0d-9d1d-525ff8ad3e3b" >


The SAWS Synth features a simple matrix with selected parameters for assigning effects to the LFOs, Modwheel, pitch wheel and velocity.<br>
LFO1 + Dirt : Pitch, PW for OSC1-3, and cutoff, res and global vol<br>
LFO2 : PW, Vol for OSC1-3, cutoff, res and pan<br>
Modwheel : PW, Vibr, Cutoff, Res<br>
Pitchwheel : Pitch<br>
Velocity : Vol, Cutoff, Res, Sculpt<br>

### **Portamento**


<img src="https://github.com/user-attachments/assets/b06cfcbc-ed9f-4651-86bc-ad26360ad403" >


The overall voice management mode can be set to **Poly**, **Mono** and **Legato**.<br>
**Portamento time** sets the glide time between notes. Works in all voice modes.<br>

### **Presets**

<img src="https://github.com/user-attachments/assets/455e69d9-1c87-4d99-9709-5a2c4c750aea" >



The presets are managed the (xml) files located in the file folders: "User", "Factory" and "Reference".<br>
A given voice parameter state can be saved as a user preset.<br>
Due to the simple menu structure, prefixes in the patch names may be used to organize voices into categories:<br>

BE - Bells<br>
BS - Basses<br>
IN - Acoustic instruments and ensembles<br>
KE - Keys<br>
LE - Leads<br>
PD - Pads<br>
PEC - Percussion<br>
PLK - pluck sounds<br>
PO - poly synths<br>

**Reference sound** button toggles the reference sound patch (first file in the "Reference" folder) temporarily, to allow comparison with reference sound levels, etc.
Your previous batch will reappear when the the ref sound button is turned off again. Note, dont try to change parameters, or save presets when ref sound is on, you may lose your original patch.<br>

**Specifications**

### **Appendix**

Unison detune and distribution models.<br>

Distrib



<img src="https://github.com/user-attachments/assets/21f16e55-d90f-41ea-a5ae-aaeb74e695ed" >

St. Width



<img src="https://github.com/user-attachments/assets/3cf48c34-1608-46e5-af02-4242ad45f7ef" >




<img src="https://github.com/user-attachments/assets/c3ef8b10-7fff-4ac1-8985-1aab7664211f" >
Distrib



<img src="https://github.com/user-attachments/assets/4991a553-a344-4083-a97e-44da6fccec0a" >


Var

 
<img src="https://github.com/user-attachments/assets/3755292b-c36c-4364-8595-7278c2dc430" >


Att

