# ESP32-S3 Wi-Fi Scanner

An ESP32-S3 Wi-Fi scanner written in C using ESP-IDF. The firmware scans nearby access points and prints their SSID, RSSI, Wi-Fi channel, and authentication mode to the serial terminal.

## Features

- ESP32-S3 station-mode initialization
- Active scanning for nearby Wi-Fi access points
- Displays up to 20 access points per scan
- Reports SSID, RSSI, primary channel, and authentication type
- Includes open, WEP, WPA, WPA2, mixed WPA/WPA2, and WPA3 reporting
- Repeats the scan every 10 seconds using a FreeRTOS task

## Technology

- ESP32-S3
- C
- ESP-IDF
- FreeRTOS
- ESP Wi-Fi API

The project was developed with ESP-IDF 5.3.x.

## Project Structure

```text
.
├── CMakeLists.txt
├── sdkconfig
└── main/
    ├── CMakeLists.txt
    └── main.c
```

## Build and Flash

Open an ESP-IDF terminal in the repository root.

Set the target:

```bash
idf.py set-target esp32s3
```

Build:

```bash
idf.py build
```

Flash the board, replacing `<PORT>` with your serial port such as `COM6` or `/dev/ttyUSB0`:

```bash
idf.py -p <PORT> flash
```

Open the serial monitor:

```bash
idf.py -p <PORT> monitor
```

Exit the monitor with `Ctrl+]`.

## Example Output

```text
Nr   SSID                             RSSI   CH   Encrypt
1    ExampleNetwork                   -42    6    WPA2_PSK
2    GuestNetwork                     -67    11   WPA3_PSK
```

## Notes

The generated `build/` directory and local VS Code configuration are intentionally excluded from version control. They can be recreated by ESP-IDF on any configured development machine.
#Author 
Kemal Berkay Lak
Wrocław University of Science and Technology, Electronics and Computer Engineering
