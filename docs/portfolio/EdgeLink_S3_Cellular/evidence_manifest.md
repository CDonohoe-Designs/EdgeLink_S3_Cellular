# Portfolio evidence manifest

Source commit: `8bded932abc2eb7f814c76b664655bd760522112` on `main`.
Date: 12 October 2026. Phase A image generation and inspection only.

All primary figures are project-derived. Direct KiCad exports retain electrical
and physical geometry; schematic crops omit surrounding material only. The
mechanical, stack-up and manufacturing panels are explicitly labelled evidence
illustrations derived from source coordinates, settings and actual records.

## Primary figures

### Figure A01 schematic-controller.png

- Image: [open](images/schematic-controller.png)
- Caption: ESP32-S3 module, supply decoupling, named USB/UART/I2C signals and source design notes.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/02_ESP32_S3.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 2424 × 2228 pixels
- SHA-256: `fe7318e8ff5996d8edcec00d8e86b9377b3009e3785bcc94f218a4f1df6999cc`
- Notes: Crop coordinates (17, 16, 177, 163) mm; no rewiring or labels added to the schematic.

### Figure A02 schematic-usb-c.png

- Image: [open](images/schematic-usb-c.png)
- Caption: USB-C connector, CC resistors, TPD2EUSB30A protection and series data resistors.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/01_Power_USB.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 1743 × 1243 pixels
- SHA-256: `dcb478e11b31433139eb718144cf835d9286216497cedd0e731b8a559cc85f78`
- Notes: Crop coordinates (15, 21, 130, 103) mm; no rewiring or labels added to the schematic.

### Figure A03 schematic-bq25185-power-path.png

- Image: [open](images/schematic-bq25185-power-path.png)
- Caption: BQ25185 charging/power-path circuitry and single-cell battery connector.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/01_Power_USB.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 2303 × 1243 pixels
- SHA-256: `b1779ea9e210e6365a7911ea8d58b56ff11f7ce69f1a44484b645c31b5da5d34`
- Notes: Crop coordinates (130, 21, 282, 103) mm; no rewiring or labels added to the schematic.

### Figure A04 schematic-tps63802-regulator.png

- Image: [open](images/schematic-tps63802-regulator.png)
- Caption: TPS63802 buck-boost power stage, inductor, capacitors and feedback divider.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/01_Power_USB.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 2046 × 1197 pixels
- SHA-256: `c759f9dba1ceded1b0f6a9fab8a8aa419cd283261e466844b9439fc1be239a74`
- Notes: Crop coordinates (15, 103, 150, 182) mm; no rewiring or labels added to the schematic.

### Figure A05 schematic-fuel-gauge.png

- Image: [open](images/schematic-fuel-gauge.png)
- Caption: MAX17048 battery monitor and internal I2C connection.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/01_Power_USB.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 1954 × 939 pixels
- SHA-256: `580aa96955014a05a74cf613eefeb79351381d0bebd744ea246a9627c48bf669`
- Notes: Crop coordinates (151, 103, 280, 165) mm; no rewiring or labels added to the schematic.

### Figure A06 schematic-sim7080g-interface.png

- Image: [open](images/schematic-sim7080g-interface.png)
- Caption: SIM7080G symbol with its power, UART, SIM and RF interface nets.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/03_SIM7080G_Cellular_GNSS.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 2085 × 3015 pixels
- SHA-256: `bb3fe37cbd2c16b1d992c2e3556efcd0af59412c81c89cfbd65454e35665d432`
- Notes: Crop coordinates (151, 60, 290, 261) mm; no rewiring or labels added to the schematic.

### Figure A07 schematic-modem-uart-level-shifter.png

- Image: [open](images/schematic-modem-uart-level-shifter.png)
- Caption: TXB0108 level shifter and modem/controller UART and control signals.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/03_SIM7080G_Cellular_GNSS.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 1725 × 975 pixels
- SHA-256: `c788b35b925d93d775fa1b8a209160a5207eb406974e83b5c5801c9b5d582dc3`
- Notes: Crop coordinates (23, 145, 138, 210) mm; no rewiring or labels added to the schematic.

### Figure A08 schematic-gnss-antenna-power.png

- Image: [open](images/schematic-gnss-antenna-power.png)
- Caption: GNSS U.FL interface and TPS22919 antenna-bias switching circuit.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/03_SIM7080G_Cellular_GNSS.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 1695 × 1800 pixels
- SHA-256: `9ebd3aa3b246d924cb11c49ac61be0ce6101de40046585863e5f1f5b59d0f855`
- Notes: Crop coordinates (292, 18, 405, 138) mm; no rewiring or labels added to the schematic.

