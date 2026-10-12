# References and CAD attribution

Manufacturer documentation is linked rather than redistributed as a bulk
datasheet collection. These links are reference sources, not evidence that
this board has been tested or that every datasheet requirement has been checked.

## Selected devices

| Device | Manufacturer reference |
| --- | --- |
| ESP32-S3-MINI-1-N8 | [Espressif module datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-s3-mini-1_mini-1u_datasheet_en.pdf) |
| SIM7080G | [SIMCom product and documentation](https://www.simcom.com/product/SIM7080G.html) |
| BQ25185 | [Texas Instruments product/datasheet](https://www.ti.com/product/BQ25185) |
| TPS63802 | [Texas Instruments product/datasheet](https://www.ti.com/product/TPS63802) |
| MAX17048 | [Analog Devices product/datasheet](https://www.analog.com/en/products/max17048.html) |
| BMI323 | [Bosch Sensortec product](https://www.bosch-sensortec.com/en/products/motion-sensors/imus/bmi323) |
| SHT40 | [Sensirion product/datasheet](https://sensirion.com/products/catalog/SHT40) |
| BMP384 | [Bosch Sensortec product](https://www.bosch-sensortec.com/en/products/environmental-sensors/pressure-sensors/bmp384) |
| TPS22919 | [Texas Instruments product/datasheet](https://www.ti.com/product/TPS22919) |
| TXB0108 | [Texas Instruments product/datasheet](https://www.ti.com/product/TXB0108) |

## CAD library and model provenance

| Assets | Available provenance and limitations |
| --- | --- |
| Standard symbols, footprints and `${KICAD10_3DMODEL_DIR}` models | Supplied by the installed KiCad 10 libraries. See [KiCad library licensing](https://www.kicad.org/libraries/license/). Install those libraries to resolve standard model references. |
| Many part-specific local libraries | Their generator headers identify [uPesy/easyeda2kicad.py](https://github.com/uPesy/easyeda2kicad.py), an EasyEDA/LCSC-to-KiCad conversion tool. This identifies the conversion workflow, not ownership or a licence grant for the upstream CAD data. |
| DFE201612E-R47M_P2 symbol | Contains a [SnapEDA/SnapMagic source link](https://www.snapeda.com/parts/DFE201612E-R47M=P2/Murata/view-part/). Retained symbol and footprint are under the local `libraries/` folder. |
| TPS63802 symbol and footprint | Contains a [SnapEDA/SnapMagic source link](https://www.snapeda.com/parts/TPS63802DLAR/Texas+Instruments/view-part/). Other TPS63802 local assets carry easyeda2kicad generator metadata. |
| `S3Stick_Symbols.kicad_sym` and `S3Stick_Footprints.pretty` | Retained project-local assets. Their names alone do not establish original authorship or redistribution terms. Embedded metadata and original file contents are preserved. |
| `3D_Models/ESP32`, `3D_Models/JST` and `3D_Models/MAX17048G` | Retained project-local model files. A complete original-source/licence record was not available in this publication snapshot. |
| `Sensors.kicad_sym` and `Sensor_Footprints.pretty` | Project-local sensor definitions used by this design. Existing BMP390 identifiers remain for the BMP384 selection; identifier reuse is not a compatibility claim. |

Part-specific converted assets include BQ25185, TPS63802, MAX17048, SIM7080G,
BMP390/BMP384 support, SHT40, TPS22919, TXB0108, protection parts, connectors,
switches and passives. Relevant generator headers, links and notices inside
the files have been retained. A generator's software licence does not by itself
license every downloaded symbol, footprint or model.

Third-party reference-design bundles are retained locally and excluded from
this release. Their inclusion in the local research folder does not establish
that their authors contributed to this project or granted rights to its design.

## Rights and review gaps

No project-wide licence is included. Normal copyright restrictions apply.
Downloaded libraries and models retain their respective ownership, notices and
terms; they have not acquired a new licence through repository publication.
Where provenance or permission is incomplete, resolve it before wider reuse or
redistribution. This record reports the evidence available in the files and
does not certify a completed third-party rights audit.
