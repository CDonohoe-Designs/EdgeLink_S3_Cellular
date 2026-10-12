# Rev A checks and known limitations

The design is unbuilt. These are CAD/publication and manufacturing-file
consistency checks, not electrical, RF, EMC, thermal or full DFM qualification.

## KiCad evidence

KiCad 10.0.6 checks on 11 October 2026 and the post-preparation repeat on
12 October 2026 completed successfully with the same results:

| Check | Result |
| --- | --- |
| ERC | Zero violations |
| Layout DRC | Zero errors; six warnings |
| Unconnected items | Zero |
| Additional schematic parity | 141 warnings |

The six layout warnings consist of two silkscreen/board-edge warnings at U6,
three silkscreen/solder-mask warnings at D6/D7/D8, and one library-footprint
mismatch at D5. The placed D5 footprint has not been replaced from its library.

The 141 parity warnings are triaged as follows:

| Category | Count | Interpretation and action |
| --- | --- | --- |
| Custom symbol/footprint fields | 109 | PCB and schematic metadata differ, including manufacturer/part fields. Review separately; no automatic PCB update was performed. |
| Symbol/footprint mismatch | 21 | R8's PCB value text is `R8` versus schematic `10k`; TP1-TP16 and C19-C22 BOM-exclusion flags differ. The explicit release BOM/CPL excludes those test/DNP refs. Preserve source and review metadata before future exports. |
| Extra footprints | 5 | Four mounting-hole footprints and one board graphic/mechanical footprint are PCB-only objects. Preserve them. |
| Duplicate footprint references | 4 | Repeated `REF**` among the PCB-only mechanical/graphic objects; not duplicate fitted BOM/CPL designators. |
| Footprint filters | 2 | JBT1 and L1 do not match the symbols' filter strings. This is not proof of physical incompatibility; pad/package review remains separate. |

The warning set is disclosed rather than presented as a fully clean design.
Publication changes do not resolve the 141 warnings through a schematic-to-PCB
update.

## Publication changes

Only documentation, output/model paths and optional model references were
prepared. Four unsupported power-sheet check labels were changed to pending
review/testing labels. The ESP32 free-text notes were corrected to match its
actual I2C pairs, modem UART and IMU interrupt. Electrical schematic nodes and
PCB geometry, routing, placement, nets and stack-up were preserved.

The current PCB's existing lock settings were retained, including the 1,176
lock additions identified in the Phase A diff. The complete current board has
1,263 `locked yes` settings. The existing I2C net colour was retained.

The corrected schematic PDF was regenerated from the current source. All six
pages were visually reviewed for rendering and private information before staging. Page
six is the existing empty block-diagram child sheet. The separate architecture
diagram describes the design's functional blocks.

## Model references

Four `S3Stick_Footprints.pretty` model paths formerly pointed to missing files
under `Custom_Footprints.pretty`. Each now references its same-named existing
STEP file alongside the footprint. No pad geometry was changed.

Project-local `Libraries` paths were normalised to `libraries`, and the bare
JST SH connector model path was made explicitly `${KIPRJMOD}`-relative. All
remaining project-local model/library references are checked with exact path
case. Standard models still require the installed KiCad 10 libraries.

The optional model block was removed from
`libraries/TPS22919DCKR/TPS22919DCKR.pretty/SC-70-6_L2.2-W1.3-P0.65-LS2.1-BR.kicad_mod`.
Its reference pointed to an absent `SC-70-6_L2.0-W1.3-H1.0-P0.65.wrl`.
The footprint has six pads at 0.65 mm pitch. The existing TPS22919 candidate
STEP has an approximately 2.10 by 2.00 mm Cartesian-point envelope, but its
pin-1 orientation and registration against this footprint were not established.
It was not substituted. Pads, numbering, position and existing candidate model
files are retained; a future verified model association remains open.
The placed board's model references are preserved except for path-case/JST
normalisation.

## Manufacturing consistency

The release BOM has 46 rows and 89 unique fitted references. The CPL has the
same 89 unique references, all Top; supplier codes are nonblank. TP1-TP16 and
C19-C22 are absent. U12 is BMP384 / C5577555; R8,R12,R14,R25 use C2906861;
U6's original coordinates are 49.600000, -66.650000, 90 degrees, Top.

The readable Gerber ZIP contains 12 outputs that match the loose files exactly.
Four copper layers, masks, silkscreens, outline, PTH/NPTH and job file are present.
Four 2.2 mm NPTH mounting holes are present in source and drill output. No paste
Gerbers are included. The existing manufacturing data is preserved unchanged.
Repository `.gitattributes` disables Git line-ending conversion for manufacturing
CSV and Gerber/drill/job/ZIP files so the staged loose outputs remain
byte-for-byte identical to ZIP members, including their original line endings.

## Still pending

Fabrication, assembly, bring-up, firmware, RF validation, sensor validation,
power testing, EMC/compliance and full DFM qualification remain pending. This
release does not establish full datasheet/pin/package verification, component
lifecycle/stock, supplier rotation conventions, verified impedance or completed
third-party rights clearance. Independently review before manufacture or use.
