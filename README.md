# sine_synth

**Sinewave Synthesis of Speech**


This notebook presents and shows how to use a speech synthesizer that converts formant trajectories into time-varying sinusoidal waves - **sinewave speech**. See for example Remez et al. (1981).

The function sine_synth() requires a pandas dataframe with speech analysis data in these columns:

- sec: Time (seconds) of the frames. The assumption is that these are equally spaced.
- rms: The RMS amplitude of each frame.
- f1,f2,f3,f4: Frequencies (Hz) of the lowest four vowel formants, in the frames.

In our implementation these are produced by the program "ifc_formant" as a tab separated text file.

The overall amplitude contour of the sine wave speech waveform is determined by the RMS contour in the input file. The frequencies of four sine wave components are given by the formant estimates in the input file.

The amplitude of the sine wave speech waveform is scaled to use the full amplitude range available with 16 bit integer samples. Also, short 20ms on-ramp and off-ramp amplitude contours are applied at the beginning and end of the audio file.

This is a python translation of code that Keith Johnson got from Howard Nusbaum, via Alexander Francis, in 1998.

Remez, R. E.; Rubin, P. E.; Pisoni, D. B.; Carrell, T. D. (1981). "Speech perception without traditional speech cues". *Science*. **212** (4497): 947–950. doi:10.1126/science.7233191.
