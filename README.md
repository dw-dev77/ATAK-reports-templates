# ATAK Reports Templates

A collection of XML-based operational reporting templates for [ATAK](https://tak.gov), covering established reporting formats and purpose-built templates for tactical, intelligence, logistics, communications, incident response, and other operational requirements.

## Included Templates

| Template | Description |
| :--- | :--- |
| **SITREP** | Situation report covering operational status assessment, unit readiness, and mission progress. |
| **SALUTE** | Standard report for tactical field observations (Size, Activity, Location, Unit, Time, Equipment). |
| **INTREP** | Intelligence report for documenting observed activities, target characteristics, collection information, and analytical assessments, including source reliability and information credibility ratings (Admiralty Code). |
| **LINKREP** | Report template for logging tactical data link (TDL) status, network connectivity, node health, transport mediums, signal quality, and operational disruptions. |
| **LOGREP** | Logistics report covering personnel strength and availability, supply status, equipment readiness, and resupply requirements. |
| **UXO / IED** | Explosive hazard reporting template based on the 9-Line reporting format. |
| **TALON** | Structured C-UAS reporting template for documenting and classifying unmanned aircraft system (UAS) observations, including platform and propulsion types, observed activity, location, orientation, acoustic signatures, group formations, control links, guidance and navigation characteristics, estimated altitude, payload assessments, and visual characteristics. |
| **COMREP** | RF observation report for documenting observed frequencies, signal strength, communications types, direction of arrival, and interference conditions, including suspected or confirmed jamming. |
| **METHANE** | Major incident report for emergency triage, scene hazard identification, access routing, and Mass Casualty (MASCAL) counts. |
| **CBRNREP** | CBRN incident reporting, including hazard detection, agent identification confidence, contamination assessment, personnel exposure and protective measures. |

## Key Features

- **Established reporting formats:** XML implementations of established reporting formats and conventions, including `SITREP`, `SALUTE`, `INTREP`, `LOGREP`, `METHANE`, and `UXO/IED` (9-line), with appropriate adaptations for ATAK.
- **Purpose-built templates:** Dedicated templates for tactical data link status (`LINKREP`), counter-UAS observations (`TALON`), and RF communications observations (`COMREP`).
- **Contemporary Operational Adaptation:** Reporting structures and conventions adapted to reflect current operational environments, evolving technologies, and modern reporting requirements.
- **Multi-Select Fields:** Checkbox-based selections for recording multiple observations, hazards, conditions, and requirements where applicable.
- **Geospatial Integration:** Utilizes ATAK-native `geometry` and `rangeBearing` field types for location selection and map-derived directional observations.
- **Configurable XML Templates:** Lightweight XML-based report definitions that can be adapted to different operational reporting requirements.

## Installation

### Manual Installation

Installation paths may vary depending on the ATAK distribution and version.

#### ATAK-CIV — Reports Plugin

Copy the `.xml` template files to:

```text
/sdcard/atak/tools/reports/templates/custom/
```

Create the `custom` directory if it does not exist.

#### ATAK-MIL / GOV — Native Forms

For deployments using the native Form Manager, copy the `.xml` files to the appropriate forms directory:

```text
/sdcard/atak/support/files/forms/
```

#### Windows — WinTAK

Copy the `.xml` template files to the WinTAK support forms directory:

```text
C:\ProgramData\WinTAK\Support\Forms\
```

Verify the installation location for your ATAK distribution and version before deployment.

## Usage

1. Open ATAK or WinTAK.
2. Launch the Reports plugin or Forms tool.
3. Select the desired reporting template.
4. Complete the relevant fields.
5. Submit or share the report through the available ATAK reporting workflow.

## Testing and Compatibility

Templates are designed for ATAK's XML-based reporting and form functionality.

Testing should cover:

- Template loading and display.
- Required and optional field behaviour.
- Dropdown and multi-select interactions.
- Geospatial field selection and map interaction.
- Numeric fields and measurement units.
- Report submission and data transmission.

XML well-formedness checks alone do not establish runtime compatibility.

## Contributing

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/new-template`).
3. Ensure XML files are well-formed and special characters are properly escaped.
4. Test changes in the intended ATAK environment.
5. Submit a Pull Request.

## License

Distributed under the [MIT License](LICENSE).
