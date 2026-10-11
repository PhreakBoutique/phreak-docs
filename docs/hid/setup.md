# Set up your computer

You'll program your Evil USB Cable or PwnPixel with the free **Arduino IDE**. You only need to do this setup once.

## 1. Install the Arduino IDE

Download and install the Arduino IDE (version 2.x) from [arduino.cc/en/software](https://www.arduino.cc/en/software).

## 2. Add the Digistump board package

Your device is compatible with the Digispark ATtiny85 board. The original Digistump package is no longer maintained, so we use the community-maintained version, which works with Arduino IDE 2.

1. Open **File → Preferences** (on macOS: **Arduino IDE → Settings**).
2. In **Additional boards manager URLs**, paste:

    ```
    https://raw.githubusercontent.com/ArminJo/DigistumpArduino/master/package_digistump_index.json
    ```

3. Click **OK**.
4. Open **Tools → Board → Boards Manager**, search for **Digistump**, and install **Digistump AVR Boards** (version 1.7.2 or newer).

## 3. Install drivers

=== "Windows"

    Windows needs a driver to talk to the device's bootloader. After step 2, run the installer included with the board package:

    1. Press ++win+r++, paste the path below, and press ++enter++:

        ```
        %LOCALAPPDATA%\Arduino15\packages\digistump\tools\micronucleus
        ```

    2. Open the version folder (for example `2.5`), then `Digistump_Drivers`.
    3. Run **`Install_Digistump_Drivers.bat`** and accept the prompts.

    If that folder doesn't exist, download `Digistump.Drivers.zip` from the [DigistumpArduino releases page](https://github.com/ArminJo/DigistumpArduino/releases) and run `InstallDrivers.exe`.

=== "macOS"

    No drivers needed. :tada:

=== "Linux"

    Let your user access the bootloader without `sudo` by adding a udev rule:

    ```bash
    echo 'SUBSYSTEMS=="usb", ATTRS{idVendor}=="16d0", ATTRS{idProduct}=="0753", MODE:="0666"' \
      | sudo tee /etc/udev/rules.d/49-micronucleus.rules
    sudo udevadm control --reload-rules
    ```

## 4. Select the board

In the Arduino IDE, go to **Tools → Board → Digistump AVR Boards** and choose **Digispark (Default - 16.5mhz)**.

That's it. You're ready to [write your first payload](payloads.md).
