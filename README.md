# EdgeLink S3 Cellular

**Rev A is an unbuilt engineering portfolio/reference design** for an ESP32-S3
cellular, GNSS and environmental-sensing platform. The schematic, PCB and
manufacturing package are prepared. Fabrication, assembly, bring-up, firmware,
RF validation, sensor validation, power testing, EMC/compliance testing and full
DFM qualification remain pending.

## Overview

This project brings together an ESP32-S3 controller, a SIM7080G LTE-M/NB-IoT and
GNSS modem, USB-C, single-cell battery power management and motion/environmental
sensors on a four-layer PCB. It demonstrates hardware architecture, power-tree
design, interface integration, RF-aware layout, project-local KiCad libraries
and preparation of a fabrication/assembly handoff.

## System architecture

![Rev A design architecture](docs/images/architecture-reva.svg)

The diagram describes the CAD design, not measured hardware behaviour. See
[architecture notes](docs/architecture/README.md) for the rails, interfaces and
source-sheet mapping.

## Hardware

| Function | Selected device or connection |
| --- | --- |
| Controller and Wi-Fi/Bluetooth LE | U6: ESP32-S3-MINI-1-N8 |
| LTE-M/NB-IoT and GNSS | U8: SIMCom SIM7080G |
| Battery charging and power path | U5: Texas Instruments BQ25185 |
| Main 3.3 V buck-boost rail | U4: Texas Instruments TPS63802DLAR |
| Battery fuel gauge | U1: MAX17048G+T10 |
| Motion sensing | U10: Bosch BMI323 six-axis IMU |
| Temperature and humidity | U11: Sensirion SHT40-AD1B-R2 |
| Pressure sensing | U12: Bosch Sensortec BMP384 |
| GNSS antenna supply control | U9: TPS22919DCKR |
| External interfaces | USB-C, battery connector, Nano-SIM, LTE/GNSS U.FL and external I2C |

### Power and connectivity

USB-C supplies the BQ25185 input and carries the ESP32-S3 native USB data pair.
The BQ25185 manages the single-cell battery connection and provides `VSYS` to
the TPS63802, which generates `+3V3`. The SIM7080G supply is derived from `VBAT`
through its filtering network. The MAX17048 monitors the battery.

The controller communicates with the modem through the U7 TXB0108 UART level
shifter. The modem connects to the Nano-SIM holder and separate LTE and GNSS
U.FL connectors. BMI323, SHT40, BMP384 and the fuel gauge share the internal I2C
pair; the external I2C connector uses a separate ESP32 signal pair. GNSS antenna
bias is controlled through U9. Firmware is not included.

## PCB and supplier configuration

The CAD file records four-layer FR4, approximately **1.558 mm** total thickness,
a **1.238 mm** core, 0.035 mm outer copper, 0.015 mm inner copper and copper
finish **`None`**. Four 2.2 mm non-plated mounting holes are present.

The intended supplier order is nominal **1.6 mm, ENIG, JLC04161H-3313**. Those
ordering assumptions differ from the CAD settings and must be reconciled with
the supplier before fabrication. The layout uses geometry intended for the RF
and USB routes; no formal controlled-impedance verification or certification
is claimed.

## Open the design

Use **KiCad 10** with its standard symbol, footprint and 3D-model libraries.
Open
[`EdgeLink_S3_Cellular.kicad_pro`](hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pro).
Keep the project folder, `libraries/` and `3D_Models/` together. Local library and
model paths are project-relative; manufacturing output is directed to
`../../../manufacturing/REV_A/gerbers` from the project directory.

The main schematic contains power/USB, ESP32-S3, modem/GNSS and sensor sheets,
plus an empty block-diagram child sheet retained from the source hierarchy.
The schematic PDF therefore has six pages, including that empty sheet.

## Repository structure

| Path | Contents |
| --- | --- |
| `hardware/kicad/EdgeLink_S3_Cellular_RevA/` | Editable Rev A design, local libraries and models |
| `docs/architecture/` and `docs/images/` | Source-based architecture notes and diagram |
| `docs/schematics/` | Current six-page schematic PDF |
| `docs/verification.md` | Check results, warning triage and model-reference limitations |
| `docs/references.md` | Manufacturer links and available CAD attribution |
| `manufacturing/REV_A/` | Current BOM, CPL, Gerber ZIP and matching loose outputs |

## Manufacturing package

The authoritative upload files are:

- [Fabrication ZIP](manufacturing/REV_A/gerbers/EdgeLink_S3_Cellular_RevA_Gerbers.zip)
- [Assembly BOM](manufacturing/REV_A/bom/EdgeLink_S3_Cellular_RevA_BOM_JLCPCB_UPLOAD.csv)
- [Component placement](manufacturing/REV_A/cpl/EdgeLink_S3_Cellular_RevA_CPL_JLCPCB_READY.csv)

The BOM has 46 part groups and 89 fitted references, with the existing
`LCSC Part #` supplier column. The CPL contains the same 89 unique references,
all on Top. The package contains **no solder-paste Gerbers**. Its PCB fabrication
content has been checked; stencil and assembly requirements must be confirmed
before ordering. See [manufacturing notes](manufacturing/REV_A/README.md).

## Verification and known considerations

KiCad 10.0.6 checks on 11 October 2026 reported zero ERC violations, zero layout
DRC errors, zero unconnected items, **six layout warnings** and **141 additional
schematic-parity warnings**. The publication changes preserve electrical
connectivity, PCB geometry, placement, routing and stack-up. Details and the
post-preparation checks are recorded in [verification notes](docs/verification.md).

The layout warnings concern silkscreen at board edges/mask openings and D5's
library-footprint mismatch. Parity warnings concern custom fields, values/BOM
exclusions, mechanical references and footprint filters. These results do not
establish a fully clean or qualified design.

U12 is BMP384 / C5577555; its existing footprint/model names retain `BMP390`.
U6 retains an `ESP32-S2-MINI-1` footprint identifier. Naming alone establishes
neither compatibility nor incompatibility. The release preserves their existing
pads and placement. U6's original CPL coordinates remain unchanged; the
assembler must confirm placement against actual pads and pin orientation,
including the previously observed preview-overlay offset.

Four local model paths have been repaired. One optional broken TPS22919 library
model reference has been removed without changing its pads; the candidate model
files remain available for a future orientation/registration check.

## Design status and use

This is a prepared Rev A CAD/manufacturing snapshot. The hardware remains
unbuilt. Fabrication, assembly, board bring-up, application firmware, RF and
sensor validation, power measurements, EMC/compliance testing and full DFM
qualification remain pending. Independently review the source, component
selection, manufacturing outputs and supplier requirements before manufacture
or deployment.

No project-wide licence has been selected. Normal copyright restrictions
apply. Third-party libraries and models retain their own rights and notices;
their inclusion does not grant them a project-wide licence. See
[references and attribution](docs/references.md).
