# Troubleshooting

### The upload times out after "Plug in device now…"

- **Windows:** make sure you [installed the drivers](setup.md#3-install-drivers). Without them, Windows can't see the bootloader.
- **Linux:** make sure you added the [udev rule](setup.md#3-install-drivers).
- **Try a different USB port.** These devices are happiest on a USB 2.0 port or a USB hub. Some USB 3 ports, especially on newer laptops, don't detect the bootloader in time.
- **Evil USB Cable:** plug the **USB-A** end into your computer, and leave the USB-C end unplugged while programming.
- Plug the device in *after* the "Plug in device now" message appears, not before.

### It types gibberish or the wrong characters

`DigiKeyboard` assumes a **US keyboard layout**. If the target computer uses another layout (UK, German, French…), symbols like `@`, `"`, `\` and `|` come out wrong. Switch the target to a US layout for testing, or adjust the payload for that layout.

### Some keystrokes are missing

The computer may not be ready when the payload starts typing. Add or increase `DigiKeyboard.delay(...)` calls, especially:

- at the very start of `setup()` (try 2000–3000 ms)
- after opening a window or the Run dialog (try 500–1000 ms)

Slower or busy computers need longer delays.

### The payload runs while I'm trying to program it

Click **Upload** first, *then* plug the device in. See [How uploading works](payloads.md#how-uploading-works).

### Compilation fails

- Check that the board is set to **Digispark (Default - 16.5mhz)** under **Tools → Board → Digistump AVR Boards**.
- The ATtiny85 only has about 6 KB of space for your sketch. Very long payloads (lots of text) may not fit, so shorten strings where you can.

### Still stuck?

[Email us](mailto:support@phreakboutique.com) with your operating system, a screenshot of the error, and which device you have. We'll get you sorted.
