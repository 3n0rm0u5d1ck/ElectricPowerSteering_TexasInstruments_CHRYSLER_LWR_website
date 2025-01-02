---
layout: default
title: WIR_Input_Qualification_MDD
nav_order: 21
parent: Chrysler TMS570 Project
---
{% raw %}
# pointsModule --  [pointsmodule---]

# High-Level Description

This module is responsible for performing the qualification of the Wheel
Speed inputs to the Wheel Imbalance Rejection algorithm.

# Figures

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/WIRInputQual/doc/mediax/media/image1.tiff"
style="width:3.54167in;height:2.75in" alt="WIRInputQual.tif" />

## Diagram – Function Data Sharing

This diagram shows all data that is shared between functions within the
module.

No Shared Data

### Diagram – Function (Name)

This diagram describes the functional characteristics and data flow of a
given function.

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs            | Module Outputs |                          |
|--------------------------|----------------|--------------------------|
| SrlComLWhlSpdVld_Cnt_lgc |                | QualWhlFreqL_Hz_f32      |
| SrlComRWhlSpdVld_Cnt_lgc |                | QualWhlFreqR_Hz_f32      |
| SrlComLWhlSpd_Hz_f32     |                | WhlFreqQualified_Cnt_lgc |
| SrlComRWhlSpd_Hz_f32     |                |                          |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table>
<colgroup>
<col style="width: 31%" />
<col style="width: 16%" />
<col style="width: 13%" />
<col style="width: 13%" />
<col style="width: 25%" />
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
<td>PrevQualWhlSpdLeft_Hz_M_f32</td>
<td>single precision float</td>
<td>0</td>
<td>40</td>
<td>CLEARED_32</td>
</tr>
<tr class="even">
<td>PrevQualWhlSpdRight_Hz_M_f32</td>
<td>single precision float</td>
<td>0</td>
<td>40</td>
<td>CLEARED_32</td>
</tr>
<tr class="odd">
<td>QualLevelLeft_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>10</td>
<td>CLEARED_16</td>
</tr>
<tr class="even">
<td>QualLevelRight_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>10</td>
<td>CLEARED_16</td>
</tr>
<tr class="odd">
<td>QualErrAccLeft_Cnt_M_u16</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>CLEARED_16</td>
</tr>
<tr class="even">
<td>QualErrAccRight_Cnt_M_u16</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>CLEARED_16</td>
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
<td>None</td>
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
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

| Constant Name            |
|--------------------------|
| k_WhlSpdQPStep_Cnt_u16   |
| k_WhlSpdQLimit_Cnt_u16   |
| k_WhlSpdQNStep_Cnt_u16   |
| t_FreqScaleTblX_Hz_u7p9  |
| k_WhlSpdQualDiag_Cnt_Str |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name      | Resolution             | Units | Value |
|--------------------|------------------------|-------|-------|
| D_WHLSPDMIN_HZ_F32 | single precision float | Hz    | 0     |
| D_WHLSPDMAX_HZ_F32 | single precision float | Hz    | 40    |

####  [section]

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name |
|---------------|
| \<None\>      |
|               |

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as
other tables)

| Constant Name | Resolution | Value | Software Segment |
|---------------|------------|-------|------------------|
| None          |            |       |                  |

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

1.  Limit_m

2.  Min_m

3.  FPM_FloatToFixed_m

4.  DiagPStep_m

5.  DiagNStep_m

6.  DiagFailed_m

## Data Hiding Functions

1.  \<None\>

2.  

## Global Functions/Macros Defined by this Module

### Global Function \#1

| **Function Name**    | None | Type | Min | Max | UTP Tol. |
|----------------------|------|------|-----|-----|----------|
| **Arguments Passed** |      |      |     |     |          |
|                      |      |      |     |     |          |
| **Return Value**     |      |      |     |     |          |

#### Description

(Place flowchart/design for local function)

## Local Functions/Macros Used by this MDD only

### Qualify Wheel Speed

| **Function Name**    | QualifyWhlSpd            | Type               | Min   | Max  | UTP Tol. |
|----------------|-----------------------------|----------|-------|------|------|
| **Arguments Passed** | WhlSpd_Ptr_T_f32         | pointer to float32 | 0     | 40   |          |
|                      | PrevQualWhlSpd_Ptr_T_f32 | pointer to float32 | 0     | 40   |          |
|                      | WhlSpdValid_Cnt_T_lgc    | boolean            | FALSE | TRUE |          |
|                      | QualLevel_Ptr_T_u16      | pointer to uint16  | 0     | 10   |          |
| **Return Value**     | N/A                      |                    |       |      |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/WIRInputQual/doc/mediax/media/image2.emf)

