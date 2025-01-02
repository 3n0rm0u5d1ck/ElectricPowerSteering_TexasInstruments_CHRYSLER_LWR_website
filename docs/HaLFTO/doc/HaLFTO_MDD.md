---
layout: default
title: HaLFTO_MDD
nav_order: 4
parent: Component
---
{% raw %}
# Module -- HaLFTO [module----halfto]

# High-Level Description

This function describes the activation logic used to implement the
torque overlay functionality related to lane departure warning with
haptic lane feedback.

# Figures

## Component Diagram

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image2.png"
style="width:3.06944in;height:4.56528in" />

### Diagram – Function HaLFTO_Per1

This diagram describes the functional characteristics and data flow of a
given function.

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image3.wmf)

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs                      | Module Outputs |                     |
|------------------------------------|----------------|---------------------|
| HaLFEnableRqst_Cnt_lgc             |                | HaLFActive_Cnt_lgc  |
|                                    |                | HaLFState_Cnt_u08   |
| HaLFIntSystemFltActive_Cnt_lgc     |                | HaLFSuspend_Cnt_lgc |
| HaLFErrInterfaceActive_Cnt_lgc     |                |                     |
| HaLFExtSystemFltActive_Cnt_lgc     |                |                     |
| VehicleSpeed_Kph_f32               |                |                     |
| HaLFSWATrqFail_Cnt_lgc             |                |                     |
| HaLFTrqOvReverseGearEngage_Cnt_lgc |                |                     |
| HaLFSlewComplete_Cnt_lgc           |                |                     |
| HaLFFuncPresent_Cnt_lgc            |                |                     |
| HwTorque_HwNm_f32                  |                |                     |
| SystemState_Mode                   |                |                     |
| LimitPercentFiltered_Uls_f32       |                |                     |
| DSTState_Cnt_u08                   |                |                     |
| TOEOLDisable_Cnt_lgc               |                |                     |
| PrevHaLFEnableRqst_Cnt_lgc         |                |                     |
| PrevHaLFTrqOvCmdRqst_MtrNm_f32     |                |                     |

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
<td>HaLFTO_DeactDSTStateChkFail_Cnt_D_lgc</td>
<td>1</td>
<td>FALSE</td>
<td>TRUE</td>
<td>HALFTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>HaLFTO_IncorHaLFActvnFailed_Cnt_M_lgc</td>
<td>1</td>
<td>FALSE</td>
<td>TRUE</td>
<td>HALFTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>HaLFTO_HaLFDeactLongFailed_Cnt_M_lgc</td>
<td>1</td>
<td>FALSE</td>
<td>TRUE</td>
<td>HALFTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>HaLFTO_IncorHaLFActvnHwTrqTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>HALFTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>HaLFTO_IncorHaLFActvnVehSpdTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>HALFTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>HaLFTO_IncorHaLFActvnRevGearTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>HALFTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>HaLFTO_HaLFDeactHwTrqTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>HALFTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>HaLFTO_HaLFDeactVehSpdTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>HALFTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>HaLFTO_HaLFDeactRevGearTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>HALFTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>HaLFTO_DSTSyncTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>HALFTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>HaLFTO_LimitPercentFilteredTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>HALFTO_START_SEC_VAR_NOINIT_32</td>
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
<td>HaLFTO_State_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>3</td>
<td>HALFTO_START_SEC_VAR_CLEARED_8</td>
</tr>
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

