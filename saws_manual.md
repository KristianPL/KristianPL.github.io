


https://github.com/user-attachments/assets/38ab3386-ed6c-4cde-bd6d-689910cee5be 



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

[<img width="1301" height="618" alt="Image" src="" />](https://github.com/user-attachments/assets/927cf6f3-479c-45be-913a-7159aa090ed8)


### **Installations guide**


### **Disclaimer**

### **UI overview**

[<img width="1337" height="759" alt="Image" src="https://github.com/user-attachments/assets/07a45029-ec08-4f23-90db-61ac7e8c9d2b" />](https://github.com/user-attachments/assets/07a45029-ec08-4f23-90db-61ac7e8c9d2b)

Below the overall organization and the signal flow logic of the UI. 

[<img width="1209" height="402" alt="Image" src="https://github.com/user-attachments/assets/bcf95bba-74f7-4f08-8226-acf5e1922486" />](https://github.com/user-attachments/assets/bcf95bba-74f7-4f08-8226-acf5e1922486)

### **Oscillators**

[<img width="505" height="255" alt="Image" src="https://github.com/user-attachments/assets/97f26fca-64ae-4eed-be7d-7c0462d57a55" />
](https://github.com/user-attachments/assets/97f26fca-64ae-4eed-be7d-7c0462d57a55)

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

[<img width="393" height="264" alt="Image" src="https://github.com/user-attachments/assets/b0deada9-f57b-417f-95e6-34ce7b995388" />](https://github.com/user-attachments/assets/b0deada9-f57b-417f-95e6-34ce7b995388)

**Voices** and **Type**. Set 1-8 unison voices. When voices is 1, the unison unit is just passed through. 
The "**SuperSaw**" type uses static detuned voices spread out with given detune range, amplitude and pan spread. "**ChorusLike**" unison type uses oscillating detune values spread by a phase difference (frequency set by **Ch. Freq**).
**Detune** and **Distrib**, sets the maximum detune value and the distribution/ spread of the detuned voices, being wide, flat or narrow.  (see appendix for details)
**St.Width** and **Distrib**, sets the stereo pan with and spread function of individual pan positions, being wide, flat or narrow. (see appendix for details).
Asym, is an extra fine tuning parameter causing different effects depending on the unison mode 
**Ch. Freq** set the common frequency for all unison modules, affects the "ChorusLike" unision mode chorusing frequency.

### **Osc mixer**

[<img width="203" height="259" alt="Image" src="https://github.com/user-attachments/assets/07f1c57d-3d67-49b2-9fe9-5e8a437a8556" />](https://github.com/user-attachments/assets/07f1c57d-3d67-49b2-9fe9-5e8a437a8556)

**Vol** and **Pan** mixes the output from the unision module before entering the filter.
**Pre-attack** controls an attack ramp time of the signal before the filter.

### **Filter routing & Mix**

[<img width="516" height="350" alt="Image" src="https://github.com/user-attachments/assets/aa1b4162-3459-4890-be5d-35c94d6a3486" />](https://github.com/user-attachments/assets/aa1b4162-3459-4890-be5d-35c94d6a3486)

After the unision module, the signals can be fed through on of the two independent instances of the filter, F1 and F2. The gain before the filter, and how the oscillator signals are combined, affects the filter drive and saturation.
**O1,O2,O3** to **F1** and **F2** switch board matrix sets the routing.
On the F2 line, it is possible apply **Sat** before and/or after the filter.

**F1 and F2 Mixer**
Final mix of the filter output.

### **Amp Envelope**
[<img width="213" height="344" alt="Image" src="https://github.com/user-attachments/assets/26c394a9-5802-40a8-a4ff-62f1a0ad0a7b" />](https://github.com/user-attachments/assets/26c394a9-5802-40a8-a4ff-62f1a0ad0a7b)

**ADSR** control of the signal.
**Curve** sets the envelope curve form from round to linear.
**DELTA F. ENV** sets a time delay of the AMP Envelope relative to the Filter Envelope. Can be negative or positive, when negative the filter envelope is delayed after the amp envelope. When positive the AMP envelope comes after the filter envelope.

### **Master Out**

[<img width="212" height="277" alt="Image" src="https://github.com/user-attachments/assets/64cbbb9a-b556-4975-ab5c-afd4687414d1" />](https://github.com/user-attachments/assets/64cbbb9a-b556-4975-ab5c-afd4687414d1)

**HP** and  **SHLF THRU** controls a high pass shelve filter of the final output. Shelf through level = 0 resembles a normal 1st order HP filter, increasing the shelf level represents the dry mix level. For shelve values 100% - 200% the filter suppresses the higher frequencies above HP freq, turning the filter into a low pass filter.
Vol and Meter


### **Filters**

[<img width="257" height="293" alt="Image" src="https://github.com/user-attachments/assets/0905a4d9-0959-443b-9879-426326c0792d" />
](https://github.com/user-attachments/assets/0905a4d9-0959-443b-9879-426326c0792d)
**Filter Types** include 5 custom developed filters:

- **LP12 Linear**. Minimum phase distortion, Bessel style, smooth low pass filter.
- **LP12 Bright**. Distorted brighter 12dB filter, good for leads and other voices that must break through the mix
- **LP24 Linear**. Cascaded LP12 minimum phase Bessel style filter.
- **CombLike**. Comb/ notch filter useful in broadband pads
- **LP12 Drive**. Alternative, non linear filter, that changes character depending on drive

Standard filter controls with **Cutoff**, **Res** and  **Contour**
**Keytrack** scales the cutoff sculpting value to the keynumber. 100% scales the note freq to the cutoff. Negative key tracking values can be used to effectivly dampen the higher notes.

### **Filter Envelope**

[<img width="214" height="339" alt="Image" src="https://github.com/user-attachments/assets/0878c30a-4b4d-47d0-9717-f9372a1d45ef" />
](https://github.com/user-attachments/assets/0878c30a-4b4d-47d0-9717-f9372a1d45ef)
**ADSR** standard coltrols
**Pitch ENV**  sets pitch bend to the filter envelope. This is active even when sculpt is 0.
**PW ENV** sets Pulse width and shape to the filter envelope. This is active even when sculpt is 0.


### **Soft Mod**

<img width="216" height="105" alt="Image" src="https://github.com/user-attachments/assets/2ad44f27-68a3-4ceb-9ba4-159d0bdb09eb" />

The SAWS Synth features a "**Soft Mod**" option, where the signal(s) routed to the F2 path (after first optional saturation and before the filter) is used for FM of the OSC1 waveform.
The effect is limited to relative small amplitudes, therefore the name "soft mod". The total modulation amplitude depends on the Soft Mod value and the amplitude of signals routed to F2.
Full FM effect is achieved when OSC1 is a sine waveform. For other waveforms (saw, square, triangle) the FM is limited to positive delta modulation.



### **LFOs**

[<img width="469" height="92" alt="Image" src="https://github.com/user-attachments/assets/bbd7305d-8ee3-4615-863b-fcd270664372" />
](https://github.com/user-attachments/assets/bbd7305d-8ee3-4615-863b-fcd270664372)
The **Sine or Triangle** lever sets the waveform for LFO1 and LFO2 to sine or triangle.  
Freq, Ph. and Att. control the frequency, start phase and attack ramp time of the LFO. In the lower settings of the frequency slider there are options to sync the LFO freq to DAW tempo. 
In the lower range of the phase slider, 2 special modes "Rnd" for random phase onset, and "Scene" for shared running phase of all active voices.

### **LFO1 Dirt**
[<img width="393" height="61" alt="Image" src="https://github.com/user-attachments/assets/bc8a1be8-5b4b-4c8f-9546-71eddde4c6d2" />
](https://github.com/user-attachments/assets/bc8a1be8-5b4b-4c8f-9546-71eddde4c6d2)
Brownian style noise source that can be added independently to the LFO1 signal and associated matrix parameters.
**Color** and  **Ampl** set the noise color and amplitude, where a higher color value has more high frequency content.

### **Vibrato**
[<img width="259" height="130" alt="Image" src="https://github.com/user-attachments/assets/c076bdd2-e514-4f47-9856-df8b28ad181a" />
](https://github.com/user-attachments/assets/c076bdd2-e514-4f47-9856-df8b28ad181a)
**Vibrato**, **pitch** and **Frequency** defines the vibrato of the voice.

### **Matrix**

[<img width="1392" height="328" alt="Image" src="https://github.com/user-attachments/assets/ba5f08f2-b5a4-43c7-8a78-f0daf0a3a1e2" />
](https://github.com/user-attachments/assets/ba5f08f2-b5a4-43c7-8a78-f0daf0a3a1e2)
The SAWS Synth features a simple matrix with selected parameters for assigning effects to the LFOs, Modwheel, pitch wheel and velocity.
LFO1 + Dirt : Pitch, PW for OSC1-3, and cutoff, res and global vol
LFO2 : PW, Vol for OSC1-3, cutoff, res and pan
Modwheel : PW, Vibr, Cutoff, Res
Pitchwheel : Pitch
Velocity : Vol, Cutoff, Res, Sculpt

### **Portamento**

[<img width="312" height="205" alt="Image" src="[https](https://github.com/user-attachments/assets/4311ef4a-5697-4b8e-9f90-281e086199a9)://github.com/user-attachments/assets/4311ef4a-5697-4b8e-9f90-281e086199a9" />
](https://github.com/user-attachments/assets/4311ef4a-5697-4b8e-9f90-281e086199a9)
The overall voice management mode can be set to **Poly**, **Mono** and **Legato**
**Portamento time** sets the glide time between notes. Works in all voice modes.

### **Presets**

[<img width="891" height="114" alt="Image" src="https://github.com/user-attachments/assets/841f052e-5195-4838-9b5d-4c47919c793d" />
](https://github.com/user-attachments/assets/841f052e-5195-4838-9b5d-4c47919c793d)
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

[<img width="883" height="507" alt="Image" src="https://github.com/user-attachments/assets/d351c4f8-00e8-4d4f-94d3-4c51502f2ac1" />
](https://github.com/user-attachments/assets/d351c4f8-00e8-4d4f-94d3-4c51502f2ac1)

St. Width

[<img width="926" height="571" alt="Image" src="https://github.com/user-attachments/assets/01d846ee-ffdb-42cc-ac99-69023bfef041" />
](https://github.com/user-attachments/assets/01d846ee-ffdb-42cc-ac99-69023bfef041)
[<img width="988" height="346" alt="Image" src="https://github.com/user-attachments/assets/566ced5e-9ce6-4a38-a780-990e0c7427f2" />
](https://github.com/user-attachments/assets/566ced5e-9ce6-4a38-a780-990e0c7427f2)


Distrib

[<img width="810" height="459" alt="Image" src="https://github.com/user-attachments/assets/3e8018ef-16f1-4710-9722-a8e7181653c6" />
](https://github.com/user-attachments/assets/3e8018ef-16f1-4710-9722-a8e7181653c6)
Var

[<img width="977" height="534" alt="Image" src="https://github.com/user-attachments/assets/6fe954d9-ca79-44e9-bdcb-a930349169af" />
](https://github.com/user-attachments/assets/6fe954d9-ca79-44e9-bdcb-a930349169af)
Att

