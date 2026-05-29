# Sensors & Modules

## Logic level shifters — BSS138-based, 2-channel

- Package: bare module, 0.1" header pins
- Qty: 10
- Notes: Bidirectional 3.3V ↔ 5V. BSS138 N-channel MOSFETs. Two independent channels per board. Standard SparkFun-style design, works for I2C, SPI, UART.

## Logic level shifters — BSS138-based, 4-channel

- Package: bare module, 0.1" header pins
- Qty: 10
- Notes: Same as above, 4 channels per board. Use where multiple signal lines need shifting simultaneously (SPI with CS, parallel data buses).

## Hall effect sensor — 49E (analog linear)

- Package: TO-92 (3-leg), through-hole
- Qty: 10
- Notes: Analog linear output, ratiometric. Supply 4.5–6V, output ~2.5V at zero field. Sensitivity ~1.4 mV/Gauss typical. Generic part — exact sensitivity varies by batch.

## Hall effect sensor — SS495A (analog linear, ratiometric)

- Package: TO-92 (3-leg), through-hole
- Qty: 10
- Notes: Ratiometric linear sensor, Honeywell/Allegro lineage. Supply 5V, output 0.5–4.5V over ±670 Gauss range, 3.125 mV/Gauss. More consistent spec than the 49E. Well-suited for position sensing, current sensing.

## DS18B20 temperature sensor

- Package: TO-92 (3-leg), through-hole
- Qty: 1
- Notes: Dallas/Maxim 1-Wire digital temperature sensor. -55°C to +125°C, ±0.5°C accuracy (-10 to +85°C range). 9–12 bit resolution, programmable. Parasitic power mode supported. Marking: "Dallas 18B20 2342C4 +817AB". Scarce — treat as critical stock. Earmarked for Serenity Now! Argus Environment node — water temperature probe (hull-mounted, below waterline).

## ESP8266 — NodeMCU Amica v2

- Package: dev board, ~48×25mm, micro-USB, 0.1" headers
- Qty: 1
- Notes: WiFi only, Tensilica L106 80MHz (overclockable to 160MHz), 4MB flash, CP2102 USB-UART. 3.3V GPIO, not 5V tolerant. Amica variant uses CP2102 (vs. CH340 on v3 LoLin). Mature ecosystem, limited RAM (~50KB heap usable). Good for simple WiFi nodes.

## ESP32-S3 N16R8 — dev board

- Package: full dev board with headers and USB connectors
- Qty: 1 — ⚠️ in repair bin
- Notes: Dual-core Xtensa LX7 240MHz, 16MB flash, 8MB PSRAM (N16R8). WiFi + BT5/BLE, USB OTG. Faulty CH343P USB-UART bridge — needs SMD rework (hot air). See REPAIR-BIN.md.

## ESP32-C6-N16

- Package: dev board
- Qty: 2
- Notes: Single-core RISC-V 160MHz, 16MB flash. WiFi 6 (802.11ax), BLE 5, Thread/Zigbee (802.15.4). The 802.15.4 radio makes this the only board on the bench capable of Thread/Zigbee — relevant if mesh networking or Matter comes up. Newer chip, ecosystem still maturing vs C3/S3.

## ESP32-C3 SuperMini — HW-466AB (black)

- Package: SuperMini dev board, ~22×18mm, USB-C
- Qty: 2
- Notes: ESP32-C3FN4 (4MB flash in-package), single-core RISC-V 160MHz, WiFi + BLE. Tiny footprint. PCB antenna only. USB-C, can do USB serial natively (no CP2102/CH340). GPIO count limited — check pinout before committing to a project. 3.3V IO, not 5V tolerant.

## ESP32-C3 SuperMini Plus — TenStar (red), external antenna + RGB

- Package: SuperMini+ dev board, USB-C
- Qty: 2
- Notes: Red board variant with u.FL/IPEX external antenna connector and onboard RGB LED. Otherwise similar to the black C3 SuperMini above. External antenna improves range significantly for anything through-hull or in enclosed spaces — relevant for Argus nodes.

