# Repair Bin

Components and modules awaiting repair. Each entry notes the fault, what's needed to fix it, and any blockers.

---

## ESP32-S3 N16R8 dev board

- **Fault:** Dead CH343P USB-UART bridge — board not enumerated over USB
- **Fix:** Replace CH343P (SMD, QFN or SOP package depending on variant on this board)
- **Blocker:** Hot air rework station required
- **Inventory ref:** sensors-modules.md

## MB102 breadboard power supply module

- **Fault:** No output — suspected dead AMS1117C LDO regulator
- **Fix:** Replace AMS1117C (SOT-223)
- **Blocker:** None beyond a fine-tip iron and the replacement part; AMS1117-3.3 or AMS1117-ADJ depending on board revision — check silk screen for C version
- **Inventory ref:** power.md
