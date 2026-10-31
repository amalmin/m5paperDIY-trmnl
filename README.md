# M5PaperDIY TRMNL Firmware

Arduino firmware for using the M5PaperDIY e-ink device as a display for TRMNL-like servers.

## Features
- Full M5Unified library support (M5EPD deprecated)
- PNG and BMP image support
- PM chip power management with RTC persistence
- ~32uA idle current
- Battery voltage and Wifi RSSI monitoring
- Automatic WiFi retry logic
- Wake on button press or timer

## Hardware Requirements
- M5PaperDIY e-ink display (960x540)
- WiFi network access

## Installation


### Arduino IDE
- Install M5Unified library
- Install ArduinoJson library
- Configure ESP32 board settings

## Configuration
Edit these values in the code:
- `SERVER_URL` - the URL for your TRMNL-like server
- `TRMNL_API_KEY` - Your TRMNL API key from trmnl.app if used - the code uses MAC address by default.
- `WIFI_SSID` - Your WiFi network name
- `WIFI_PASS` - Your WiFi password

## Usage
The device will:
1. Wake up (timer or power button press)
2. Connect to WiFi
3. Fetch display from SERVER_URL
4. Render image to e-ink screen
5. Power down  until next refresh

## Troubleshooting
- **WiFi won't connect**: Check credentials, device will auto-retry 3x
- **Image won't load**: Verify TRMNL API key and network connectivity
- **Battery drain**: It should be pretty minimal.  Mainly depends on update rate.

## Credits
Built for the [TRMNL BYOD program](https://docs.trmnl.com/go/diy/byod)
But I use LaraPaper instead!!

## License
MIT
