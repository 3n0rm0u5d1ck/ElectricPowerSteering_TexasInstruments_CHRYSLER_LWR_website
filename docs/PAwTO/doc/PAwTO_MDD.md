---
layout: default
title: PAwTO_MDD
nav_order: 4
parent: Component
---
{% raw %}
# Module --  [module---]

# High-Level Description

This function describes the algorithms used to implement the activation
logic for torque overlay functionality related to park assist.

# Figures

## Diagram – Component Diagram

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image1.png"
style="width:3.06736in;height:4.94028in" />

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be
shown here)

| Module Inputs                         | Module Outputs |                            |
|-----------------------------------|--|------------------------------------|
| PATrqOvCmdRqst_HwNm_f32               |                | PrkAssistActive_Cnt_lgc    |
| PAEnableRqst_Cnt_lgc                  |                | PrkAssistState_Cnt_u08     |
| PAIntSystemFltActive_Cnt_lgc          |                | HandsOnDetect_Cnt_lgc      |
| PAErrInterfaceActive_Cnt_lgc          |                | PrkAssistSuspend_Cnt_lgc   |
| PAExtSystemFltActive_Cnt_lgc          |                | PABoostCurveSwitch_Cnt_lgc |
| VehicleSpeed_Kph_f32                  |                |                            |
| TrqOvReverseGearEngage_Cnt_lgc        |                |                            |
| PAWheelCriteriaMet_Cnt_lgc            |                |                            |
| LimitPercentFiltered_Uls_f32          |                |                            |
| DiagStsNonRecRmpToZeroFltPres_Cnt_lgc |                |                            |
| DiagStsRecRmpToZeroFltPres_Cnt_lgc    |                |                            |
| TOEOLDisable_Cnt_lgc                  |                |                            |
| HwTorque_HwNm_f32                     |                |                            |
| PrkAsstSlewComplete_Cnt_lgc           |                |                            |
| PrkAsstFuncPresent_Cnt_lgc            |                |                            |
| PAWhlDirRLStat_Cnt_u08                |                |                            |
| PAWhlDirRRStat_Cnt_u08                |                |                            |
| PAWhlPlsCntRLValid_Cnt_lgc            |                |                            |
| PAWhlPlsCntRRValid_Cnt_lgc            |                |                            |
| PAManoeuvrePhase_Cnt_u08              |                |                            |
| IWSSCalcVspd_Kph_f32                  |                |                            |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 14%" />
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
<td>PAwTO_PrkAssistState_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>3</td>
<td>PAWTO_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>PAwTO_VSpdActvnMet_Cnt_M_lgc</td>
<td>1</td>
<td>FALSE</td>
<td>TRUE</td>
<td>PAWTO_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>PAwTO_IWSSComputedSpin_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>3</td>
<td>PAWTO_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>PAwTO_HandsOnHwTrqSV_HwNm_M_s4p27</td>
<td>7.45058E-09</td>
<td>-10</td>
<td>10</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>PAwTO_BoostCurveSwitchTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>PAwTO_LimitPercentFilteredTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>PAwTO_RvsGearTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>PAwTO_TrqOvRqNotZeroTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>PAwTO_VehSpdNotLowTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>PAwTO_IWSSWhlSpinTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>PAwTO_IWSSWhlSpinClrTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>PAwTO_ExcessVehSpdTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>PAwTO_ExcessVehSpdClrTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>PAwTO_MovMismatchTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>PAwTO_MovMismatchClrTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>PAwTO_VehicleSpeedMismatchTimer_mS_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>PAWTO_START_SEC_VAR_NOINIT_32</td>
</tr>
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

| Constant Name                     |
|-----------------------------------|
| k_HandsOnLPFKn_Cnt_u16            |
| k_TrqOverlayHandsOnTrq_HwNm_u5p27 |
| k_PARvsGearChkTime_mS_u16         |
| k_PATrqOvNotZeroChkTime_mS_u16    |
| k_PAVehSpdNotLowTime_mS_u16       |
| k_PAVSpdNotLowMin_Kph_f32         |
| k_PAVSpdNotLowMax_Kph_f32         |
| k_PAIWSSWhlSpinSetTime_mS_u16     |
| k_PAIWSSWhlSpinClrTime_mS_u16     |
| k_PAExcessVehSpdSetTime_mS_u16    |
| k_PAExcessVehSpdClrTime_mS_u16    |
| k_PAExcessVehSpd_Kph_f32          |
| k_PAMovMismatchSetTime_mS_u16     |
| k_PAMovMismatchClrTime_mS_u16     |
| k_PAMovMismatchVSpd_Kph_f32       |
| k_PAVspdMismatchSetTime_mS_u16    |
| k_PAEIWSSChkVspd_Kph_f32          |
| k_PABoostCurveTime_mS_u16         |
| k_TrqOverlayLimitPerc_Uls_f32     |
| k_TrqOverlaySuspendTime_mS_u16    |

