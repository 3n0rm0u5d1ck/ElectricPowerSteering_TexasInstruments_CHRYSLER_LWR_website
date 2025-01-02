---
layout: default
title: ePWM_1_MDD
nav_order: 2
parent: Enhanced Pwm (TMS570)
---
{% raw %}
# Module –  [module]

# High-Level Description

This module implements functionality with respect to the EPWM module.
This module implements the requirements other than the EPWM output
direction control, which is implemented in the diverse path as required.

# Figures

## Component Diagram

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs                | Module Outputs |      |
|------------------------------|----------------|------|
| CDD_PWMPeriod_Cnt_G_u16      |                | None |
| CDD_DCPhsComp_Cnt_G_u16\[3\] |                |      |

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
<td>etpwmBASE_t</td>
<td><p>TBSTS</p>
<p>TBCTL</p>
<p>TBPHS</p>
<p>TBPHSHR</p>
<p>TBPRD</p>
<p>TBCTR</p>
<p>CMPCTL</p>
<p>TBPRDHR</p>
<p>CMPA</p>
<p>CMPAHR</p>
<p>AQCTLA</p>
<p>CMPB</p>
<p>AQSFRC</p>
<p>AQCTLB</p>
<p>DBCTL</p>
<p>AQCSFRC</p>
<p>DBFED</p>
<p>DBRED</p>
<p>TZDCSEL</p>
<p>TZSEL</p>
<p>TZEINT</p>
<p>TZCTL</p>
<p>TZCLR</p>
<p>TZFLG</p>
<p>ETSEL</p>
<p>TZFRC</p>
<p>ETFLG</p>
<p>ETPS</p>
<p>ETFRC</p>
<p>ETCLR</p>
<p>rsvd_1</p>
<p>PCCTL</p>
<p>HRPWR</p>
<p>HRCNFG</p>
<p>rsvd_3</p>
<p>rsvd_2</p>
<p>rsvd_5</p>
<p>rsvd_4</p>
<p>rsvd_6</p>
<p>HRMSTEP</p>
<p>rsvd_7</p>
<p>HRPCTL</p>
<p>TBPRDM</p>
<p>TBPRDHRM</p>
<p>CMPAM</p>
<p>CMPAHRM</p>
<p>DCACTL</p>
<p>DCTRIPSEL</p>
<p>DCFCTL</p>
<p>DCBCTL</p>
<p>DCFOFFSET</p>
<p>DCCAPCTL</p>
<p>DCFWINDOW</p>
<p>DCFOFFSETCNT</p>
<p>DCCAP</p>
<p>DCFWINDOWCNT</p></td>
<td><p>Uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p></td>
<td><p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p></td>
<td><p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p>
<p>FULL</p></td>
</tr>
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Constant Name</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>k_ADCTrig1Offset_Cnt_s16</td>
</tr>
<tr class="even">
<td><p>k_PwmDeadBand_Cnt_u16</p>
<p>k_PwmRelay_Cnt_u16</p></td>
</tr>
</tbody>
</table>

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
<td>ePWM1</td>
<td>etpwmBASE_t</td>
<td>FULL</td>
<td>FULL</td>
<td>ePWM Register</td>
</tr>
<tr class="even">
<td>ePWM2</td>
<td>etpwmBASE_t</td>
<td>FULL</td>
<td>FULL</td>
<td>ePWM Register</td>
</tr>
<tr class="odd">
<td>ePWM3</td>
<td>etpwmBASE_t</td>
<td>FULL</td>
<td>FULL</td>
<td>ePWM Register</td>
</tr>
<tr class="even">
<td>ePWM4</td>
<td>etpwmBASE_t</td>
<td>FULL</td>
<td>FULL</td>
<td>ePWM Register</td>
</tr>
<tr class="odd">
<td>ePWM5</td>
<td>etpwmBASE_t</td>
<td>FULL</td>
<td>FULL</td>
<td>ePWM Register</td>
</tr>
<tr class="even">
<td>ePWM6</td>
<td>etpwmBASE_t</td>
<td>FULL</td>
<td>FULL</td>
<td>ePWM Register</td>
</tr>
<tr class="odd">
<td>ePWM7</td>
<td>etpwmBASE_t</td>
<td>FULL</td>
<td>FULL</td>
<td>ePWM Register</td>
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

