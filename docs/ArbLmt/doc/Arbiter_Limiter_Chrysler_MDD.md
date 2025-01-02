---
layout: default
title: Arbiter_Limiter_Chrysler_MDD
nav_order: 1
parent: Arbiter Limit
---
{% raw %}
# Module –  [module]

# High-Level Description

This module arbitrates between the HaLF, DST, and PA features to produce
the input and output torque overlay signals. It also provides an output
showing which features are enabled.

# Figures

## Component Diagram

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ArbLmt/doc/mediax/media/image1.png"
style="width:3.24375in;height:2.79097in" />

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs              | Module Outputs |                              |
|----------------------------|----------------|------------------------------|
| HaLFTrqOvCmdRqst_MtrNm_f32 |                | OpTrqOvr_MtrNm_f32           |
| DSTTrqOvCmdRqst_HwNm_f32   |                | IpTrqOvr_HwNm_f32            |
| PATrqOvCmdRqst_HwNm_f32    |                | ActiveFunctionBits_Cnt_u08   |
| HaLFActive_Cnt_lgc         |                | DSTSlewComplete_Cnt_lgc      |
| DSTActive_Cnt_lgc          |                | HaLFSlewComplete_Cnt_lgc     |
| VehicleSpeed_Kph_f32       |                | PPPASlewComplete_Cnt_lgc     |
| DSTState_Cnt_u08           |                | PAReturnSclFct_Uls_f32       |
| HalfTOState_Cnt_u08        |                | PICmpDisableLearning_Cnt_lgc |
| PrkAssistState_Cnt_u08     |                |                              |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table style="width:100%;">
<colgroup>
<col style="width: 31%" />
<col style="width: 17%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 26%" />
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
<td>DSTScalarSlew_Uls_M_f32</td>
<td>Single Precision Float`</td>
<td>0</td>
<td>1</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>HaLFScalarSlew_Uls_M_f32</td>
<td>Single Precision Float`</td>
<td>0</td>
<td>1</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>DSTSlew_HwNm_M_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>1</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>HaLFSlew_MtrNm_M_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>1</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>PPPASlew_HwNm_M_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>1</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>DSTLowSpdPri_Cnt_M_lgc</td>
<td>boolean</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>PrevDSTActive_Cnt_M_lgc</td>
<td>boolean</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>PrevDSTRampActive_Cnt_M_lgc</td>
<td>boolean</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>PrevHaLFRampActive_Cnt_M_lgc</td>
<td>boolean</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>PPPAPriority_Cnt_D_lgc</td>
<td>boolean</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>SlewActive_Cnt_M_lgc</td>
<td>boolean</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>PrevDSTSlewState_Cnt_M_lgc</td>
<td>boolean</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>PrevHaLFSlewState_Cnt_M_lgc</td>
<td>boolean</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>PrevPPPASlewState_Cnt_M_lgc</td>
<td>boolean</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN</td>
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
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

| Constant Name                 |
|-------------------------------|
| k_PPPAPriorityVehSpd_Kph_f32  |
| k_RateLimit_UlspS_f32         |
| k_DSTSlewRate_NmpS_f32        |
| k_HaLFSlewRate_NmpS_f32       |
| k_PPPASlewRate_NmpS_f32       |
| t2_AsstY0_MtrNm_s4p11\[\]\[\] |
| t2_HwtX0_HwNm_u8p8\[\]\[\]    |
| t_PPPAVehSpd_Kph_u9p7\[\]     |
| k_HalFPICmpThresh_MtrNm_f32   |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name         | Resolution             | Units  | Value |
|-----------------------|------------------------|--------|-------|
| D_4MS_S_F32           | Single Precision Float | S      | 0.004 |
| D_PPPAFUNCBIT_CNT_U08 | 1                      | Counts | 1     |
| D_DSTFUNCBIT_CNT_U08  | 1                      | Counts | 2     |
| D_HALFFUNCBIT_CNT_U08 | 1                      | Counts | 4     |
| D_PPPALOLMT_MTRNM_F32 | Single Precision Float | MtrNm  | -0.1  |
| D_PPPAHILMT_MTRNM_F32 | Single Precision Float | MtrNm  | 8.8   |

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name  |
|----------------|
| D_ONE_ULS_F32  |
| D_ZERO_ULS_F32 |
| D_ZERO_CNT_U8  |

### Module specific Lookup Tables Constants

| Constant Name | Resolution | Value | Software Segment |
|---------------|------------|-------|------------------|
| None          |            |       |                  |

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

1.  Limit_m

2.  Abs_f32_m

3.  FPM_FloatToFixed_m

4.  FPM_FixedToFloat_m

5.  Sign_f32_m

6.  BilinearXMYM_s16_u16XMs16YM_Cnt