## Program (fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name                | Resolution | Units  | Value |
|------------------------------|------------|--------|-------|
| D_PASTATEINACTIVE_CNT_U08    | 1          | Counts | 0     |
| D_PASTATEACTIVE_CNT_U08      | 1          | Counts | 1     |
| D_PASTATEINHIBITED_CNT_U08   | 1          | Counts | 2     |
| D_PASTATERECOVERABLE_CNT_U08 | 1          | Counts | 3     |
| D_STDSTIL_CNT_U08            | 1          | Counts | 0     |
| D_FORWARD_CNT_U08            | 1          | Counts | 1     |
| D_BACKWRD_CNT_U08            | 1          | Counts | 2     |
| D_INVALID_CNT_U08            | 1          | Counts | 3     |
| D_MANOEUVREPAHSEBKWD_CNT_U08 | 1          | Counts | 0     |
| D_MANOEUVREPAHSEFWD_CNT_U08  | 1          | Counts | 1     |
| D_PARVSGEARMASK_CNT_U08      | 1          | Counts | 1     |
| D_PATRQOVNOTZEROMASK_CNT_U08 | 1          | Counts | 2     |
| D_PAVSPDNOTLOW_CNT_U08       | 1          | Counts | 4     |

####  [section]

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name  |
|----------------|
| D_ZERO_ULS_F32 |
| D_ONE_CNT_U8   |
| FLT_EPSILON    |

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as
other tables)

<table style="width:100%;">
<colgroup>
<col style="width: 32%" />
<col style="width: 11%" />
<col style="width: 40%" />
<col style="width: 16%" />
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
<td>T2_IWSSCOMPSPIN_CNT_U08</td>
<td>1</td>
<td><p>{</p>
<p>{D_STDSTIL_CNT_U08, D_FORWARD_CNT_U08, D_BACKWRD_CNT_U08,
D_STDSTIL_CNT_U08},</p>
<p>{D_FORWARD_CNT_U08, D_FORWARD_CNT_U08, D_FORWARD_CNT_U08,
D_FORWARD_CNT_U08},</p>
<p>{D_BACKWRD_CNT_U08, D_FORWARD_CNT_U08, D_BACKWRD_CNT_U08,
D_BACKWRD_CNT_U08},</p>
<p>{D_STDSTIL_CNT_U08, D_FORWARD_CNT_U08, D_BACKWRD_CNT_U08,
D_INVALID_CNT_U08}</p>
<p>};</p></td>
<td>PAWTO_START_SEC_CONST_8</td>
</tr>
</tbody>
</table>

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

1.  FPM_FloatToFixed_m

2.  Rte_Call_NxtrDiagMgr_SetNTCStatus

3.  Rte_Call_NxtrDiagMgr_GetNTCActive

4.  Rte_Call_SystemTime_GetSystemTime_mS_u32

5.  Rte_Call_SystemTime_DtrmnElapsedTime_mS_u16

6.  LPF_SvUpdate_s16InFixKTrunc_m

7.  Abs_s32_m

## Data Hiding Functions

1.  Rte_Mode_SystemState_Mode

```{=html}
<!-- -->
```
1.  

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data                                  | Value |
|---------------------------------------|-------|
| DiagStsNonRecRmpToZeroFltPres_Cnt_lgc | FALSE |
| DiagStsRecRmpToZeroFltPres_Cnt_lgc    | FALSE |
| HandsOnDetect_Cnt_lgc                 | FALSE |
| HwTorque_HwNm_f32                     | 0     |
| IWSSCalcVspd_Kph_f32                  | 0     |
| LimitPercentFiltered_Uls_f32          | 0     |
| PABoostCurveSwitch_Cnt_lgc            | FALSE |
| PAEnableRqst_Cnt_lgc                  | FALSE |
| PAErrInterfaceActive_Cnt_lgc          | FALSE |
| PAExtSystemFltActive_Cnt_lgc          | FALSE |
| PAIntSystemFltActive_Cnt_lgc          | FALSE |
| PAManoeuvrePhase_Cnt_u08              | 0     |
| PATrqOvCmdRqst_HwNm_f32               | 0     |
| PAWheelCriteriaMet_Cnt_lgc            | FALSE |
| PAWhlDirRLStat_Cnt_u08                | 3     |
| PAWhlDirRRStat_Cnt_u08                | 3     |
| PAWhlPlsCntRLValid_Cnt_lgc            | FALSE |
| PAWhlPlsCntRRValid_Cnt_lgc            | FALSE |
| PrkAssistActive_Cnt_lgc               | FALSE |
| PrkAssistState_Cnt_u08                | 0     |
| PrkAssistSuspend_Cnt_lgc              | FALSE |
| PrkAsstFuncPresent_Cnt_lgc            | FALSE |
| PrkAsstSlewComplete_Cnt_lgc           | FALSE |
| TOEOLDisable_Cnt_lgc                  | FALSE |
| TrqOvReverseGearEngage_Cnt_lgc        | FALSE |
| VehicleSpeed_Kph_f32                  | 0     |

