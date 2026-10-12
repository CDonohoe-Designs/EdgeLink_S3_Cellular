# EdgeLink S3 Cellular

**ESP32-S3 Embedded Hardware Design | LTE-M / NB-IoT | GNSS | Power Management | Four-Layer PCB | KiCad**

![Rev A system architecture](docs/images/architecture-reva.svg)

## Engineering overview

EdgeLink S3 Cellular is a four-layer embedded hardware platform combining an ESP32-S3 controller, cellular/GNSS connectivity, USB-C, single-cell battery management and motion/environmental sensing.

I developed the Rev A schematic and PCB design as an engineering portfolio project demonstrating hardware architecture, power-tree design, wireless-module integration, digital interfaces, RF-aware layout and preparation of fabrication and assembly deliverables.

**Design status:** Rev A CAD and manufacturing documentation are prepared. The hardware is **unbuilt**; fabrication, assembly, firmware, bring-up, electrical/RF testing and compliance evaluation remain outstanding.

## Engineering evidence — start here

| Resource | What it demonstrates |
| --- | --- |
| [System architecture](docs/images/architecture-reva.svg) | Subsystem integration and functional signal flow |
| [Complete schematic PDF](docs/schematics/EdgeLink_S3_Cellular_RevA_Schematic.pdf) | Hierarchical circuit implementation |
| [Editable KiCad 10 project](hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pro) | Source schematic, four-layer PCB and supporting project assets |
| [Architecture notes](docs/architecture/README.md) | Power rails, interfaces and schematic-sheet mapping |
| [Manufacturing package](manufacturing/REV_A/) | Gerbers, drill data, supplier BOM and component placement |
| [Verification record](docs/verification.md) | Recorded checks, warning triage and remaining limitations |

An illustrated portfolio report and PCB/3D views can be linked here when the actual exports are added to the repository.

## Hardware architecture

| Function | Device / implementation |
| --- | --- |
| Embedded controller and Wi-Fi/Bluetooth LE | ESP32-S3-MINI-1-N8 (U6) |
| LTE-M / NB-IoT and GNSS | SIMCom SIM7080G (U8) |
| Single-cell charging and power path | TI BQ25185 (U5) |
| Main 3.3 V buck-boost supply | TI TPS63802DLAR (U4) |
| Battery fuel gauge | MAX17048G+T10 (U1) |
| Six-axis motion sensing | Bosch BMI323 (U10) |
| Temperature and humidity | Sensirion SHT40 (U11) |
| Barometric pressure | Bosch BMP384 (U12) |
| GNSS antenna bias switching | TPS22919 (U9) |
| External connections | USB-C, battery, Nano-SIM, LTE/GNSS U.FL and I²C |

### Power and interfaces

USB-C provides power to the BQ25185 and carries the ESP32-S3 native USB data signals. The charger/power-path device supplies `VSYS`; the TPS63802 generates `+3V3`. The SIM7080G is supplied from the battery rail through its input filtering, and the MAX17048 monitors the battery.

The modem communicates with the controller through a TXB0108 level-shifting stage and connects to a Nano-SIM holder and separate LTE/GNSS U.FL connectors. The IMU, environmental sensors and fuel gauge use the internal I²C bus; an external I²C connector uses a separate ESP32-S3 signal pair.

## Schematic engineering

The KiCad project uses functional sheets for power/USB, ESP32-S3 processing, cellular/GNSS and sensors. The schematic PDF also includes a retained empty block-diagram sheet. This structure keeps interfaces and power domains understandable during design review and future development.

The design brings together charging and regulation, native USB, cellular modem control, antenna connections, sensor interfaces and local component protection/decoupling. See the [schematic PDF](docs/schematics/EdgeLink_S3_Cellular_RevA_Schematic.pdf) for actual circuit details.

## Four-layer PCB implementation

The Rev A PCB integrates the digital, power, cellular/GNSS and sensing subsystems on a four-layer FR4 board, with four 2.2 mm non-plated mounting holes. Component grouping, local decoupling, ground-return considerations and RF/USB routing geometry form part of the layout work.

The CAD stack records approximately 1.558 mm thickness. The intended supplier order is nominal 1.6 mm, ENIG, JLC04161H-3313; these settings require reconciliation before fabrication. **Formal controlled-impedance verification and measured signal integrity/RF performance are not claimed.**

The editable [PCB project](hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pro) is the authoritative layout source.

## Manufacturing preparation

The repository includes a JLCPCB-oriented Rev A handoff:

- [Gerber fabrication ZIP](manufacturing/REV_A/gerbers/EdgeLink_S3_Cellular_RevA_Gerbers.zip) and drill outputs
- [Assembly BOM with LCSC references](manufacturing/REV_A/bom/EdgeLink_S3_Cellular_RevA_BOM_JLCPCB_UPLOAD.csv)
- [Component placement / CPL](manufacturing/REV_A/cpl/EdgeLink_S3_Cellular_RevA_CPL_JLCPCB_READY.csv)
- [Manufacturing notes](manufacturing/REV_A/README.md)

The BOM groups 89 fitted component references into 46 rows; the CPL contains the matching 89 unique references, all on the top side. Solder-paste Gerbers are **not** included. Stencil requirements, assembler placement preview and supplier configuration require confirmation before an order.

## Verification and project status

Recorded KiCad 10.0.6 checks on 11 October 2026 found **zero ERC violations, zero PCB DRC errors and zero unconnected items**, with **six layout warnings and 141 additional schematic-parity warnings**. These warnings have not been presented as a fully clean design release.

Known considerations include silkscreen clearance, library/footprint identity differences, the U6 placement-preview discrepancy and supplier stack/finish reconciliation. The detailed findings, including the U6 and U12 footprint-name considerations, remain in [verification notes](docs/verification.md).

**Not yet completed:** fabrication, assembly, board bring-up, application firmware, electrical/power measurements, cellular/GNSS and sensor testing, RF verification, EMC/compliance assessment or full manufacturing qualification. The existing design should be independently reviewed before production.

## What this project demonstrates

- ESP32-S3 module integration and hierarchical schematic design
- Cellular/GNSS modem interfaces and RF-aware PCB planning
- Single-cell battery charging, power-path and buck-boost architecture
- USB-C and digital sensor/I²C connectivity
- Four-layer PCB design and project library management in KiCad
- Supplier-oriented BOM, CPL and Gerber preparation
- Traceable verification records and transparent engineering documentation

## Repository guide

| Location | Contents |
| --- | --- |
| `hardware/kicad/EdgeLink_S3_Cellular_RevA/` | KiCad 10 source project, local libraries and 3D assets |
| `docs/architecture/` and `docs/images/` | Architecture notes and diagram |
| `docs/schematics/` | Schematic PDF |
| `docs/verification.md` | Verification evidence and open considerations |
| `docs/references.md` | Manufacturer sources and CAD attribution |
| `manufacturing/REV_A/` | Fabrication and assembly handoff |

**Tools and workflow:** KiCad 10, ESP32-S3 hardware integration, cellular/GNSS module integration, LCSC/JLCPCB-oriented manufacturing preparation and Git/GitHub.

## Attribution and reuse

No project-wide licence has been selected. Normal copyright restrictions apply. Third-party CAD assets retain their respective rights and notices. See [references and attribution](docs/references.md).
