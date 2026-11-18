# Custom Template Examples

This guide provides platform-specific examples of custom report templates for ATAK and WinTAK. Each implementation demonstrates the available field types and structural elements used to create custom reporting forms.

The XML definitions are platform-specific and are not directly interchangeable. Use the appropriate implementation as a starting point for your target platform.

---

## ATAK - Reports Plugin

The ATAK example uses the XML structure supported by the ATAK Reports plugin. It demonstrates nested sections, field configuration, geospatial inputs, measurement units, formulas, and selection controls.

### Demonstrated Fields

| Field Type | Description |
|---|---|
| `string` | Free-text input |
| `time` | Time input |
| `dateTime` | Date and time input |
| `geometry` | Geospatial point or geometry selection |
| `rangeBearing` | Range and bearing input |
| `route` | Route definition |
| `number` | Numeric input |
| `number` with `unitOptions` | Numeric input with selectable measurement units |
| `formula` | Formula-based field |
| `checkbox` | Checkbox selection |
| `dropdown` | Single-selection dropdown |
| `radio` | Single-selection radio buttons |

### Example XML

```xml
<?xml version='1.0' encoding='UTF-8' standalone='yes'?>
<report type='CUSTOM' title='Custom Template Example' visibilityStatus='false' delimiter='
' userCallsign='' userDescription='' dateTime='' dateTimeDescription='' location='' locationDescription='' tags='' showOptions='false' showTags='false' eventScale='' scaleDescription='' importance='' status='None' id='custom_example'>

    <!-- Main Template Section -->
    <section title='Main Section' role='All' id='template_main' selected='false'>

        <!-- Nested Sections -->

        <section title='Optional Section' role='All' id='template_optional_section' selected='false'>
            <option type='string' required='false' title='Optional Text Field' value='' id='template_optional_text'/>
        </section>

        <section title='Required Section' role='All' id='template_required_section' selected='false'>
            <option type='string' required='true' title='Required Text Field' value='' id='template_required_text'/>
        </section>

        <!-- Date and Time Fields -->

        <option type='time' required='false' title='Time Field' value='' id='template_time'/>
        <option type='dateTime' required='false' title='Date and Time Field' value='' id='template_datetime'/>

        <!-- Geospatial Fields -->

        <option type='geometry' required='false' title='Location / Geometry Field' value='' id='template_geometry' drawMapItem='false'/>
        <option type='rangeBearing' required='false' title='Range and Bearing Field' value='' id='template_range_bearing'/>
        <option type='route' required='false' title='Route Field' value='' id='template_route'/>

        <!-- Numeric and Measurement Fields -->

        <option type='number' required='false' title='Number Field' value='' id='template_number'/>
        <option type='number' required='false' title='Number Field with Custom Units' value='' unitOptions='&#34;unit one&#34;,&#34;unit two&#34;' id='template_number_units'/>

        <!-- Formula Field -->

        <option type='formula' required='false' title='Formula Field' value='no pattern' id='template_formula'/>

        <!-- Selection Fields -->

        <list title='Multi-Select Checkboxes' required='false' multiple='true' type='checkbox'>
            <option type='checkbox' value='false' required='' selected='false' title='Checkbox One'/>
            <option type='checkbox' value='false' required='' selected='false' title='Checkbox Two'/>
        </list>

        <list title='Single-Select Dropdown' type='dropdown' required='false'>
            <option type='checkbox' value='false' required='' selected='false' title='Option One'/>
            <option type='checkbox' value='false' required='' selected='false' title='Option Two'/>
        </list>

        <list title='Single-Select Radio Buttons' multiple='false' type='radio' required='false'>
            <option type='checkbox' value='false' required='' selected='false' title='Radio One'/>
            <option type='checkbox' value='false' required='' selected='false' title='Radio Two'/>
        </list>

    </section>
</report>
```

---

## WinTAK - Custom Reports

