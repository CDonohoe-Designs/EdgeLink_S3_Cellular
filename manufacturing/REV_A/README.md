# Rev A manufacturing package

This package is prepared for an **unbuilt Rev A portfolio/reference design**.
Fabrication and assembly have not been completed. Bring-up, firmware, RF/sensor
validation, power testing, EMC/compliance and full DFM qualification remain
pending.

## Authoritative files

| Purpose | File |
| --- | --- |
| PCB fabrication upload | `gerbers/EdgeLink_S3_Cellular_RevA_Gerbers.zip` |
| Assembly BOM upload | `bom/EdgeLink_S3_Cellular_RevA_BOM_JLCPCB_UPLOAD.csv` |
| Assembly placement upload | `cpl/EdgeLink_S3_Cellular_RevA_CPL_JLCPCB_READY.csv` |
| Enriched supporting BOM | `bom/EdgeLink_S3_Cellular_RevA_BOM_JLCPCB.csv` |
| Original KiCad placement export | `cpl/EdgeLink_S3_Cellular-all-pos.csv` |

Use the explicit upload files above. The enriched BOM carries additional part
metadata and is retained as a supporting record, not as a substitute upload.
The upload BOM preserves `Comment`, `Designator`, `Footprint` and **`LCSC Part #`**.
Its supplier header has not been renamed. Confirm supplier import acceptance
before approving assembly.

## BOM and placement consistency

- 46 BOM rows, 89 fitted references, no duplicate designators or blank supplier codes.
- 89 unique CPL references, exactly matching the BOM; all placements are `Top`.
- TP1-TP16 and C19-C22 are excluded from the fitted BOM and CPL.
- U12: BMP384 / C5577555. Its retained footprint name includes BMP390.
- R8,R12,R14,R25: 10 kohm / C2906861.
- U6: ESP32-S3-MINI-1-N8 / C2913206, X 49.600000 mm,
  Y -66.650000 mm, rotation 90 degrees, Top.

U6 retains the original coordinates and PCB position. An apparent offset was
observed in a supplier preview overlay; no coordinate counter-offset has been
applied. Confirm actual pads and pin orientation with the assembler before
placement approval. The checks do not establish supplier rotation conventions
or current component stock.

## Gerbers and drills

The ZIP is readable and contains 12 files, byte-for-byte matching the loose
outputs beside it:

- F.Cu, In1.Cu, In2.Cu and B.Cu
- Front/back solder mask and silkscreen
- Edge.Cuts, PTH drill, NPTH drill and Gerber job file

The board and drill output contain four 2.2 mm NPTH mounting holes. The NPTH
file also contains two 0.65 mm connector holes.

**There are no solder-paste Gerbers.** The present package has been checked for
PCB fabrication content. Confirm stencil and assembly output requirements with
the supplier before ordering. The Gerber/drill release has been preserved;
publication preparation has not regenerated or changed it.

## CAD stack-up and intended order

| Item | CAD record | Intended supplier order |
| --- | --- | --- |
| Construction | Four-layer FR4 | Four-layer FR4 |
| Thickness | Approximately 1.558 mm | Nominal 1.6 mm |
| Core | 1.238 mm | Supplier stack JLC04161H-3313 |
| Copper finish | `None` | ENIG |
| Copper thickness | Outer 0.035 mm; inner 0.015 mm | 1 oz outer; 0.5 oz inner |

Confirm the actual supplier stack and any impedance implications before
fabrication. No certified or formally controlled impedance is claimed.

The original ordering assumptions were Standard PCBA, five boards, top-side
assembly, supplier-added rails/fiducials, customer/self-service part selection
and **Confirm Parts Placement: Yes**. These describe an intended order, not
manufacturing history. Green solder mask and white silkscreen were intended
supplier selections.

## Source checks and release limitations

KiCad 10.0.6 reported zero ERC violations, zero layout DRC errors, zero
unconnected items, six layout warnings and 141 schematic-parity warnings.
See [verification and warning triage](../../docs/verification.md).

The current source is
[`hardware/kicad/EdgeLink_S3_Cellular_RevA/`](../../hardware/kicad/EdgeLink_S3_Cellular_RevA/).
Re-export and review manufacturing files after any electrical or physical
design change. Do not automatically update the PCB from the schematic to
resolve the disclosed parity warnings as part of this release.

The misnamed placement file `BOM_JLCPCB_READY.csv`, the earlier BMP390
`BOM_Final.csv`, historical workbooks and legacy exports are excluded from
publication and retained locally. They are not authoritative release inputs.
