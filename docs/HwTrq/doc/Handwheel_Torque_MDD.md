---
layout: default
title: Handwheel_Torque_MDD
nav_order: 3
parent: Handwheel Torque
---
{% raw %}
# Module -- Hand Wheel Torque2626 [module----hand-wheel-torque2626]

# High-Level Description

This function calculates the Hand Wheel Torque and performs the
diagnostics on the Torque input signals T1 and T2.

# Figures

## Component Diagram 

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image1.png"
style="width:2.5in;height:2.01042in" />

# Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

|                                      |                                       |
|----------------------------------|--------------------------------------|
| Module Inputs (Global Variable Name) | Module Outputs (Global Variable Name) |
| T1ADC_Volt_f32                       | AnaHwTorque_HwNm_f32                  |
| T2ADC_Volt_f32                       | SysCAnaHwTorque_HwNm_f32              |
| SysCHwTorqueSqd_HwNmSq_f32           | AnaDiffHwTrq_HwNm_f32                 |
| AbsPosStepSignal_Cnt_u08             | SrlComHwTrqValid_Cnt_lgc              |
| CntrlDisRampComplete_Cnt_lgc         | ErrorActiveAnalog_Cnt_enum            |
| MECCounter_Cnt_enum                  |                                       |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table>
<colgroup>
<col style="width: 34%" />
<col style="width: 12%" />
<col style="width: 13%" />
<col style="width: 13%" />
<col style="width: 27%" />
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
<td>CorrDiagFiltOut_Volt_M_s4p11</td>
<td>2<sup>-11</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>CorrDiagFiltSV_Volt_M_s4p27</td>
<td>2<sup>-11</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ_START_SEC_ VAR_SAVED_ZONEH_32</td>
</tr>
<tr class="even">
<td>SSDiagFiltOut_Volt_M_s4p11</td>
<td>2<sup>-11</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>SSDiagFiltSV_Volt_M_s4p27</td>
<td>2<sup>-27</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>TDiagFiltOut_Volt_M_s4p11</td>
<td>2<sup>-11</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>TDiagFiltSV_Volt_M_s4p27</td>
<td>2<sup>-27</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>SumFltOut_Volt_M_u5p11</td>
<td>2<sup>-11</sup></td>
<td>0</td>
<td>5.0</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>T1RngErrAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>T2RngErrAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>AnaDiffHwTrq_Volt_M_f32</td>
<td>Single Precision Floating Point</td>
<td>-5</td>
<td>5</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>AnaHwTorque_HwNm_M_f32</td>
<td>Single Precision Float</td>
<td>-10</td>
<td>10</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>TrqSum_Volts_M_s4p11</td>
<td>2<sup>-11</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>TrqSensorRecDiagAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>NvMBlkStatus_Cnt_M_u8</td>
<td>NvM_RequestResultType</td>
<td>N/A</td>
<td>N/A</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>AnaHwTorqueSqd_HwNmSq_D_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>100</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>HWTorqCorrLimDiff_HwNmSq_D_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>100</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>HwTorqCh1vsCh2CorrLim_HwNmSq_D_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>100</td>
<td>HWTRQ_START_SEC_VAR_CLEARED_32</td>
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
<td>HwTrqStatusType</td>
<td><p>HWTRQSTATUS_NONE = 0</p>
<p>HWTRQSTATUS_ACTIVE = 1</p>
<p>HWTRQSTATUS_FAULT = 2</p></td>
<td>uint8</td>
<td>0</td>
<td>2</td>
</tr>
<tr class="odd">
<td>ManufModeType</td>
<td><p>ProductionMode = 0</p>
<p>ManufacturingMode = 1</p>
<p>EngineeringMode = 2</p></td>
<td>Uint8</td>
<td>0</td>
<td>2</td>
</tr>
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

