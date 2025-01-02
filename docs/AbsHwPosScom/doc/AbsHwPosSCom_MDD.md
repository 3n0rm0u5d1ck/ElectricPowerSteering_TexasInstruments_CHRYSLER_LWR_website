---
layout: default
title: AbsHwPosSCom_MDD
nav_order: 1
parent: Absolute Handwheel Position Serial Com
---
{% raw %}
# Module -- AbsHwPosScom  [module----abshwposscom]

This module determines the handwheel position representing the angle of
the output shaft without using a physical column position sensor.

The function uses the Motor Position to provide an estimate of the
handwheel position. In addition this function also uses the absolute hw
position transmitted on the serial communication interface to provide
and estimate of the HwPos. value.

# High-Level Description

(Description must be within 8-10 lines.)

# Figures

## Diagram – Function Data Sharing

### Diagram – Function (Name)

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be
shown here)

| Module Inputs                  | Module Outputs |                        |
|--------------------------------|----------------|------------------------|
| CRFCumMtrPos_Deg_f32           |                | HwPosAuthority_Uls_f32 |
| CRFMtrTrqCmd_MtrNm_f32         |                | HwPos_HwDeg_f32        |
| CRFMtrVel_MtrRadpS_f32         |                |                        |
| DiagStsHwPosDis_Cnt_lgc        |                |                        |
| HwTrq_HwNm_f32                 |                |                        |
| SComInpHwAValid_Cnt_lgc        |                |                        |
| SComInpHwA_HwDeg_f32           |                |                        |
| VehicleSpeedValid_Cnt_lgc      |                |                        |
| VehicleSpeed_Kph_f32           |                |                        |
| KinIntDiagSrlComSvcDft_Cnt_lgc |                |                        |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table>
<colgroup>
<col style="width: 34%" />
<col style="width: 13%" />
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
<td>HwPFilter1En_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>HwPFilter2En_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>VehDynTrgtAngle_HwDeg_M_f32</td>
<td>Single precision floating point</td>
<td>-1575164.8</td>
<td>1575164.8</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>VehDynTrgtAuth_Uls_M_f32</td>
<td>Single precision floating point</td>
<td>0</td>
<td>1</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>HwPHighSpdAC_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>PinTrqFiltSV_HwNm_M_Str</td>
<td>N/A</td>
<td>N/A</td>
<td>N/A</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_UNPECIFIED</td>
</tr>
<tr class="odd">
<td>PinTrqFiltSV_HwNm_M_Str .K_Uls_f32</td>
<td>Single precision floating point</td>
<td>8.04215E-05</td>
<td>0.039414597</td>
<td></td>
</tr>
<tr class="even">
<td>PinTrqFiltSV_HwNm_M_Str.SV_Uls_f32</td>
<td>Single precision floating point</td>
<td>-318</td>
<td>318</td>
<td></td>
</tr>
<tr class="odd">
<td>HwPMtrVelT1Cal_MtrRadpS_M_f32</td>
<td>Single precision floating point</td>
<td>0</td>
<td>700</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>HwPVSpdT1Cal_Kph_M_f32</td>
<td>Single precision floating point</td>
<td>0</td>
<td>255</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>HwPPinTrqT1Cal_HwNm_M_f32</td>
<td>Single precision floating point</td>
<td>0</td>
<td>10</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>HwPTimer1Max_ms_M_u16</td>
<td>1</td>
<td>0</td>
<td>60000</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>HwPWindowCal_HwDeg_M_f32</td>
<td>Single precision floating point</td>
<td>0</td>
<td>100</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>HwPFilter1Kn_Hz_M_f32</td>
<td>Single precision floating point</td>
<td>0.0002</td>
<td>0.1</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>HwPFilter2Kn_Hz_M_f32</td>
<td>Single precision floating point</td>
<td>0.0002</td>
<td>0.1</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>AutoCntrTrgtAuth_Uls_M_f32</td>
<td>Single precision floating point</td>
<td>0</td>
<td>1</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>HwPTimer2Max_ms_M_u16</td>
<td>1</td>
<td>0</td>
<td>60000</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>HwPAutoCenter_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>HwPFilter1Init_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>HwPFilter2Init_Cnt_M_lgc</td>
<td>BOOLEAN</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>HwPFilter1Prev_HwDeg_M_f32</td>
<td>Single Precision Floating point</td>
<td>-787558.4</td>
<td>787606.4</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>HwPFilter1Out_HwDeg_M_f32</td>
<td>Single Precision Floating point</td>
<td>-787558.4</td>
<td>787606.4</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>HwPFilter1SV_HwDeg_M_Str</td>
<td>N/A</td>
<td>N/A</td>
<td>N/A</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_UNPECIFIED</td>
</tr>
<tr class="even">
<td>HwPFilter1SV_HwDeg_M_Str.K_Uls_f32</td>
<td>Single Precision Floating point</td>
<td>8.04215E-05</td>
<td>0.039414597</td>
<td></td>
</tr>
<tr class="odd">
<td>HwPFilter1SV_HwDeg_M_Str.SV_Uls_f32</td>
<td>Single Precision Floating point</td>
<td>-787558.4</td>
<td>787606.4</td>
<td></td>
</tr>
<tr class="even">
<td>HwPFilter2Out_HwDeg_M_f32</td>
<td>Single Precision Floating point</td>
<td>-787558.4</td>
<td>787606.4</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>HwPFilter2SV_HwDeg_M_Str</td>
<td>N/A</td>
<td>N/A</td>
<td>N/A</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_UNPECIFIED</td>
</tr>
<tr class="even">
<td>HwPFilter2SV_HwDeg_M_Str .K_Uls_f32</td>
<td>Single Precision Floating point</td>
<td>8.04215E-05</td>
<td>0.039414597</td>
<td></td>
</tr>
<tr class="odd">
<td>HwPFilter2SV_HwDeg_M_Str *SV_Uls_f32</td>
<td>Single Precision Floating point</td>
<td>-787558.4</td>
<td>787606.4</td>
<td></td>
</tr>
<tr class="even">
<td>HwPTimer1_ms_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>HwPTimer2_ms_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>HwPTimer4_ms_M_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>ScaledMtrPos_HwDeg_M_f32</td>
<td>Float32</td>
<td>-787558.4</td>
<td>787606.4</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>MtrComplErr_HwDeg_M_f32</td>
<td>Float32</td>
<td>-1126.4</td>
<td>1126.4</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>TempHwPos_HwDeg_M_f32</td>
<td>Float32</td>
<td>-1575164.8</td>
<td>1575164.8</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>RelHwPos_HwDeg_M_f32</td>
<td>Float32</td>
<td>-787558.4</td>
<td>787606.4</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>FiltPinionTrq_HwNm_M_f32</td>
<td>single precision floating point</td>
<td>-318</td>
<td>318</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>FinHwPosLPFOp_HwDeg_M_f32</td>
<td>single precision floating point</td>
<td>-1620</td>
<td>1620</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>FinHwAuth_Uls_M_f32</td>
<td>single precision floating point</td>
<td>0</td>
<td>1</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>FinHwPosFiltSV_HwDeg_M_Str</td>
<td>N/A</td>
<td>N/A</td>
<td>N/A</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_UNPECIFIED</td>
</tr>
<tr class="even">
<td>FinHwPosFiltSV_HwDeg_M_Str.K_Uls_f32</td>
<td>single precision floating point</td>
<td>0</td>
<td>0.999984637</td>
<td></td>
</tr>
<tr class="odd">
<td>FinHwPosFiltSV_HwDeg_M_Str.SV_Uls_f32</td>
<td>single precision floating point</td>
<td>-1575164.8</td>
<td>1575164.8</td>
<td></td>
</tr>
<tr class="even">
<td>RelToSComOffset_HwDeg_M_f32</td>
<td>Float32</td>
<td>-789654</td>
<td>789606.3</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>StabilitySyncTimer_mS_M_u32</td>
<td>UINT32</td>
<td>FULL</td>
<td>FULL</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>NewScomInpHwA_HwDeg_M_f32</td>
<td>Single precison floating point</td>
<td>-1578812.8</td>
<td>1578812.738</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>ScomHwPosAuth_Uls_M_f32</td>
<td>Single precison floating point</td>
<td>0</td>
<td>1</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>VdynToScomErrorThy_HwDeg_M_f32</td>
<td>Single precison floating point</td>
<td>-1600</td>
<td>1600</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_SAVED_ZONEH_32</td>
</tr>
<tr class="odd">
<td>HwPosSrvSetToZero_Cnt_M_lgc</td>
<td>n/a</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>RelToScomOfstFound_Cnt_M_lgc</td>
<td>n/a</td>
<td>FALSE</td>
<td>TRUE</td>
<td>ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN</td>
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
<td><p>(Name given for the user defined typdef of type struct/union)</p>
<p>(Variable name qualified similar to all other variables)</p></td>
<td>(Variable name qualified similar to all other variables)</td>
<td>as other variables</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>(Variable name qualified similar to all other variables)</td>
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
<td>k_AutoCtrMtrVelT1L_MtrRadpS_f32</td>
</tr>
<tr class="even">
<td><p>k_AutoCtrVehSpdT1L_Kph_f32</p>
<p>k_AutoCtrPinTrqT1L_HwNm_f32</p>
<p>k_HwPTimer1MaxL_ms_u16</p>
<p>k_AutoCtrWindowL_HwDeg_f32</p>
<p>k_AutoCtrFiltOneCoeffkL_Hz_f32</p>
<p>k_AutoCtrFiltTwoCoeffkL_Hz_f32</p>
<p>k_VDAuthL_Uls_f32</p>
<p>k_AutoCtrTimer2LSpd_ms_u16</p>
<p>k_InvGearRatio_Uls_f32</p>
<p>k_AutoCtrPinTrqLPFCoeffK_Hz_f32</p>
<p>k_MtrVelTmr4H_MtrRadpS_f32</p>
<p>k_VehSpdTmr4H_kph_f32</p>
<p>k_PinTrqTmr4H_HwNm_f32</p>
<p>k_Tmr4CntrWindowH_HwDeg_f32</p>
<p>k_AutoCtrTimer4H_ms_u16</p>
<p>k_HwPMtrVelT1H_MtrRadpS_f32</p>
<p>k_HwPVehSpdT1H_Kph_f32</p>
<p>k_HwPPinionTrqT1H_HwNm_f32</p>
<p>k_HwPTimer1MaxH_ms_u16</p>
<p>k_HwPWindowCalH_HwDeg_f32</p>
<p>k_HwPFilter1KnH_Hz_f32</p>
<p>k_HwPFilter2KnH_Hz_f32</p>
<p>k_HiSpdAcAuth_Uls_f32</p>
<p>k_HwPTmr2MaxHiSpd_ms_u16</p>
<p>t_MtrPosComplTblX_MtrNm_u8p8[6]</p>
<p>t_MtrPosComplTblY_HwDegpMtrNm_u6p10[6]</p>
<p>k_RbstPosLPFKn_Hz_f32</p>
<p>k_KinmIntDiagMaxRackLmt_HwDeg_f32</p>
<p>k_HwPosOpLPFError_HwDeg_f32</p>
<p>k_HwPosAuthorityStep_Uls_f32</p></td>
</tr>
<tr class="odd">
<td>k_ScomHwPosAuth_Uls_f32</td>
</tr>
<tr class="even">
<td>k_HwPosVehStabilityTime_mS_u16</td>
</tr>
<tr class="odd">
<td>k_HwPosVehStabilityTrqCmd_MtrNm_f32</td>
</tr>
<tr class="even">
<td>k_HwPosVehStabilityHwTrq_HwNm_f32</td>
</tr>
<tr class="odd">
<td>k_HwPosVehStabilityMtrVel_MtrRadpS_f32</td>
</tr>
<tr class="even">
<td>k_VdynToScomMaxErr_HwDeg_f32</td>
</tr>
</tbody>
</table>

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name           | Resolution                      | Units | Value |
|-------------------------|---------------------------------|-------|-------|
| D_ABSPOSLOLMT_HWDEG_F32 | Single precision floating point | HWDEG | -1620 |
| D_ABSPOSHILMT_HWDEG_F32 | Single precision floating point | HWDEG | 1620  |
| D_10MS_SEC_F32          | Single precision floating point | SEC   | 0.010 |