## Initialization Functions

### Init: PAwTO_Init1(void)

#### Design Rationale

This init function initializes the hand wheel torque low pass filter,
and the fault timers. Also initializes the state from the perspective of
the SCom module.

#### Module Outputs

None

#### Module Internal 

HwTorque_HwNm_T_f32 = Rte_IRead_PAwTO_Init1_HwTorque_HwNm_f32()

PAwTO_HandsOnHwTrqSV_HwNm_M_s4p27 =
FPM_FloatToFixed_m(HwTorque_HwNm_T_f32, s4p27_T)

Rte_Call_SystemTime_GetSystemTime_mS_u32(&Time_mS_T_u32)

PAwTO_BoostCurveSwitchTimer_mS_M_u32 = Time_mS_T_u32

PAwTO_LimitPercentFilteredTimer_mS_M_u32 = Time_mS_T_u32

PAwTO_RvsGearTimer_mS_M_u32 = Time_mS_T_u32

PAwTO_TrqOvRqNotZeroTimer_mS_M_u32 = Time_mS_T_u32

PAwTO_VehSpdNotLowTimer_mS_M_u32 = Time_mS_T_u32

PAwTO_IWSSWhlSpinTimer_mS_M_u32 = Time_mS_T_u32

PAwTO_IWSSWhlSpinClrTimer_mS_M_u32 = Time_mS_T_u32

PAwTO_ExcessVehSpdTimer_mS_M_u32 = Time_mS_T_u32

PAwTO_ExcessVehSpdclrTimer_mS_M_u32 = Time_mS_T_u32

PAwTO_MovMismatchTimer_mS_M_u32 = Time_mS_T_u32

PAwTO_MovMismatchClrTimer_mS_M_u32 = Time_mS_T_u32

PAwTO_VehicleSpeedMismatchTimer_mS_M_u32 = Time_mS_T_u32

Rte_Call_PrkAssistState_SCom_Transition(D_PASTATEINACTIVE_CNT_U08)

##  Periodic Functions

(Note: For multiple periodic functions, insert new headers at the
“Header 2” level – subset of “5.2 Periodic Functions” and follow the
same sub-section design shown below)

### Per: PAwTO_Per1(void)

#### Design Rationale

This periodic handles all portions of PAwTO with a 2ms trigger rate.

#### Program Flow Start

Rte_Call_PAwTO_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

DiagStsNonRecRmpToZeroFltPres_Cnt_T_lgc =
Rte_IRead_PAwTO_Per1_DiagStsNonRecRmpToZeroFltPres_Cnt_lgc()

DiagStsRecRmpToZeroFltPres_Cnt_T_lgc =
Rte_IRead_PAwTO_Per1_DiagStsRecRmpToZeroFltPres_Cnt_lgc()

HwTorque_HwNm_T_f32 = Rte_IRead_PAwTO_Per1_HwTorque_HwNm_f32()

LimitPercentFiltered_Uls_T_f32 =
Rte_IRead_PAwTO_Per1_LimitPercentFiltered_Uls_f32()

PAEnableRqst_Cnt_T_lgc = Rte_IRead_PAwTO_Per1_PAEnableRqst_Cnt_lgc()

PAErrInterfaceActive_Cnt_T_lgc =
Rte_IRead_PAwTO_Per1_PAErrInterfaceActive_Cnt_lgc()

PAExtSystemFltActive_Cnt_T_lgc =
Rte_IRead_PAwTO_Per1_PAExtSystemFltActive_Cnt_lgc()

PAIntSystemFltActive_Cnt_T_lgc =
Rte_IRead_PAwTO_Per1_PAIntSystemFltActive_Cnt_lgc()

PAWheelCriteriaMet_Cnt_T_lgc =
Rte_IRead_PAwTO_Per1_PAWheelCriteriaMet_Cnt_lgc()