|                                      |
|--------------------------------------|
| Constant Name                        |
| k_TbarStiff_NmpDeg_f32               |
| k_HwTrqSclNom_VoltspDeg_f32          |
| k_AnaRngDiag_Cnt_str                 |
| k_T1LowRange_Volts_f32               |
| k_T1HghRange_Volts_f32               |
| k_T2LowRange_Volts_f32               |
| k_T2HghRange_Volts_f32               |
| k_MaxTrqSumLmt_Volts_f32             |
| t_TdiagFiltKnTbl_Cnt_u16\[17\]       |
| t_TdiagIndptTbl_Volts_u5p11\[17\]    |
| k_TdiagLim_Volts_u5p11               |
| k_SSDiagKn_Cnts_u16                  |
| k_CorrDiagKn_Cnts_u16                |
| k_TdiagCorrLim_Volts_u5p11           |
| k_SSDiagLim_Volts_u5p11              |
| k_CorrDiagFiltActiv_Volts_u5p11      |
| k_MaxHwTrqTrim_Volts_f32             |
| k_SumFiltRecLim_Volt_u5p11           |
| k_SSFiltRecLim_Volt_u5p11            |
| k_TrqFltRecLim_Cnt_u16               |
| k_T1AccRecLim_Cnt_u16                |
| k_T2AccRecLim_Cnt_u16                |
| k_AnaT1T2ErrThreshold_Volts_u5p11    |
| t_HwTorqCorrLimXAxis_HwNm_u4p12\[\]  |
| t_HwTorqCorrLimYAxis_HwNmSq_u7p9\[\] |
| k_HwTorqCorrLimDiag_Cnt_str          |

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image5.wmf)

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

|                                       |                                 |                                                            |
|------------------------------------|-----------------|--------------------|
| Constant Name                         | Resolution                      | Value                                                      |
| D_HWTRQLOLMT_HWNM_F32                 | Single Precision Floating Point | -10.0                                                      |
| D_HWTRQHILMT_HWNM_F32                 | Single Precision Floating Point | 10.0                                                       |
| D_DFLTRTRQTRIM_VOLT_F32               | Single Precision Floating Point | 2.5                                                        |
| D_TRQSCALEWNDW_ULS_F32                | Single Precision Floating Point | 0.20                                                       |
| D_NTCFAILED_CNT_U08                   | 1                               | 0x01U                                                      |
| D_SSDIAGNFILTSVLMT_VOLT_S4P27         | 2^-27^                          | FPM_Fix_m((k_SSDiagLim_Volts_u5p11 + 1), u5p11_T, s4p27_T) |
| D_FAILEDANDFAILEDTHISOPCYCLE_CNT_U08  | 1                               | 0x03                                                       |
| D_TESTNOTCOMPLETEDTHISOPCYCLE_CNT_U08 | 1                               | 0x40                                                       |
| D_NUMTRQSTEP_CNT_U08                  | 1                               | 10                                                         |

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

|                 |
|-----------------|
| Constant Name   |
| D_FALSE_CNT_LGC |
| D_ZERO_ULS_F32  |
| D_ZERO_CNT_U16  |
| D_ZERO_CNT_U8   |

### Module specific Lookup Tables Constants

|               |            |       |                  |
|---------------|------------|-------|------------------|
| Constant Name | Resolution | Value | Software Segment |
| None          |            |       |                  |

# Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library functions / Macros that are called by the various sub
modules are identified below,

1.  FPM_FixedToFloat_m()

2.  FPM_FloatToFixed_m()

3.  Limit_m()

4.  Abs_f32_m ()

5.  IntplVarXY_u16_u16Xu16Y_Cnt()

6.  LPF_SvUpdate_s16InFixKTrunc_m()

7.  LPF_OpUpdate_s16InFixKTrunc_m()

8.  DiagPStep_m()

9.  DiagNStep_m()

10. DiagFailed_m()

## Data Hiding Functions

The data hiding functions / macros used in this module are identified
below,

1.  Rte_Pim_HwTrqTrimData()

