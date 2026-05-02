
![title](){: width="100px"}
![titlen](){: .float-left}
![title](){: .medium-size}
![title](){: .card-img}



![Front page](https://github.com/user-attachments/assets/c3270e34-230a-4b87-b8ca-735411a9b412){: .full-width}





**Copyright** 

**Contact**


### **Design**

Building on classic subtractive principles, the SAWS Synth is a virtual analog synthesizer featuring 8 voice polyphony, 3 oscillators, extended 8-voice unison control and a full stereo path architecture.
The single-page layout displays all parameter values in plain view for the active patch.
By use of classic subtractive elements the synth targets musical synth sounds, with dynamic wide stereo image, phase control and precise attack tuning. Dirt and drift noise can be added to main parameters for an analog feel.
It uses a ring buffer and BLEP techniques for effective quality antialiasing with variable cutoff strength.
It features 4 fully in-house developed unconventional resonant and distorted low pass filters which covers: 1) linear phase Bessel filters, 2) a brighter lattice 12 dB and 24 dB, a CombEffect filter for pads and finallt a 12 dB Bessel filter variant with experimental distortion/drive
Selected functions targeting musical tones withing the range of virtual analog principles. Notably missing osc sync, only one lfo waveform (sine), limited phase modulation (softmod), fairly limited modulation matrix.



### **Signal path** 


