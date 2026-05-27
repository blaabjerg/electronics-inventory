# Wishlist

Component gaps identified against current inventory. Organized by priority.

---

## Make: Electronics 3rd ed. (Platt) — specific gaps

Items called out in the official Kit 1 (Sections 1–3) and Kit 2 (Sections 4–5) that aren't in stock.

### Kit 1 / Sections 1–3

- **9V relay, DPDT, PCB mount** — the book uses a relay as a core component in several experiments. Get a 9V coil DPDT type (same as Platt recommends). ~2–3 pcs.
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
- **Optocouplers** — PC817 or 4N35. None in stock. Important for isolating ESP32/logic from mains-adjacent or high-voltage circuits. Already implicitly needed for the Orion-Tr remote control in the Argus project (optocoupler spec'd but not procured for bench use).
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

### Electromechanical / power

- **5V relay module** — the L298N drives motors; nothing drives a relay from ESP32 logic directly. A small optocoupler-isolated relay module (1- or 2-channel, 5V coil) covers mains-adjacent switching safely.
- **Step-up (boost) converter module** — the Mini360 is step-down only. A small MT3608-based boost module covers 3.7V LiPo → 5V and similar.
- **LiPo battery for bench use** — the 523450 cells have connectors; consider a dedicated bench LiPo with a standard PH2.0 or XT30 connector for powering projects during development.

---

## On order / incoming

- MAX3485 RS-485 transceivers (3.3V logic, drop-in RS-485 for ESP32 nodes)
- PC817 optocouplers — bare chips + breakout boards for prototyping
- Additional op-amps (TBD)