2.  Rte_Pim_HwTrqScaleData()

3.  Rte_Pim_EOLTrqStepData()

4.  Rte_Call_NxtrDiagMgr_SetNTCStatus()

5.  Rte_Call_HwTrqTrim_WriteBlock()

6.  Rte_Call_HwTrqScale_WriteBlock()

7.  Rte_Call_NxtrDiagMgr_GetNTCFailed()

8.  Rte_Call_NxtrDiagMgr_ResetEventStatus()

9.  Rte_Call_HwTrqTrim_GetErrorStatus()

## Local Functions/Macros Used by this MDD only

The local functions/macros in this module are identified below,

1.  IsTrqScaleInRng_lgc()

2.  TrqTrimPerfDiag()

# Software Module Implementation

## Initialization Functions

### Init: HwTrq_Init

#### Design Rationale

None

#### Check Faults and Initialize Filters

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image6.wmf)

## Periodic Functions

### Per: HwTrq_Per1

#### Design Rationale

None

#### Program Flow Start

Rte_Call_HwTrq_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

AbsPosStepSignal_Cnt_T_u08 =
Rte_IRead_HwTrq_Per1_AbsPosStepSignal_Cnt_u08()

Torque1_Volt_T_f32 = Rte_Iread_HwTrq_Per1_T1ADC_Volt_f32()

Torque2_Volt_T_f32 = Rte_Iread_HwTrq_Per1_T2ADC_Volt_f32()

Rte_Call_NxtrDiagMgr_GetNTCStatus(NTC_Num_TrqSensorRecoveryFlt,
&DiagTrqRecvStatus_Cnt_T_u08)

Rte_Call_NxtrDiagMgr_GetNTCStatus(NTC_Num_T1OutofRange,
&DiagT1OutofRangeStatus_Cnt_T_u08)

Rte_Call_NxtrDiagMgr_GetNTCStatus(NTC_Num_T2OutofRange,
&DiagT2OutofRangeStatus_Cnt_T_u08)

Rte_Call_NxtrDiagMgr_GetNTCStatus(NTC_Num_T1vsT2,
&DiagT1vsT2Status_Cnt_T_u08)

Rte_Call_NxtrDiagMgr_GetNTCStatus(NTC_Num_TrqSensorNotTrimmed,
&DiagTrqTrimNotPerfStatus_Cnt_T_u08)

Rte_Call_NxtrDiagMgr_GetNTCStatus(NTC_Num_PriSnsrTrqStorFlt,
&DiagTrqTrimInvalidStatus_Cnt_T_u08)

AbsPosStepSignal_Cnt_T_u08 = Limit_m(AbsPosStepSignal_Cnt_T_u08,
D_ZERO_CNT_U8, D_NUMTRQSTEP_CNT_U08 - 1U)

#### Calculate Handwheel Torque and SCom Validity

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image7.wmf)

#### Analog Error Active

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image8.wmf)

#### Store Local copy of outputs into Module Outputs

AnaDiffHwTrq_Volt_M_f32 = DiffHwTorque_Volts_T_f32

AnaHwTorque_HwNm_M_f32 = AnaHwTorque_HwNm_T_f32

Rte_IWrite_HwTrq_Per1_AnaDiffHwTrq_Volt_f32(DiffHwTorque_Volts_T_f32)

Rte_Iwrite_HwTrq_Per1_AnaHwTorque_HwNm_f32(AnaHwTorque_HwNm_T_f32)

Rte_IWrite_HwTrq_Per1_SysCAnaHwTorque_HwNm_f32(AnaHwTorque_HwNm_T_f32)

Rte_IWrite_HwTrq_Per1_ErrorActiveAnalog_Cnt_enum(ErrorActiveAnalog_Cnt_T_enum)

Rte_Iwrite_HwTrq_Per1_SrlComHwTrqValid_Cnt_lgc(SrlComHwTrqValid_Cnt_T_lgc)

