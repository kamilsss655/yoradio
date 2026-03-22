# ёRadio (Updated I2S Fork)

<img src="images/yologo.png" width="190" height="142">

Minimal fork of yoRadio focused on **better audio quality and stable FLAC playback**.

Based on:
- yoRadio v0.9.693 (https://github.com/e2002/yoradio)
- ESP32-audioI2S v3.4.5 (https://github.com/schreibfaul1/ESP32-audioI2S)

This fork updates yoRadio to a modern I2S audio library, combining the original project with newer audio improvements that were missing upstream.

**Requires PSRAM either with ESP32 or ESP32-S3.**

**Goal:** best of both worlds — stable yoRadio + up-to-date high-quality audio.

## Custom network libraries


For ESP32 you can use included, precompiled, optimized (bigger receive buffer) network libraries for Arduino `/esp32-libs`, or compile them yourself with this Docker image: https://hub.docker.com/r/espressif/esp32-arduino-lib-builder
  - if building manually provide the exact commit hash you current Arduino library is using (found in `/home/username/.arduino15/packages/esp32/tools/esp32-libs/3.3.7/versions.txt`)

You need to replace the Arduino esp32 library files with these.

* Tested `big-buffer` precompiled lib with ESP32 Lolin Lite V1 board and manually added 8MB PSRAM (https://blog.pagefault-limited.co.uk/lolin32-lite-esp32-8mb-psram-upgrade-mod):
  * FLAC upto 1200 kBit/s is stutter free and very stable operation of the whole platform
* If you are not chasing FLAC playback `medium-buffer` will likely offer noticable improvements in 320 kBit/s MP3 streams etc.

For ESP32-S3 you can either compile binaries yourself with Espressif Arduino Lib Builder mentioned above, or use precompiled binaries provided here: https://github.com/VaraiTamas/yoRadio/tree/main/Lib_tools
