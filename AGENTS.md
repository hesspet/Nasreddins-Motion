# AGENTS.md

Tiny repo: Arduino sketches for the M5Stack Atomic Motion base (M5AtomS3 + STM32F030 I2C module). Magician prop motion control — experimental, unfinished.

## Layout

- `examples/DriverSample/DriverSample.ino` — only executable code. Arduino sketch.
- `documentation/` — hardware specs, pin map, schematic PDF for the A090-V12 Atomic Motion Base v1.2.
- No build system, no package manifest, no tests, no CI, no lint config. Do not invent commands.

## Working here

- Code targets Arduino IDE / PlatformIO with the M5Stack board support. It cannot be compiled or run on the host PC — it runs on M5AtomS3 (ESP32-S3) and talks to the motion module over I2C.
- Required Arduino libraries (declared in the sketch header, not via a deps file): `M5Unified`, `M5GFX`, `M5AtomicMotion`. Board Manager platform: M5Stack v2.0.9.
- I2C pins are board-dependent: AtomS3 uses SDA=38/SCL=39; other M5 boards use SDA=25/SCL=21. Preserve this branch when editing the init code.
- Hardware capabilities: 2 DC motor channels (RZ7899 driver) + 4 servo channels. Motor speed range -127..127; servo angle 0..180.
- Treat `README.md` as authoritative for project intent (German-speaking maintainer; prose is English but commit/PR conventions and communication may use German with proper umlauts).

## Editing rules

- There is no verification step available on this host. Before claiming a change "works," state it is unverified without hardware.
- Do not add build/lint/test commands — none exist. If the user sets up PlatformIO or a CI workflow later, update this file then.
