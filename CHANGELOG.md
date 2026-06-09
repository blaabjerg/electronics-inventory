# Changelog

Changes to the inventory after initial population are logged here. The initial population session is not logged — the category files themselves are the record of that.

## 2026-06-09 — ESP32-C6 board + isolated RS-485 transceivers
* Added: 1× ESP32-C6-N16 dev board
* Added: 3× opto-isolated TTL–RS-485 transceiver modules

## 2026-06-06 — ESP32-S3 boards + isolated RS-485 transceivers
- Added: 2× generic ESP32-S3-N16R8 dev boards (consolidated into the existing S3-N16R8 entry: now 2 working + 1 repair-bin)
- Added: 2× opto-isolated TTL–RS-485 transceiver modules (SN65HVD75 + B0505XT-1WR3, auto-direction) to sensors-modules.md — the Argus production bus part
- Updated: WISHLIST opto-isolated RS-485 gap → ✅ in stock, but 3 more wanted to complete the 5-board Argus fleet

## 2026-06-05 — AliExpress haul (ICs, optos, MAX3485, BNO085)
- Added: ICs — LM324 (~5), LM393 (~10), UA741 (~10), NE5532 (~10), LM386 (~10), ULN2003 (~5), ULN2803 (~5)
- Added: PC817 optocouplers ×~30 to semiconductors-discrete.md; 2-channel PC817 board to sensors-modules.md
- Added: 5× MAX3485 RS-485 transceiver modules and 1× Tenstar BNO085 IMU board to sensors-modules.md
- Updated: NE555 qty 2→~12, LM358 qty 2→~12 (10 each from this batch)
- Updated: MAX485 note (MAX3485 now in stock, not "on order")
- Updated: WISHLIST.md — added "Mouser order" category (Traco TSR 1-2433, TMR 2-2411WI + quality-critical suggestions); marked optocouplers ✅; cleared "On order / incoming"

## 2026-06-05 — BNO085 verified genuine
- Updated: Tenstar BNO085 board note → verified genuine (I²C 0x4B, SH-2 product-ID handshake OK, streams valid rotation vector). Pi hardware-I²C clock-stretching garbles occasional frames — Pi quirk, not a board fault; use SPI/UART-RVC or an ESP32 for clean streaming.

## 2026-05-29 — MAX485 to repair bin
- Updated: MAX485 qty 5→4; 1 unit moved to repair bin (suspected dead, power backfeed)

## 2026-05-29 — Repair bin, ESP32-C6-N16, MB102
- Added: 2× ESP32-C6-N16 dev boards to sensors-modules.md
- Added: MB102 breadboard PSU module to power.md (repair bin)
- Updated: ESP32-S3 N16R8 marked as repair bin (faulty CH343P)
- Added: REPAIR-BIN.md to track items awaiting repair

## 2026-05-27 — INA226 modules
- Added: 2× INA226 current/power monitor breakout (R100 shunt, 0.1Ω) to sensors-modules.md

---
