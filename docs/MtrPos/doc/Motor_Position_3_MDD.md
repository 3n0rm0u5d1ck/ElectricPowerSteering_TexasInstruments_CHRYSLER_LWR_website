---
layout: default
title: Motor_Position_3_MDD
nav_order: 3
parent: Motor Position
---
{% raw %}
# Module – Motor Position 3 [module-motor-position-3]

# High-Level Description

This module implements the systematic coverage for MtrPos. This includes
calculating an alternate MechMtrPos signal and performing diagnostics.

# Figures

## Component Diagram

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image1.png"
style="width:1.99097in;height:1.24792in" />

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs          | Module Outputs |     |
|------------------------|----------------|-----|
| InvSin2Scaled_Volt_f32 |                |     |
| InvCos2Scaled_Volt_f32 |                |     |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table style="width:100%;">
<colgroup>
<col style="width: 33%" />
<col style="width: 17%" />
<col style="width: 13%" />
<col style="width: 13%" />
<col style="width: 23%" />
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
<td>MtrPos3_SysCValidityFltAcc_Cnt_M_u16</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRPOS3_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>MtrPos3_SysCCorrFltAcc_Cnt_M_u16</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRPOS3_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>MtrPos3_DiagCorrectedMtrPos_Rev_M_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>1</td>
<td>MTRPOS3_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>MtrPos3_DiagMechMtrPos_Rev_M_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>1</td>
<td>MTRPOS3_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>MtrPos3_SysCErrorTerm_Rev_D_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>1</td>
<td>MTRPOS3_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>MtrPos3_SysCValidErr_VoltsSqrd_D_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>6.25</td>
<td>MTRPOS3_START_SEC_VAR_CLEARED_32</td>
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

### User defined typedef definition/declaration 

This section documents any user types uniquely used for the module.

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
<td>TaylorATanTblType</td>
<td><p>offset_f32</p>
<p>slope_s08</p>
<p>SinMinVal_lgc</p></td>
<td><p>float32</p>
<p>sint8</p>
<p>boolean</p></td>
<td><p>0</p>
<p>-1</p>
<p>FALSE</p></td>
<td><p>2π</p>
<p>1</p>
<p>TRUE</p></td>
</tr>
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

| Constant Name                   |
|---------------------------------|
| k_NominalOffset_Volts_f32       |
| k_CorrelationError_Rev_f32      |
| k_MtrPosCorrDiag_Cnt_str        |
| k_SysCValMinError_VoltsSqrd_f32 |
| k_SysCValMaxError_VoltsSqrd_f32 |
| k_SysCMtrPosValDiag_Cnt_str     |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name             | Resolution             | Units    | Value        |
|---------------------------|------------------------|----------|--------------|
| NUMOCTANTS_CNT_u16        | 1                      | Counts   | 8            |
| D_HALF_ULS_F32            | Single Precision Float | Unitless | 0.5          |
| D_THREE_ULS_F32           | Single Precision Float | Unitless | 3            |
| D_ELECREVPMECHREV_ULS_U16 | 1                      | Unitless | 3            |
| D_MASK16BITS_CNT_U32      | 1                      | Counts   | 0x0000FFFFUL |

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name  |
|----------------|
| D_ZERO_ULS_F32 |
| D_PI_ULS_F32   |
| D_2PI_ULS_F32  |
| D_ONE_ULS_F32  |
| D_ZERO_CNT_U16 |

### Module specific Lookup Tables Constants

<table>
<colgroup>
<col style="width: 37%" />
<col style="width: 19%" />
<col style="width: 19%" />
<col style="width: 24%" />
</colgroup>
<thead>
<tr class="header">
<th>Constant Name</th>
<th>Resolution</th>
<th>Value</th>
<th>Software Segment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>TaylorATanTbl[NUMOCTANTS_CNT_u16]</td>
<td>TaylorATanTblType</td>
<td><p>{0, 1, TRUE},</p>
<p>{ π/2, -1, FALSE},</p>
<p>{ π/2, 1, FALSE},</p>
<p>{ π, -1, TRUE},</p>
<p>{ π, 1, TRUE},</p>
<p>{3 π/2, -1, FALSE},</p>
<p>{3 π/2, 1, FALSE},</p>
<p>{2 π, -1, TRUE}</p></td>
<td>MTRPOS3_START_SEC_CONST_UNSPECIFIED</td>
</tr>
</tbody>
</table>

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