## ESP32-C3 with 0.42" OLED display

- Package: compact dev board with integrated display
- Qty: 1
- Notes: ESP32-C3 with integrated 0.42" OLED (72×40px typically, I²C). Unusual display size — library support is narrower than SSD1306 0.96". Good for small status displays where a dedicated display board is too bulky.

## Seeed XIAO ESP32-S3 Sense

- Package: XIAO form factor (~21×17.5mm) + OV2640 camera daughter board + external antenna
- Qty: 1
- Notes: ESP32-S3R8 (8MB PSRAM), dual-core LX7 240MHz, 8MB flash, WiFi + BLE, USB OTG. OV2640 camera module attached (2MP, up to 1600×1200). Onboard microphone. External antenna connector populated. Most capable and most expensive board in the collection — treat as scarce. Well-suited for camera/CV work or audio capture nodes.

## MAX485 RS-485 transceiver breakout

- Package: small breakout board, 0.1" headers
- Qty: 5
- Notes: MAX485 is a 5V half-duplex RS-485/RS-422 transceiver. 2.5Mbps max. Breakout provides DE/RE pins for direction control. Note: MAX485 logic levels are 5V — not directly 3.3V compatible without level shifting. MAX3485 (3.3V version, on order) is the better choice for ESP32 nodes. Keep MAX485 for 5V bus masters or where level shifting is already present.

## Microphone module — omnidirectional, small round

- Package: small circular PCB module
- Qty: 1
- Notes: Omnidirectional electret or MEMS capsule, smart-home type. Interface unknown (likely analog output or I2S — check board markings). Scarce — 1 unit.

## eInk display — 1.54" 200×200 monochrome SPI

- Package: bare display + FPC, likely with small driver PCB
- Qty: 1
- Notes: SSD1681 controller (assumed — verify). 200×200 px, monochrome (black/white), SPI interface. Supports partial refresh. 3.3V logic. Scarce — 1 unit.

## OLED display — 0.96" 128×64 monochrome I²C

- Package: bare module with 0.1" 4-pin header (GND/VCC/SCL/SDA)
- Qty: 2
- Notes: SSD1306 controller (assumed — verify). White pixels on black. 3.3V/5V tolerant on most clone boards. I²C address 0x3C (default) or 0x3D (jumper). Ubiquitous — well-supported in Arduino/ESP-IDF/MicroPython.

## L298N motor driver module

- Package: large module with heatsink on L298N
- Qty: 2
- Notes: Dual H-bridge, 2A per channel, up to 46V motor supply. Drives 2× DC motors or 1× stepper. Onboard 5V regulator (active when motor supply >7V — jumper to disable for high-voltage use). Logic 5V. Inefficient at low voltages due to ~2V dropout per channel — consider DRV8833/TB6612 for small 3.7V-fed DC motors.

## INA226 current/power monitor breakout

- Package: small breakout board, 0.1" headers
- Qty: 2
- Notes: I²C, 16-bit resolution. Shunt resistor R100 (0.1Ω). Superior to INA219 — higher resolution, better accuracy, plus an alert/limit pin useful for overcurrent interrupts. I²C address configurable via A0/A1 pads (0x40–0x4F). Directly relevant to Argus Electrons node design.

## INA219 current/power monitor breakout

- Package: small breakout board, 0.1" headers
- Qty: 5
- Notes: I²C, measures shunt voltage, bus voltage, calculates current and power. Shunt resistor is 0.1Ω (R100). At 0.1Ω: ±3.2A range, ~0.8mA resolution (12-bit). I²C address configurable via A0/A1 pads (0x40–0x4F), so all 5 can coexist on one bus. Well-suited for per-circuit current monitoring (cf. Argus Electrons node).

## Rain detection modules — resistive

- Package: sensor PCB + driver board (2-board set)
- Qty: 5 sets
- Notes: Resistive sensing element (parallel trace PCB exposed to rain) + driver board with LM393 comparator, threshold pot, DO (digital) and AO (analog) outputs. 3.3V/5V compatible. Not suitable for outdoor permanent installation without conformal coating.