####  [section]

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name |
|---------------|
| D_2MS_SEC_F32 |
| D_ONE_ULS_F32 |

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

1.  FPM_FloatToFixed_m

2.  LPF_SvUpdate_s16InFixKTrunc_m

3.  LPF_OpUpdate_s16InFixKTrunc_m

4.  Limit_m

5.  FPM_FixedToFloat_m

6.  Min_m

7.  Max_m

8.  LPF_SvInit_s16InFixKTrunc_m

## Data Hiding Functions

1.  Rte_Call_NxtrDiagMgr_SetNTCStatus

## Global Functions/Macros Defined by this Module

### Global Function \#1

| **Function Name**    | (Exact name used)                                  | Type | Min | Max |
|---------------|--------------------------------|---------|---------|---------|
| **Arguments Passed** | (if none, write None)                              |      |     |     |
|                      | (Insert more rows for additional passed arguments) |      |     |     |
| **Return Value**     | (if no value returned, write N/A)                  |      |     |     |

#### Description

(Place flowchart/design for local function)

## Local Functions/Macros Used by this MDD only

##  [section-1]

### Local Function \#1

| **Function Name**    | HwPosSLFilter1                    | Type    | Min       | Max      |
|---------------|--------------------------------|---------|---------|---------|
| **Arguments Passed** | MtrPos_HwDeg_T_f32                | float32 | -787558.4 | 787606.4 |
|                      | FilterEn                          | boolean | FALSE     | TRUE     |
| **Return Value**     | (if no value returned, write N/A) |         |           |          |