PrkAsstFuncPresent_Cnt_T_lgc =
Rte_IRead_PAwTO_Per1_PrkAsstFuncPresent_Cnt_lgc()

PrkAsstSlewComplete_Cnt_T_lgc =
Rte_IRead_PAwTO_Per1_PrkAsstSlewComplete_Cnt_lgc()

TrqOvReverseGearEngage_Cnt_T_lgc =
Rte_IRead_PAwTO_Per1_TrqOvReverseGearEngage_Cnt_lgc()

TOEOLDisable_Cnt_T_lgc = Rte_IRead_PAwTO_Per1_TOEOLDisable_Cnt_lgc()

VSpdActvnMet_Cnt_T_lgc = PAwTO_VSpdActvnMet_Cnt_M_lgc

Rte_Call_NxtrDiagMgr_GetNTCActive(NTC_Num_ExVoltageLow,
&NTCLowBattVtg_Cnt_T_lgc)

Rte_Call_NxtrDiagMgr_GetNTCActive(NTC_Num_VLF_02,
&ParkAsstActvnFailed_Cnt_T_lgc)

Rte_Call_NxtrDiagMgr_GetNTCActive(NTC_Num_VLF_08,
&NTCPAVspdMismatch_Cnt_T_lgc)

Rte_Call_NxtrDiagMgr_GetNTCActive(NTC_Num_VLF_05,
&NTCPAIWSSVspdValidity_Cnt_T_lgc)

Rte_Call_NxtrDiagMgr_GetNTCActive(NTC_Num_VLF_06,
&NTCPAExcessVspd_Cnt_T_lgc)

Rte_Call_NxtrDiagMgr_GetNTCActive(NTC_Num_VLF_07,
&NTCPARationalityChk_Cnt_T_lgc)

Rte_Call_NxtrDiagMgr_GetNTCActive(NTC_Num_InvalidMsg_W,
&NTCTireCircmInvalid_Cnt_T_lgc)

#### Hands On Detection

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image2.wmf)

#### Process for PrkAssist_Activate Flag

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image3.emf)

#### Process PA_BoostCurv_Switch Output

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image4.emf)

#### Processing for PrkAssist_Suspend Flag

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image5.emf)

#### PrkAssist_State

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image6.wmf)

#### Inactive Transitions

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image7.emf)

#### Active Transitions

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image8.emf)

#### Recoverable Transitions

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image9.emf)

#### Transition Complete

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image10.wmf)

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_PawTO_Per1_HandsOnDetect_Cnt_lgc(HandsOnDetect_Cnt_T_lgc)

Rte_Iwrite_PawTO_Per1_PABoostCurveSwitch_Cnt_lgc(PABoostCurveSwitch_Cnt_T_lgc)

Rte_Iwrite_PawTO_Per1_PrkAssistActive_Cnt_lgc(PrkAssistActive_Cnt_T_lgc)

Rte_Iwrite_PawTO_Per1_PrkAssistState_Cnt_u08(PrkAssistState_Cnt_T_u08)

Rte_Iwrite_PawTO_Per1_PrkAssistSuspend_Cnt_lgc(PrkAssistSuspend_Cnt_T_lgc)

#### Program Flow End

Rte_Call_PawTO_Per1_CP1_CheckpointReached()

###  Per: PawTO_Per2(void)

#### Design Rationale

This periodic handles all portions of PawTO with a 10ms trigger rate.

#### Program Flow Start

Rte_Call_PawTO_Per2_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

IWSSCalcVspd_Kph_T_f32 = Rte_Iread_PawTO_Per2_IWSSCalcVspd_Kph_f32()

PAEnableRqst_Cnt_T_lgc = Rte_Iread_PawTO_Per2_PAEnableRqst_Cnt_lgc()

PAManoeuvrePhase_Cnt_u08 =
Rte_Iread_PawTO_Per2_PAManoeuvrePhase_Cnt_u08()

PATrqOvCmdRqst_HwNm_T_f32 =
Rte_Iread_PawTO_Per2_PATrqOvCmdRqst_HwNm_f32()

PAWhlDirRLStat_Cnt_T_u08 = Rte_Iread_PawTO_Per2_PAWhlDirRLStat_Cnt_u08()

PAWhlDirRRStat_Cnt_T_u08 = Rte_Iread_PawTO_Per2_PAWhlDirRRStat_Cnt_u08()

PAWhlPlsCntRLValid_Cnt_T_lgc =
Rte_Iread_PawTO_Per2_PAWhlPlsCntRLValid_Cnt_lgc()

PAWhlPlsCntRRValid_Cnt_T_lgc =
Rte_Iread_PawTO_Per2_PAWhlPlsCntRRValid_Cnt_lgc()

