# WT32-SC01 Development

A collection of tools and how-to's about developing GUI-applications for the WT32-SC01.


# LVGL

Based on this project: https://github.com/wireless-tag-com/lv_port_esp32

## Installing ESP32 SDK

Download the [Installer](https://dl.espressif.com/dl/esp-idf-tools-setup-offline-2.5.exe) which will install Embedded Python, Cross-compilers, OpenOCD, Cmake, Ninja and the ESP-IDF on your system.

If the installer does not work correctly, manually add these environments variables:

| Environment variable | Value |
|---|---|
| `IDF_TOOLS_PATH` | `C:\Users\User\.espressif` |
| `PATH` (add) | `C:\Users\User\esp\esp-idf\tools` |
| `PATH` (add) | `C:\Users\User\.espressif\tools\ninja\1.10.0` |
| `PATH` (add) | `C:\Users\Mathis\.espressif\tools\xtensa-esp32-elf\esp-2020r3-8.4.0\xtensa-esp32-elf\bin` |


## Building the project

Clone from git `git clone --recurse-submodules https://github.com/wireless-tag-cn/lv_port_esp32.git`
Cd into it.
(Optional: Run `idf.py menuconfig` to configure stuff)
Run `idf.py build`
Run `idf.py flash` (Optional: `idf.py -p (PORT) flash`)

# With wsl 

Follow this tutorial https://gist.github.com/abobija/2f11d1b2c7cb079bec4df6e2348d969f

Create these symbolic links: (needed as non-aliases in the wsl bash)
ln -s YOUR_WINDOWS_PYTHON_PATH/python.exe python.exe
ln -s YOUR_WINDOWS_PYTHON_PATH/Scripts/pip.exe pip.exe
ln -s /mnt/c/Windows/System32/WindowsPowerShell/v1.0/powershell.exe powershell.exe

# With arduino

Follow this tutorial https://www.youtube.com/watch?v=AvJms6_Pf_o

For WT32-SC01-specific setup, see this repo https://github.com/sowbug/WT32-SC01-Demo
> Copy `User_Setup.h` from there or this repo
> Download Adafruit_FT6206_Library to Arduino library dir
> In code, do the following after `tft.init`
```
tft.init()

// Thanks to https://github.com/seaniefs/WT32-SC01-Exp
// for figuring this out
pinMode(TFT_BL, OUTPUT);
digitalWrite(TFT_BL, 128);
```






