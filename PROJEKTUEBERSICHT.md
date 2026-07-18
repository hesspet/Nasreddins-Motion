# Projektübersicht

## Nasreddins-Motion

Experimentelles, unvollständiges Proof-of-Concept-Projekt zur Steuerung von Aktoren über kostengünstige Mikrocontroller. Zweck: Zauberkünstler einfache Möglichkeiten geben, Bühnenbewegungen per Mikrocontroller, Smartphone oder Smartwatch auszulösen.

## Technologie

- **Hardware:** M5Stack Atomic Motion Base v1.2 (A090-V12)
  - MCU: M5AtomS3 (ESP32-S3, Arduino-kompatibel)
  - motion module: STM32F030F4P6, per I2C angebunden
  - 2 DC-Motor-Kanäle (Treiber RZ7899), Geschwindigkeit -127..127
  - 4 Servo-Kanäle, Winkel 0..180
  - einstellbare Lithium-Batterie 18350@900mAh, Lade-/Entladeschutz
- **Toolchain:** Arduino IDE / PlatformIO, M5Stack Board Manager v2.0.9
- **Arduino-Bibliotheken:** `M5Unified`, `M5GFX`, `M5AtomicMotion`
- **Kein** Build-System, **keine** Tests, **keine** CI, **keine** Lint-Konfiguration im Repo.

## Struktur

```
.
├── examples/DriverSample/DriverSample.ino   # einzige ausführbare Datei
├── documentation/                            # Spezifikationen, Pin-Map, Schema
│   ├── A090-V12_Atomic Motion Base v1.2_readings_and_links.md
│   └── A090-V12_Atomic Motion Base v1.2_schematic.pdf
├── README.md
├── LICENSE
└── AGENTS.md
```

## Wichtige Hinweise

- Code ist **nicht** auf dem Host-Compilier- oder ausführbar. Läuft ausschließlich auf M5AtomS3, Spricht mit motion module über I2C.
- I2C-Pins plattformabhängig: M5AtomS3 SDA=38/SCL=39, andere M5-Boards SDA=25/SCL=21. Verzweigung im Setup bleibt erhalten.
- `Overview.md` hierzu Gleicher Wahrheitsgehalt wie `README.md` für Projektabsicht.
- Beiträge und Feedback willkommen. Maintainer deutschsprachig → Commits/PRs mit Umlauten (äöüß), Prosa im Repo ist Englisch.

## Bezüge

- Quelle/Historie: https://github.com/hesspet/Nasreddins-Motion
- Bibliotheken: https://github.com/m5stack/{M5Unified,M5GFX,M5Atomic-Motion}
- Hardware-Schema: siehe `documentation/`
