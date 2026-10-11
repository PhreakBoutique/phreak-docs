# Proxmark3 Easy

Thank you for your Proxmark3 Easy purchase from PhreakBoutique and DC207! The Proxmark3 is the go-to tool for RFID and NFC research. It can read, write, sniff and emulate a huge range of low-frequency (125 kHz) and high-frequency (13.56 MHz) tags.

## What you've got

Your Proxmark3 Easy comes flashed with the **[Iceman firmware](https://github.com/RfidResearchGroup/proxmark3)** (RfidResearchGroup). It's the actively developed version of the Proxmark3 software, with far more features and supported tags than the original. You use it from your computer with the matching **Iceman client**.

!!! info "Use the Iceman client, not the old one"
    Older guides point to the original `proxmark/proxmark3` repository. That client won't work properly with your device's firmware, so stick with the RfidResearchGroup (Iceman) builds below.

## 1. Install the client

=== "Windows"

    The easiest route is a ready-made build. No compiling needed.

    1. Go to **[proxmarkbuilds.org](https://www.proxmarkbuilds.org/)** and download the **RRG / Iceman generic build (non-RDV4)**. It's the one for the Proxmark3 Easy, RDV1–RDV3, and similar devices.
    2. Extract it with [7-Zip](https://www.7-zip.org/) to a folder **with no spaces in the path**, for example `C:\pm3`.
    3. Plug in your Proxmark3 with a **micro-USB data cable**. Windows 10 and 11 recognize it automatically as a COM port, with no driver needed.
    4. Run the client launcher in the extracted folder (`pm3.bat`).

    Prefer to build it yourself? Iceman's [Windows instructions](https://github.com/RfidResearchGroup/proxmark3/blob/master/doc/md/Installation_Instructions/Windows-Installation-Instructions.md) cover ProxSpace and WSL.

=== "macOS"

    Install with Homebrew, using the **generic** (non-RDV4) build for the Easy:

    ```bash
    brew tap RfidResearchGroup/proxmark3
    brew install --with-generic proxmark3
    ```

    Plug in your Proxmark3 and run:

    ```bash
    pm3
    ```

=== "Linux"

    Build from source. Install the [dependencies for your distro](https://github.com/RfidResearchGroup/proxmark3/blob/master/doc/md/Installation_Instructions/Linux-Installation-Instructions.md), then:

    ```bash
    git clone https://github.com/RfidResearchGroup/proxmark3.git
    cd proxmark3
    cp Makefile.platform.sample Makefile.platform
    ```

    Edit `Makefile.platform` and set `PLATFORM=PM3GENERIC` (this is important for the Easy), then build and run it:

    ```bash
    make clean && make -j
    ./pm3
    ```

## 2. Your first commands

When the client connects, you'll see the `[usb] pm3 -->` prompt. Try these:

| Command | What it does |
|---|---|
| `hw version` | Shows the firmware and client versions. Check that they match. |
| `hw tune` | Checks your LF and HF antennas |
| `auto` | Place a tag on the device and let it identify it |
| `lf search` | Searches for a low-frequency (125 kHz) tag, like most building badges |
| `hf search` | Searches for a high-frequency (13.56 MHz) tag, like MIFARE or NFC cards |
| `help` | Lists everything. Add `-h` to any command for details. |

The Easy has separate **LF** and **HF** antenna areas on the board. If a tag isn't detected, move it around and try both.

For more, see Iceman's **[command cheat sheet](https://github.com/RfidResearchGroup/proxmark3/blob/master/doc/cheatsheet.md)** and the [project documentation](https://github.com/RfidResearchGroup/proxmark3/tree/master/doc).

## 3. Keeping the firmware and client in sync

The Iceman client and firmware are developed together, so **they should come from the same version**. If `hw version` or the startup banner warns about a mismatch, flash the firmware that came with your client:

=== "Windows (proxmarkbuilds)"

    Run the flash scripts in the extracted folder: **bootrom** first, then **fullimage**.

=== "macOS / Linux"

    ```bash
    pm3-flash-all        # or ./pm3-flash-all when built from source
    ```

!!! tip "If flashing fails or the device isn't detected"
    Unplug the Proxmark3, **hold its button** while plugging it back in, and release the button once two of the four LEDs stay lit. It's now in bootloader mode. Run the flash again.

## Handle with care

The Proxmark3 is a professional tool with an enormous range of capabilities. Explore and experiment freely, but only on your own tags and cards. See [Use it responsibly](../responsible-use.md).

## Need help?

If you hit an issue or need help with a specific feature, [reach out](../support.md). We're always here to help. :blush:

Thank you again for your order! Your support helps us run programs like DC207 that serve the wider hacking community. Enjoy exploring RFID and NFC.
