---
layout: default
title: StabiliCtrlTorqueOverlay_MDD
nav_order: 3
parent: Component
---
{% raw %}
# Module -- Stability Control Torque Overlay66 [module----stability-control-torque-overlay66]

# High-Level Description

This function describes the algorithms used to implement the activation
logic for torque overlay functionality related to dynamic stability.

# Figures

## Diagram – Function Data Sharing

This diagram shows all data that is shared between functions within the
module.

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image1.png"
style="width:4.30139in;height:5.20764in" />

# Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be
shown here)

|                                       |                                       |
|----------------------------------|--------------------------------------|
| Module Inputs (Global Variable Name)  | Module Outputs (Global Variable Name) |
| DSTTOCState_Cnt_u08                   | DSTActive_Cnt_lgc                     |
| DSTEnableRqst_Cnt_lgc                 | DSTState_Cnt_u08                      |
| DSTExtSystemFltActive_Cnt_lgc         | DSTSlewStart_Cnt_lgc                  |
| DSTErrCntrRecvLevel_Cnt_u08           |                                       |
| DSTTrqOvCmdRqst_HwNm_f32              |                                       |
| DSTTrqOvRqstValid_Cnt_lgc             |                                       |
| NTCDSTMaxValue_Cnt_T_lgc              |                                       |
| NTCDSTMaxRate_Cnt_lgc                 |                                       |
| NTCDSTMaxTime_Cnt_lgc                 |                                       |
| NTCDSTXOR_Cnt_lgc                     |                                       |
| NTCDSTStuckValue_Cnt_lgc              |                                       |
| TOEOLDisable_Cnt_lgc                  |                                       |
| DSTSlewComplete_Cnt_lgc               |                                       |
| TrqOvReverseGearEngage_Cnt_lgc        |                                       |
| VehicleSpeed_Kph_f32                  |                                       |
| VehicleSpeedValid\_ Cnt_lgc           |                                       |
| LimitPercentFiltered_Uls_f32          |                                       |
| NTCLowBattVtg_Cnt_T_lgc               |                                       |
| DiagStsNonRecRmpToZeroFltPres_Cnt_lgc |                                       |
| DiagStsRecRmpToZeroFltPres_Cnt_lgc    |                                       |
| DSTFuncPresent_Cnt_lgc                |                                       |
| SystemState_Mode                      |                                       |
| DSTRevGearValid_Cnt_lgc               |                                       |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table>
<colgroup>
<col style="width: 38%" />
<col style="width: 12%" />
<col style="width: 11%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>Variable Name</th>
<th>User Defined Type</th>
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
<td>DSTRDTimer_M_mS_u32</td>
<td>UINT32</td>
<td>N/A</td>
<td>FULL</td>
<td>FULL</td>
<td>STBCTO_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>DSTTNATimer_M_mS_u32</td>
<td>UINT32</td>
<td>N/A</td>
<td>FULL</td>
<td>FULL</td>
<td>STBCTO_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>RDStateCounter_Cnt_M_u08</td>
<td>UINT8</td>
<td>N/A</td>
<td>0</td>
<td>255</td>
<td>STBCTO_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>DSTVspdActive_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>STBCTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>DSTBkwdMotionAbsent_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>STBCTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>VehExtCondDSTActive_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>STBCTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>IntCondDSTEnable_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>STBCTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>LoSpdInactive_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>STBCTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>HiSpdInactive_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>STBCTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>DiagStsNonRecRmpToZeroFltPres_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>STBCTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>DiagStsRecRmpToZeroFltPres_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>STBCTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>DSTInternalCondTimer_mS_M_u32</td>
<td>UINT32</td>
<td>N/A</td>
<td>FULL</td>
<td>FULL</td>
<td>STBCTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>DSTBkwdMotionTime_mS_M_u32</td>
<td>UINT32</td>
<td>N/A</td>
<td>FULL</td>
<td>FULL</td>
<td>STBCTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>activeTimer_mS_M_u32</td>
<td>UINT32</td>
<td>N/A</td>
<td>FULL</td>
<td>FULL</td>
<td>STBCTO_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>InactiveTimer_mS_M_u32</td>
<td>UINT32</td>
<td>N/A</td>
<td>FULL</td>
<td>FULL</td>
<td>STBCTO_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>DSTState_Cnt_M_enum</td>
<td>TOC_STATE</td>
<td>N/A</td>
<td>0</td>
<td>8</td>
<td>STBCTO_START_SEC_VAR_CLEARED_UNSPECIFIED</td>
</tr>
<tr class="odd">
<td>StartTNATimer_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>STBCTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>StartRDTimer_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>STBCTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
</tbody>
</table>

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
<td colspan="5">typedef
void(*DSTHandler_T)(boolean*DSTActive_T_lgc,boolean*DSTSlewStart_T_lgc)</td>
</tr>
<tr class="odd">
<td>TOC_STATE</td>
<td>TOCSTATE_OFF</td>
<td rowspan="9">Uint8</td>
<td colspan="2">0</td>
</tr>
<tr class="even">
<td></td>
<td>TOCSTATE_TNA</td>
<td colspan="2">1</td>
</tr>
<tr class="odd">
<td></td>
<td>TOCSTATE_PNA</td>
<td colspan="2">2</td>
</tr>
<tr class="even">
<td></td>
<td>TOCSTATE_READY</td>
<td colspan="2">3</td>
</tr>
<tr class="odd">
<td></td>
<td>TOCSTATE_REQUESTDENIED</td>
<td colspan="2">4</td>
</tr>
<tr class="even">
<td></td>
<td>TOCSTATE_ACTIVEMODE05</td>
<td colspan="2">5</td>
</tr>
<tr class="odd">
<td></td>
<td>TOCSTATE_ACTIVEMODE06</td>
<td colspan="2">6</td>
</tr>
<tr class="even">
<td></td>
<td>TOCSTATE_ACTIVEMODE07</td>
<td colspan="2">7</td>
</tr>
<tr class="odd">
<td></td>
<td>TOCSTATE_NOTAVAILABLE</td>
<td colspan="2">8</td>
</tr>
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