| Constant Name                  |
|--------------------------------|
| k_HaLFActvHwTrqTime_mS_u16     |
| k_HaLFActvMaxHwTrq_mS_f32      |
| k_HaLFActvVehSpdTime_mS_u16    |
| k_HaLFActvMinVehSpd_Kph_f32    |
| k_HaLFActvMaxVehSpd_Kph_f32    |
| k_HaLFActvRevGearTime_mS_u16   |
| k_HaLFDeactHwTrqTime_mS_u16    |
| k_HaLFDeactMaxHwTrq_HwNm_f32   |
| k_HaLFDeactVehSpdTime_mS_u16   |
| k_HaLFDeactMinVehSpd_Kph_f32   |
| k_HaLFDeactMaxVehSpd_Kph_f32   |
| k_HaLFDeactRevGearTime_mS_u16  |
| k_HaLFDSTSyncTime_mS_u16       |
| k_TrqOverlayLimitPerc_Uls_f32  |
| k_TrqOverlaySuspendTime_mS_u16 |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name                  | Resolution | Units  | Value |
|--------------------------------|------------|--------|-------|
| D_HALFSTATEINACTIVE_CNT_U08    | 1          | Counts | 0     |
| D_HALFSTATEACTIVE_CNT_U08      | 1          | Counts | 1     |
| D_HALFSTATEIHIBITED_CNT_U08    | 1          | Counts | 2     |
| D_HALFSTATERECOVERABLE_CNT_U08 | 1          | Counts | 3     |
| D_DSTACTIVE1_CNT_U08           | 1          | Counts | 5     |
| D_DSTACTIVE2_CNT_U08           | 1          | Counts | 6     |
| D_DSTACTIVE3_CNT_U08           | 1          | Counts | 7     |
| D_INCORHALFACTVNMASK_CNT_U08   | 1          | Counts | 1     |
| D_HALFDEACTLONGMASK_CNT_U08    | 1          | Counts | 2     |

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name  |
|----------------|
| D_ZERO_ULS_F32 |
| FLT_EPSILON    |

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

1.  Abs_f32_m

2.  Rte_Call_SystemTime_GetSystemTime_mS_u32

3.  Rte_Call_SystemTime_DtrmnElapsedTime_mS_u16

4.  Rte_Call_NxtrDiagMgr_GetNTCFailed

5.  Rte_Call_NxtrDiagMgr_SetNTCStatus

6.  Rte_Call_HaLFState_SCom_Transition

## Data Hiding Functions

1.  Rte_Mode_SystemState_Mode

2.  

## Local Functions/Macros Used by this MDD only

### Common HwTrqVehSpdRevGear Check

|                      |                           |                         |     |      |            |
|--------------|----------------------|-----------------|------|------|---------|
| **Function Name**    | HwTrqVehSpdRevGearCheck   | Type                    | Min | Max  | UTP Tol.   |
| **Arguments Passed** | HwTrqTime_mS_T_u16        | Uint16                  | 0   | FULL | 0          |
|                      | HwTrqTimerPtr_mS_T_u32    | Uint32\*                | 0   | FULL | 0          |
|                      | MaxHwTrq_HwNm_T_f32       | float32                 | 0.0 | 10.0 | 0.00390625 |
|                      | VehSpdTime_mS_T_u16       | Uint16                  | 0   | FULL | 0          |
|                      | VehSpdTimerPtr_mS_T_u32   | Uint32\*                | 0   | FULL | 0          |
|                      | MinVehSpd_Kph_T_f32       | float32                 | 0   | 255  | .0078125   |
|                      | MaxVehSpd_Kph_T_f32       | float32                 | 0   | 255  | .0078125   |
|                      | RevGearChkTime_mS_T_u16   | Uint16                  | 0   | FULL | 0          |
|                      | RevGearTimerPtr_mS_T_u32  | Uint32\*                | 0   | FULL | 0          |
| **Return Value**     | HaLFDiagStatus_Cnt_T_enum | Uint8 NxtrDiagMgrStatus | 0   | 3    | 0          |

#### Description

HaLFEnableRqst_Cnt_T_lgc =
Rte_IRead_HaLFTO_Per1_HaLFEnableRqst_Cnt_lgc()

HwTorque_HwNm_T_f32 = Rte_IRead_HaLFTO_Per1_HwTorque_HwNm_f32()

HaLFTrqOvReverseGearEngage_Cnt_T_lgc =
Rte_IRead_HaLFTO_Per1_HaLFTrqOvReverseGearEngage_Cnt_lgc()

VehicleSpeed_Kph_T_f32 = Rte_IRead_HaLFTO_Per1_VehicleSpeed_Kph_f32()

HaLFDiagStatus_Cnt_T_enum = NTC_STATUS_PASSED

#### Hw Trq Check

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image4.emf)

#### Vehicle Speed Check

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image5.emf)

#### Reverse Gear Check

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image6.emf)