### Figure A09 schematic-lte-rf-interface.png

- Image: [open](images/schematic-lte-rf-interface.png)
- Caption: LTE U.FL interface, RF support components and DNP capacitor positions.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/03_SIM7080G_Cellular_GNSS.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 1680 × 840 pixels
- SHA-256: `70070248eea752379a608aac5c38051b17c01a2183e1075f5ce7c76f8bbc346e`
- Notes: Crop coordinates (292, 140, 404, 196) mm; no rewiring or labels added to the schematic.

### Figure A10 schematic-nano-sim.png

- Image: [open](images/schematic-nano-sim.png)
- Caption: Nano-SIM holder, interface resistors and ESDA6V1W5 protection.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/03_SIM7080G_Cellular_GNSS.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 1725 × 1095 pixels
- SHA-256: `dbae2f77595f81d3e231ff35c83b2e01d3852d1048049269f9f3f3f28529403e`
- Notes: Crop coordinates (23, 211, 138, 284) mm; no rewiring or labels added to the schematic.

### Figure A11 schematic-sensors-i2c.png

- Image: [open](images/schematic-sensors-i2c.png)
- Caption: BMP384, SHT40, BMI323, internal pull-ups and external I2C connector.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/04_Sensors.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 4106 × 1757 pixels
- SHA-256: `03ea7fe48f6ce21fcea3185188af79dad669c9c64028bb9f49a2b2a97bd71564`
- Notes: Crop coordinates (14, 43, 285, 159) mm; no rewiring or labels added to the schematic.

### Figure A12 schematic-bmp384.png

- Image: [open](images/schematic-bmp384.png)
- Caption: BMP384 pressure-sensor supply, decoupling and I2C wiring.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/04_Sensors.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 1440 × 985 pixels
- SHA-256: `d4414b8ac9c368927ab3577cf7cd8a978a75c8fedd9a0a880d4ac5951525e484`
- Notes: Crop coordinates (14, 44, 109, 109) mm; no rewiring or labels added to the schematic.

### Figure A13 schematic-sht40.png

- Image: [open](images/schematic-sht40.png)
- Caption: SHT40 temperature/humidity sensor and local decoupling.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/04_Sensors.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 1212 × 924 pixels
- SHA-256: `2170c3b49d32c949a1e851ed04f9b09ff615074523c46f37c58901572bd9d0bd`
- Notes: Crop coordinates (110, 44, 190, 105) mm; no rewiring or labels added to the schematic.

### Figure A14 schematic-bmi323.png

- Image: [open](images/schematic-bmi323.png)
- Caption: BMI323 IMU supply, I2C interface and INT1 connection.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/04_Sensors.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 1409 × 1318 pixels
- SHA-256: `18e6ff6c37852e281bd2577a3f02424a14dc4f404eb4da2a05f041ad8b1eab9f`
- Notes: Crop coordinates (191, 44, 284, 131) mm; no rewiring or labels added to the schematic.

### Figure A15 schematic-external-i2c.png

- Image: [open](images/schematic-external-i2c.png)
- Caption: External I2C connector with separate I2C_EXT signals and pull-ups.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/04_Sensors.kicad_sch`
- Method: KiCad CLI SVG export; aspect-preserving PNG conversion; crop in source-page millimetres.
- Size: 1166 × 818 pixels
- SHA-256: `8b9ef1bcc7e624d7e25ab61fb8898efc16cafb3eb3ef766a0fd509bd63d8b7aa`
- Notes: Crop coordinates (110, 105, 187, 159) mm; no rewiring or labels added to the schematic.

### Figure A16 pcb-top-layout.png

- Image: [open](images/pcb-top-layout.png)
- Caption: Top-side copper and silkscreen plot of the actual Rev A board.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pcb`
- Method: KiCad CLI pcb export svg; 3000-pixel-wide aspect-preserving PNG.
- Size: 3000 × 2786 pixels
- SHA-256: `2ac61cbfda643938ea7c98f2caff72fd120db2aa2d977398c1b73d3586d6d5d5`
- Notes: Top viewing orientation; F.Cu, F.SilkS and Edge.Cuts. No fabrication-value overlay.

### Figure A17 pcb-bottom-layout.png

