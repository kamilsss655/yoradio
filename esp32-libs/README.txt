*2026 by https://github.com/kamilsss655*

You can use these precompiled optimized (bigger receive buffer) network libraries for Arduino, or compile them yourself with this Docker image: https://hub.docker.com/r/espressif/esp32-arduino-lib-builder
  - if building manually provide the exact commit hash you current Arduino library is using (found in /home/username/.arduino15/packages/esp32/tools/esp32-libs/3.3.7/versions.txt)

You need to replace the Arduino esp32 library files with these.

Tested "big-buffer" precompiled lib with ESP32 Lolin Lite V1 board and manually added 8MB PSRAM (https://blog.pagefault-limited.co.uk/lolin32-lite-esp32-8mb-psram-upgrade-mod):
  - FLAC upto 1200 kBit/s is stutter free and very stable operation of the whole platform

If you are not chasing FLAC playback "medium-buffer" will likely offer noticable improvements in 320 kBit/s MP3 streams etc.
