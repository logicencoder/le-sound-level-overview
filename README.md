# Le Sound Normalizer

![Development dashboard with synthetic signals](images/dashboard-preview.png)

This version 5.4.12 preview uses synthetic signals, not a live playback measurement.

Normalizes loud scenes for more comfortable listening. Set an output ceiling, then adjust compression sensitivity to reduce the difference between quiet dialogue and loud effects.

- **Soft 23%**, **Balanced 42%**, **NMS 66%** compression starting points, plus an adjustable sensitivity slider.
- **Output level** sets the digital peak ceiling. **Volume** controls everyday listening volume.
- Bass, middle and treble controls, left/right balance, green digital meters and a collapsible frequency spectrum.
- Save and load your own sound presets. Settings remember your preferences and window layout.
- A speaker button mutes or unmutes the selected Windows output only when clicked.
- Recording-input meters and explicit Enable/Disable listening actions, applied on Save.
- Short Help, purpose-focused About and local application/native/crash diagnostics.

## Audio paths

System DSP uses the application's own Windows audio component. It does not require Equalizer APO, Peace or a virtual cable. Setup requires administrator approval once; normal controller use does not. Compatibility is an optional alternative using WASAPI and an existing VB-CABLE installation.

Native processing supports mono, stereo, 5.1 and 7.1 PCM. The player must decode compressed audio to PCM. Encoded HDMI/S/PDIF passthrough and paths bypassing Windows audio effects cannot be assumed to receive the ceiling. Digital dBFS readings are not physical sound-pressure measurements. Spectrum bars show individual frequency components; LED meters show the full-signal peak, so their values differ.

## Availability and verification

This is a development build with automated DSP/controller/package checks and limited host verification, not certification across all Windows systems or playback modes. The clean distribution contains the controller, bundled setup, runtime libraries and license, without development material. A new PC needs setup once to register the system audio component. No public binary download is published in this repository.

The controller is built with C# and Windows Forms; its audio component is C++. Technical source and detailed versioned verification are maintained in the private repository.

[Private source](https://github.com/logicencoder/le-sound-normalizer) · [Logic Encoder](https://logicencoder.com)

Version 5.4.13 fixes meter connection status while muted: connected outputs retain MUTED even when audio blocks stop arriving, while readings clear to the floor.