- Image: [open](images/pcb-bottom-layout.png)
- Caption: Bottom-side copper and silkscreen plot of the actual Rev A board.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pcb`
- Method: KiCad CLI pcb export svg; 3000-pixel-wide aspect-preserving PNG.
- Size: 3000 × 2786 pixels
- SHA-256: `c131934cefa3177e89f2ce6aa11fcd629b94565989d80f272a176085a448667e`
- Notes: Intentionally mirrored by KiCad to represent viewing the underside; B.Cu, B.SilkS and Edge.Cuts.

### Figure A18 pcb-copper-top.png

- Image: [open](images/pcb-copper-top.png)
- Caption: F.Cu source copper plot.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pcb`
- Method: KiCad CLI pcb export svg; 3000-pixel-wide aspect-preserving PNG.
- Size: 3000 × 2786 pixels
- SHA-256: `90a19ed1ba36a525668c9a30093297915f16578b44961ddbbfcb22d89ed29e66`
- Notes: Common top-view orientation used for the layer comparison.

### Figure A19 pcb-copper-inner-1.png

- Image: [open](images/pcb-copper-inner-1.png)
- Caption: In1.Cu source copper plot with GND zone.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pcb`
- Method: KiCad CLI pcb export svg; 3000-pixel-wide aspect-preserving PNG.
- Size: 3000 × 2786 pixels
- SHA-256: `88d5d8458cb1b3b8d6b5f673609474438d84087e4e7e559762b95f61dd936f34`
- Notes: Common top-view orientation; source zone assignment GND.

### Figure A20 pcb-copper-inner-2.png

- Image: [open](images/pcb-copper-inner-2.png)
- Caption: In2.Cu source copper plot with +3V3 and SIM_BAT zones.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pcb`
- Method: KiCad CLI pcb export svg; 3000-pixel-wide aspect-preserving PNG.
- Size: 3000 × 2786 pixels
- SHA-256: `010b92f711c3f2af9c28d7e1848ae845f71cc0d30d0ccf67a37dd6a0dafa916e`
- Notes: Common top-view orientation; do not call this a single uninterrupted ground plane.

### Figure A21 pcb-copper-bottom.png

- Image: [open](images/pcb-copper-bottom.png)
- Caption: B.Cu source copper plot with GND zone.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pcb`
- Method: KiCad CLI pcb export svg; 3000-pixel-wide aspect-preserving PNG.
- Size: 3000 × 2786 pixels
- SHA-256: `4ea5fc8b0101fa26e10d486cdfa7f5b57541d56e42f3c0fa9ddedd947b81c33b`
- Notes: Common top-view orientation, not mirrored, for direct layer comparison.

### Figure A22 architecture-reva.png

- Image: [open](images/architecture-reva.png)
- Caption: Rev A architecture diagram including the actual power tree, controller, modem and sensors.
- Source: `docs/images/architecture-reva.svg`
- Method: Existing project SVG rasterised to 3960 pixels wide.
- Size: 3960 × 2550 pixels
- SHA-256: `1dc9431aad4d860dd6fce8debb9b5db742b526c3301fc57a107073fec49fcadf`

### Figure A23 pcb-four-layer-copper.png

- Image: [open](images/pcb-four-layer-copper.png)
- Caption: Four-layer copper organisation: source GND and supply-zone assignments.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pcb`
- Method: Four native copper exports arranged without stretching or changing orientation.
- Size: 3300 × 3470 pixels
- SHA-256: `a3f055306baaf9ab91f976e9e3acb7d0fd3a64192f02d908abdfed0e9f4a8a04`

### Figure A24 pcb-mechanical-geometry.png

- Image: [open](images/pcb-mechanical-geometry.png)
- Caption: 56 × 52 mm nominal board outline and four 2.2 mm mounting holes.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pcb`
- Method: Dimensioned diagram constructed from source Edge.Cuts start/end/radius and NPTH pad coordinates.
- Size: 2700 × 2700 pixels
- SHA-256: `57604aef5127e9472ed7301ed009bb379d08e3328ffc8944a8e5a71380c96e44`
- Notes: No geometric edits to the board; small USB holes explicitly excluded from this simplified illustration.

### Figure A25 manufacturing-and-verification-evidence.png

- Image: [open](images/manufacturing-and-verification-evidence.png)
- Caption: BOM/CPL excerpts, release contents and disclosed ERC/DRC/parity results.
- Source: `manufacturing/REV_A/bom/EdgeLink_S3_Cellular_RevA_BOM_JLCPCB_UPLOAD.csv; manufacturing/REV_A/cpl/EdgeLink_S3_Cellular_RevA_CPL_JLCPCB_READY.csv; docs/verification.md; manufacturing/REV_A/README.md`
- Method: Actual CSV rows and recorded check results typeset as evidence; values checked against source.
- Size: 3300 × 2360 pixels
- SHA-256: `8f717587ae0e76d84357382f2b8988c25ac221c01a4a6a55116db3713de3d7bc`
- Notes: Footprint library prefixes omitted in the panel for fit; full strings remain in the CSV. Not an order, manufacturing receipt or test certification.

### Figure A26 pcb-stackup-evidence.png

- Image: [open](images/pcb-stackup-evidence.png)
- Caption: Actual CAD stack-up distinguished from intended supplier order.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pcb; manufacturing/REV_A/README.md`
- Method: Source stack-up values and recorded intended order typeset as an explicitly non-scale diagram.
- Size: 2800 × 1700 pixels
- SHA-256: `30e55affbafd0d578bdfa0003d45bb2012e25be85bf8b1e6e9e7a75fd0e382d1`
- Notes: Mask layers omitted from the sketch, included in CAD total; thicknesses are recorded values, not measurements.