#### Program Flow End

Rte_Call_HwTrq_Per1_CP1_CheckpointReached()

### Per: HwTrq_Per2

#### Design Rationale

None

#### Program Flow Start

Rte_Call_HwTrq_Per2_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

CntrlDisRampComplete_Cnt_T_lgc =
Rte_IRead_HwTrq_Per2_CntrlDisRampComplete_Cnt_lgc()

SysCHwTorqueSqd_HwNmSq_T_f32 =
Rte_IRead_HwTrq_Per2_SysCHwTorqueSqd_HwNmSq_f32()

Torque1_Volt_T_f32 = Rte_Iread_HwTrq_Per2_T1ADC_Volt_f32()

Torque2_Volt_T_f32 = Rte_Iread_HwTrq_Per2_T2ADC_Volt_f32()

T1Trim_Volt_T_f32 = Rte_Pim_HwTrqTrimData()-\>T1Trim_Volts_f32

T2Trim_Volt_T_f32 = Rte_Pim_HwTrqTrimData()-\>T2Trim_Volts_f32

#### T1 & T2 Out of Range

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image9.wmf)

#### T1 vs T2 Diagnostic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image10.wmf)

#### Torque Recovery Diagnostic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image11.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image12.wmf)

#### Handwheel Diff Torque Cross Check

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image13.wmf)

#### Store Local copy of outputs into Module Outputs

TrqSum_Volt_M_s4p11 = TrqSum_Volt_T_s4p11

TDiagFiltOut_Volt_M_s4p11 = TDiagFiltOut_Volt_T_s4p11

AnaHwTorqueSqd_HwNmSq_D_f32 = AnaHwTorqueSqd_HwNmSq_T_f32

HWTorqCorrLimDiff_HwNmSq_D_f32 = HwTorqCorrLimDiff_HwNmSq_T_f32

HwTorqCh1vsCh2CorrLim_HwNmSq_D_f32 = HwTorqCh1vsCh2CorrLim_HwNmSq_T_f32

#### Program Flow End

Rte_Call_HwTrq_Per2_CP1_CheckpointReached()

### Per: HwTrq_Per3

#### Design Rationale

None

#### Program Flow Start

Rte_Call_HwTrq_Per3_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

None

#### T1 Vs T2 Diagnostic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image14.wmf)

#### Store Local copy of outputs into Module Outputs

#### Program Flow End

Rte_Call_HwTrq_Per3_CP1_CheckpointReached()

## Serial Communication Functions

### Scomm: HwTrq_Scom_ClrHwTrqScale

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

#### Clear Handwheel Torque Scale Service

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image15.wmf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

### Scomm: HwTrq_Scom_ClrHwTrqTrim

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

#### Clear Handwheel Torque Trim Service

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image16.wmf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

### Scomm: HwTrq_Scom_ReadHwTrqScale

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

None

#### Read Handwheel Torque Scale Service

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image17.wmf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

### Scomm: HwTrq_Scom_ReadHwTrqTrim

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

None

#### Read Handwheel Torque Trim Service

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image18.wmf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

### Scomm: HwTrq_Scom_SetHwTrqScale

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

None

#### Set Handwheel Torque Scale Service

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image19.wmf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

### Scomm: HwTrq_Scom_SetHwTrqTrim

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

 Rte_Read_T1ADC_Volt_f32(&Torque1_Volt_T_f32)

Rte_Read_T2ADC_Volt_f32(&Torque2_Volt_T_f32)

Rte_Read_MECCounter_Cnt_enum(&MECCounter_Cnt_T_enum)

#### Set Handwheel Torque Trim Service

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image20.wmf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

### Manual Set Hand wheel Torque Trim

#### Description

# ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image21.wmf)  [section]

### Scomm: HwTrq_SCom_ReadEOLTrqStep 