#  [section]

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data                                  | Value |
|---------------------------------------|-------|
| DSTState_Cnt_u08                      | 0     |
| DiagStsNonRecRmpToZeroFltPres_Cnt_lgc | FALSE |
| DiagStsRecRmpToZeroFltPres_Cnt_lgc    | FALSE |
| HaLFActive_Cnt_lgc                    | FALSE |
| HaLFEnableRqst_Cnt_lgc                | FALSE |
| HaLFErrInterfaceActive_Cnt_lgc        | FALSE |
| HaLFExtSystemFltActive_Cnt_lgc        | FALSE |
| HaLFFuncPresent_Cnt_lgc               | FALSE |
| HaLFIntSystemFltActive_Cnt_lgc        | FALSE |
| HaLFSWATrqFail_Cnt_lgc                | FALSE |
| HaLFSlewComplete_Cnt_lgc              | FALSE |
| HaLFState_Cnt_u08                     | 0     |
| HaLFSuspend_Cnt_lgc                   | FALSE |
|                                       | 0     |
| HwTorque_HwNm_f32                     | 0     |
| LimitPercentFiltered_Uls_f32          | 0     |
| HaLFTrqOvReverseGearEngage_Cnt_lgc    | FALSE |
| VehicleSpeed_Kph_f32                  | 0     |
| TOEOLDisable_Cnt_lgc                  | FALSE |
| PrevHaLFEnableRqst_Cnt_lgc            |       |
| PrevTrqOvCmdRqst_MtrNm_f32            |       |

## Initialization Functions

### Init: HaLFTO_Init1(void)

#### Design Rationale

The init function here sets all timers to some valid value, and informs
SCom that the module is transitioning into the inactive state.

#### Initial State Transition

Rte_Call_HaLFState_SCom_Transition(D_HALFSTATEINACTIVE_CNT_U08)

#### Module Internal 

Rte_Call_SystemTime_GetSystemTime_mS_u32(&Time_mS_u32)

HaLFTO_IncorHaLFActvnHwTrqTimer_mS_M_u32 = Time_mS_u32

HaLFTO_IncorHaLFActvnVehSpdTimer_mS_M_u32 = Time_mS_u32

HaLFTO_IncorHaLFActvnRevGearTimer_mS_M_u32 = Time_mS_u32

HaLFTO_HaLFDeactHwTrqTimer_mS_M_u32 = Time_mS_u32

HaLFTO_HaLFDeactVehSpdTimer_mS_M_u32 = Time_mS_u32

HaLFTO_HaLFDeactRevGearTimer_mS_M_u32 = Time_mS_u32

HaLFTO_DSTSyncTimer_mS_M_u32 = Time_mS_u32

HaLFTO_LimitPercentFilteredTimer_mS_M_u32 = Time_mS_u32

(void)Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_VLF_04, 0x0U,
NTC_STATUS_PASSED);

##  Periodic Functions

### Per: \_Per1(void)

#### Design Rationale

None

#### Program Flow Start

Rte_Call_HaLFTO_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

DSTState_Cnt_T_u08 = Rte_IRead_HaLFTO_Per1_DSTState_Cnt_u08()

DiagStsNonRecRmpToZeroFltPres_Cnt_T_lgc =
Rte_IRead_HaLFTO_Per1_DiagStsNonRecRmpToZeroFltPres_Cnt_lgc()

DiagStsRecRmpToZeroFltPres_Cnt_T_lgc =
Rte_IRead_HaLFTO_Per1_DiagStsRecRmpToZeroFltPres_Cnt_lgc()

HaLFEnableRqst_Cnt_T_lgc =
Rte_IRead_HaLFTO_Per1_HaLFEnableRqst_Cnt_lgc()

HaLFErrInterfaceActive_Cnt_T_lgc =
Rte_IRead_HaLFTO_Per1_HaLFErrInterfaceActive_Cnt_lgc()

HaLFExtSystemFltActive_Cnt_T_lgc =
Rte_IRead_HaLFTO_Per1_HaLFExtSystemFltActive_Cnt_lgc()

HaLFFuncPresent_Cnt_T_lgc =
Rte_IRead_HaLFTO_Per1_HaLFFuncPresent_Cnt_lgc()

HaLFIntSystemFltActive_Cnt_T_lgc =
Rte_IRead_HaLFTO_Per1_HaLFIntSystemFltActive_Cnt_lgc()

HaLFSWATrqFail_Cnt_T_lgc =
Rte_IRead_HaLFTO_Per1_HaLFSWATrqFail_Cnt_lgc()