![title](https://github.com/user-attachments/assets/a146ad89-db86-4a25-bab6-6f8c55adc5cd){: .medium-size}




### **Installations guide**


### **Disclaimer**

### **UI overview**

![title](https://github.com/user-attachments/assets/a38e3f45-08fb-4235-9c00-2196a1c336c4){: .medium-size}



Below the overall organization and the signal flow logic of the UI. 



![title](https://github.com/user-attachments/assets/907da503-07e6-40b1-bd77-82a29b16a92e){: .medium-size}


### **Oscillators**


![titlen](https://github.com/user-attachments/assets/b8f78be1-095b-4038-ae67-7fd8e5d1fa34){: .float-left}


**Type**, select waveform: Saw, Square, Triangle and Noise
**Oct**, **Pitch** and **Detune** sets the oscillator tuning at respectively levels; octave, semi tones and fine tuning 
**Phase** and **Ph. Rnd** set the start phase of the oscillator and the amount of randomness of the start phase. 
**PW / Shp** sets the pulse width of square waveform, and morph shape of the triangle (triangle-to-saw morph).
**BLEP fc** sets the cutoff value of the BLEP waveform used for the fundamental antialiasing filter. Fc = 0.45 corresponds to a cutoff close to Nyquist producing bright tone, while a lower value e.g 0.25 yields a warmer sound with stronger aliasing suppression. 
3 special BLEP modes are found when turning the slider to 0 includes, for special BLEP lowpass filters variants that alterns the fundamental waveform sound/grit
- "**ResGrit**" using a BLEP with more resonant cutoff
- "**c64Grit**" lower cutoff and wider res peak somehow resembling HP filter gritty sound of the c64
- "**LeakyGrit**" imperfect lowpass filter with 2 extra pass band lobes

### **Unison**


![titlen](https://github.com/user-attachments/assets/8f1c74c1-d3c5-42d1-ab45-3ed794a73101){: .float-left}



**Voices** and **Type**. Set 1-8 unison voices. When voices is 1, the unison unit is just passed through. 
The "**SuperSaw**" type uses static detuned voices spread out with given detune range, amplitude and pan spread. "**ChorusLike**" unison type uses oscillating detune values spread by a phase difference (frequency set by **Ch. Freq**).
**Detune** and **Distrib**, sets the maximum detune value and the distribution/ spread of the detuned voices, being wide, flat or narrow.  (see appendix for details)
**St.Width** and **Distrib**, sets the stereo pan with and spread function of individual pan positions, being wide, flat or narrow. (see appendix for details).
Asym, is an extra fine tuning parameter causing different effects depending on the unison mode 
**Ch. Freq** set the common frequency for all unison modules, affects the "ChorusLike" unision mode chorusing frequency.

### **Osc mixer**

![titlen](https://github.com/user-attachments/assets/3e3afdd5-9fbc-4105-95b0-d0053100a373){: .float-left}



**Vol** and **Pan** mixes the output from the unision module before entering the filter.
**Pre-attack** controls an attack ramp time of the signal before the filter.

### **Filter routing & Mix**


![titlen](https://github.com/user-attachments/assets/8986df42-800e-473c-ab17-a7d7ded75b0e){: .float-left}


After the unision module, the signals can be fed through on of the two independent instances of the filter, F1 and F2. The gain before the filter, and how the oscillator signals are combined, affects the filter drive and saturation.
**O1,O2,O3** to **F1** and **F2** switch board matrix sets the routing.
On the F2 line, it is possible apply **Sat** before and/or after the filter.

**F1 and F2 Mixer**
Final mix of the filter output.

### **Amp Envelope**

![titlen](https://github.com/user-attachments/assets/02a15eb2-ecc7-4549-ac74-6f384ab15a36){: .float-left}



**ADSR** control of the signal.
**Curve** sets the envelope curve form from round to linear.
**DELTA F. ENV** sets a time delay of the AMP Envelope relative to the Filter Envelope. Can be negative or positive, when negative the filter envelope is delayed after the amp envelope. When positive the AMP envelope comes after the filter envelope.

### **Master Out**

![titlen](https://github.com/user-attachments/assets/e46512bf-4f24-4e74-8c50-3286a417c16c){: .float-left}



**HP** and  **SHLF THRU** controls a high pass shelve filter of the final output. Shelf through level = 0 resembles a normal 1st order HP filter, increasing the shelf level represents the dry mix level. For shelve values 100% - 200% the filter suppresses the higher frequencies above HP freq, turning the filter into a low pass filter.
Vol and Meter


### **Filters**


![titlen](https://github.com/user-attachments/assets/144f6baa-3157-45b0-939e-695eb80798b1){: .float-left}



**Filter Types** include 5 custom developed filters:

- **LP12 Linear**. Minimum phase distortion, Bessel style, smooth low pass filter.
- **LP12 Bright**. Distorted brighter 12dB filter, good for leads and other voices that must break through the mix
- **LP24 Linear**. Cascaded LP12 minimum phase Bessel style filter.
- **CombLike**. Comb/ notch filter useful in broadband pads
- **LP12 Drive**. Alternative, non linear filter, that changes character depending on drive

Standard filter controls with **Cutoff**, **Res** and  **Contour**
**Keytrack** scales the cutoff sculpting value to the keynumber. 100% scales the note freq to the cutoff. Negative key tracking values can be used to effectivly dampen the higher notes.

### **Filter Envelope**

![titlen](https://github.com/user-attachments/assets/d19d317a-8df8-44ef-87dd-080d737b317f){: .float-left}


 
**ADSR** standard coltrols
**Pitch ENV**  sets pitch bend to the filter envelope. This is active even when sculpt is 0.
**PW ENV** sets Pulse width and shape to the filter envelope. This is active even when sculpt is 0.


### **Soft Mod**


![titlen](https://github.com/user-attachments/assets/2fafc8d3-5957-494b-9f2b-1ca23ca1a07d){: .float-left}



The SAWS Synth features a "**Soft Mod**" option, where the signal(s) routed to the F2 path (after first optional saturation and before the filter) is used for FM of the OSC1 waveform.
The effect is limited to relative small amplitudes, therefore the name "soft mod". The total modulation amplitude depends on the Soft Mod value and the amplitude of signals routed to F2.
Full FM effect is achieved when OSC1 is a sine waveform. For other waveforms (saw, square, triangle) the FM is limited to positive delta modulation.



### **LFOs**

![titlen](https://github.com/user-attachments/assets/7fdc7980-4d07-4195-9e3e-cbe149739c0){: .float-left}



The **Sine or Triangle** lever sets the waveform for LFO1 and LFO2 to sine or triangle.  
Freq, Ph. and Att. control the frequency, start phase and attack ramp time of the LFO. In the lower settings of the frequency slider there are options to sync the LFO freq to DAW tempo. 
In the lower range of the phase slider, 2 special modes "Rnd" for random phase onset, and "Scene" for shared running phase of all active voices.

### **LFO1 Dirt**
 
![titlen](https://github.com/user-attachments/assets/dc6d77e2-67ee-495f-a99c-e4c010c61b18){: .float-left}



Brownian style noise source that can be added independently to the LFO1 signal and associated matrix parameters.
**Color** and  **Ampl** set the noise color and amplitude, where a higher color value has more high frequency content.

### **Vibrato**

![titlen](https://github.com/user-attachments/assets/6beffdfd-7616-48d7-9a0e-6af5921dd4c2){: .float-left}




**Vibrato**, **pitch** and **Frequency** defines the vibrato of the voice.

### **Matrix**

![titlen](https://github.com/user-attachments/assets/8dc01325-8b50-4f0d-9d1d-525ff8ad3e3b){: .float-left}




The SAWS Synth features a simple matrix with selected parameters for assigning effects to the LFOs, Modwheel, pitch wheel and velocity.
LFO1 + Dirt : Pitch, PW for OSC1-3, and cutoff, res and global vol
LFO2 : PW, Vol for OSC1-3, cutoff, res and pan
Modwheel : PW, Vibr, Cutoff, Res
Pitchwheel : Pitch
Velocity : Vol, Cutoff, Res, Sculpt

### **Portamento**

![titlen](https://github.com/user-attachments/assets/b06cfcbc-ed9f-4651-86bc-ad26360ad403){: .float-left}




The overall voice management mode can be set to **Poly**, **Mono** and **Legato**
**Portamento time** sets the glide time between notes. Works in all voice modes.

### **Presets**

![titlen](https://github.com/user-attachments/assets/455e69d9-1c87-4d99-9709-5a2c4c750aea){: .float-left}




The presets are managed the (xml) files located in the file folders: "User", "Factory" and "Reference"
A given voice parameter state can be saved as a user preset.
Due to the simple menu structure, prefixes in the patch names may be used to organize voices into categories:

BE - Bells
BS - Basses
ENS - Acoustic instruments and ensembles
KE - Keys
LE - Leads
PD - Pads
PEC - Percussion
PLK - pluck sounds
PO - poly synths

**Reference sound** button toggles the reference sound patch (first file in the "Reference" folder) temporarily, to allow comparison with reference sound levels, etc.
Your previous batch will reappear when the the ref sound button is turned off again. Note, dont try to change parameters, or save presets when ref sound is on, you may lose your original patch.

**Specifications**

### **Appendix**

Unison detune and distribution models


Distrib


![title](https://github.com/user-attachments/assets/21f16e55-d90f-41ea-a5ae-aaeb74e695ed)



St. Width


![title](https://github.com/user-attachments/assets/3cf48c34-1608-46e5-af02-4242ad45f7ef)




![title](https://github.com/user-attachments/assets/c3ef8b10-7fff-4ac1-8985-1aab7664211f)



Distrib


![title](https://github.com/user-attachments/assets/4991a553-a344-4083-a97e-44da6fccec0a)




Var
![title](https://github.com/user-attachments/assets/3755292b-c36c-4364-8595-7278c2dc430)

 



Att

