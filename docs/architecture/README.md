# Rev A architecture

![Rev A CAD architecture](../images/architecture-reva.svg)

This diagram follows the current Rev A schematic. It shows intended interfaces
and supply paths; it is not evidence of functioning or tested hardware.

## Power paths

USB-C `USB_VBUS` feeds U5 BQ25185. The single-cell battery connects to its BAT
path and the `VBAT` net. U5's `VSYS` supplies U4 TPS63802, which generates the
main `+3V3` rail. U1 MAX17048 monitors `VBAT` and reports through internal I2C.
The modem supply comes from `VBAT` through the L2/filter/decoupling network.

U9 TPS22919 switches `+3V3` for the GNSS antenna-bias network, controlled by
`GNSS_PWR_EN`. It does not implement an external 7-24 V input or a general
switched sensor rail. Battery-current performance remains unmeasured.

## Controller, modem and expansion

U6 ESP32-S3-MINI-1-N8 provides the controller and intended Wi-Fi/Bluetooth LE
capability. Native USB connects to the USB-C data pair through protection and
series components. EN/BOOT buttons and a status LED are present.

U8 SIM7080G supplies LTE-M/NB-IoT and GNSS functionality. U7 TXB0108 provides
the UART/control level-shifting interface to the controller. The modem connects
to the Nano-SIM holder, LTE U.FL and GNSS U.FL. A separate GNSS antenna-bias path
is shown above; antenna and RF performance remain to be tested.

Internal I2C uses ESP32 GPIO13/GPIO14 and connects U1 MAX17048, U10 BMI323,
U11 SHT40 and U12 BMP384. BMI323 INT1 connects to GPIO15. The external I2C
connector uses a separate pair on GPIO1/GPIO2, with its own pull-ups.

## Source sheets

| File | Content |
| --- | --- |
| `EdgeLink_S3_Cellular.kicad_sch` | Hierarchical interconnect |
| `01_Power_USB.kicad_sch` | USB-C, BQ25185, TPS63802 and MAX17048 |
| `02_ESP32_S3.kicad_sch` | ESP32-S3, reset/boot controls and status LED |
| `03_SIM7080G_Cellular_GNSS.kicad_sch` | Modem, level shifter, Nano-SIM, LTE/GNSS RF and antenna bias |
| `04_Sensors.kicad_sch` | BMI323, SHT40, BMP384 and external I2C |
| `00_System_Block_Diagram.kicad_sch` | Existing empty child sheet, retained in the six-page PDF |

Publication preparation replaces the obsolete architecture illustration and
corrects stale free-text ESP32 notes and unsupported power-sheet check labels.
It does not change electrical symbols, pins, wires, labels, junctions or nets.
No schematic-to-PCB update was performed.
