# Wishlist

Component gaps identified against current inventory. Organized by priority.

---

## Mouser order (VOEC — fee-free into Norway)

Mouser is VOEC-registered: 25% MVA collected at checkout, no *fortollingsgebyr* on orders under 3000 NOK. Use it for parts where genuine silicon and known-good quality matter more than AliExpress pricing — especially anything on the always-on Argus path, which has to survive months unattended in a marine environment.

### Argus — committed parts

- **Traco TSR 1-2433** — 12V→3.3V switching regulator, SIP-3, one per ESP32-C6 node (Nav, Environment, Engine, Electrons). Standardised buck for all nodes (Argus decisions, 2026-06-05). Buy **~6** (4 in use + 2 spares).
- **Traco TMR 2-2411WI** — 9–36V in → isolated 5V/400mA, 1.5kVDC. Field-side supply for the MPPT VE.Direct digital-isolator link on the Electrons node. Buy **2** (1 + spare).
- **Mean Well DDR-15G-5** — 9–18V in → 5V/3A (15W), DIN-rail. Central-enclosure DC-DC #1 (internal 5V rail: Nexus + 18650 charging + e-ink + LEDs + internal sensors). Already spec'd in `central-enclosure.md`. Buy **1–2**. Note: 18V input ceiling — depends on the rail TVS clamp (below) to survive load-dump transients above 18V.

### Suggested — quality-critical

Parts where an AliExpress clone/fake is a known reliability or accuracy risk, and where a marine always-on system can't afford a silent failure:

- **Genuine MORNSUN B0505XT-1WR3** (×2–3) — the opto-isolated RS-485 boards were sourced cheap; a couple of genuine isolated bricks as known-good references to validate the AliExpress boards' real idle current against datasheet (ties to Argus NFR-6.1).
- **Digital isolators** — ADuM1201 / TI ISO7221 / Skyworks Si8621 for the VE.Direct isolation. Relabels are common on AliExpress and this sits on the safety-critical telemetry path. ~3–5 pcs, genuine.
- **Genuine Bosch BME688** (×3) — the Environment node sensor array. AliExpress "BME680/688" modules are frequently BMP280 relabels or uncalibrated; for a sensor whose whole value is calibrated output, buy genuine (Bosch via Mouser, or an Adafruit/Pimoroni breakout).
- **Genuine BNO085 breakout** — the Tenstar AliExpress board just arrived; a genuine-silicon spare (Adafruit/SparkFun) de-risks the Nav node if the clone turns out to be a relabelled BNO055.
- **Quality electrolytic / polymer caps, ≥25V** — Panasonic FC/FR, Nichicon, or Würth, for the raw-battery rail (can hit 14.6V absorption; the ≥25V rule is in the Argus power decision). AliExpress electrolytics are the single most common bench-reliability problem — worth doing right on the always-on rail.
- **TVS / transient protection** — SMBJ or P6KE series sized for the 12V house rail (load-dump / alternator transients are real on a boat). Genuine part, correct standoff voltage.
- **v2-PCB regulator ICs (optional, future)** — Renesas RAA211403 or TI LM5165, the integrated buck planned for the v2 board. Worth grabbing a few while an order is open, even if the PCB is months out.

> **SN65HVD75 bare ICs — decided: skip.** Staying on the AliExpress opto modules through bench bring-up; the eventual v2 isolated-RS485 board will be ordered pre-populated (no hand-assembly of fine-pitch parts).

---

## Make: Electronics 3rd ed. (Platt) — specific gaps

Items called out in the official Kit 1 (Sections 1–3) and Kit 2 (Sections 4–5) that aren't in stock.

### Kit 1 / Sections 1–3

- **Omron G5V-2-H1 DC9 relay** — DPDT, 9V coil, DIP-8 footprint (breadboard-compatible). This is the relay Platt uses. Source from DigiKey or Mouser — Aliexpress only sells in quantities of 10+. 2–3 pcs is enough.
- **9V battery + snap connector** — needed for early experiments. Not currently stocked.
- **Full-size panel-mount potentiometers** — the RM065 trimmers are there, but Platt uses full-size rotary pots (10KΩ, 100KΩ). Aliexpress knurled-shaft type is fine.
- **5×20mm glass fuses** — the inventory has 3.6×10mm slow-blow fuses; Platt specifies 5×20mm fast-blow (1A, 3A). Verify fit in any fuse holder before assuming they're interchangeable.
- **Hookup wire** — ✅ in stock
- **Alligator clip test leads** — ✅ in stock

### Kit 2 / Sections 4–5