#### Description

(Place flowchart/design for local
function)![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image1.emf)

### Local Function \#2

| **Function Name**    | HwPosSLFilter2                    | Type    | Min       | Max      |
|--------------|--------------------------------|----------|---------|---------|
| **Arguments Passed** | MtrPos_HwDeg_T_f32                | float32 | -787558.4 | 787606.4 |
|                      | FilterEn                          | boolean | FALSE     | TRUE     |
| **Return Value**     | (if no value returned, write N/A) |         |           |          |

#### Description

(Place flowchart/design for local function)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image2.emf)

### Local Function \#3

| **Function Name**    | Filter1Enable            | Type    | Min   | Max  |
|----------------------|--------------------------|---------|-------|------|
| **Arguments Passed** | CRFMtrVel_MtrRadpS_T_f32 | float32 | -1118 | 1118 |
|                      | VehSpd_Kph_T_f32         | float32 | 0     | 512  |
|                      | VSpdValid \_Cnt_T_lgc    | boolean | FALSE | TRUE |
|                      | PinionTrq_HwNm_T_f32     | float32 | -318  | 318  |
| **Return Value**     | HwPFilter1En_Cnt_T_lgc   | boolean | FALSE | TRUE |

#### Description

(Place flowchart/design for local function)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image3.emf)