|                      |                    |                                     |     |     |          |
|----------|---------------------|---------------------|------|------|---------|
|                      |                    | Type                                | Min | Max | UTP Tol. |
| **Arguments Passed** | TrqStep_HwNm_T_f32 | float \* (array of 10 float values) | -10 | 10  |          |
| **Return Value**     | None               |                                     |     |     |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image22.wmf)

### Scomm: HwTrq_SCom_SetEOLTrqStep

|                      |                    |                                     |     |     |          |
|----------|---------------------|---------------------|------|------|---------|
|                      |                    | Type                                | Min | Max | UTP Tol. |
| **Arguments Passed** | TrqStep_HwNm_T_f32 | float \* (array of 10 float values) | -10 | 10  |          |
| **Return Value**     | None               |                                     |     |     |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image23.wmf)

## Local Function/Macro Definitions

If these are numerous and defined in a separate source file then
reference the source file only.

### Is Torque Scale In Range Check

|                      |                          |                                 |     |      |          |
|-------------|-----------------------------|--------|--------|--------|--------|
| **Function Name**    | IsTrqScaleInRng_lgc      | Type                            | Min | Max  | UTP Tol. |
| **Arguments Passed** | TrqScale_VoltspDeg_T_f32 | Single Precision Floating Point | 0   | FULL |          |
| **Return Value**     | TrqSclInRng_Cnt_T_lgc    | BOOLEAN                         | N/A | N/A  |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image24.wmf)

### Torque Trim Performance Diagnostic

|                      |                       |               |     |     |          |
|-------------|----------------------------|-----------|--------|--------|--------|
| **Function Name**    | TrqTrimPerfDiag       | Type          | Min | Max | UTP Tol. |
| **Arguments Passed** | MECCounter_Cnt_T_enum | ManufModeType | N/A | N/A |          |
| **Return Value**     | None                  |               |     |     |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image25.wmf)

# Execution Requirements

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

|               |                        |                             |
|---------------|------------------------|-----------------------------|
| Function Name | Calling Frequency      | System State(s)             |
| HwTrq_Init    | Once at Initialization | STARTUP                     |
| HwTrq_Per1    | 2ms                    | WARM INIT, OPERATE, DISABLE |
| HwTrq_Per2    | 4ms                    | WARM INIT, OPERATE, DISABLE |
| HwTrq_Per3    | 100ms                  | WARM INIT, OPERATE, DISABLE |

## Execution Requirements for Serial Communication Functions 

|                               |                                                   |
|------------------------------|------------------------------------------|
| Function Name                 | Sub-Module called by (Serial Comm Function Name)  |
| HwTrq_Scom_ClrHwTrqScale()    | EPSInternalPIDWrite(),EPSInternalRoutineControl() |
| HwTrq_Scom_ClrHwTrqTrim()     | EPSInternalRoutineControl()                       |
| HwTrq_Scom_ReadHwTrqScale()   | EPSInternalPIDRead()                              |
| HwTrq_Scom_ReadHwTrqTrim()    | EPSInternalPIDRead()                              |
| HwTrq_Scom_SetHwTrqScale()    | EPSInternalPIDWrite()                             |
| HwTrq_Scom_SetHwTrqTrim()     | EPSInternalRoutineControl()                       |
| HwTrq_SCom_ManualSetHwTrqTrim |                                                   |
| HwTrq_SCom_ReadEOLTrqStep     |                                                   |
| HwTrq_SCom_SetEOLTrqStep      |                                                   |

#   [section-1]

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