|                                    |
|------------------------------------|
| Constant Name                      |
| k_DSTVSpdVLH_Kph_f32               |
| k_DSTVSpdVHH_Kph_f32               |
| k_DSTVSpdVLL_Kph_f32               |
| k_DSTVSpdVHL_Kph_f32               |
| k_DSTVehSpdActvTime_mS_u16         |
| k_DSTVehSpdInActvTime_mS_u16       |
| k_DSTBkwdMotionTime_mS_u16         |
| k_TrqOverlayLimitPerc_Uls_f32      |
| k_TrqOverlaySuspendTime_mS_u16     |
| k_DSTTrqOvActiveMaxLimit_MtrNm_f32 |
| k_DSTTNAMaxTime_mS_u16             |
| k_DSTRDMaxTime_mS_u16              |
| k_DSTRDStateMaxCount_Cnt_u08       |

## Program (fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

|               |            |       |
|---------------|------------|-------|
| Constant Name | Resolution | Value |
|               |            |       |

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

|               |
|---------------|
| Constant Name |
| D_ONE_CNT_U8  |
|               |

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as
other tables)

<table>
<colgroup>
<col style="width: 36%" />
<col style="width: 18%" />
<col style="width: 26%" />
<col style="width: 18%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Constant Name</td>
<td>Resolution</td>
<td>Value</td>
<td>Software Segment</td>
</tr>
<tr class="even">
<td>t_DSTStates_Cnt_Fn</td>
<td>n/a</td>
<td><p>&amp;StbCTO_DSTSt_Off</p>
<p>&amp;StbCTO_DSTSt_TNA</p>
<p>&amp;StbCTO_DSTSt_PNA</p>
<p>&amp;StbCTO_DSTSt_Ready</p>
<p>&amp;StbCTO_DSTSt_RequestDenied</p>
<p>&amp;StbCTO_DSTSt_Active</p>
<p>&amp;StbCTO_DSTSt_Active</p>
<p>&amp;StbCTO_DSTSt_Active</p>
<p>&amp;StbCTO_DSTSt_NotApplicable</p></td>
<td>AP_STBCTO_CODE</td>
</tr>
</tbody>
</table>

# Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library functions / Macros that are called by the various sub
modules are identified below,

## Data Hiding Functions

The data hiding functions / macros used in this module are identified
below,

1.  Rte_Call_NxtrDiagMgr_SetNTCStatus()

## Local Functions/Macros Used by this MDD only

