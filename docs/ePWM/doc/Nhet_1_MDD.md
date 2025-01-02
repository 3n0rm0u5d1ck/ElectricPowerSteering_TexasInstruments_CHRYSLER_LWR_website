---
layout: default
title: Nhet_1_MDD
nav_order: 5
parent: Enhanced Pwm (TMS570)
---
{% raw %}
# Module – NHET [module-nhet]

# High-Level Description

This module implements NHET functionality with respect to the NHET
module.

# Figures

## Component Diagram

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs | Module Outputs |      |
|---------------|----------------|------|
| HET_INIT1_PST |                | None |
|               |                |      |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table>
<colgroup>
<col style="width: 24%" />
<col style="width: 21%" />
<col style="width: 13%" />
<col style="width: 13%" />
<col style="width: 28%" />
</colgroup>
<thead>
<tr class="header">
<th>Variable Name</th>
<th>Resolution</th>
<th><p>Legal Range</p>
<p>(min)</p></th>
<th><p>Legal Range</p>
<p>(max)</p></th>
<th>Software Segment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>None</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

### User defined typedef definition/declaration 

This section documents any user types uniquely used for the module.

(Refer the included ref for more details of register)

<table>
<colgroup>
<col style="width: 37%" />
<col style="width: 24%" />
<col style="width: 16%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>Typedef Name</th>
<th>Element Name</th>
<th>User Defined Type</th>
<th><p>Legal Range</p>
<p>(min)</p></th>
<th><p>Legal Range</p>
<p>(max)</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

| Constant Name |
|---------------|
|               |
|               |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

<table>
<colgroup>
<col style="width: 22%" />
<col style="width: 19%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 34%" />
</colgroup>
<thead>
<tr class="header">
<th>Variable Name</th>
<th>Resolution</th>
<th><p>Legal Range</p>
<p>(min)</p></th>
<th><p>Legal Range</p>
<p>(max)</p></th>
<th>Software Segment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

####  [section]

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name |
|---------------|
| None          |

### Module specific Lookup Tables Constants

| Constant Name | Resolution | Value | Software Segment |
|---------------|------------|-------|------------------|
| None          |            |       |                  |

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

1.  Memcpy

## Data Hiding Functions

1.  None

## Global Functions/Macros Defined by this Module

### Global Functions \#1 (For detailed info regarding values assigned to registers refer Reference Pdf attached below)

| **Function Name**    | NHET_Init1 | Type | Min | Max | UTP Tol. |
|----------------------|------------|------|-----|-----|----------|
| **Arguments Passed** | None       |      |     |     |          |
|                      |            |      |     |     |          |
| **Return Value**     | None       |      |     |     |          |

#### Description

**<u>NHET</u>**

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ePWM/doc/mediax/media/image1.emf)

## Local Functions/Macros Used by this MDD only

### Local Macro \#1

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data | Value |
|------|-------|
| None |       |

## Initialization Functions

### Init: 

#### Design Rationale

None

#### Module Outputs

None

#### Module Internal 

None

#### Initialize NHET Direction Register

## Periodic Functions

None

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

## Transition Functions

None

##  

# Execution Requirements

## Execution Rates for sub-modules called by the Subroutine

This table serves as reference for the Scheduler design

| Global Function Name | Calling Frequency | Function in which the function is called |
|--------------------------|-----------------|------------------------------|
| NHET_Init1           | On Event          | ECU start up                             |
|                      |                   |                                          |

## Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| None          |                                                  |

#  [section-2]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module | Software Segment             |
|--------------------|------------------------------|
| NHET_Init1         | \#define NHET_START_SEC_CODE |
|                    |                              |

##  [section-3]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module | Software Segment |
|--------------------|------------------|
| None               |                  |

#  [section-4]

#  Known Issues / Limitations With Design

1.  None

#  [section-5]

#  Reference 

Register Reference

# ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ePWM/doc/mediax/media/image2.emf) [section-6]

#  [section-7]

# Revision Control Log

| **Item \#** | **Rev \#** | **Change Description**     | **Date** | **Author Initials** |
|------|------|--------------------------------------------|---------|---------|
| 1           | 1.0        | Initial Version ( FDD 34B) |          | Selva               |

{% endraw %}