HaLFSlewComplete_Cnt_T_lgc =
Rte_IRead_HaLFTO_Per1_HaLFSlewComplete_Cnt_lgc()

LimitPercentFiltered_Uls_T_f32 =
Rte_IRead_HaLFTO_Per1_LimitPercentFiltered_Uls_f32()

TOEOLDisable_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_TOEOLDisable_Cnt_lgc()

PrevHaLFEnableRqst_Cnt_T_lgc =
Rte_IRead_HaLFTO_Per1_PrevHaLFEnableRqst_Cnt_lgc()

PrevTrqOvCmdRqst_MtrNm_T_f32 =
Rte_IRead_HaLFTO_Per1_PrevHaLFTrqOvCmdRqst_MtrNm_f32()

#### Initialize Faults

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image7.emf)

#### Incorrect HaLF Activation Diagnostic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image8.emf)

#### HaLF Deactivation Diagnostic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image9.emf)

#### HaLF Deactivation Diagnostic continued…

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image10.emf)

#### HalF Torque Overlay Enable

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image11.emf)

#### Transition Vector Logic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image12.wmf)

#### Inactive Transitions

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image13.emf)

#### Active Transitions

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image14.emf)

#### Recoverable Transitions

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image15.emf)

#### Transitions Complete

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HaLFTO/doc/mediax/media/image16.emf)

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_HaLFTO_Per1_HaLFState_Cnt_u08(HaLFTO_State_Cnt_M_u08)

Rte_IWrite_HaLFTO_Per1_HaLFSuspend_Cnt_lgc(HaLFSuspend_T_lgc)

#### Program Flow End

Rte_Call_HaLFTO_Per1_CP1_CheckpointReached()

##  Execution Requirements

### Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name | Calling Frequency | System State(s) in which the function is called |
|--------------------------|-----------------|------------------------------|
| HaLFTO_Per1   | 2ms               | Warm Init, Disable, Operate                     |

### Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| \<None\>      |                                                  |

#  [section-1]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module | Software Segment                  |
|--------------------|-----------------------------------|
| HaLFTO_Init1       | RTE_START_SEC_AP_HALFTO_APPL_CODE |
| HaLFTO_Per1        | RTE_START_SEC_AP_HALFTO_APPL_CODE |

##  [section-2]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module      | Software Segment        |
|-------------------------|-------------------------|
| HwTrqVehSpdRevGearCheck | RTE_AP_HALFTO_APPL_CODE |

#  [section-3]

#  Known Issues / Limitations With Design

1.  Inline functions in GlobalMacro.h are not unit tested.

#  Revision Control Log

|            |                                                                                        |           |                     |
|------|-----------------------------------------------|---------|----------|
| **Rev \#** | **Change Description**                                                                 | **Date**  | **Author Initials** |
| 1          | Initial component creation.                                                            | 5-Nov-12  | BWL                 |
| 2          | Corrected vehicle speed check Incorrect HaLF activation(DST Active State Deactivation) | 20-Feb-13 | SR                  |
| 3          | Corrected Transition T5 from Recoverable to Inactive as per anomaly 4527               | 26-Feb-13 | SR                  |
| 4          | Update to FDD 40D v004                                                                 | 09-May-13 | BDO                 |
| 5          | Updated to CF 08A V001                                                                 | 09-Jul-13 | SP                  |
| 6          | Added logic to pass the NTCs if the enable criteria is FALSE.                          | 08-Oct-13 | MR                  |
| 7          | Updated to FDD CF-08C v004                                                             | 23-Jan-14 | VT                  |
| 8          | Updated to FDD CF-08C v005                                                             | 04-Feb-14 | VT                  |
| 9          | Unit Testing Finding Fixes                                                             | 20-Feb-14 | KPIT-PM             |
| 10         | Updated to FDD CF-08C v006                                                             | 24-Feb-14 | VT                  |
| 11         | Updated to FDD CF-08C v007                                                             | 06-Mar-14 | VT                  |
| 12         | Updated per Design Review and Updated to FDD CF-08Cv008                                | 24-Apr-14 | M. Story            |
| 13         | A6806 anomaly fix 11959                                                                | 20-May-14 | SB                  |

{% endraw %}