7.  TableSize_m

## Data Hiding Functions

1.  None

## Global Functions/Macros Defined by this Module

None

## Local Functions/Macros Used by this MDD only

### Abriter Slew Limit

|                      |                         |           |       |      |              |
|-------------|---------------------------|----------|--------|--------|--------|
| **Function Name**    | ArbiterSlewLimit        | Type      | Min   | Max  | UT Tolerance |
| **Arguments Passed** | TrqOvCmdRqst_HwNm_T_f32 | Float32   | -10   | 10   | N/A          |
|                      | SlewState_Cnt_T_lgc     | Boolean   | FALSE | TRUE | N/A          |
|                      | SlewRate_NmpS_T_f32     | Float32   | 0     | 2    | N/A          |
|                      | TrqOvCmdOut_HwNm_T_f32  | \*Float32 | -10   | 10   | 3.05E-05     |
|                      | SlewComplete_Cnt_T_lgc  | \*Boolean | FALSE | TRUE | N/A          |
|                      | CmdActive_Cnt_T_lgc     | \*Boolean | FALSE | TRUE | N/A          |
|                      | Slew_Uls_T_f32          | \*Float32 | -10   | 10   | 3.05E-05     |
|                      | PrevSlewState_Cnt_T_lgc | \*Boolean | FALSE | TRUE | N/A          |
| **Return Value**     | None                    |           |       |      |              |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ArbLmt/doc/mediax/media/image2.emf)

### Arbiter Priority

|                      |                         |         |       |      |              |
|-------------|---------------------------|----------|--------|--------|--------|
| **Function Name**    | ArbiterPriority         | Type    | Min   | Max  | UT Tolerance |
| **Arguments Passed** | VehSpd_Kph_T_f32        | Float32 | 0     | 511  | N/A          |
|                      | DSTCmdActive_Cnt_T_lgc  | Boolean | FALSE | TRUE | N/A          |
|                      | PPPACmdActive_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A          |
|                      | HaLFCmdActive_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A          |
|                      | HaLFPriActive_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A          |
|                      | PPPAPriActive_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A          |
|                      | DSTPriActive_Cnt_T_lgc  | boolean | FALSE | TRUE | N/A          |
| **Return Value**     | None                    |         |       |      |              |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ArbLmt/doc/mediax/media/image3.emf)

### Arbiter Ramping

|                      |                            |         |       |      |              |
|-------------|---------------------------|----------|--------|--------|--------|
| **Function Name**    | ArbiterRamping             | Type    | Min   | Max  | UT Tolerance |
| **Arguments Passed** | DSTEnable_Cnt_T_lgc        | Boolean | FALSE | TRUE | N/A          |
|                      | DSTSlewComplete_Cnt_T_lgc  | Boolean | FALSE | TRUE | N/A          |
|                      | HaLFEnable_Cnt_T_lgc       | Boolean | FALSE | TRUE | N/A          |
|                      | HaLFSlewComplete_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A          |
|                      | DSTScalar_Uls_T_f32        | Float32 | 0     | 1    | 3.05E-05     |
|                      | HaLFScalar_Uls_T_f32       | Float32 | 0     | 1    | 3.05E-05     |
| **Return Value**     | None                       |         |       |      |              |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ArbLmt/doc/mediax/media/image4.emf)

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data                                      | Value |
|-------------------------------------------|-------|
| Rte_InitValue_ActiveFunctionBits_Cnt_u08  | 0     |
| Rte_InitValue_DSTActive_Cnt_lgc           | FALSE |
| Rte_InitValue_DSTSlewComplete_Cnt_lgc     | FALSE |
| Rte_InitValue_DSTState_Cnt_u08            | 0     |
| Rte_InitValue_DSTTrqOvCmdRqst_HwNm_f32    | 0     |
| Rte_InitValue_HaLFActive_Cnt_lgc          | FALSE |
| Rte_InitValue_HaLFSlewComplete_Cnt_lgc    | FALSE |
| Rte_InitValue_HaLFTOState_Cnt_u08         | 0     |
| Rte_InitValue_HaLFTrqOvCmdRqst_MtrNm_f32  | 0     |
| Rte_InitValue_IpTrqOvr_HwNm_f32           | 0     |
| Rte_InitValue_OpTrqOvr_MtrNm_f32          | 0     |
| Rte_InitValue_PAReturnSclFct_Uls_f32      | 1     |
| Rte_InitValue_PATrqOvCmdRqst_HwNm_f32     | 0     |
| Rte_InitValue_PrkAssistState_Cnt_u08      | 0     |
| Rte_InitValue_PrkAsstSlewComplete_Cnt_lgc | FALSE |
| Rte_InitValue_VehicleSpeed_Kph_f32        | 0     |

## Initialization Functions

