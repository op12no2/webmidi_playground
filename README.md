# Web MIDI test

A little web MIDI test connecting a browser to a DAW/synth etc. and using Javascript to control it.

I used Windows and Bitwig:-

- Create a virtual MIDI port using loopMIDI. Leave it at the default port name.
- Start Bitwig which auto-detects the port as a controller. Or at least it did in my case; you may need to add it manually.
- Settings → Synchronization → MIDI Clock - select loopMIDI as a sync source (for Play/Stop).
- Start the test: https://op12no2.github.io/webmidi_test/ 

Or clone the repo and run it locally:-
```
cd webmidi_test
python -m http.server 8000
http://localhost:8000
```

There is also a little test for the webmidi.js library here:-

https://op12no2.github.io/webmidi_test/webmidijs.html 

### macOS and Linux (not tested)

On macOS, you'll likely want to use [IAC Driver](https://support.apple.com/en-gb/guide/audio-midi-setup/ams1013/mac) (available through Audio MIDI Setup) instead of loopMIDI to create a virtual MIDI port. Linux users have a few options depending on your setup: if you're running JACK, you can create a virtual MIDI port through QjackCtl, or use [Alsa Loopback](https://www.alsa-project.org/) for a more straightforward approach. The test looks for ports containing "loopMIDI" or "IAC" in the name, so you might need to tweak the port detection code if your virtual port is named something else.

### Links

- https://www.w3.org/TR/webmidi/
- https://www.tobias-erichsen.de/software/loopmidi.html
- https://www.bitwig.com/
- https://midi.org/about-web-midi
- https://webmidijs.org/
 



