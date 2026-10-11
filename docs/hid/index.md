# Evil USB Cable & PwnPixel

Thanks for picking up one of our keystroke injectors, built and serviced by the hackers at PhreakBoutique! :blush:

Both products work the same way inside, so they share this guide:

| | Evil USB Cable | PwnPixel |
|---|---|---|
| **What it looks like** | An ordinary USB-A to USB-C cable | A small USB device |
| **Brains** | ATtiny85 (Digispark-compatible) | ATtiny85 (Digispark-compatible) |
| **Plugs into the computer with** | The USB-A end | Its USB-A connector |

## What it does

When you plug it in, the computer thinks it's a **keyboard** (a USB "HID" device). Once it's running, it types whatever keystrokes and commands it was programmed with, much faster than any human could. It can also move the mouse and do anything else a keyboard can.

## It came pre-loaded with a rickroll

Your device ships with our classic prank payload. On a **Windows** computer it shows a fake, never-ending Windows Update screen while streaming Rick Astley's *Never Gonna Give You Up* for the next 12 hours. Classic.

**Try it:**

1. Plug it into a Windows computer you own (or a friend's who's in on the joke).
2. Wait about 5 seconds. The device spends a few seconds in its bootloader before the payload starts.
3. Enjoy. To end it early, close the full-screen window with ++alt+f4++.

!!! warning "Heads up when reprogramming"
    Your device runs its payload **every time** it's plugged in. When you go to reprogram it, click **Upload** in the Arduino IDE *before* plugging the device in. The IDE catches it in the bootloader, so the payload doesn't run on your own machine. See [Write your own payloads](payloads.md).

## Make it your own

<div class="grid cards" markdown>

-   **1. [Set up your computer](setup.md)**

    Install the Arduino IDE, the board package and drivers. This takes about 10 minutes, and you only do it once.

-   **2. [Write your own payloads](payloads.md)**

    Upload your first "hello world", then explore hundreds of community payloads.

-   **3. [Troubleshooting](troubleshooting.md)**

    Device not detected? Typing gibberish? Start here.

</div>

And please read [Use it responsibly](../responsible-use.md) before you plug it into anything that isn't yours.