### Local Function \#4

| **Function Name**    | Filter2Enable          | Type    | Min       | Max      |
|----------------------|------------------------|---------|-----------|----------|
| **Arguments Passed** | MtrPos_HwDeg_T_f32     | float32 | -787558.4 | 787606.4 |
|                      | HwPFilter1En_Cnt_T_lgc | boolean | FALSE     | TRUE     |
| **Return Value**     | HwPFilter2En_Cnt_T_lgc | boolean | FALSE     | TRUE     |

#### Description

(Place flowchart/design for local function)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image4.emf)

### Local Function \#5

| **Function Name**    | CalSwitchTimer           | Type    | Min   | Max  |
|----------------------|--------------------------|---------|-------|------|
| **Arguments Passed** | CRFMtrVel_MtrRadpS_T_f32 | float32 | -1118 | 1118 |
|                      | VehSpd_Kph_T_f32         | float32 | 0     | 512  |
|                      | VSpdValid \_Cnt_T_lgc    | boolean | FALSE | TRUE |
|                      | PinionTrq_HwNm_T_f32     | float32 | -318  | 318  |
|                      | HwPFilter1En_Cnt_T_lgc   | boolean | FALSE | TRUE |
|                      | HwPFilter2En_Cnt_T_lgc   | boolean | FALSE | TRUE |
| **Return Value**     | None                     |         |       |      |

#### Description

(Place flowchart/design for local function)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image5.emf)

### Local Function \#6

| **Function Name**    | ScomHwPosAuth | Type | Min | Max |
|----------------------|---------------|------|-----|-----|
| **Arguments Passed** | None          |      |     |     |
| **Return Value**     | None          |      |     |     |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image6.emf)

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data                           | Value |
|--------------------------------|-------|
| CRFCumMtrPos_Deg_f32           | 0     |
| CRFMtrTrqCmd_MtrNm_f32         | 0     |
| CRFMtrVel_MtrRadpS_f32         | 0     |
| DiagStsHwPosDis_Cnt_lgc        | FALSE |
| HwTrq_HwNm_f32                 | 0     |
| SComInpHwAValid_Cnt_lgc        | FALSE |
| SComInpHwA_HwDeg_f32           | 0     |
| VehicleSpeedValid_Cnt_lgc      | FALSE |
| VehicleSpeed_Kph_f32           | 0     |
| KinIntDiagSrlComSvcDft_Cnt_lgc | FALSE |
| HwPosAuthority_Uls_f32         | 0     |
| HwPos_HwDeg_f32                | 0     |