(Note if they are defined in another source file, then reference the
appropriate header file)

The local functions/macros in this module are identified below,

1.  StbCTO_DSTSt_Notvailable ()

2.  StbCTO_DSTSt_Off()

3.  StbCTO_DSTSt_TNA()

4.  StbCTO_DSTSt_PNA()

5.  StbCTO_DSTSt_Ready()

6.  StbCTO_DSTSt_Active()

7.  StbCTO_DSTSt_RequestDenied()

# Software Module Implementation

## Initialization Functions

Module state variables are initialized to 0 at start-up by RAM init.

LoSpdInactive_Cnt_M_lgc = TRUE

###   [section]

## Periodic Functions [periodic-functions]

### Per: StbCTO_Per1

#### Design Rationale

1.  StartTNATimer_Cnt_M_lgc, This var is set to TRUE whenever
    transitioning to TNA state to initialize TNA Timer and set to FALSE
    when TNA timer is expired. Timer expired is checked in
    StartandStopTimer()

2.  StartRDTimer_Cnt_M_lgc, This var is set to TRUE whenever
    transitioning to RD state to initialize RD Timer and set to FALSE
    when RD timer is expired. Timer expired is checked in
    StartandStopTimer()

#### Program Flow Start

Rte_Call_StbCTO_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies 

SysState_Cnt_T_Enum = Rte_Mode_SystemState_Mode()

DSTFuncPresent_Cnt_T_lgc =
Rte_IRead_StbCTO_Per1_DSTFuncPresent_Cnt_lgc()

Rte_Call_NxtrDiagMgr_GetNTCFailed(NTC_Num_ExVoltageLow,
&NTCLowBattVtg_Cnt_T_lgc)

HalfActive_Cnt_T_lgc = Rte_IRead_StbCTO_Per1_HalfActive_Cnt_lgc()

LimitPercentFiltered_Uls_T_f32 =
Rte_IRead_StbCTO_Per1_LimitPercentFiltered_Uls_f32()

PrkAssistActive_Cnt_T_lgc =
Rte_IRead_StbCTO_Per1_PrkAssistActive_Cnt_lgc()

TrqOvReverseGearEngage_Cnt_lgc =
Rte_IRead_StbCTO_Per1_TrqOvReverseGearEngage_Cnt_lgc()

VehicleSpeed_Kph_T_f32 = Rte_IRead_StbCTO_Per1_VehicleSpeed_Kph_f32()

DiagStsNonRecRmpToZeroFltPres_Cnt_M_lgc =
Rte_IRead_StbCTO_Per1_DiagStsNonRecRmpToZeroFltPres_Cnt_lgc()

DiagStsRecRmpToZeroFltPres_Cnt_M_lgc =
Rte_IRead_StbCTO_Per1_DiagStsRecRmpToZeroFltPres_Cnt_lgc()

VehicleSpeedValid_Cnt_T_lgc =
Rte_IRead_StbCTO_Per1_VehicleSpeedValid_Cnt_lgc()

DSTRevGearValid_Cnt_T_lgc =
Rte_IRead_StbCTO_Per1_DSTRevGearValid_Cnt_lgc()

PrevDSTState_Cnt_T_enum = DSTState_Cnt_M_enum;

Rte_Call_NxtrDiagMgr_GetNTCFailed(NTC_Num_VLF_10,
&NTCDSTNotPresentCmdNotZero_Cnt_T_lgc);

Rte_Call_NxtrDiagMgr_GetNTCFailed(NTC_Num_VLF_11,
&NTCDSTEnableTrqRqstNotZero_Cnt_T_lgc);

Rte_Call_NxtrDiagMgr_GetNTCFailed(NTC_Num_VLF_12,
&NTCDSTStateRqstDenied_Cnt_T_lgc);

Rte_Call_NxtrDiagMgr_GetNTCFailed(NTC_Num_VLF_13,
&NTCDSTPresentTNARDTimerExpired_Cnt_T_lgc)

#### Perform Over and Low Voltage Diagnostics

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image3.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image4.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image5.wmf)

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_StbCTO_Per1_DSTSlewStart_Cnt_lgc(DSTSlewStart_Cnt_T_lgc)

Rte_IWrite_StbCTO_Per1_DSTActive_Cnt_lgc(DSTActive_Cnt_M_lgc)