|                               |                        |
|-------------------------------|------------------------|
| Name of Sub Module            | Software Segment       |
| HwTrq_Init()                  | RTE_SA_HWTRQ_APPL_CODE |
| HwTrq_Per1()                  | RTE_SA_HWTRQ_APPL_CODE |
| HwTrq_Per2()                  | RTE_SA_HWTRQ_APPL_CODE |
| HwTrq_Per3()                  | RTE_SA_HWTRQ_APPL_CODE |
| HwTrq_Scom_ClrHwTrqScale()    | RTE_SA_HWTRQ_APPL_CODE |
| HwTrq_Scom_ClrHwTrqTrim()     | RTE_SA_HWTRQ_APPL_CODE |
| HwTrq_Scom_ReadHwTrqScale()   | RTE_SA_HWTRQ_APPL_CODE |
| HwTrq_Scom_ReadHwTrqTrim()    | RTE_SA_HWTRQ_APPL_CODE |
| HwTrq_Scom_SetHwTrqScale()    | RTE_SA_HWTRQ_APPL_CODE |
| HwTrq_Scom_SetHwTrqTrim()     | RTE_SA_HWTRQ_APPL_CODE |
| HwTrq_Scom_ManualSetHwTrqTrim | RTE_SA_HWTRQ_APPL_CODE |
| HwTrq_SCom_ReadEOLTrqStep     | RTE_SA_HWTRQ_APPL_CODE |
| HwTrq_SCom_SetEOLTrqStep      | RTE_SA_HWTRQ_APPL_CODE |

## Local Functions

This table identifies the software segments for local functions
identified in this module.

|                       |                        |
|-----------------------|------------------------|
| Name of Sub Module    | Software Segment       |
| IsTrqScaleInRng_lgc() | RTE_SA_HWTRQ_APPL_CODE |
| TrqTrimPerfDiag()     | RTE_SA_HWTRQ_APPL_CODE |

#   [section-2]

# Known Issues / Limitations With Design

# INLINE functions defined in globalmacro.h are not unit tested 

# Revision Control Log

