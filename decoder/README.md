# WiFi decoder

Use this decoder to decode Ir signals in the workshop.

## Requirements

* IR receiver
* A pull-up resistor
* ESP8266 (ESP32 should also work)
* An LED and a resistor (optional)

Adopted from:
[IRrecvDumpV2](https://github.com/crankyoldgit/IRremoteESP8266/tree/master/examples/IRrecvDumpV2)#d2fa206

## Wiring

| IR receiver | ESP8266 |
|------------|---------|
| Data out   | GPIO14 (D5 on NodeMCU or WeMos D1 mini) and 1K ohms pull-up resistor |

Another pin of 1K ohms resistor must be connected to 3V3.

Optionally, add a resistor and an LED to Data out pin so that signal can be
seen visually. Note that the LED is on by default as the signal is inverted
(high == 0, low == 1). Add a transistor to reverse the signal if preferred.

## Usage

Build the firmware.

```console
pio run -e nodemcuv2
```

Upload the firmware.

```console
pio run -e nodemcuv2 -t upload
```

Show the log from the device. Baud rate is 115200. Replace `/dev/cuaU0` with
the path to the serial port.

```console
cu -s 115200 -l /dev/cuaU0
```