### Wheel Speed In Range Check

| **Function Name**    | WhlSpdInRange     | Type    | Min   | Max  | UTP Tol. |
|----------------------|-------------------|---------|-------|------|----------|
| **Arguments Passed** | WhlSpd_Hz_T_f32   | float32 | 0     | 40   |          |
| **Return Value**     | InRange_Cnt_T_lgc | boolean | FALSE | TRUE | 0        |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/WIRInputQual/doc/mediax/media/image3.emf)

### Wheel Speed Qualification Check

| **Function Name**    | WhlSpdQualCheck          | Type              | Min   | Max  | UTP Tol. |
|----------------|-----------------------------|----------|-------|------|------|
| **Arguments Passed** | QualLevel_Cnt_T_u16      | uint16            | 1     | 10   |          |
|                      | InRange_Cnt_T_lgc        | boolean           | FALSE | TRUE |          |
|                      | QualErrAcc_Ptr_T_u16     | pointer to uint16 | FULL  | FULL |          |
| **Return Value**     | WhlSpdQualfied_Cnt_T_lgc | Boolean           | FALSE | TRUE | 0        |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/WIRInputQual/doc/mediax/media/image4.emf)

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data                     | Value |
|--------------------------|-------|
| SrlComLWhlSpdVld_Cnt_lgc | FALSE |
| SrlComRWhlSpdVld_Cnt_lgc | FALSE |
| SrlComLWhlSpd_Hz_f32     | 0     |
| SrlComRWhlSpd_Hz_f32     | 0     |
| QualWhlFreqL_Hz_f32      | 0     |
| QualWhlFreqR_Hz_f32      | 0     |
| WhlFreqQualified_Cnt_lgc | TRUE  |

## Initialization Functions

None

##  Periodic Functions

### Per: \_Per1

#### Design Rationale

None

#### Program Flow Start

Rte_Call_WIRInputQual_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

WhlSpdLeftValid_Cnt_T_lgc =
Rte_IRead_WIRInputQual_Per1_SrlComLWhlSpdVld_Cnt_lgc()

WhlSpdLeft_Hz_T_f32 = Rte_IRead_WIRInputQual_Per1_SrlComLWhlSpd_Hz_f32()

WhlSpdRightValid_Cnt_T_lgc =
Rte_IRead_WIRInputQual_Per1_SrlComRWhlSpdVld_Cnt_lgc()

WhlSpdRight_Hz_T_f32 =
Rte_IRead_WIRInputQual_Per1_SrlComRWhlSpd_Hz_f32()

#### Processing

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/WIRInputQual/doc/mediax/media/image5.emf)

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_WIRInputQual_Per1_QualWhlFreqL_Hz_f32(WhlSpdLeft_Hz_T_f32)

Rte_IWrite_WIRInputQual_Per1_QualWhlFreqR_Hz_f32(WhlSpdRight_Hz_T_f32)

Rte_IWrite_WIRInputQual_Per1_WhlFreqQualified_Cnt_lgc(WhlFreqQualified_Cnt_T_lgc)

#### Program Flow End

Rte_Call_WIRInputQual_Per1_CP1_CheckpointReached()

##  Fault Recovery Functions

None

##  Shutdown Functions

None

##  Interrupt Functions

None

##  Serial Communication Functions

None

##  

# Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the
different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name     | Calling Frequency | System State(s) in which the function is called |
|--------------------------|-----------------|------------------------------|
| WIRInputQual_Per1 | 2ms               | ALL                                             |

## Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| \<None\>      |                                                  |

#  [section-2]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module | Software Segment                        |
|--------------------|-----------------------------------------|
| WIRInputQual_Per1  | RTE_START_SEC_AP_WIRINPUTQUAL_APPL_CODE |
|                    |                                         |

##  [section-3]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module | Software Segment                   |
|--------------------|------------------------------------|
| QualifyWhlSpd      | N/A (Inline with calling function) |
| WhlSpdInRange      | N/A (Inline with calling function) |
| WhlSpdQualCheck    | N/A (Inline with calling function) |

#  [section-4]

#  Known Issues / Limitations With Design

1.  Inline function defined in globalmacro.h are not unit tested

#  Revision Control Log

| **Item \#** | **Rev \#** | **Change Description** | **Date**  | **Author Initials** |
|------|------|--------------------------------------------|---------|---------|
| 1           | 1          | Initial version        | 20-Feb-12 | LWW                 |
| 2           | 2          | Checkpoints added      | 11-Nov-12 | NRAR                |

{% endraw %}