- **74HC-series logic ICs** — Platt uses 74HC04 (inverter), 74HC08 (AND), 74HC32 (OR), 74HC00 (NAND). None in stock. Get a small assortment.
- **7-segment LED display** — common cathode, 1-digit. Platt uses these in Section 4. ~2–3 pcs.
- **Arduino UNO** (or equivalent AVR dev board) — Platt's Section 5 introduces microcontrollers via Arduino. The ESP32 boards on the bench work for most things, but the book is written against Arduino UNO specifically. A Nano or clone UNO covers it cheaply.
- **Voltage regulator** — LM7805 (5V fixed, TO-220). Used in Platt for regulated supply experiments. ~3 pcs.
- **Magnet wire** — enameled copper, 28AWG or similar. Used in inductor/coil winding experiments.

---

## General bench gaps

Beyond Platt — things a rounded hobbyist kit typically includes.

### Passives

- **Inductors** — none in stock. A small assortment (10µH–10mH, through-hole) covers most filter and SMPS work.
- **Zener diodes** — none in stock. 3.3V, 5.1V, 6.2V, 12V in DO-35 cover most reference/clamp needs.
- **Photoresistors (LDRs)** — useful for light-sensing projects, Platt also references these. ~5 pcs.
- **NTC thermistors** — 10KΩ at 25°C is the standard value. Useful for analog temperature sensing.

### Semiconductors

- **Logic-level MOSFETs** — nothing in stock for power switching from 3.3V/5V logic. IRLZ44N (N-ch, TO-220, Vgs(th) ~2V) and AO3400 (N-ch, SOT-23) cover most use cases. Also 2N7000 (TO-92) for small-signal work.
- **Optocouplers** — ✅ in stock (PC817 ×~30 + a 2-channel PC817 board, 2026-06-05). Covers the Argus Orion-Tr remote-enable opto and general isolation.
- **Schottky diodes (more variety)** — 1N5819/1N5822 are already stocked; add BAT43 or BAT85 (small SOD-80/DO-35 package) for signal-level work.

### ICs

- **AMS1117 LDO regulators** — 3.3V and 5V variants (SOT-223). The LM7805 covers through-hole; AMS1117 covers SMD/module-scale work. Very frequently needed when powering ESP32 from unregulated supplies.
- **LM317** — adjustable linear regulator, TO-220. More flexible than fixed 7805 for bench experimentation.
- **74HC595 shift register** — serial-in parallel-out. Extremely useful for driving multiple outputs (7-segment, LED arrays) from 3 GPIO pins. Not in Platt but a bench staple.
- **CD4017 decade counter** — used in light chaser and sequencer circuits. Common in Platt-adjacent experimentation.
- **TL072 / TL074 op-amp** — lower noise than LM358, FET input. Good complement to the LM358/JRC4558 already in stock.

### Modules / breakouts

- **DS3231 RTC module** — real-time clock with battery backup, I²C. Extremely useful for any datalogging project. 1–2 pcs.
- **DHT22 (or SHT31) temperature/humidity** — none listed. DHT22 is cheap and adequate; SHT31 is better but pricier.
- **HC-SR04 ultrasonic distance sensor** — common, cheap, useful for ranging experiments.
- **Buzzer — active (5V)** — ✅ in stock. Passive buzzer (PWM-driven for tone control) still worth adding.
- **Rotary encoder with pushbutton** — not in stock. Very useful for UI input on embedded projects.
- **Servo motor (SG90 or MG90S)** — not in stock. Covers basic PWM/actuator experiments.

### Comms modules

- **Opto-isolated RS-485 modules** — replacement for the non-isolated MAX485 breakouts. Look for modules with a built-in isolation barrier (e.g. based on ADM2483, or MAX485 + ADUM1201 combo boards). Prevents ground loop and backfeed issues. Relevant for any Argus node where RS-485 bus ground and device ground may differ (engine bay sensor, external nodes).

### Electromechanical / power

- **5V relay modules** — for driving from ESP32 GPIO. SRD-05VDC-SL-C is the bare relay (SPDT); the ready-made 1- or 2-channel relay modules with transistor driver and flyback diode are more convenient for prototyping. Aliexpress, cheap. Get a few.
- **Step-up (boost) converter module** — the Mini360 is step-down only. A small MT3608-based boost module covers 3.7V LiPo → 5V and similar.
- **LiPo battery for bench use** — the 523450 cells have connectors; consider a dedicated bench LiPo with a standard PH2.0 or XT30 connector for powering projects during development.

---

## On order / incoming

- ✅ MAX3485 RS-485 transceivers — arrived 2026-06-05 (5× modules, in sensors-modules.md)
- ✅ PC817 optocouplers — arrived 2026-06-05 (bare chips + 2-channel board)
- ✅ Op-amp / IC haul — arrived 2026-06-05 (LM324, LM393, UA741, NE5532, LM386, ULN2003, ULN2803, more LM358/NE555)

_Nothing currently outstanding on order. Next planned buy is the Mouser order above._
