# ESP32 Marauder

Thanks so much for picking up PhreakBoutique's ESP32 Marauder! It's an ESP32-based device pre-configured with a suite of tools for exploring and learning about Wi-Fi and Bluetooth security.

## What you've got

- **Hardware:** the ESP32 "Cheap Yellow Display" (CYD) board with a 2.8" resistive touchscreen. Yours is the **CYD2USB** version, with both a micro-USB and a USB-C port.
- **Firmware:** the CYD port of Marauder by [Fr4nkFletcher](https://github.com/Fr4nkFletcher/ESP32-Marauder-Cheap-Yellow-Display), based on the original [ESP32 Marauder](https://github.com/justcallmekoko/ESP32Marauder) project led by justcallmekoko.
- **SD card** (if your order included one): preloaded with evil portal templates.

## First power-on

1. Plug it into any USB power source or computer with either USB port.
2. The Marauder menu appears on the touchscreen.
3. Tap through the menus. The screen is **resistive**, so press firmly with a fingertip or fingernail, or use a stylus.

Good first things to try:

- **WiFi → Sniffers / Scanners:** scan for nearby access points and stations.
- **Bluetooth → Sniffers:** see which Bluetooth devices are around you.

Scanning and sniffing are passive. Attacks (deauthentication, evil portals, beacon spam) are not, so use them only on networks you own. See [Use it responsibly](../responsible-use.md).

## Learn the tools

The **[Marauder Wiki](https://github.com/justcallmekoko/ESP32Marauder/wiki)** is the best reference for what everything does. It covers:

- **Commands:** what every menu item and command does, with examples
- **Tools:** Wi-Fi deauthentication, Bluetooth sniffing, packet capture and more
- **Usage guides:** step-by-step walkthroughs

The **[CYD firmware repository](https://github.com/Fr4nkFletcher/ESP32-Marauder-Cheap-Yellow-Display)** covers what's specific to your board: adding evil portals, drivers, and firmware updates.

## Your preloaded SD card

If your Marauder came with an SD card, we preloaded evil portal configurations in the `portals` folder so you can get started right away. They're plain HTML files, so you can open them, customize them, or add your own. The [evil portal examples](https://github.com/Fr4nkFletcher/ESP32-Marauder-Cheap-Yellow-Display/tree/master/evilportal) and the [Marauder Wiki](https://github.com/justcallmekoko/ESP32Marauder/wiki) explain the file format.

## Updating the firmware

New Marauder features come out regularly. The easiest way to update is the web flasher. You'll need **Chrome** or **Edge**, because Firefox and Safari don't support Web Serial.

1. Connect the Marauder to your computer with a USB **data** cable. Some charge-only cables won't work.
2. Open the **[CYD Web Flasher](https://fr4nkfletcher.github.io/Adafruit_WebSerial_ESPTool/)**.
3. Hold the **BOOT** button on the board, click **Connect**, and choose the serial port.
4. Choose the **2.8" Resistive MicroUSB/Type-C "2USB"** model and the version you want.
5. Click **Program** and wait for it to finish, then press **RST** (reset).

!!! warning "Pick the right model"
    Your board is the **CYD2USB** version. Flashing firmware for a different CYD model can leave you with a blank or garbled screen. If that happens, flash again with the correct model.

??? question "The flasher can't connect or fails partway"
    1. Unplug the board and plug it back in.
    2. Hold **RST**, tap **BOOT**, then release **RST**. The screen should go blank, which means the board is in flashing mode.
    3. Refresh the web flasher page and click **Connect** again.

    If no serial port shows up at all, try another cable. You may also need a USB-serial driver: most CYD boards use a **CH340** chip, and its driver is available from the chip maker, WCH.

## Need help?

If you run into trouble or have questions, [reach out to us](../support.md). We can help with configuration, troubleshooting, and the advanced features. For community support, both GitHub repositories link to active Discord groups where you can ask questions and swap ideas.

Thanks again for supporting PhreakBoutique! Your purchase also supports the local hacking community, including DC207. We can't wait to see what you build. :rocket:
