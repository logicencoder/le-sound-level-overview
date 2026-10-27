# Le Sound Level

Windows audio level control by [Logic Encoder](https://logicencoder.com).

Le Sound Level is designed to reduce loud jumps in movies and other shared-mode Windows audio, with a configurable maximum sample level, compression and tone controls.

![Development dashboard preview, synthetic signal](images/dashboard-preview.png)

*Version 5.3 development preview with synthetic meter/spectrum signals. This image is not a live playback measurement.*

## Controls

- Maximum output level in dBFS. More negative values set a quieter digital ceiling; this is not a calibrated physical loudness limit.
- Gentle, Movie and Night compression presets, plus adjustable compression strength.
- Bass, middle and treble EQ, each ±18 dB, and L/R balance.
- Before/after LED meters, green digital readouts and a collapsible output spectrum.
- Settings for audio engines, meter behavior, spectrum, appearance and window preferences; local diagnostics and a log viewer.

## Audio engines

**System DSP** uses the application's own Windows audio component. Equalizer APO, Peace and a virtual cable are not requirements for this mode. Installing the bundled component requires Windows administrator approval.

**Compatibility** uses WASAPI and an existing VB-CABLE installation. It is optional and requires that separate cable component. **Automatic** can fall back to compatibility when its prerequisites are present.

Native processing supports mono, stereo, 5.1 and 7.1 PCM. Movie codecs such as AC-3 must first be decoded by the player. Encoded HDMI/S/PDIF passthrough or audio modes that bypass Windows effects cannot be assumed to be limited. The selected endpoint must show active processor telemetry before relying on its limit.

## Status

This is a development build, not a broadly certified public release. Native DSP, installer transactions and controller behavior have isolated automated coverage; live compatibility and driver coverage remain scoped to tested configurations. A 1.5 ms native lookahead is not a measurement of total A/V or playback latency.

This public repository contains product information and preview images only. Application source is maintained privately. No public binary download is published here yet.

© Logic Encoder. Third-party names identify compatibility only.

## Latest controller patch

Version 5.3.1 cleans up the File menu and expires stale meter telemetry without suppressing genuine quiet audio. The existing preview above shows the 5.3 dashboard layout.

Version 5.3.2 adds **Settings > Inputs > Listen to USB input**, with the current Windows state and changes applied on Save. It controls listening through playback without disabling the input device or changing recording/mute/volume settings. [USB input Settings preview](images/usb-input-settings-preview.png) uses an isolated fixture.

## Version 5.4

- Settings > Inputs lists every Windows recording endpoint, including microphones, line-in, stereo mix and virtual inputs. Active inputs have independent live LED/dBFS meters; unavailable inputs retain their status. Paging prevents clipped controls. Refresh inputs rescans devices. Listen changes apply only on Save, without disabling recording or changing mute/default routes.
- Balance attenuates the opposite side while processing is ON: 50% means -6.02 dB, the edge silences that side, and center restores unity. Mono/center/LFE are preserved.
- Logs separate App events, Native component and Crashes, with UTC timestamps to milliseconds on every new line and repeated timestamps on wrapped display lines. No audio is recorded in logs.

[All-input Settings preview](images/all-inputs-settings-preview.png) uses synthetic fixture devices, not the user's Windows device list. Host verification found all 27 recording endpoints and fresh meter data for the three active inputs; multichannel balance was verified with numerical tests. This is not a universal hardware/stream-mode guarantee.
