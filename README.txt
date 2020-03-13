This is a formant synth based on the cascade/parallel model described by Klatt.

This works best with a Arturia Minilab mkII, as the pads are used to select formants.
Otherwise, the formants are selected using the midi range 36-43



Startup:
1. Open formantTest.pd
2. Check the red toggle button to turn on DSP
3. BEWARE! The first note you play will boom. I don't know why.



Usage:
A mapping of midi keys to consonants and vowels is shown in key_ref.png.

To select a consonant-vowel pair, press the corresponding keys once and press midi
note 43 (right-most pad on minilab) to enter the CV pair.

Queuing up multiple CV pairs is possible. Each midi note played with value at least 
44 will dequeue a CV pair and play it. When all CV pairs are dequeued, and last CV
pair will be repeated until a new CV pair is queued




Known issues:
-The current parameters need more tweaking. Only have a few vowels and consonants 
	sounding correctly
-Interpolation issue for bandwidth causes clicks. Hopefully not an issue in C
-Filter implementation causes a lot of gain loss, making extreme value tweaks necessary



Notes:
-The patch may get glitchy on low power computers (did on my laptop, but ran smoothly 
	on my desktop)
-I added a reverb because I got tired of hearing the raw buzzing sounds. It likely
	won't make it to the final version. 
-Output_Effects, Waveform_Viewer, and a couple other patches are recycled from MUS 172