None

##  Periodic Functions

### Per: \_Per1

#### Design Rationale

None

#### Program Flow Start

Rte_Call_ArbLmt_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

DSTActive_Cnt_T_lgc = Rte_IRead_ArbLmt_Per1_DSTActive_Cnt_lgc()

HaLFActive_Cnt_T_lgc = Rte_IRead_ArbLmt_Per1_HaLFActive_Cnt_lgc()

DSTState_Cnt_T_u08 = Rte_IRead_ArbLmt_Per1_DSTState_Cnt_u08()

DSTTrqOvCmdRqst_HwNm_T_f32 =
Rte_IRead_ArbLmt_Per1_DSTTrqOvCmdRqst_HwNm_f32()

HaLFTrqOvCmdRqst_MtrNm_T_f32 =
Rte_IRead_ArbLmt_Per1_HaLFTrqOvCmdRqst_MtrNm_f32()

HaLFTOState_Cnt_T_u08 = Rte_IRead_ArbLmt_Per1_HaLFTOState_Cnt_u08()

PATrqOvCmdRqst_HwNm_T_f32 =
Rte_IRead_ArbLmt_Per1_PATrqOvCmdRqst_HwNm_f32()

PrkAssistState_Cnt_T_u08 =
Rte_IRead_ArbLmt_Per1_PrkAssistState_Cnt_u08()

VehicleSpeed_Kph_T_f32 = Rte_IRead_ArbLmt_Per1_VehicleSpeed_Kph_f32()

#### DST Slew

c

#### HaLF Slew

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ArbLmt/doc/mediax/media/image5.emf)

#### PPPA Slew

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ArbLmt/doc/mediax/media/image6.emf)

#### Priority

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ArbLmt/doc/mediax/media/image7.emf)

#### Ramping

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ArbLmt/doc/mediax/media/image8.emf)

#### Arbiter

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/ArbLmt/doc/mediax/media/image9.emf)

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_ArbLmt_Per1_ActiveFunctionBits_Cnt_u08(ActiveFunctionBits_Cnt_T_u08)

Rte_IWrite_ArbLmt_Per1_DSTSlewComplete_Cnt_lgc(DSTSlewComplete_Cnt_T_lgc)

Rte_IWrite_ArbLmt_Per1_HaLFSlewComplete_Cnt_lgc(HaLFSlewComplete_Cnt_T_lgc)

Rte_IWrite_ArbLmt_Per1_IpTrqOvr_HwNm_f32(IpTrqOvr_HwNm_T_f32)

Rte_IWrite_ArbLmt_Per1_OpTrqOvr_MtrNm_f32(OpTrqOvr_MtrNm_T_f32)

Rte_IWrite_ArbLmt_Per1_PAReturnSclFct_Uls_f32(PAReturnSclFct_Uls_T_f32)

Rte_IWrite_ArbLmt_Per1_PrkAsstSlewComplete_Cnt_lgc(PPPASlewComplete_Cnt_T_lgc)

Rte_IWrite_ArbLmt_Per1_PICmpDisableLearning_Cnt_lgc(PICmpDisableLearning_Cnt_T_lgc)

#### Program Flow End

Rte_Call_ArbLmt_Per1_CP1_CheckpointReached()

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

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name | Calling Frequency | System State(s) in which the function is called |
|--------------------------|-----------------|------------------------------|
| ArbLmt_Per1   | 4 ms              | ALL                                             |

## Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| None          |                                                  |

#  [section-1]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module | Software Segment                  |
|--------------------|-----------------------------------|
| ArbLmt_Per1        | RTE_START_SEC_AP_ARBLMT_APPL_CODE |

##  [section-2]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module | Software Segment |
|--------------------|------------------|
| ArbiterSlewLimit   | N/A              |
| ArbiterPriority    | N/A              |
| ArbiterRamping     | N/A              |

#  [section-3]

#  Known Issues / Limitations With Design

1.  INLINE functions defined in GlobalMacro.h are not unit tested.

#  Revision Control Log

|             |            |                        |           |                     |
|------|------|--------------------------------------------|---------|---------|
| **Item \#** | **Rev \#** | **Change Description** | **Date**  | **Author Initials** |
| 1           | 1.0        | Initial Version        | 29-Oct-12 | OT                  |
| 2           | 2.0        | Anomaly 4668           | 22-Mar-13 | M. Story            |
| 3           | 3.0        | Update to FDD ver 003  | 15-May-13 | Jared               |
| 4           | 4.0        | UTP corrections        | 30-May-13 | Jared               |
| 5           | 5.0        | Updated to FDD ver 004 | 10-Jul-13 | SP                  |
| 6           | 6.0        | Anomaly 6467           | 14-MAR-14 | M. Story            |

{% endraw %}