# Micro Speech Example

This example shows how to run a 20 kB model that can recognize 2 keywords,
"yes" and "no", from speech data.

The application listens to its surroundings with a microphone and indicates
when it has detected a word by displaying data on a screen.

## Deploy to ESP32

The following instructions will help you build and deploy this sample
to [ESP32](https://www.espressif.com/en/products/hardware/esp32/overview)
devices using the [ESP IDF](https://github.com/espressif/esp-idf).

The sample has been tested on ESP-IDF version `stable (v5.0)` with the following device:
- [ESP32-S3-BOX](https://github.com/espressif/esp-box/blob/master/docs/hardware_overview/esp32_s3_box/hardware_overview_for_box.md)

ESP32-S3-BOX has 2 analog MICs and an ADC, which supports up to 4 MIC inputs, behind them.
This fork adds configuration of the ADC using the components from [ESP-BOX AIoT Development Framework](https://github.com/espressif/esp-box).

### Install the ESP IDF

Follow the instructions of the
[ESP-IDF get started guide](https://docs.espressif.com/projects/esp-idf/en/latest/get-started/index.html)
to setup the toolchain and the ESP-IDF itself.

The next steps assume that the
[IDF environment variables are set](https://docs.espressif.com/projects/esp-idf/en/latest/get-started/index.html#step-4-set-up-the-environment-variables) :

 * The `IDF_PATH` environment variable is set
 * `idf.py` and Xtensa-esp32 tools (e.g. `xtensa-esp32-elf-gcc`) are in `$PATH`


### Building the example

Set the chip target (For esp32s3 target, IDF version `release/v4.4` is needed):

```
idf.py set-target esp32s3
```

Then build with `idf.py`
```
idf.py build
```

### Load and run the example

To flash (replace `/dev/ttyUSB0` with the device serial port):
```
idf.py --port /dev/ttyUSB0 flash
```

Monitor the serial output:
```
idf.py --port /dev/ttyUSB0 monitor
```

Use `Ctrl+]` to exit.

The previous two commands can be combined:
```
idf.py --port /dev/ttyUSB0 flash monitor
```

### Sample output

  * When a keyword is detected you will see following output sample output on the log screen:

```
Heard yes (<score>) at <time>
```
