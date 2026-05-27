# Claude Instructions — Electronics Inventory

This vault tracks Joachim's bench electronics components. Claude is both the primary consumer (reading stock when assisting with design) and the primary maintainer (updating files based on natural-language intake from the user).

## Category files

One markdown file per category, in the `inventory/` subfolder:

- `inventory/passives.md` — resistors, capacitors, inductors, crystals, ferrite beads
- `inventory/semiconductors-discrete.md` — diodes, transistors, MOSFETs, triacs, optocouplers
- `inventory/ics.md` — logic, op-amps, regulators, microcontrollers, drivers, comms ICs
- `inventory/sensors-modules.md` — sensor breakouts, display modules, radio modules, dev boards
- `inventory/electromechanical.md` — relays, switches, fans, motors, buzzers, fuses
- `inventory/connectors.md` — pin headers, JST, Dupont, terminal blocks, USB, barrel jacks
- `inventory/power.md` — batteries, buck/boost converters, LDOs, charger modules, anything power-supply-related
- `inventory/misc.md` — anything that doesn't fit cleanly above; propose a new category if a misc entry grows

New categories can be proposed and added as the collection grows.

## Component schema

Plain markdown. Component name as a heading, details as a list:

```markdown
## Component name / value

- Package: [package or form factor]
- Qty: [quantity — see conventions below]
- Notes: [optional — voltage rating, tolerance, source, specific part number, known use]
```

Multiple related values can live under a shared section heading if that reads more naturally (e.g. a resistor value range).

## Quantity conventions

- `~50`, `~100`, `~200` etc. — well-stocked, no need to count precisely
- `~10`, `~20` — moderate stock, worth noting
- `marginal` — low stock, user should physically check before relying on it
- `2`, `1` — exact count for scarce or critical parts
- `unknown` — present but not counted (use for initial intake if genuinely unsure)

## Intake workflow

User describes new arrivals in natural language. Claude identifies the right category file, adds or updates entries, and logs the batch in `CHANGELOG.md`. Ask clarifying questions about package, value, or quantity if the description is ambiguous enough to matter.

## Changelog

After every update session (not the initial population), append an entry to `CHANGELOG.md` in this format:

```
## YYYY-MM-DD — [brief description]
- Added: [what was added]
- Updated: [what quantities or notes changed]
- Restructured: [any category or schema changes]
```

## Design assistance

When helping with a circuit or design, check the relevant category files for available stock and factor that into recommendations — prefer parts on hand where reasonable, and flag if a design calls for something not in stock or marginal.
