# Write your own payloads

Payloads are short Arduino sketches that use the `DigiKeyboard` library to type keystrokes. Make sure you've finished [Set up your computer](setup.md) first.

## How uploading works

This part trips most people up the first time, so here's the order:

1. **Unplug** your device.
2. Open your sketch and click **Upload** (the → arrow).
3. Wait for the message at the bottom: **`Plug in device now... (will timeout in 60 seconds)`**
4. **Now** plug in your device.
5. Wait a few seconds for `Micronucleus done. Thank you!`, and you're done.

!!! warning
    If you plug the device in *before* clicking Upload, it runs its current payload on your computer. If that payload is the rickroll, you'll get rickrolled. Ask us how we know. :sweat_smile:

## Your first payload: hello world

This opens Notepad on Windows and types a message. Paste it into a new sketch and upload it:

```cpp
#include "DigiKeyboard.h"

void setup() {
  DigiKeyboard.sendKeyStroke(0);       // wake up the computer's keyboard driver
  DigiKeyboard.delay(2000);            // give Windows time to recognize the "keyboard"

  DigiKeyboard.sendKeyStroke(KEY_R, MOD_GUI_LEFT);  // Win+R opens the Run dialog
  DigiKeyboard.delay(600);
  DigiKeyboard.print("notepad");
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
  DigiKeyboard.delay(1000);

  DigiKeyboard.println("Hello from my PhreakBoutique device!");
}

void loop() {
  // Nothing here, so the payload runs once per plug-in
}
```

Now unplug the device and plug it back in. Notepad opens and the message types itself. :tada:

### The building blocks

| Code | What it does |
|---|---|
| `DigiKeyboard.print("text")` | Types text |
| `DigiKeyboard.println("text")` | Types text and presses Enter |
| `DigiKeyboard.sendKeyStroke(KEY_ENTER)` | Presses a single key |
| `DigiKeyboard.sendKeyStroke(KEY_R, MOD_GUI_LEFT)` | Presses a key combo (here, ++win+r++) |
| `DigiKeyboard.delay(1000)` | Waits 1 second. Use this instead of `delay()` |

On macOS, Spotlight is `DigiKeyboard.sendKeyStroke(KEY_SPACE, MOD_GUI_LEFT)` (++cmd+space++).

## Get inspired

The community has written hundreds of payloads. Browse, read, and adapt them:

- **[CedArctic/DigiSpark-Scripts](https://github.com/CedArctic/DigiSpark-Scripts)**: a big collection of example payloads for this exact hardware.

To use one, open the `.ino` file in the Arduino IDE, check that the board is set to **Digispark (Default - 16.5mhz)**, and follow the upload steps above.

!!! tip "Always read a payload before you run it"
    Some community payloads do destructive things on purpose. Know what a script does before you upload it.

## Want the rickroll back?

[Email us](mailto:support@phreakboutique.com) and we'll send you the sketch.

Please read [Use it responsibly](../responsible-use.md). Keystroke injection on machines you don't own is illegal, even as a joke.
