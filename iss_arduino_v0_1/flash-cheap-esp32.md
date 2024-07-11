Executing action: all (aliases: build)
Running ninja in directory /Users/adrien/Dev/esp/projects/iss/build
Executing "ninja all"...
[1/4] cd /Users/adrien/Dev/esp/projects/iss/build/esp-idf/esptool_py && /Users/adrien/.espre...ild/partition_table/partition-table.bin /Users/adrien/Dev/esp/projects/iss/build/tea5767.bi
tea5767.bin binary size 0x42f10 bytes. Smallest app partition is 0x100000 bytes. 0xbd0f0 bytes (74%) free.
[1/1] cd /Users/adrien/Dev/esp/projects/iss/build/bootloader/esp-idf/esptool_py && /Users/ad... 0x8000 bootloader 0x1000 /Users/adrien/Dev/esp/projects/iss/build/bootloader/bootloader.bi
Bootloader binary size 0x6860 bytes. 0x7a0 bytes (7%) free.
[4/4] Completed 'bootloader'Executing action: flash
Serial port /dev/cu.wchusbserial210
Connecting....
Detecting chip type... Unsupported detection protocol, switching and trying again...
Connecting.......
Detecting chip type... ESP32
Running ninja in directory /Users/adrien/Dev/esp/projects/iss/build
Executing "ninja flash"...
[1/5] cd /Users/adrien/Dev/esp/projects/iss/build/esp-idf/esptool_py && /Users/adrien/.espre...ild/partition_table/partition-table.bin /Users/adrien/Dev/esp/projects/iss/build/tea5767.bi
tea5767.bin binary size 0x42f10 bytes. Smallest app partition is 0x100000 bytes. 0xbd0f0 bytes (74%) free.
[1/1] cd /Users/adrien/Dev/esp/projects/iss/build/bootloader/esp-idf/esptool_py && /Users/ad... 0x8000 bootloader 0x1000 /Users/adrien/Dev/esp/projects/iss/build/bootloader/bootloader.bi
Bootloader binary size 0x6860 bytes. 0x7a0 bytes (7%) free.
[4/5] cd /Users/adrien/Dev/esp/esp-idf/components/esptool_py && /opt/homebrew/Cellar/cmake/3...jects/iss/build -P /Users/adrien/Dev/esp/esp-idf/components/esptool_py/run_serial_tool.cmak
esptool.py --chip esp32 -p /dev/cu.wchusbserial210 -b 460800 --before=default_reset --after=hard_reset write_flash --flash_mode dio --flash_freq 40m --flash_size 2MB 0x1000 bootloader/bootloader.bin 0x10000 tea5767.bin 0x8000 partition_table/partition-table.bin
esptool.py v4.7.0
Serial port /dev/cu.wchusbserial210
Connecting....
Chip is ESP32-D0WD-V3 (revision v3.1)
Features: WiFi, BT, Dual Core, 240MHz, VRef calibration in efuse, Coding Scheme None
Crystal is 40MHz
MAC: a0:dd:6c:85:c9:88
Uploading stub...
Running stub...
Stub running...
Changing baud rate to 460800
Changed.
Configuring flash size...
Flash will be erased from 0x00001000 to 0x00007fff...
Flash will be erased from 0x00010000 to 0x00052fff...
Flash will be erased from 0x00008000 to 0x00008fff...
Compressed 26720 bytes to 16342...
Writing at 0x00001000... (100 %)
Wrote 26720 bytes (16342 compressed) at 0x00001000 in 0.5 seconds (effective 401.1 kbit/s)...
Hash of data verified.
Compressed 274192 bytes to 145900...
Writing at 0x0004cf91... (100 %)
Wrote 274192 bytes (145900 compressed) at 0x00010000 in 3.5 seconds (effective 622.8 kbit/s)...
Hash of data verified.
Compressed 3072 bytes to 103...
Writing at 0x00008000... (100 %)
Wrote 3072 bytes (103 compressed) at 0x00008000 in 0.0 seconds (effective 821.5 kbit/s)...
Hash of data verified.

