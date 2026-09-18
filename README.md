# Prospero Vibrate

Haptics that move you. A frame-driven studio for the PS4 & PS5 controller's vibration motors.

## Features

- Live control: two sliders drive the large and small motors in real time. Optional motor link, one-touch
  full drive, one-touch release.
- Preset library: 18 curated patterns (heartbeat, alarm, distress SOS, drum roll, earthquake, gunfire,
  ratchet, chirp, metronomes, warmup and cooldown ramps, wave in, wave out, three-pulse burst, low growl,
  high buzz, double tap).
- Custom pattern editor: build a sequence of up to eight steps, each with a large and small level, a
  duration and a fade flag. Save, load and delete named patterns from writable storage.
- Timed play: run any preset (built-in or saved) for a chosen number of seconds and stop automatically.
- Settings: pick between the full and reduced drive ranges, adjust a master intensity that scales every
  pattern, weaken haptics while the built-in microphone is in use, restore defaults.
- Toast messages announce state changes; footer shows current motor levels.

## Controls

- D-pad or Joystick up/down: move focus between controls on the visible tab.
- D-pad or Joystick left/right: change the value under the current control, or switch tabs when focus is on the tab
  row.
- Cross: activate a button or list entry.
- Circle: cancel a modal or exit the app when nothing else consumes the press.
- Options: exit.

## Build

```
setx SHARPPROSPERO_ROOT "<sdk>"
pwsh $SHARPPROSPERO_ROOT/samples/prospero-vibrate/build.ps1 -Output Folder
```

The signed module lands under `out/module/`. Zip that folder to install.

## Persistent storage

Custom patterns land in `/data/prospero-vibrate/patterns/<name>.json`; app settings in
`/data/prospero-vibrate/settings.json`. If the writable path is refused, the app continues from
built-in defaults.