Rte_IWrite_StbCTO_Per1_DSTState_Cnt_u08 (DSTState_Cnt_M_enum)

#### Program Flow End

Rte_Call_StbCTO_Per1_CP1_CheckpointReached()

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

## Local Function/Macro Definitions

### NotAVailable

|                      |                           |                 |       |      |
|---------------|--------------------------------|---------|---------|---------|
| **Function Name**    | StbCTO_DSTSt_NotAvailable | Type            | Min   | Max  |
| **Arguments Passed** | DSTActive_T_lgc           | boolean pointer | FALSE | TRUE |
|                      | DSTSlewStart_T_lgc        | boolean pointer | FALSE | TRUE |
| **Return Value**     | N/A                       |                 |       |      |

#### Description

/\* This function does nothing. \*/

DSTActive_T_lgc = DSTActive_T_lgc

DSTSlewStart_T_lgc = DSTSlewStart_T_lgc

### OFF state

|                      |                    |                 |       |      |
|----------------------|--------------------|-----------------|-------|------|
| **Function Name**    | StbCTO_DSTSt_Off   | Type            | Min   | Max  |
| **Arguments Passed** | DSTActive_T_lgc    | boolean pointer | FULL  | FULL |
|                      | DSTSlewStart_T_lgc | boolean pointer | FALSE | TRUE |
| **Return Value**     | N/A                |                 |       |      |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image6.wmf)

### TNA

|                      |                    |                 |       |      |
|----------------------|--------------------|-----------------|-------|------|
| **Function Name**    | StbCTO_DSTSt_TNA   | Type            | Min   | Max  |
| **Arguments Passed** | DSTActive_T_lgc    | boolean pointer | FALSE | TRUE |
|                      | DSTSlewStart_T_lgc | boolean pointer | FALSE | TRUE |
| **Return Value**     | N/A                |                 |       |      |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image7.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image8.wmf)

### PNA

|                      |                    |                 |       |      |
|----------------------|--------------------|-----------------|-------|------|
| **Function Name**    | StbCTO_DSTSt_PNA   | Type            | Min   | Max  |
| **Arguments Passed** | DSTActive_T_lgc    | boolean pointer | FULL  | FULL |
|                      | DSTSlewStart_T_lgc | boolean pointer | FALSE | TRUE |
| **Return Value**     | N/A                |                 |       |      |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image9.wmf)

### READY

|                      |                    |                 |       |      |
|----------------------|--------------------|-----------------|-------|------|
| **Function Name**    | StbCTO_DSTSt_Ready | Type            | Min   | Max  |
| **Arguments Passed** | DSTActive_T_lgc    | boolean pointer | FULL  | FULL |
|                      | DSTSlewStart_T_lgc | boolean pointer | FALSE | TRUE |
| **Return Value**     | N/A                |                 |       |      |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image10.wmf)![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image11.wmf)

###   [section-1]

### ACTIVE

|                      |                     |                 |       |      |
|----------------------|---------------------|-----------------|-------|------|
| **Function Name**    | StbCTO_DSTSt_Active | Type            | Min   | Max  |
| **Arguments Passed** | DSTActive_T_lgc     | boolean pointer | FULL  | FULL |
|                      | DSTSlewStart_T_lgc  | boolean pointer | FALSE | TRUE |
| **Return Value**     | N/A                 |                 |       |      |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image12.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image13.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image14.wmf)

### REQUEST DENIED

|                      |                            |                 |       |      |
|---------------|--------------------------------|---------|---------|---------|
| **Function Name**    | StbCTO_DSTSt_RequestDenied | Type            | Min   | Max  |
| **Arguments Passed** | DSTActive_T_lgc            | boolean pointer | FULL  | FULL |
|                      | DSTSlewStart_T_lgc         | boolean pointer | FALSE | TRUE |
| **Return Value**     | DSTActive_T_lgc            | boolean pointer | FULL  | FULL |

#### Description

# ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image15.wmf) [section-2]

### StartAndStopTimer

|                      |                      |                 |       |      |
|----------------------|----------------------|-----------------|-------|------|
| **Function Name**    | StartAndStopTimer    | Type            | Min   | Max  |
| **Arguments Passed** | StartTime_mS_T_u32   | Uint32          | FULL  | FULL |
|                      | TimeOut_mS_T_u16     | Uint16          | 0     | 5000 |
|                      | StartTimer_Cnt_T_lgc | Boolean pointer | FALSE | TRUE |
| **Return Value**     | N/A                  |                 |       |      |