1.  Abs_f32_m

2.  DiagPStep_m

3.  DiagNStep_m

4.  DiagFailed_m

## Data Hiding Functions

1.  None

## Global Functions/Macros Defined by this Module

None

## Local Functions/Macros Used by this MDD only

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data                                 | Value |
|--------------------------------------|-------|
| Rte_InitValue_InvCos2Scaled_Volt_f32 | 0     |
| Rte_InitValue_InvSin2Scaled_Volt_f32 | 0     |

## Initialization Functions

None

##  Periodic Functions

### Per: MtrPos3_Per1

#### Design Rationale

This function should be run after MtrPos2_Per1, as the comparisons (in
both the main and diverse paths) on the generated signals assume that
this order will be followed.

#### Program Flow Start

Rte_Call_MtrPos3_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

InvCos2_Volts_T_f32 = Rte_IRead_MtrPos3_Per1_InvCos2Scaled_Volt_f32()

InvSin2_Volts_T_f32 = Rte_IRead_MtrPos3_Per1_InvSin2Scaled_Volt_f32()

#### Compute Alternate Motor Position

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image3.emf)

#### Store Local copy of outputs into Module Outputs

#### Program Flow End

Rte_Call_MtrPos3_Per1_CP1_CheckpointReached()

### Per: MtrPos3_Per2

#### Design Rationale

None

#### Program Flow Start

Rte_Call_MtrPos3_Per2_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

CorrectedMtrPos_Rev_T_f32 =
Rte_IRead_MtrPos3_Per2_CorrectedMtrPos_Rev_f32()

InvCos2_Volts_T_f32 = Rte_IRead_MtrPos3_Per2_InvCos2Scaled_Volt_f32()

InvSin2_Volts_T_f32 = Rte_IRead_MtrPos3_Per2_InvSin2Scaled_Volt_f32()

#### Correlation Diagnostic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image4.emf)

#### Secondary Sensor Validity Diagnostic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image5.emf)

#### Store Local copy of outputs into Module Outputs

MtrPos3_SysCErrorTerm_Rev_D_f32 = SysCErrorTerm_Rev_T_f32

MtrPos3_SysCValidErr_VoltsSqrd_D_f32 = SysCValidErr_VoltsSqrd_T_f32

#### Program Flow End

Rte_Call_MtrPos3_Per2_CP1_CheckpointReached()

##  Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

##  

# Execution Requirements

## Execution Sequence of the Module

See section 6.3.1.1 for details on task organization.

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name | Calling Frequency | System State(s) in which the function is called |
|--------------------------|-----------------|------------------------------|
| MtrPos3_Per1  | 2 ms              | ALL                                             |
| MtrPos3_Per2  | 4 ms              | ALL                                             |

## Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| None          |                                                  |

#  [section-1]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module | Software Segment                   |
|--------------------|------------------------------------|
| MtrPos3_Per1       | RTE_START_SEC_SA_MTRPOS3_APPL_CODE |
| MtrPos3_Per2       | RTE_START_SEC_SA_MTRPOS3_APPL_CODE |

##  [section-2]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module | Software Segment |
|--------------------|------------------|
| None               |                  |

#  [section-3]

#  Known Issues / Limitations With Design

1.  INLINE functions defined in GlobalMacro.h are not unit tested.

#  Revision Control Log

|             |            |                                                                          |            |                     |
|------|------|--------------------------------------------|---------|---------|
| **Item \#** | **Rev \#** | **Change Description**                                                   | **Date**   | **Author Initials** |
| 1           | 1.0        | Initial Version                                                          | 23-Oct-12  | OT                  |
| 2           | 2.0        | MDD catchup matching SRC ver 4                                           | 14-June-13 | NRAR                |
| 3           | 3          | Anomaly 4947 fix to correct MtrPos correlation issues cause by buffering | 18-Oct-13  | Jared               |

{% endraw %}