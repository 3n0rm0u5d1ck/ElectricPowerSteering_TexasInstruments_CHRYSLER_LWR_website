---
layout: default
title: MotorVelocity3_MDD
nav_order: 3
parent: Motor Velocity
---
{% raw %}
# Module -- Motor Velocity [module----motor-velocity]

# High-Level Description

This function is responsible for calculating motor velocity from the
sine and cosine motor position sensor signals. This portion of the motor
velocity component actually runs in the motor control ISR to capture
motor position values for use in calculating the motor velocity in
MtrVel(1).

# Figures

## Diagram – Function Data Sharing

This diagram shows all data that is shared between functions within the
module.

No Shared Data

Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be
shown here)

|                                      |                                       |
|----------------------------------|--------------------------------------|
| Module Inputs (Global Variable Name) | Module Outputs (Global Variable Name) |
| MtrPos_SinTheta1_Volts_G_s2p13       | N/A                                   |
| MtrPos_CosTheta1_Volts_G_s2p13       |                                       |
| MtrPos_MechMtrPos_Rev_G_u0p16        |                                       |
| MtrPos_SampleTime_uS_G_u32           |                                       |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table style="width:100%;">
<colgroup>
<col style="width: 41%" />
<col style="width: 12%" />
<col style="width: 13%" />
<col style="width: 13%" />
<col style="width: 18%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Variable Name</td>
<td>Resolution</td>
<td><p>Legal Range</p>
<p>(min)</p></td>
<td><p>Legal Range</p>
<p>(max)</p></td>
<td>Software Segment</td>
</tr>
<tr class="even">
<td>MtrVel3_SinBuffer_Uls_M_s2p13[4][8]</td>
<td>2^-13</td>
<td>-2</td>
<td>2</td>
<td>MTRVEL3_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>MtrVel3_CosBuffer_Uls_M_s2p13[4][8]</td>
<td>2^-13</td>
<td>-2</td>
<td>2</td>
<td>MTRVEL3_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>MtrVel3_PosBuffer_Rev_M_u0p16[4][8]</td>
<td>2^-16</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRVEL3_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>MtrVel3_TimeBuffer_uS_M_u16p0[4][8]</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRVEL3_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>MtrVel3_OsBufPos_Cnt_M_u08[4]</td>
<td>1</td>
<td>0</td>
<td>7</td>
<td>MTRVEL3_START_SEC_VAR_CLEARED_8</td>
</tr>
</tbody>
</table>

\* Note: These ranges are based on the range of the normalized sine and
cosine global inputs, which in turn are based on the maximum amount of
signal variation that can be caused by temperature changes on the MSB
signals.

### User defined typedef definition/declaration 

This section documents any user types uniquely used for the module.

<table>
<colgroup>
<col style="width: 34%" />
<col style="width: 31%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Typedef Name</td>
<td>Element Name</td>
<td>User Defined Type</td>
<td><p>Legal Range</p>
<p>(min)</p></td>
<td><p>Legal Range</p>
<p>(max)</p></td>
</tr>
<tr class="even">
<td>N/A</td>
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

|               |
|---------------|
| Constant Name |
| N/A           |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

|                            |            |                             |
|----------------------------|------------|-----------------------------|
| Constant Name              | Resolution | Value                       |
| D_BUFFERMASK_CNT_U08       | 1          | D_MTRVELOSBUFSZ_CNT_U08 – 1 |
| D_MTRVELOSBUFNUM_CNT_U08   | 1          | 4                           |
| D_MTRVELOSBUFSZ_CNT_U08    | 1          | 8                           |
| D_MTRVELNUMBUFINIT_CNT_U08 | 1          | 2                           |
| D_SAMPLETNOM_US_U16        | 1          | 62                          |
| D_MTRVELTNOM_US_U16        | 1          | 1000                        |

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

|               |
|---------------|
| Constant Name |
| N/A           |

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as
other tables)

|               |            |       |                  |
|---------------|------------|-------|------------------|
| Constant Name | Resolution | Value | Software Segment |
| None          |            |       |                  |

# Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library functions / Macros that are called by the various sub
modules are identified below,

1.  N/A

## Data Hiding Functions

The data hiding functions / macros used in this module are identified
below,

## Local Functions/Macros Used by this MDD only

(Note if they are defined in another source file, then reference the
appropriate header file)

The local functions/macros in this module are identified below,

1.  N/A

Software Module Implementation

## Initialization Functions

### Init: MtrVel3_Init1

#### Design Rationale

None

#### Module Outputs

N/A

#### Module Internal 

None

#### Description

#### ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image1.wmf)  [section]

#### Periodic Functions

### Per: MtrVel3_Per1

#### Design Rationale

N/A

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

N/A

#### Populate Sample Buffers

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image2.wmf)

#### Store Local copy of outputs into Module Outputs

N/A

#### Program Flow End

N/A

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

## Local Function/Macro Definitions

If these are numerous and defined in a separate source file then
reference the source file only.

# Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the
different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

|               |                   |                                                 |
|---------------------------|----------------|-----------------------------|
| Function Name | Calling Frequency | System State(s) in which the function is called |
| MtrVel3_Init1 | Once              | ALL STATES                                      |
| MtrVel3_Per1  | Motor Control ISR | ALL STATES                                      |

## Execution Requirements for Serial Communication Functions 

|               |                                                  |
|---------------|--------------------------------------------------|
| Function Name | Sub-Module called by (Serial Comm Function Name) |
| N/A           |                                                  |

#   [section-1]

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

|                    |                         |
|--------------------|-------------------------|
| Name of Sub Module | Software Segment        |
| MtrVel3_Init1      | RTE_SA_MTRVEL_APPL_CODE |
| MtrVel3_Per1       | RTE_SA_MTRVEL_APPL_CODE |

## Local Functions

This table identifies the software segments for local functions
identified in this module.

|                    |                  |
|--------------------|------------------|
| Name of Sub Module | Software Segment |
| None               |                  |

#   [section-2]

# Known Issues / Limitations With Design

1.  N/A

# Revision Control Log

|             |            |                                                               |           |                     |
|------|------|--------------------------------------------|---------|---------|
| **Item \#** | **Rev \#** | **Change Description**                                        | **Date**  | **Author Initials** |
| 1           | 1.0        | Initial release for FDD v010                                  | 6-FEB-13  | JWJ                 |
| 2           | 2.0        | Corrections per UTP feedback                                  | 04-APR-13 | JJW                 |
| 3           | 3.0        | Corrected typo in MtrVel3_Init per UTP feedback               | 04-APR-13 | JJW                 |
| 5           | 5          | Corrected value of D_MTRVELOSBUFNUM_CNT_U08                   | 08-APR-13 | JJW                 |
| 6           | 6          | Added mask to convert 32 bit value and store in 16-bit buffer | 13-JUN-13 | KJS                 |

{% endraw %}