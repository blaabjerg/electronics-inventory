# Power

## 18650 Li-ion cells — protected

- Package: 18650 with PCB protection circuit
- Qty: 2
- Notes: Aliexpress, origin and capacity unknown — not for critical applications. Protected cells (built-in over-discharge/over-current PCB). Store at ~50% SoC if unused.

## LiPo cells — 523450 1000mAh 3.7V

- Package: 523450 soft pouch, PH 2.0 connector
- Qty: 2
- Notes: Aliexpress, 3.7V nominal, 1000mAh, 5.2×34×50mm. PH 2.0 (2-pin). Not for critical applications. Charge with TP4056 module or equivalent — do not exceed 4.2V.

## MB102 breadboard power supply module

- Package: breadboard-mount module, barrel jack + USB input
- Qty: 1 — ⚠️ in repair bin
- Notes: Switchable 3.3V/5V output, designed to plug into breadboard power rails. Faulty AMS1117C LDO — needs replacement. See REPAIR-BIN.md.

## Mini360 buck converter modules

- Package: bare module, ~17×11mm
- Qty: 5
- Notes: Adjustable step-down, ~4.75–23V in, 1–17V out, ~1.8A continuous (derate in practice — thermal limit is the real constraint). MP2307-based or similar. Trim output voltage with onboard pot before connecting load.

## TP4056 charger modules

- Package: bare module (ZX-056 board), USB-C input
- Qty: 7
- Notes: Single-cell LiPo/Li-ion charger, 4.2V cutoff, 1A default charge current. Confirmed with protection circuit: DW01 + FS8205A dual MOSFET (visible on board). Safe to use with unprotected cells. 5V input via USB-C.
