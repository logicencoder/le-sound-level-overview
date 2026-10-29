# Le Sound Normalizer

![Development dashboard with synthetic signals](images/dashboard-preview.png)

This version 5.5.0 preview uses synthetic signals, not a live playback measurement.

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

This is a development build with automated DSP/controller/package checks and limited host verification, not certification across all Windows systems or playback modes. The clean shareable distribution is one setup EXE with the controller, audio component, runtime libraries and license embedded inside. No adjacent DLLs, icons or development files are needed. A new PC needs setup once to register the system audio component. No public binary download is published in this repository.

The controller is built with C# and Windows Forms; its audio component is C++. Technical source and detailed versioned verification are maintained in the private repository.

[Private source](https://github.com/logicencoder/le-sound-normalizer) · [Logic Encoder](https://logicencoder.com)

Version 5.4.13 fixes meter connection status while muted: connected outputs retain MUTED even when audio blocks stop arriving, while readings clear to the floor.

Version 5.4.14 improves action contrast, enlarges Normalize, unifies application/installer/window icons and delivers the shareable package as a single setup EXE. Existing audio settings are preserved.

## New in 5.5.0

Choose a simple tone panel or a ten-band vertical EQ in Settings > Audio: 31, 63, 125, 250, 500 Hz, 1, 2, 4, 8 and 16 kHz. Each band supports +/-18 dB, and the two views keep their values. A collapsible oscilloscope below the spectrum displays the actual waveform using the same capture source.

The Volume control supports a small preamp boost up to 125% before the limiter while Normalize is ON. L/R balance now sits beside it on the left and snaps to the center. Rounded Normalize ON/OFF controls, silent Help, clear Saved feedback, a single engine chooser, classic option checkboxes and a populated Diagnostics page improve everyday use.

Version 5.5.0 passed 326 native processing scenarios plus controller, UI and standalone installer checks. It was also activated on the existing host: the exact native module was confirmed loaded by Windows Audio and a zero-only playback probe confirmed fresh processing telemetry. The installer contains all application payloads in one file.