The WinTAK example uses the custom report XML structure exported by WinTAK. It demonstrates section-based report organization, list options, standalone checkboxes, and the field types available in the exported custom report definition.

### Demonstrated Fields

| Field Type | Description |
|---|---|
| `string` | Free-text input |
| `time` | Time input |
| `dateTime` | Date and time input, with configurable display format |
| `geometry` | Geospatial location selection |
| `number` | Numeric input |
| `number` with `unitOptions` | Numeric input with selectable measurement units |
| `rangeBearing` | Range and bearing input |
| `route` | Route definition |
| `checkbox` | Standalone checkbox |
| `list` | Grouped selection options |
| `list` with `multiple='true'` | Multi-select list |

### Example XML

```xml
<report type="Custom">
    <section title="Section Title" invert="False" role="All">

        <!-- Single-Select List -->

        <list title="Options Title" required="false">
            <option title="Option One" required="false" type="string" />
            <option title="Option Two" required="false" type="string" />
        </list>

        <!-- Multi-Select List -->

        <list title="Multi-Select Options Title" required="false" multiple="true">
            <option title="Option One" required="false" type="string" />
            <option title="Option Two" required="false" type="string" />
        </list>

        <!-- Standalone Checkbox -->

        <option type="checkbox" required="false" title="Checkbox Title" />

        <!-- Date and Time Fields -->

        <option format="MM dd yyyy HH:mm" type="dateTime" required="false" title="Date Title" />
        <option title="Time Title" required="false" type="time" />

        <!-- Geospatial Fields -->

        <option title="Location Title" required="false" type="geometry" />
        <option title="Range Title" required="false" type="rangeBearing" />
        <option title="Route Title" required="false" type="route" />

        <!-- Numeric and Measurement Fields -->

        <option title="Number With Units Title" required="false" type="number" unitOptions="Unit" />
        <option title="Number Title" required="false" type="number" />

        <!-- Text Field -->

        <option title="Text Title" required="false" type="string" />

    </section>
</report>
```
### Adding Custom Templates to WinTAK

Custom WinTAK report templates can be added through the `Surveillance/Templates/` directory using either of the following methods:

**1. Add templates to `custom.xml`**

Add individual `<report>` definitions to the existing `custom.xml` file in the `Surveillance/Templates/` directory. Each report is defined using its own `<report>` element.

**2. Create a separate custom category**

Create a separate XML file in the `Surveillance/Templates/` directory. The filename identifies the custom category, while the XML contents define the individual report templates belonging to it.

Use a `<reports>` root element containing one or more `<report>` elements. Each `<report>` defines an individual template within that category.

For example, `Example.xml` creates a category containing two report templates:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<reports>
    <report type="First-Custom-Report">
        <section title="First Report" invert="False" role="All">
            <option title="Text Field" required="false" type="string" />
        </section>
    </report>

    <report type="Second-Custom-Report">
        <section title="Second Report" invert="False" role="All">
            <option title="Location" required="false" type="geometry" />
        </section>
    </report>
</reports>
```
Both methods allow custom report definitions to be loaded by WinTAK. Keep each report definition within its own `<report>` element and preserve the appropriate XML structure for the selected method.

Restart WinTAK after adding or modifying report definitions for the changes to take effect.

---

## Implementation Notes

- **Platform-specific XML:** ATAK and WinTAK use different report definition structures and attributes. Do not assume that a field or attribute supported by one implementation is supported by the other.
- **Field requirements:** The `required` attribute determines whether a field must be completed, where supported by the relevant platform.
- **Nested sections:** ATAK supports nested sections in the example above. The WinTAK example uses the section structure provided by its exported definition.
- **Selection controls:** Selection options and their behavior are configured differently between the two platforms.
- **Geospatial inputs:** Geometry, range and bearing, and route fields are included where supported by the respective implementation.
- **Custom units:** Replace the example unit labels with the measurement units relevant to your reporting requirements.
- **Testing:** Validate modified templates in the intended platform before operational use. Field rendering and behavior may vary between platform versions.