1.  None

## Data Hiding Functions

1.  None

## Global Functions/Macros Defined by this Module

### Global Functions \#1 (For detailed info regarding values assigned to registers refer Reference Pdf attached below)

| **Function Name**    | ePWM_Init1 | Type | Min | Max | UTP Tol. |
|----------------------|------------|------|-----|-----|----------|
| **Arguments Passed** | None       |      |     |     |          |
|                      |            |      |     |     |          |
| **Return Value**     | None       |      |     |     |          |

#### Description

**<u>EPWM1</u>**

**<u>EPWM2</u>**

**<u>EPWM3</u>**

**<u>EPWM4</u>**

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ePWM/doc/mediax/media/image7.emf)

**<u>EPWM7</u>**

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ePWM/doc/mediax/media/image8.emf)

### Global Functions \#2

| **Function Name**    | ePWM_Per1 | Type | Min | Max | UTP Tol. |
|----------------------|-----------|------|-----|-----|----------|
| **Arguments Passed** | None      |      |     |     |          |
|                      |           |      |     |     |          |
| **Return Value**     | None      |      |     |     |          |

#### Description

For detailed info regarding values assigned to registers refer Reference
Pdf attached below

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ePWM/doc/mediax/media/image9.emf)

## Local Functions/Macros Used by this MDD only

### Local Macro \#1

| **Function Name**    | ePWM_DisableOutputs | Type | Min | Max | UTP Tol. |
|----------------------|---------------------|------|-----|-----|----------|
| **Arguments Passed** | None                |      |     |     |          |
|                      |                     |      |     |     |          |
| **Return Value**     | None                |      |     |     |          |

#### Description

Disables the EPWM registers (Refer the included register reference for
more details of register)

ePWM1-\>AQCSFRC = 5U

ePWM1-\>DBCTL &= 0xFFFFFFFCU

ePWM2-\>AQCSFRC = 5U

ePWM2-\>DBCTL &= 0xFFFFFFFCU

ePWM3-\>AQCSFRC = 5U

ePWM3-\>DBCTL &= 0xFFFFFFFCU

### Local Macro \#2

| **Function Name**    | ePWM_EnableOutputs | Type | Min | Max | UTP Tol. |
|----------------------|--------------------|------|-----|-----|----------|
| **Arguments Passed** | None               |      |     |     |          |
|                      |                    |      |     |     |          |
| **Return Value**     | None               |      |     |     |          |

#### Description

Enables the EPWM registers (Refer the included register reference for
more details of register)

ePWM1-\>AQCSFRC = 0U;

ePWM1-\>DBCTL \|= 3U;

ePWM2-\>AQCSFRC = 0U;

ePWM2-\>DBCTL \|= 3U;

ePWM3-\>AQCSFRC = 0U;

ePWM3-\>DBCTL \|= 3U;

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

#### Initialize EPWM Direction Register

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
| ePWM_Init1           | On Event          | ECU start up                             |
| ePWM_Per1            | On Event          | Motor Control ISR subroutine             |

## Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| None          |                                                  |

#  [section-2]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module | Software Segment    |
|--------------------|---------------------|
| ePWM_Init1         | EPWM_START_SEC_CODE |
| ePWM_Per1          | EPWM_START_SEC_CODE |

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

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ePWM/doc/mediax/media/image10.emf)

#  Revision Control Log

| **Rev \#** | **Change Description**                                  | **Date**  | **Author Initials** |
|------|-----------------------------------------------|----------|----------|
| 1.0        | Initial Version ( FDD 34B) –Shutdown Mech not included  | 18-Feb-13 | Selva               |
| 2          | Anomaly 4605 – changed active state of ePWM modules 1-3 | 11-Mar-13 | OT                  |

{% endraw %}