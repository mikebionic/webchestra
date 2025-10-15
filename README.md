# Mike's WebChestra - Documentation

A pure JS browser-based music mixer inspired by Incredibox and Sprunki Beats. Click character icons to layer instrumental loops and create your own beat. Uses Web Audio API - no external libraries needed.

> No, Billy, I haven't done that dance since my wife died...

### Two Types of Sounds:

**1. Drums** (Kick, Snare, Hi-Hat)
- Created using **oscillators** (kick) or **white noise** (snare/hi-hat)
- Kick: Sine wave that pitch-bends from 150Hz → 55Hz
- Snare/Hi-Hat: Filtered noise (bandpass/highpass filters)
- Triggered on an **8-beat loop**

**2. Melodic Instruments** (Bass, Lead)
- Play **specific musical frequencies** from predefined note arrays
- Each note is a short tone burst with volume fade-out
- Follow a **64-beat pattern**
- Bass uses triangle waves, Lead uses square waves

### The Beat Engine

- Runs at **200ms per beat** (300 BPM)
- While any sound is active, a timer triggers notes/drums according to their patterns
- Pattern arrays: `0` = silence, `1-9` = which note to play

## The 5 Instruments

### 🎸 Bass (Triangle Wave)
**Notes**: D2, F2, G2, Bb2, C3, D3, Eb3, F#3, G3 (73.42 - 196.00 Hz)  
Deep bass line that provides the foundation

### 🪘 Kick Drum (Sine Wave)
**Sound**: Pitch drops from 150Hz → 55Hz  
Classic "thump" bass drum on the beat

### 🥁 Snare (Filtered Noise)
**Sound**: White noise through 10kHz bandpass filter  
Sharp snare hits on backbeats

### 🪇 Hi-Hat (Filtered Noise)
**Sound**: White noise through 5kHz highpass filter  
Crispy hi-hat on off-beats

### 🎹 Lead Synth (Square Wave)
**Notes**: G4, A#4, C5, C#5, D5, D#5, F#5, G5, A5 (392.00 - 880.00 Hz)  
Melodic lead playing over the rhythm

## Why These Frequencies?

Musical notes have specific frequencies. For example:
- **A4 = 440 Hz** (standard tuning pitch)
- Lower notes = lower Hz (bass around 73-196 Hz)
- Higher notes = higher Hz (lead around 392-880 Hz)

The code uses exact frequencies to play real musical notes, creating harmony between instruments.

---

**A fun experiment in browser-based sound synthesis** 🎵