<table>
<colgroup>
<col style="width: 7%" />
<col style="width: 68%" />
<col style="width: 11%" />
<col style="width: 12%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Rev #</strong></td>
<td><strong>Change Description</strong></td>
<td><strong>Date</strong></td>
<td><strong>Author Initials</strong></td>
</tr>
<tr class="even">
<td>1.0</td>
<td>Initial AutoSAR Release.</td>
<td>04FEB11</td>
<td>L.N.</td>
</tr>
<tr class="odd">
<td>2.0</td>
<td>Rte_Call_CorrDiagFiltSV_SetRamBlockStatus() added in Init() and
Cross Check Diag Support Added</td>
<td>03May11</td>
<td>N.R.A.R</td>
</tr>
<tr class="even">
<td>3.0</td>
<td>Updated for anomaly 3258</td>
<td>17JUN11</td>
<td>LWW</td>
</tr>
<tr class="odd">
<td>4.0</td>
<td>Removed Cross Check Diag Support</td>
<td>20JUL11</td>
<td>LWW</td>
</tr>
<tr class="even">
<td>5.0</td>
<td>Changes as per FDD #04 rev008</td>
<td>22Nov11</td>
<td>VK</td>
</tr>
<tr class="odd">
<td>5.1</td>
<td>Changes to Scom functions passing a null pointer instead of Boolean
flag for the writeblock Rte call. Changed SumFltOut_Volt_M_u5p11 and
SSDiagFiltOut_Volt_M_s4p11 to display variables</td>
<td>2Dec11</td>
<td>VK</td>
</tr>
<tr class="even">
<td>6</td>
<td><p>Per3 trigger rate moved to 100ms from 128ms</p>
<p>Removed residual periodic specifiations</p></td>
<td>5Dec11</td>
<td>JJW</td>
</tr>
<tr class="odd">
<td>7</td>
<td>Corrected GetNTCFailed RTE call arguments in Per1</td>
<td>5Dec11</td>
<td>VK</td>
</tr>
<tr class="even">
<td>8</td>
<td>Changed HwTrqScaleStatus, HwTrqTrimStatus to boolean</td>
<td>13Dec11</td>
<td>VK</td>
</tr>
<tr class="odd">
<td>9</td>
<td>Matched the names of the elements in HwTrqScale_Datatype and
HwTrqTrim_Datatype as in digital hw torque</td>
<td>14Dec11</td>
<td>VK</td>
</tr>
<tr class="even">
<td>10</td>
<td>Corrected Rte read for MEC</td>
<td>14Dec11</td>
<td>VK</td>
</tr>
<tr class="odd">
<td>11</td>
<td>Updated Argument to Set Scale function to match DigHwTrq</td>
<td>15Dec11</td>
<td>OT</td>
</tr>
<tr class="even">
<td>12</td>
<td>Fixed scale validity check logic</td>
<td>16Dec11</td>
<td>OT</td>
</tr>
<tr class="odd">
<td>13</td>
<td>Fixed NTC_STATUS_PASSED path anomaly, added error accumulator
macros</td>
<td>1Feb12</td>
<td>OT</td>
</tr>
<tr class="even">
<td>14</td>
<td>Fixed previous NTC_STATUS_PASSED anomaly fix, changed diff torque
limit</td>
<td>5Mar12</td>
<td>OT</td>
</tr>
<tr class="odd">
<td>15</td>
<td>Added manual write scom function for torque trim block, removed
MEC</td>
<td>20 Apr 12</td>
<td>VK</td>
</tr>
<tr class="even">
<td>16</td>
<td>Updated NTC's NTC_Num_TrqSensorScaleInvalid and
NTC_Num_EEPROMDiagTrqSnrStr with NTC_Num_PriSnsrTrqStorFlt and logic to
clear the fault</td>
<td>21-Apr-12</td>
<td>VK</td>
</tr>
<tr class="odd">
<td>17</td>
<td>Changes to HwTrq_SCom_ManualSetHwTrqTrim to match the name of the
argument being passed. Changes to Per1 updating
DiagTrqTrimInvalid_Cnt_T_lgc</td>
<td>23-Apr-12</td>
<td>VK</td>
</tr>
<tr class="even">
<td>18</td>
<td>Removal of polarity input (not called out in FDD)</td>
<td>27-Apr-12</td>
<td>LWW</td>
</tr>
<tr class="odd">
<td>19</td>
<td>Updated to FDD 04A v005</td>
<td>06-Jun-12</td>
<td>OT</td>
</tr>
<tr class="even">
<td>20</td>
<td>Updated to FDD 04A v006</td>
<td>14-Jun-12</td>
<td>JWJ</td>
</tr>
<tr class="odd">
<td>21</td>
<td>Removed double de-reference from EOLTrqStepData pointers in Per1 and
Scom functions.</td>
<td>17-Jun-12</td>
<td>KJS</td>
</tr>
<tr class="even">
<td>22</td>
<td>Brought in Nexteer MEC Counter</td>
<td>23-Aug-12</td>
<td>VK</td>
</tr>
<tr class="odd">
<td>23</td>
<td>Added double de-reference to EOLTrqStepData pointers in Per1 and
Scom functions.</td>
<td>04-Sep-12</td>
<td>VK</td>
</tr>
<tr class="even">
<td>24</td>
<td>MDD, Src mismatch corrections</td>
<td>10-Sep-12</td>
<td>VK</td>
</tr>
<tr class="odd">
<td>25</td>
<td>Added checkpoints and memmap software segment is updated for static
variables</td>
<td>27-Sep-12</td>
<td>Selva</td>
</tr>
<tr class="even">
<td>26</td>
<td>Implemented FDD 04A v007</td>
<td>12-Oct-12</td>
<td>OT</td>
</tr>
<tr class="odd">
<td>27</td>
<td>Anomaly 2824 – T1 vs T2 comparison cal usage</td>
<td>24-Oct-12</td>
<td>OT</td>
</tr>
<tr class="even">
<td>27.1.1</td>
<td>Anomaly 4683 Correction</td>
<td>25-Mar-13</td>
<td>LWW</td>
</tr>
</tbody>
</table>

{% endraw %}