### Figure A27 pcb-isometric-overview.png

- Image: [open](images/pcb-isometric-overview.png)
- Caption: Complete-board isometric CAD render produced by KiCad 10.0.6.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pcb; project-local and installed KiCad 3D models`
- Method: Native KiCad CLI pcb render from byte-identical temporary project copy.
- Size: 3168 × 2384 pixels
- SHA-256: `bb36e6ccad61b1adc5575581bde057f5e854dd1d96d200696eda3a22712020aa`
- Notes: Basic render quality; all corners retained. Unbuilt CAD model, not a manufactured-board photograph.

### Figure A28 pcb-isometric-detail.png

- Image: [open](images/pcb-isometric-detail.png)
- Caption: High-quality isometric CAD detail from the actual board and models.
- Source: `hardware/kicad/EdgeLink_S3_Cellular_RevA/EdgeLink_S3_Cellular.kicad_pcb; project-local and installed KiCad 3D models`
- Method: Native KiCad CLI pcb render from byte-identical temporary project copy.
- Size: 3168 × 2384 pixels
- SHA-256: `30f2c8ee0745e77d8c25f5f61dbb49f446df34405bf22008ea416179fb02bd3e`
- Notes: High render quality. Intentionally tight detail view; not used as a whole-board mechanical overview.

## Recorded verification evidence

Source: `docs/verification.md` and `manufacturing/REV_A/README.md` at the recorded commit.

| Check | Recorded result |
| --- | --- |
| ERC | 0 violations |
| Layout DRC | 0 errors, 6 warnings |
| Unconnected items | 0 |
| Additional schematic parity | 141 warnings |

Six layout warnings: two silkscreen/board-edge at U6; three silkscreen/mask at
D6/D7/D8; one D5 library-footprint mismatch.

Parity: 109 custom-field mismatches; 21 value/BOM-exclusion mismatches; five
extra mechanical/graphic footprints; four duplicate REF** mechanical-reference
warnings; two footprint-filter mismatches. No automatic source update was made.

## Manufacturing records rechecked for this portfolio

- `manufacturing/REV_A/bom/EdgeLink_S3_Cellular_RevA_BOM_JLCPCB_UPLOAD.csv`:
  46 rows, 89 unique fitted refs, existing `LCSC Part #` header.
- `manufacturing/REV_A/cpl/EdgeLink_S3_Cellular_RevA_CPL_JLCPCB_READY.csv`:
  89 unique matching refs, all Top.
- U12: BMP384 / C5577555. R8,R12,R14,R25: C2906861.
- U6 placement: X 49.600000, Y -66.650000, rotation 90 degrees, Top.
- TP1-TP16 and C19-C22 are excluded from fitted records.
- Gerber ZIP: 12 members, CRC check passes, loose files match.
- Four copper layers, masks/silkscreens, outline, PTH/NPTH and job file are present.
- Solder-paste Gerbers are absent; no assembly/fabrication success is implied.

## Orientation and rendering

`pcb-bottom-layout.png` is mirrored to show an underside inspection view, with
readable bottom silkscreen. Individual copper images and the four-layer panel
share the original top-view orientation for comparison. All PNG conversions
preserve aspect ratio. CAD colours and model display are render appearance,
not measured finish or assembly evidence. The detailed 3D view is intentionally
tightly framed; use the overview for complete-board presentation.

## Supplementary native exports

Native SVGs and four complete schematic-page PNGs are supplied for enlargement
and source inspection. They are not all intended to appear in the six-page PDF.
The blank source block-diagram child sheet is not selected for the portfolio;
the existing project architecture diagram supplies the architectural evidence.

## Scope limits

No new circuit simulation, pin/package verification, live sourcing, EMC testing
or DFM qualification was performed. The project remains unbuilt. Physical
performance and supplier assumptions require later engineering review/testing.
48 V protection, RS-485 and SPI Ethernet are target-project requirements, not
features demonstrated by this board. No Altium authorship is claimed.
