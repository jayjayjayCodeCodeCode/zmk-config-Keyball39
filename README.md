This keeb created by a group of people who loves keyball.

Special Thanks to: <br>
PCB: *[yangxing844](https://github.com/yangxing844)* <br>
Case: *[delock](https://github.com/delock)* <br>
Firmware: *[Amos698](https://github.com/Amos698)* <br>

<img src="keymap-drawer/keyball39.svg" >

## Layers

The default layer keeps ordinary macOS modifiers intact:

- `LCTRL` and `LALT` (Option) remain normal keys
- the inner left thumb is `LGUI` (Command)
- tap Escape for Escape; hold it for `CMD` with macOS Command held
- hold Space for `MOUSE`
- hold the former Command position for `SCROLL` (tap emits Command+Grave for macOS window cycling)
- Enter remains Enter
- hold Backspace for `SYM`

Moving the right-half trackball activates `AUTO_MOUSE` for 700 ms. While it is
active, J is left click, L is right click, and semicolon is middle click; every
other position passes through to normal typing. Hold Space for the richer
`MOUSE` layer with numbers, arrows, page movement, and the same click cluster.
While holding Space, tap B for a plain Tab or hold G for precision `SNIPE`.
Hold the Scroll layer-tap key in the former Command position to scroll with the
ball.

Maintenance actions require deliberate layer-restricted chords: hold Space,
hold G, and press Q+W together to enter the bootloader; hold Backspace and press
Q+W together to clear Bluetooth pairings. Bluetooth profile selection remains
on the `SYM` layer. This board has no RGB LEDs, rotary encoder, joystick, or
touch input, so live agent-status lighting and dial/joystick controls are
intentionally out of scope for this firmware.

### macOS Command layer

Tap Escape normally to send Escape. Hold Escape to activate `CMD` while holding
macOS Command. Keep Escape held and tap W repeatedly to move forward through
the macOS application switcher, or Q to move backward; release Escape to select
the application. Left Control and Left Option remain ordinary modifiers, and
the inner-thumb Command key remains available for shortcuts such as Command+W,
Command+C, and Command+V.

| Key | Action |
| --- | --- |
| W | Tab while Command is held (next application) |
| Q | Shift+Tab while Command is held (previous application) |
| E | Arm the one-shot `CODEX` layer |
| A / S / D / F / G | Command+1 / Command+2 / Command+3 / Command+4 / Command+5 |
| O / P | Command+- / Command++ (zoom out / in) |
| K / L | Command+{ / Command+} |

All other `CMD` positions are transparent, so the held Command modifier applies
to their normal base keys. Command+Grave remains available by tapping the
Scroll layer-tap key in the former Command position.

### Codex and macOS controls layer

The former `FUN` layer is now `CODEX`; F1-F12 are intentionally removed. Enter
it for one keypress by holding Escape and tapping E. The existing hold route
also works: hold Space for `MOUSE`, then hold Backspace for `CODEX` while tapping
an action key.

| Key | Action |
| --- | --- |
| Q / W | Display brightness down / up |
| I / O / P | Mute / volume down / volume up |
| E | Toggle Fast mode* |
| R / T | Open review / toggle terminal |
| Y / U | Toggle Plan mode* / continue in a new chat* |
| A / X | Approve / reject the active request |
| S / D | Toggle sidebar / start dictation |
| F / G | Find in the current chat / search chats |
| H / J / K / L | Create branch* / commit* / create PR* / create draft PR* |
| ; | Open Settings |
| Z | Merge PR* |
| C / V | Open command menu / toggle review panel |
| B / N / M | Open browser tab / new chat / open folder |
| , / . | Decrease / increase reasoning effort* |
| / | Command+Shift+/ (open the Codex shortcut explorer) |

Bindings marked `*` need these one-time assignments in Codex Settings >
Keyboard Shortcuts:

| Codex action | Assign this shortcut |
| --- | --- |
| Toggle Fast mode | Control+Option+Command+F |
| Toggle Plan mode | Control+Option+Command+P |
| Continue in a new chat | Control+Option+Command+K |
| Create branch | Control+Option+Command+B |
| Commit | Control+Option+Command+C |
| Create PR | Control+Option+Command+R |
| Create draft PR | Control+Option+Command+D |
| Merge PR | Control+Option+Command+M |
| Decrease reasoning effort | Control+Option+Command+Minus |
| Increase reasoning effort | Control+Option+Command+Equal |

The display and audio bindings use standard ZMK consumer keycodes supported by
macOS. Direct bindings use the current published Codex shortcuts; approve and
reject send Enter and Escape and are meaningful only while an approval request
is active. The custom three-modifier chords are intentionally uncommon and do
nothing Codex-specific until assigned in the app.

This reproduces the Codex Micro command surface that is available through
ordinary keyboard shortcuts. Its six assigned Agent Keys, live RGB status,
automatic app-linked layers, and exact joystick/dial behavior require the
Micro's device integration or a separate host bridge and are not emulated here.