## Initialization Functions

(Note: For multiple init functions, insert new headers at the “Header 2”
level – subset of “5.1 Initialization Functions” and follow the same
sub-section design shown below)

### Init: AbsHwPosScom_Init1

### Design Rationale

(Add design rationale specifically related to this FUNCTION. If none
required, place the text “None”)

#### Module Outputs

(Initialize all module outputs in this section)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image7.emf)

##  Periodic Functions

### Per: AbsHwPosScom_Per1

#### Design Rationale

#### Program Flow Start

####  Rte_Call_AbsHwPosScom_Per1_CP0_CheckpointReached()Store Module Inputs to Local copies

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image8.emf)

####  Processing

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image9.emf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image10.emf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image11.emf)

#### Store Local copy of outputs into Module Outputs

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image12.emf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image13.emf)

#### Program Flow End

Rte_Call_AbsHwPosScom_Per1_CP1_CheckpointReached()

### Per: \_Per2

#### Design Rationale

(Add design rationale specifically related to this FUNCTION. If none
required, place the text “None”)

#### Program Flow Start

#### Rte_Call_AbsHwPosScom_Per2_CP0_CheckpointReached()Store Module Inputs to Local copies

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image14.emf)

#### Program Flow End

Rte_Call_AbsHwPosScom_Per2_CP1_CheckpointReached()

### Per: \_Per3

#### Design Rationale

(Add design rationale specifically related to this FUNCTION. If none
required, place the text “None”)

#### Program Flow Start

#### Rte_Call_AbsHwPosScom_Per3_CP0_CheckpointReached()Store Module Inputs to Local copies

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/AbsHwPosScom/doc/mediax/media/image15.emf)

#### Program Flow End

Rte_Call_AbsHwPosScom_Per3_CP1_CheckpointReached()

##  Fault Recovery Functions

## Shutdown Functions

## Interrupt Functions

## Serial Communication Functions

### AbsHwPosScom_Scom_HwPosSrvSetToZero

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 60%" />
<col style="width: 9%" />
<col style="width: 7%" />
<col style="width: 7%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Function Name</strong></th>
<th><h3 id="abshwposscom_scom_hwpossrvsettozero-1"
class="unnumbered">AbsHwPosScom_Scom_HwPosSrvSetToZero</h3></th>
<th>Type</th>
<th>Min</th>
<th>Max</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Arguments Passed</strong></td>
<td>Par</td>
<td>Boolean</td>
<td>False</td>
<td>True</td>
</tr>
<tr class="even">
<td><strong>Return Value</strong></td>
<td>None</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

#### Design Rationale

#### Program Flow Start

#### Store Module Inputs to Local copies

N/A

#### Processing

HwPosSrvSetToZero_Cnt_M_lgc = Par

#### Store Local Copy Of Outputs into Module Outputs

N/A

#### Program Flow End

N/A

### AbsHwPosScom_Scom_HwPosSrvRead

<table>
<colgroup>
<col style="width: 19%" />
<col style="width: 46%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Function Name</strong></th>
<th><h3 id="abshwposscom_scom_-hwpossrvread"
class="unnumbered">AbsHwPosScom_Scom_ HwPosSrvRead</h3></th>
<th>Type</th>
<th>Min</th>
<th>Max</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Arguments Passed</strong></td>
<td>Par</td>
<td>Ptr to Boolean</td>
<td>False</td>
<td>True</td>
</tr>
<tr class="even">
<td><strong>Return Value</strong></td>
<td>None</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

#### Design Rationale

#### Program Flow Start

#### Store Module Inputs to Local copies

N/A

#### Processing

\*Par = HwPosSrvSetToZero_Cnt_M_lgc

#### Store Local Copy Of Outputs into Module Outputs

N/A

#### Program Flow End

N/A

# Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the
different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name      | Calling Frequency | System State(s) in which the function is called |
|--------------------------|-----------------|------------------------------|
| AbsHwPosScom_Init1 | Once at startup   | ColdInit                                        |
| AbsHwPosScom_Per1  | 2ms               | All states except ColdInit                      |
| AbsHwPosScom_Per2  | 10ms              | All states except Cold Init                     |
| AbsHwPosScom_Per3  | 10ms              | All states except Cold Init                     |

## Execution Requirements for Serial Communication Functions 