TrqOvReverseGearEngage_Cnt_T_lgc =
Rte_Iread_PawTO_Per2_TrqOvReverseGearEngage_Cnt_lgc()

VehicleSpeed_Kph_T_f32 = Rte_Iread_PawTO_Per2_VehicleSpeed_Kph_f32()

PrkAssistState_Cnt_T_u08 = PawTO_PrkAssistState_Cnt_M_u08

Rte_Call_NxtrDiagMgr_GetNTCActive(NTC_Num_VLF_05,
&NTCPAIWSSVspdValidity_Cnt_T_lgc)

Rte_Call_NxtrDiagMgr_GetNTCActive(NTC_Num_VLF_06,
&NTCPAExcessVspd_Cnt_T_lgc)

Rte_Call_NxtrDiagMgr_GetNTCActive(NTC_Num_VLF_07,
&NTCPARationalityChk_Cnt_T_lgc)

PAWhlDirRLStat_Cnt_T_u08 = Min_m(PAWhlDirRLStat_Cnt_T_u08,
D_INVALID_CNT_U08)

PAWhlDirRRStat_Cnt_T_u08 = Min_m(PAWhlDirRRStat_Cnt_T_u08,
D_INVALID_CNT_U08)

PrkAsstFuncPresent_Cnt_T_lgc =
Rte_IRead_PAwTO_Per2_PrkAsstFuncPresent_Cnt_lgc()

#### Incorrect Park Assist Activation Diagnostic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image11.emf)

#### Torque Overlay Zero Check

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image12.emf)

#### Vehicle Speed Check

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image13.emf)

#### IWSS Signal Validity Check and Wheel Spin Signal Processing

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image14.emf)

#### IWSS Wheel Spin Inactive

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image15.emf)

#### Calculate IWSS Computed Spin

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image16.wmf)

#### Excessive Vehicle Speed Condition

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image17.emf)

#### Excess Veh Speed Inactive

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image18.emf)

#### Actual Vehicle Longitudinal Movement and PPPA Computed Movement Mismatch Condition

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image19.emf)

#### Move Mismatch Inactive

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image20.emf)

#### ESC and IWSS Vehicle Speed Signal Mismatch Condition

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/PAwTO/doc/mediax/media/image21.emf)

#### Program Flow End

Rte_Call_PawTO_Per2_CP1_CheckpointReached()

# Execution Requirements

## Execution Sequence of the Module

The order of execution of the two periodic is not important.

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name | Calling Frequency | System State(s) in which the function is called |
|--------------------------|-----------------|------------------------------|
| PawTO_Per1    | 2ms               | Warm Init, Disable, Operate                     |
| PawTO_Per2    | 10ms              | Warm Init, Disable, Operate                     |

## Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| \<None\>      |                                                  |

#  [section-1]

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module | Software Segment                  |
|--------------------|-----------------------------------|
| PawTO_Init1        | RTE_START_SEC_AP_HALFTO_APPL_CODE |
| PawTO_Per1         | RTE_START_SEC_AP_HALFTO_APPL_CODE |
| PawTO_Per2         | RTE_START_SEC_AP_HALFTO_APPL_CODE |

##  [section-2]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module | Software Segment |
|--------------------|------------------|
| None               |                  |

#  Known Issues / Limitations With Design

1.  Inline functions in GlobalMacro.h are not unit tested.

#  Revision Control Log

|            |                                                                       |           |                     |
|------|-----------------------------------------------|---------|----------|
| **Rev \#** | **Change Description**                                                | **Date**  | **Author Initials** |
| 1          | Initial component creation.                                           | 5-Nov-12  | BWL                 |
| 2          | Anomaly 4434,4534 PawTO_IWSSWhlSpinTimer_mS_M_u32 used multiple times | 21-MAR-13 | MRS                 |
| 3          | Anomaly fixes 4767,4768,4777                                          | 12-APR-13 | Srikanth            |
| 4          | Anomaly 4815, 4816                                                    | 18-Apr-13 | Srikanth            |
| 5          | Update to FDD 40B v004                                                | 09-May-13 | BDO                 |
| 6          | Update to FDD 40B v005                                                | 19-Jun-13 | SP                  |
| 7          | Update to CF-08A v001                                                 | 09-Jul-13 | SP                  |
| 8          | Added logic to pass the NTCs if the enable criteria is FALSE          | 08-Oct13  | MR                  |
| 9          | Changed GetNTCFailed to GetNTCActive macro.                           | 22-Oct-13 | MR                  |
| 10         | Updated to CF-08A Park Assist rev 004                                 | 05-Feb-14 | VT                  |

{% endraw %}