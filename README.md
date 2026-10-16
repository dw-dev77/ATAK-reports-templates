# ATAK-reports-templates
## A collection of standard operational reporting templates for [ATAK](https://tak.gov)

###  Included Templates

| Template | Purpose / Scope |
| :--- | :--- |
| **SITREP** | Situation report covering operational status assessment, unit readiness, and mission progress |
| **SALUTE** | Standard spot report for tactical field observations (Size, Activity, Location, Unit, Time, Equipment) |
| **INTREP** | Intelligence report detailing threat assessments and NATO Admiralty code ratings |
| **LINKREP** | Tactical data link and radio/mesh network status monitoring |
| **LOGREP** | Logistics report covering supply state, equipment readiness, and resupply requirements |
| **UXO / IED** | Explosive hazard reporting, clearance, and cordon marking |
| **TALON** | Counter-UAS spot report for drone detection, classification, acoustic signature, and visual tracking |
| **COMREP** | RF spectrum intercept logging, signal strength (S-units/dBm), modulation, and bearing vectors |
| **METHANE** | Major incident declaration, scene hazards, and Mass Casualty (MASCAL) triage counts |

## Key Features

* **Native Multi-Select Support:** Built using proper XML syntax for multi-select checklists (e.g., tagging multiple scene hazards in `METHANE` or acoustic signatures in `TALON`).
* **Low-Bandwidth Optimized:** Lightweight schemas designed to pass smoothly over tactical mesh radios and constrained RF links.
* **Geospatial Integration:** Utilizes native ATAK `geometry` and `rangeBearing` pickers for quick map placement and vector plotting.

## Installation

### Manual Installation

### Android ATAK Reports Plugin (ATAK-CIV)
Copy the `.xml` template files directly to:
```text
/sdcard/atak/tools/reports/templates/custom/
```
(Note: Create the custom directory if it does not exist).

### Native Forms (ATAK-MIL / GOV)
For native ATAK Form Manager storage or MIL/GOV deployments, copy the `.xml` template files to:
```text
/sdcard/atak/support/files/forms/
```
### Windows (WinTAK)
Copy the `.xml` template files to the WinTAK support directory:
```text
C:\ProgramData\WinTAK\Support\Forms\
```

## Usage
1. Open ATAK or WinTAK.
2. Launch the Reports plugin or Custom Forms tool from the main menu.
3. Select your desired template (e.g., `TALON`, `COMREP`, `METHANE`).
4. Complete the required fields and broadcast over Cursor-on-Target (CoT).

## Contributing
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/new-template`).
3. Ensure your XML validates cleanly without unescaped special characters (`&`, `<`, `>`).
4. Submit a Pull Request.

## License
Distributed under the [MIT License](LICENSE).