| Function Name                       | Sub-Module called by (Serial Comm Function Name) |
|-----------------------------|-------------------------------------------|
| AbsHwPosScom_Scom_HwPosSrvRead      |                                                  |
| AbsHwPosScom_Scom_HwPosSrvSetToZero |                                                  |

#  [section-2]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module | Software Segment              |
|--------------------|-------------------------------|
| AbsHwPosScom_Init1 | RTE_AP_ABSHWPOSSCOM_APPL_CODE |
| AbsHwPosScom_Per1  | RTE_AP_ABSHWPOSSCOM_APPL_CODE |
| AbsHwPosScom_Per2  | RTE_AP_ABSHWPOSSCOM_APPL_CODE |
| AbsHwPosScom_Per3  | RTE_AP_ABSHWPOSSCOM_APPL_CODE |

##  [section-3]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module | Software Segment       |
|--------------------|------------------------|
| HwPosSLFilter1     | AP\_ ABSHWPOSSCOM_CODE |
| HwPosSLFilter2     | AP\_ ABSHWPOSSCOM_CODE |
| Filter1Enable      | AP\_ ABSHWPOSSCOM_CODE |
| Filter2Enable      | AP\_ ABSHWPOSSCOM_CODE |
| CalSwitchTimer     | AP\_ ABSHWPOSSCOM_CODE |

#  [section-4]

#  Known Issues / Limitations With Design

# Note1: Deviation from FDD: Cal k_MtrToHw_Res_Conversion is not used for Scaled_MtrPos calculations in this software. Refer FDD- 05D section 5.1.2.2.(This cal was for a fixedtype implementation). Revision Control Log [note1-deviation-from-fdd-cal-k_mtrtohw_res_conversion-is-not-used-for-scaled_mtrpos-calculations-in-this-software.-refer-fdd--05d-section-5.1.2.2.this-cal-was-for-a-fixedtype-implementation.-revision-control-log]

<table style="width:100%;">
<colgroup>
<col style="width: 6%" />
<col style="width: 6%" />
<col style="width: 64%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Item #</strong></th>
<th><strong>Rev #</strong></th>
<th><strong>Change Description</strong></th>
<th><strong>Date</strong></th>
<th><strong>Author Initials</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>1.0</td>
<td>Initial AutoSAR Release</td>
<td>24-April-12</td>
<td>NRAR</td>
</tr>
<tr class="even">
<td>2</td>
<td>2.0</td>
<td>Text format changes</td>
<td>25-April-12</td>
<td>NRAR</td>
</tr>
<tr class="odd">
<td>3</td>
<td>3.0</td>
<td>HandWheelPosition range is changed from +/-1440.11 to
+/-1620HwDeg</td>
<td>26-April-12</td>
<td>NRAR</td>
</tr>
<tr class="even">
<td>4</td>
<td>4.0</td>
<td>Anom 3257 Fix</td>
<td>4-May-12</td>
<td>NRAR</td>
</tr>
<tr class="odd">
<td>5</td>
<td>5.0</td>
<td>FDD 5D updates as per Ver002</td>
<td>27-June-12</td>
<td>NRAR</td>
</tr>
<tr class="even">
<td>6</td>
<td>6.0</td>
<td>FDD 5D updates as per ver 003,Ver002 and Anom 3382 is ignored as now
s/w is implemented in floating type.</td>
<td>05-July-12</td>
<td>NRAR</td>
</tr>
<tr class="odd">
<td>6</td>
<td>6</td>
<td><ol type="1">
<li><p>Version of thisMDD is still lshown as 6 to match up with Synergy
version</p></li>
<li><p>In per1, Typo fix for global inputs</p></li>
</ol></td>
<td>19-July-12</td>
<td>NRAR</td>
</tr>
<tr class="even">
<td>7</td>
<td>7.0</td>
<td>FDD 5D updates per Ver006</td>
<td>10-Aug-12</td>
<td>BWL</td>
</tr>
<tr class="odd">
<td>8</td>
<td>8.0</td>
<td>Update per UTP review.</td>
<td>5-Sept-12</td>
<td>BWL</td>
</tr>
<tr class="even">
<td>9</td>
<td>9.0</td>
<td>Added checkpoints and memmap software segment is updated for static
variables</td>
<td>26-Sep-12</td>
<td>Selva</td>
</tr>
<tr class="odd">
<td>10</td>
<td>10.0</td>
<td>Changed trigger rates for Per2 and Per3 to conform to new
standard</td>
<td>24-Oct-12</td>
<td>BWL</td>
</tr>
</tbody>
</table>

{% endraw %}