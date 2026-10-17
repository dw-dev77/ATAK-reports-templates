# ATAK-reports-templates
## A collection of standard operational reporting templates for [ATAK](https://tak.gov)

###  Included Templates

| Template | Description |
| :--- | :--- |
| **SITREP** | Situation report covering operational status assessment, unit readiness, and mission progress |
| **SALUTE** | Standard report for tactical field observations (Size, Activity, Location, Unit, Time, Equipment) |
| **INTREP** | Intelligence report detailing threat assessments and NATO Admiralty Code ratings |
| **LINKREP** | Report template for logging tactical data link (TDL) status, network connectivity, node health, transport mediums, signal quality, and operational disruptions |
| **LOGREP** | Logistics report covering supply state, equipment readiness, and resupply requirements |
| **UXO / IED** | Standardized 9-Line explosive ordnance and hazard report |
| **TALON** | Report template for tracking small unmanned aerial system (sUAS) threats, visual/acoustic sightings, flight vectors, and payload capabilities |
| **COMREP** | Signal intercept report for logging RF emissions, frequency/modulation tracking, Direction of Arrival (DoA), and electronic interference/jamming levels |
| **METHANE** | Major incident report for emergency triage, scene hazard identification, access routing, and Mass Casualty (MASCAL) counts |

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
