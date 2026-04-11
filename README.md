# HandSTaMp

## Bill of Materials

| Reference | Silkscreen | Part                        | Footprint | Purpose                                        |
|-----------|------------|-----------------------------|-----------|------------------------------------------------|
| C1, C2    | 1µF        | 2 × 1µF ceramic capacitors  | 0603      | Decoupling capacitors for U3                   |
| C3        | 4µ7F       | 4.7µF ceramic capacitor     | 0603      | Bulk decoupling capacitor for U1               |
| C4        | 100nF      | 100nF ceramic capacitor     | 0603      | Decoupling capacitor for U1                    |
| C5        | 100nF      | 100nF ceramic capacitor     | 0603      | Unwanted reset prevention                      |
| D1        | D1         | PMEG2010EA Schottky diode   | SOD-323   | Reverse current protection                     |
| D2, D3    | D2, D3     | 2 × 1N4148 diodes           | SOD-123   | Matrix diodes for SW1/SW2                      |
| F1        | F1         | 500mA fuse                  | 0603      | Current overload protection                    |
| J1        | J1         | HRO TYPE-C-31-M-12 USB port |           | For the pluggings in of USB cables             |
| R1, R2    | 1, 2       | 2 × 5.1kΩ resistors         | 0603      | USB power negotiation (Rd) resistors           |
| R3        | 5k1Ω – P   | 5.1kΩ resistor              | 0603      | OPTIONAL 5V pull-up for RGB data line¹         |
| R4        | 1万Ω       | 10kΩ resistor               | 0603      | Prevention of unwanted boot state              |
| S1, S2    | *None*     | 2 × MX-compatible switches  | MX plate² | Keys for row 0, columns 0/1; mountings for PCB |
| U1        | U1         | STM32C071GBU6               | UFQFPN-28 | ~~Braaaains!~~ Microcontroller                 |
| U2        | U2         | PRTR5V0U2X                  | SOT-143   | ESD protection                                 |
| U3        | U3         | XC6206P332MR-G LDO          | SOT-23-3  | 5V to 3.3V step-down for U1                    |

##### Notes

 1. Remove/do not place R3 (“P”) if not using pin PB0 to drive RGB LEDs (e.g., as a regular matrix pin).
    Pin PB0 must be set to [open drain mode][open-drain].
 2. Three-pin “plate-mount” switches can be used as-is. To use five-pin “PCB-mount” switches,
    the two extra plastic alignment “pins” must be removed.

[open-drain]: https://docs.qmk.fm/drivers/ws2812#open-drain-circuit