#  [section-3]

#  [section-4]

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/StbCTO/doc/mediax/media/image16.wmf)

# Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the
different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

|               |           |                                        |                                                 |
|--------------------------|----------------|----------------|----------------|
| Function Name | Task List | Calling Frequency                      | System State(s) in which the function is called |
| StbCTO_Init1  |           | Executed once after the RTE is started | ALL                                             |
| StbCTO_per1   |           | 2ms                                    | WARMINIT, OPERATE,DISABLE                       |

## Execution Requirements for Serial Communication Functions 

|               |                                                  |
|---------------|--------------------------------------------------|
| Function Name | Sub-Module called by (Serial Comm Function Name) |
|               |                                                  |

#   [section-5]

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

|                    |                         |
|--------------------|-------------------------|
| Name of Sub Module | Software Segment        |
| StbCTO \_Per1()    | RTE_AP_STBCTO_APPL_CODE |

## Local Functions

This table identifies the software segments for local functions
identified in this module.

|                            |                  |
|----------------------------|------------------|
| Name of Sub Module         | Software Segment |
| StbCTO_DSTSt_NotApplicable | AP_STBCTO_CODE   |
| StbCTO_DSTSt_Off           | AP_STBCTO_CODE   |
| StbCTO_DSTSt_TNA           | AP_STBCTO_CODE   |
| StbCTO_DSTSt_PNA           | AP_STBCTO_CODE   |
| StbCTO_DSTSt_Ready         | AP_STBCTO_CODE   |
| StbCTO_DSTSt_Active        | AP_STBCTO_CODE   |
| StbCTO_DSTSt_RequestDenied | AP_STBCTO_CODE   |
| StartAndStopTimer          | AP_STBCTO_CODE   |

#   [section-6]

# Known Issues / Limitations With Design

This module is not meeting FDD for below points:

1) System_State is not shown as input in FDD sec 3 and sec 3.1

2) HalF_Active and PrkAssist_Active is not used in this module, But
these are shown in FDD Sec 3, 3.1, 3.3

This is informed to FDD owner and FDD will be updated for next release.

# Revision Control Log

|             |            |                                                                                                                                                    |           |                     |
|------|------|--------------------------------------------|---------|---------|
| **Item \#** | **Rev \#** | **Change Description**                                                                                                                             | **Date**  | **Author Initials** |
| 1           | 1.0        | Initial AutoSAR release.                                                                                                                           | 19-Oct-12 | NRAR                |
| 2           | 2.0        | Updated design rationale in Per1 and Sec 9                                                                                                         | 27-Nov-12 | NRAR                |
| 3           | 3.0        | Updated some of the port names                                                                                                                     | 27-Nov-12 | NRAR                |
| 4           | 4.0        | Corrected anomaly 4476 and 4477 SCR 7438                                                                                                           | 21-Fev-13 | DD                  |
| 5           | 5.0        | Set DSTActive as a global variable                                                                                                                 | 23-Fev-13 | DD                  |
| 6           | 6.0        | Correct transition from ACTIVE to Request Denied                                                                                                   | 23-Fev-13 | DD                  |
| 7           | 7.0        | Update to FDD 40C v004, v005                                                                                                                       | 09-May-13 | BDO                 |
| 8           | 8.0        | Updated StbCTO_DSTSt_Active() to support for Tessy coverage limitations, update StartAndStopTimer()                                                | 28-May-13 | BDO                 |
| 9           | 9.0        | Updated to CF08B Ver 001                                                                                                                           | 15-Jul-13 | SP                  |
| 10          | 10.0       | Added logic to pass the NTCs if the enable criteria is FALSE, And added AbsDSTTrqOvCmdRqst_HwNm_T_f32 in StbCTO_DSTSt_Ready to fix the QAC Warning | 08-Oct-13 | MR                  |
| 11          | 11.0       | Added logic to pass the NTC as per FDD version CF08B Ver4.                                                                                         | 22-Oct-13 | MR                  |
| 12          | 12.0       | Updated to CF-08B v005                                                                                                                             | 23-Jan-14 | VT                  |

{% endraw %}