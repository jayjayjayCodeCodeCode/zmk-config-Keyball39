This keeb created by a group of people who loves keyball.

Special Thanks to: <br>
PCB: *[yangxing844](https://github.com/yangxing844)* <br>
Case: *[delock](https://github.com/delock)* <br>
Firmware: *[Amos698](https://github.com/Amos698)* <br>

<img src="keymap-drawer/keyball39.svg" >

## Layers

The default layer uses hold-taps on the thumb cluster so every defined layer is
reachable without extra hardware:

- hold left Alt for `NUM`
- hold Escape for `SNIPE`
- hold Space for `MOUSE`
- hold Alt+Grave for `SCROLL`
- hold Enter for `FUN`
- hold Backspace for `SYM`

The right-half trackball continues to activate the mouse, scroll, and snipe
layers according to its existing PMW3610 configuration. This board has no RGB
LEDs, rotary encoder, joystick, or touch input, so live agent-status lighting
and dial/joystick controls are intentionally out of scope for this firmware.

### Codex command layer

Hold Enter to access `FUN`, then tap the fourth key of its third row (formerly
F12). This activates a one-shot `CODEX` layer for the next keypress. Its first
two rows emit reserved function keys for host-side automations:

| Key position | Action label | Emits |
| --- | --- | --- |
| Q W E R T | New task, approve, reject, voice, review | F13–F17 |
| A S D F G | Debug, refactor, run, stop, next agent | F18–F22 |

These macros deliberately emit F13–F22 rather than guessing undocumented
Codex desktop shortcuts. Bind those keys in a host-side automation or in any
future Codex shortcut configuration. They cannot provide the Codex Micro's
live agent-status lighting or hardware reasoning dial.