Leaving...
Hard resetting via RTS pin...
Executing action: monitor
Running idf_monitor in directory /Users/adrien/Dev/esp/projects/iss
Executing "/Users/adrien/.espressif/python_env/idf5.2_py3.10_env/bin/python /Users/adrien/Dev/esp/esp-idf/tools/idf_monitor.py -p /dev/cu.wchusbserial210 -b 115200 --toolchain-prefix xtensa-esp32-elf- --target esp32 --revision 0 /Users/adrien/Dev/esp/projects/iss/build/tea5767.elf -m '/Users/adrien/.espressif/python_env/idf5.2_py3.10_env/bin/python' '/Users/adrien/Dev/esp/esp-idf/tools/idf.py'"...
--- esp-idf-monitor 1.4.0 on /dev/cu.wchusbserial210 115200 ---
--- Quit: Ctrl+] | Menu: Ctrl+T | Help: Ctrl+T followed by Ctrl+H --- 2) cpu_start: Max chip rev: v3.99�ets Jul 29 2019 12:21:46

rst:0x1 (POWERON_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:2
load:0x3fff0030,len:7172
load:0x40078000,len:15540
load:0x40080400,len:4
0x40080400: \_init at ??:?

ho 8 tail 4 room 4
load:0x40080404,len:3904
entry 0x40080640
I (31) boot: ESP-IDF v5.2.2 2nd stage bootloader
I (31) boot: compile time Jun 22 2024 06:25:42
I (31) boot: Multicore bootloader
I (35) boot: chip revision: v3.1
I (39) boot.esp32: SPI Speed : 40MHz
I (44) boot.esp32: SPI Mode : DIO
I (48) boot.esp32: SPI Flash Size : 2MB
I (53) boot: Enabling RNG early entropy source...
I (58) boot: Partition Table:
I (62) boot: ## Label Usage Type ST Offset Length
I (69) boot: 0 nvs WiFi data 01 02 00009000 00006000
I (77) boot: 1 phy_init RF data 01 01 0000f000 00001000
I (84) boot: 2 factory factory app 00 00 00010000 00100000
I (92) boot: End of partition table
I (96) esp_image: segment 0: paddr=00010020 vaddr=3f400020 size=0c4bch ( 50364) map
I (121) esp_image: segment 1: paddr=0001c4e4 vaddr=3ffb0000 size=022dch ( 8924) load
I (125) esp_image: segment 2: paddr=0001e7c8 vaddr=40080000 size=01850h ( 6224) load
I (130) esp_image: segment 3: paddr=00020020 vaddr=400d0020 size=25c10h (154640) map
I (189) esp_image: segment 4: paddr=00045c38 vaddr=40081850 size=0d2b4h ( 53940) load
I (217) boot: Loaded app from partition at offset 0x10000
I (218) boot: Disabling RNG early entropy source...
I (229) cpu_start: Multicore app
I (238) cpu_start: Pro cpu start user code
I (238) cpu_start: cpu freq: 160000000 Hz
I (238) cpu_start: Application information:
I (241) cpu_start: Project name: tea5767
I (246) cpu_start: App version: 2bc9284
I (251) cpu_start: Compile time: Jun 22 2024 09:33:19
I (257) cpu_start: ELF file SHA256: 7964983dc...
I (262) cpu_start: ESP-IDF: v5.2.2
I (267) cpu_start: Min chip rev: v0.0
I (272) cpu_start: Max chip rev: v3.99
I (277) cpu_start: Chip rev: v3.1
I (282) heap_init: Initializing. RAM available for dynamic allocation:
I (289) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
I (295) heap_init: At 3FFB2BE8 len 0002D418 (181 KiB): DRAM
I (301) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (307) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (314) heap_init: At 4008EB04 len 000114FC (69 KiB): IRAM
I (321) spi_flash: detected chip: generic
I (324) spi_flash: flash io: dio
W (328) spi_flash: Detected size(4096k) larger than the size in the binary image header(2048k). Using the size in the binary image header.
W (342) i2c: This driver is an old driver, please migrate your application code to adapt `driver/i2c_master.h`
I (353) main_task: Started on CPU0
I (363) main_task: Calling app_main()
I (373) MAIN: Opening Non-Volatile Storage handle
I (373) MAIN: nvs_open Done
I (373) MAIN: NVS_read_int16 Reading [preset_freq] from NVS ...
W (373) MAIN: The value is not initialized yet!
I (383) MAIN: NVS_read_int16=4354 presetFrequence=0
I (393) KEYIN: Start
I (393) MAIN: CONFIG_SDA_GPIO=21
I (393) MAIN: CONFIG_SCL_GPIO=22
