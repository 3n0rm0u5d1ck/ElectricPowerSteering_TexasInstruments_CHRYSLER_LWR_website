---
layout: default
title: Motor_Position_2_MDD
nav_order: 2
parent: Motor Position
---
{% raw %}
# Module –  [module]

# High-Level Description

This module implements the learning and diagnostic portions of MtrPos,
as well as part of the motor position determination sub function.

# Figures

## Component Diagram

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image1.emf"
style="width:3.16929in;height:3.16929in" alt="mtrpos2.emf" />

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs            | Module Outputs |                             |
|--------------------------|----------------|-----------------------------|
| MotorVelMRF_MtrRadpS_f32 |                | CorrectedMtrPos_Rev_f32     |
|                          |                | CosTheta1_Volt_f32          |
|                          |                | MechMtrPos_Rev_f32          |
|                          |                | SinTheta1_Volt_f32          |
|                          |                | SysCCorrectedMtrPos_Rev_f32 |
|                          |                | SysCMechMtrPos_Rev_f32      |
|                          |                |                             |
|                          |                |                             |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table>
<colgroup>
<col style="width: 32%" />
<col style="width: 15%" />
<col style="width: 13%" />
<col style="width: 12%" />
<col style="width: 27%" />
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
<td>MtrPos2_ValidityFltAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>65535</td>
<td>MTRPOS2_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>MtrPos2_CorrFltAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>65535</td>
<td>MTRPOS2_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>MtrPos2_PrevCorrectedMtrPos_Rev_M_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>0.99998</td>
<td>MTRPOS2_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>MtrPos2_PrevSin1RTOffset_Volts_M_f32</td>
<td>Single Precision Float</td>
<td>1.7</td>
<td>3.8</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>MtrPos2_PrevCos1RTOffset_Volts_M_f32</td>
<td>Single Precision Float</td>
<td>1.7</td>
<td>3.8</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>MtrPos2_Sin1OffsetCorr_Volts_M_f32</td>
<td>Single Precision Float</td>
<td>-0.5</td>
<td>0.5</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>MtrPos2_Cos1OffsetCorr_Volts_M_f32</td>
<td>Single Precision Float</td>
<td>-0.5</td>
<td>0.5</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>MtrPos2_Sin1GainCorr_Uls_M_f32</td>
<td>Single Precision Float</td>
<td>0.8</td>
<td>1.2</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>MtrPos2_Cos1GainCorr_Uls_M_f32</td>
<td>Single Precision Float</td>
<td>0.8</td>
<td>1.2</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>MtrPos2_CosSin1NomRatio_Uls_M_f32</td>
<td>Single Precision Float</td>
<td>1</td>
<td>10</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>MtrPos2_SinCos1NomRatio_Uls_M_f32</td>
<td>Single Precision Float</td>
<td>1</td>
<td>10</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>MtrPos2_RTToNomHighLmt_Uls_M_f32</td>
<td>Single Precision Float</td>
<td>1</td>
<td>1.02</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>MtrPos2_RTToNomLowLmt_Uls_M_f32</td>
<td>Single Precision Float</td>
<td>0.98</td>
<td>1</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>MtrPos2_Cos1RTAmpRec_Uls_M_f32</td>
<td>Single Precision Float</td>
<td>0.2</td>
<td>3.3</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>MtrPos2_Cos1RTOffset_Volt_M_f32</td>
<td>Single Precision Float</td>
<td>1.7</td>
<td>3.8</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>MtrPos2_Sin1RTAmpRec_Uls_M_f32</td>
<td>Single Precision Float</td>
<td>0.2</td>
<td>3.3</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="odd">
<td>MtrPos2_Sin1RTOffset_Volt_M_f32</td>
<td>Single Precision Float</td>
<td>1.7</td>
<td>3.8</td>
<td>MTRPOS2_START_SEC_VAR_NOINIT_32</td>
</tr>
<tr class="even">
<td>MtrPos2_Cos1MaxSV_Volts_M_s2p29</td>
<td>2<sup>-29</sup></td>
<td>0.25</td>
<td>2.5</td>
<td>MTRPOS2_START_SEC_VAR_SAVED_ZONEH_32</td>
</tr>
<tr class="odd">
<td>MtrPos2_Cos1MinSV_Volts_M_s2p29</td>
<td>2<sup>-29</sup></td>
<td>-0.25</td>
<td>-2.5</td>
<td>MTRPOS2_START_SEC_VAR_SAVED_ZONEH_32</td>
</tr>
<tr class="even">
<td>MtrPos2_Sin1MaxSV_Volts_M_s2p29</td>
<td>2<sup>-29</sup></td>
<td>0.25</td>
<td>2.5</td>
<td>MTRPOS2_START_SEC_VAR_SAVED_ZONEH_32</td>
</tr>
<tr class="odd">
<td>MtrPos2_Sin1MinSV_Volts_M_s2p29</td>
<td>2<sup>-29</sup></td>
<td>-0.25</td>
<td>-2.5</td>
<td>MTRPOS2_START_SEC_VAR_SAVED_ZONEH_32</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>MtrPos2_ValidErr_VoltsSqrd_D_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>4.5</td>
<td>MTRPOS2_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>MtrPos2_LearnedParamBfr_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>MTRPOS2_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>MtrPos2_Sin1RTOffset_Volts_M_u3p13[D_MTRPOSDBLBUFFSZ_CNT_U08]</td>
<td>2^-13</td>
<td>1.7</td>
<td>3.8</td>
<td>MTRPOS2_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>MtrPos2_Cos1RTOffset_Volts_M_u3p13[D_MTRPOSDBLBUFFSZ_CNT_U08]</td>
<td>2^-13</td>
<td>1.7</td>
<td>3.8</td>
<td>MTRPOS2_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>MtrPos2_Sin1RTAmpRec_Uls_M_u3p13[D_MTRPOSDBLBUFFSZ_CNT_U08]</td>
<td>2^-13</td>
<td>0.2</td>
<td>3.3</td>
<td>MTRPOS2_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>MtrPos_Cos1RTAmpRec_Uls_M_u3p13[D_MTRPOSDBLBUFFSZ_CNT_U08]</td>
<td>2^-13</td>
<td>0.2</td>
<td>3.3</td>
<td>MTRPOS2_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>MtrPos2_ErrorTerm_Rev_D_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>0.5</td>
<td>MTRPOS2_START_SEC_VAR_CLEARED_32</td>
</tr>
</tbody>
</table>

### User defined typedef definition/declaration 

This section documents any user types uniquely used for the module.

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 28%" />
<col style="width: 15%" />
<col style="width: 13%" />
<col style="width: 13%" />
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
<td>MtrPosCal_DataType</td>
<td><p>BEMFCal_Rev_u0p16</p>
<p>R_BEMFCal_Rev_u0p16</p>
<p>Sin1Offset_Volts_u3p13</p>
<p>Sin1AmpRec_Uls_u3p13</p>
<p>Cos1Offset_Volts_u3p13</p>
<p>Cos1AmpRec_Uls_u3p13</p>
<p>SinDelta1_Uls_s2p13</p>
<p>CosDelta1Rec_Uls_u3p13</p>
<p>Sin1OffCorr_Volts_s2p13</p>
<p>Sin1GainCorr_Uls_u1p15</p>
<p>Cos1OffCorr_Volts_s2p13</p>
<p>Cos1GainCorr_Uls_u1p15</p>
<p>SinHarTbl_Cnt_sm6p13[144]</p>
<p>CosHarTbl_Cnt_sm6p13[144]</p></td>
<td></td>
<td><p>0</p>
<p>0</p>
<p>2.2</p>
<p>0.25</p>
<p>2.2</p>
<p>0.25</p>
<p>-0.0174524</p>
<p>0.99985</p>
<p>-0.5</p>
<p>0.8</p>
<p>-0.5</p>
<p>0.8</p>
<p>-0.01551</p>
<p>-0.01551</p></td>
<td><p>1</p>
<p>1</p>
<p>2.8</p>
<p>2.5</p>
<p>2.8</p>
<p>2.5</p>
<p>0.0174524</p>
<p>1</p>
<p>0.5</p>
<p>1.2</p>
<p>0.5</p>
<p>1.2</p>
<p>0.01551</p>
<p>0.01551</p></td>
</tr>
</tbody>
</table>

\*In FDD 06B, Ver 6, range for SinHarTbl and CosHarTbl is given as -1 to
1 which is incorrect as it’s a 8bit signal. FDD needs to be updated.
Informed to FDD Owner.

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

| Constant Name               |
|-----------------------------|
| k_RTOffVelThr_MtrRadpS_f32  |
| k_RTFiltEnThresh_Uls_f32    |
| k_RTOffFiltKn_Cnt_u16       |
| k_RTOffsetLmt_Volts_f32     |
| k_AmpRecVarLmt_Uls_f32      |
| k_RTToNomRatioVar_Uls_f32   |
| k_CorrelationError_Rev_f32  |
| k_MtrPosCorrDiag_Cnt_str    |
| k_ValMinError_VoltsSqrd_f32 |
| k_ValMaxError_VoltsSqrd_f32 |
| k_MtrPosValDiag_Cnt_str     |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name                | Resolution             | Units    | Value  |
|------------------------------|------------------------|----------|--------|
| D_DEGPERREV_ULS_F32          | Single Precision Float | Unitless | 360    |
| D_OFFSETCORRTHRESH_VOLTS_F32 | Single Precision Float | Volts    | 0.02   |
| D_AMPCORRTHRESH_ULS_F32      | Single Precision Float | Unitless | 0.02   |
| D_MAXAMPLITUDE_VOLTS_F32     | Single Precision Float | Volts    | 2.5    |
| D_MINAMPLITUDE_VOLTS_F32     | Single Precision Float | Volts    | 0.25   |
| D_HALF_ULS_F32               | Single Precision Float | Unitless | 0.5    |
| D_TWO_ULS_F32                | Single Precision Float | Unitless | 2      |
| D_WORDMASK_CNT_U16           | 1                      | Counts   | 0xFFFF |

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name  |
|----------------|
| D_ZERO_ULS_F32 |
| D_ONE_ULS_F32  |
| D_2PI_ULS_F32  |
| D_ZERO_CNT_U16 |

### Module specific Lookup Tables Constants

| Constant Name | Resolution | Value | Software Segment |
|---------------|------------|-------|------------------|
| None          |            |       |                  |

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

1.  FPM_FixedToFloat_m

2.  FPM_FloatToFixed_m

3.  Abs_f32_m

4.  sinf

5.  cosf

6.  DiagPStep_m

7.  DiagNStep_m

8.  DiagFailed_m

9.  LPF_SvUpdate_s16InFixKTrunc_m

10. Limit_m

## Data Hiding Functions

1.  Rte_Pim_MtrPosSnsr_EOLData

2.  Rte_Call_NxtrDiagMgr_GetNTCFailed

## Global Functions/Macros Defined by this Module

None

## Local Functions/Macros Used by this MDD only

### Offset Initialization

| **Function Name**    | OffsetInit                   | Type      | Min  | Max   | UTP Tol. |
|----------------|----------------------------|---------|--------|-------|------|
| **Arguments Passed** | EOLAmpRec_Uls_T_f32          | float32   | 0.25 | 2.5   |          |
|                      | EOLOffset_Volts_T_f32        | float32   | 2.2  | 2.8   |          |
|                      | StateVarMaxPtr_Volts_T_s2p29 | sint32 \* | 0.25 | 2.5   | 2^-13^   |
|                      | StateVarMinPtr_Volts_T_s2p29 | sint32 \* | -2.5 | -0.25 | 2^-13^   |
| **Return Value**     | RTOffset_Volts_T_f32         | float32   | 2.2  | 2.8   | 2^-13^   |

#### <u>Note: In FDD, Range on StoredMax_volts, Stored_Mins are given as 0.25 to 2.5 and -2.5 to -0.25 respt. And in this local function these signals are compared to D_MinAmplitude, D_MaxAmplitude whose const value is 0.25 or 2.5v. 100%coverage for the below IF statement is not achieved with provided ranges. FDD should correct range and is informed to FDD owner. For UnitTesting purpose, special vectors are taken to satisfy IF condition</u>  [note-in-fdd-range-on-storedmax_volts-stored_mins-are-given-as-0.25-to-2.5-and--2.5-to--0.25-respt.-and-in-this-local-function-these-signals-are-compared-to-d_minamplitude-d_maxamplitude-whose-const-value-is-0.25-or-2.5v.-100coverage-for-the-below-if-statement-is-not-achieved-with-provided-ranges.-fdd-should-correct-range-and-is-informed-to-fdd-owner.-for-unittesting-purpose-special-vectors-are-taken-to-satisfy-if-condition]

####  [section]

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image3.emf)

### Run Time Filter

| **Function Name**    | RunTimeFilter             | Type    | Min  | Max | UTP Tol. |
|----------------|-----------------------------|----------|------|------|------|
| **Arguments Passed** | SigEst_Uls_T_f32          | float32 | -1   | 1   |          |
|                      | SigCorr_Volts_T_f32       | float32 | -3.8 | 3.3 |          |
|                      | OffsetDelta_Volts_T_f32   | float32 | -1.1 | 1.6 |          |
|                      | StateVarPtr_Volts_T_s2p29 | s2p29_T | -2.5 | 2.5 |          |
| **Return Value**     | Output_Volts_T_f32        | float32 | -2.5 | 2.5 | 2^-13^   |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image4.emf)

### Calculate Offset from Min/Max

| **Function Name**    | CalcOffsetFromMinMax  | Type    | Min   | Max  | UTP Tol. |
|----------------------|-----------------------|---------|-------|------|----------|
| **Arguments Passed** | Min_Volts_T_f32       | float32 | -0.25 | -2.5 |          |
|                      | Max_Volts_T_f32       | float32 | 0.25  | 2.5  |          |
|                      | EOLOffset_Volts_T_f32 | float32 | 2.2   | 2.8  |          |
| **Return Value**     | RTOffset_Volts_T_f32  | float32 | 1.7   | 3.8  | 2^-13^   |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image5.emf)

### Calculate Sine AmpRec

| **Function Name**    | CalcSinAmpRec          | Type    | Min  | Max | UTP Tol. |
|----------------------|------------------------|---------|------|-----|----------|
| **Arguments Passed** | TotSinAmp_Volts_T_f32  | float32 | 0.5  | 5   |          |
|                      | EOLSinAmpRec_Uls_T_f32 | float32 | 0.25 | 2.5 |          |
| **Return Value**     | SinRTAmpRec_Uls_T_f32  | float32 | 2.2  | 3.3 | 2^-13^   |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image6.emf)

### Calculate Cosine AmpRec

| **Function Name**    | CalcCosAmpRec            | Type    | Min   | Max   | UTP Tol. |
|--------------|--------------------------|---------|---------|----------|------|
| **Arguments Passed** | TotSinAmp_Volts_T_f32    | float32 | 0.5   | 5     |          |
|                      | TotCosAmp_Volts_T_f32    | float32 | 0.5   | 5     |          |
|                      | SinRTAmpRec_Uls_T_f32    | float32 | 0.2   | 3.3   |          |
|                      | SinCosNomRatio_Uls_T_f32 | float32 | 1     | 10    |          |
|                      | CosSinNomRatio_Uls_T_f32 | float32 | 1     | 10    |          |
|                      | RTToNomLowLmt_Uls_T_f32  | float32 | 0.98  | 1     |          |
|                      | RTToNomHighLmt_Uls_T_f32 | float32 | 1     | 1.02  |          |
| **Return Value**     | CosRTAmpRec_Uls_T_f32    | float32 | 1.96. | 33.66 | 2^-13^   |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image7.emf)

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data                                      | Value |
|-------------------------------------------|-------|
|                                           |       |
| Rte_InitValue_CorrectedMtrPos_Rev_f32     | 0     |
| Rte_InitValue_Cos1RTAmpRec_Uls_f32        | 0     |
| Rte_InitValue_Cos1RTOffset_Volt_f32       | 0     |
|                                           |       |
|                                           |       |
| Rte_InitValue_DiagCorrectedMtrPos_Rev_f32 | 0     |
|                                           |       |
| Rte_InitValue_MechMtrPos_Rev_f32          | 0     |
| Rte_InitValue_MotorVelMRF_MtrRadpS_f32    | 0     |
|                                           |       |
|                                           |       |
| Rte_InitValue_Sin1RTOffset_Volt_f32       | 0     |
|                                           |       |
|                                           |       |

## Initialization Functions

### Init: \_Init1

#### Design Rationale

None

#### Calculate Ratios

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image8.emf)

#### Check Correction Terms

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image9.emf)

#### Calculate Limits and Initialize RT Offsets

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image10.emf)

#### Initialize AmpRec

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image11.emf)

##  Periodic Functions

### Per: \_Per1

#### Design Rationale

This function should be run before MtrPos3_Per1, as the comparisons (in
both the main and diverse paths) on the generated signals assume that
this order will be followed.

#### Program Flow Start

Rte_Call_MtrPos2_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

CDD_Read_MtrPos_ActvDblBuf_Cnt_u08(&IdleDblBuf_Cnt_T_u08)

IdleDblBuf_Cnt_T_u08 = (IdleDblBuf_Cnt_T_u08 & 1u)\^1u

CorrectedMtrPos_Rev_T_f32 =
FPM_FixedToFloat_m(MtrPos_CorrectedMtrPos_Rev_M_u0p16\[IdleDblBuf_Cnt_T_u08\],
u0p16_T)

Cos1Scaled_Volt_T_f32 =
FPM_FixedToFloat_m(MtrPos_Cos1Scaled_Volts_M_u3p13\[IdleDblBuf_Cnt_T_u08\],
u3p13_T)

DiagCorrectedMtrPos_Rev_T_f32 = MtrPos3_DiagCorrectedMtrPos_Rev_M_f32

MechMtrPos_Rev_T_f32 =
\_FixedToFloat_m(MtrPos_MechMtrPos_Rev_M_u0p16\[IdleDblBuf_Cnt_T_u08\],
u0p16_T)

MotorVelMRF_MtrRadpS_T_f32 =
Rte_IRead_MtrPos2_Per1_MotorVelMRF_MtrRadpS_f32()

Sin1Scaled_Volt_T_f32 =
FPM_FixedToFloat_m(MtrPos_Sin1Scaled_Volts_M_u3p13\[IdleDblBuf_Cnt_T_u08\],
u3p13_T)

Rte_Call_NxtrDiagMgr_GetNTCFailed(NTC_Num_PriMSB_SinCosCorr,
&MtrPosFault1_Cnt_T_lgc)

Rte_Call_NxtrDiagMgr_GetNTCFailed(NTC_Num_PriVsSec_SinCosCorr,
&MtrPosFault2_Cnt_T_lgc)

Sin1Offset_Volts_T_f32 =
FPM_FixedToFloat_m(MtrPos_EOLDataPtr_Cnt_M_Str-\>Sin1Offset_Volts_u3p13,
u3p13_T)

Cos1Offset_Volts_T_f32 =
FPM_FixedToFloat_m(MtrPos_EOLDataPtr_Cnt_M_Str-\>Cos1Offset_Volts_u3p13,
u3p13_T)

Sin1AmpRec_Uls_T_f32 =
FPM_FixedToFloat_m(MtrPos_EOLDataPtr_Cnt_M_Str-\>Sin1AmpRec_Uls_u3p13,
u3p13_T)

#### Motor Position Measurement

#### Run Time Learning

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image13.emf)

#### Back EMF Diagnostic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image14.emf)

#### Correlation Diagnostic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image15.emf)

#### Validity Diagnostic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image16.emf)

#### Store Local copy of outputs into Module Outputs

MtrPos2_PrevCorrectedMtrPos_Rev_M_f32 = CorrectedMtrPos_Rev_T_f32

MtrPos2_ErrorTerm_Rev_D_f32 = CorrelationDelta_Rev_T_f32

MtrPosValidErr_VoltsSqrd_D_f32 = ValidErr_VoltsSqrd_T_f32

Rte_IWrite_MtrPos2_Per1_CorrectedMtrPos_Rev_f32(CorrectedMtrPos_Rev_T_f32)

Rte_IWrite_MtrPos2_Per1_SysCCorrectedMtrPos_Rev_f32(CorrectedMtrPos_Rev_T_f32)

Rte_IWrite_MtrPos2_Per1_MechMtrPos_Rev_f32(MechMtrPos_Rev_T_f32)

Rte_IWrite_MtrPos2_Per1_SysCMechMtrPos_Rev_f32(MechMtrPos_Rev_T_f32)

Rte_IWrite_MtrPos2_Per1_CosTheta1_Volt_f32(FPM_FixedToFloat_m(MtrPos_CosTheta1_Volts_G_s2p13,
s2p13_T))

Rte_IWrite_MtrPos2_Per1_SinTheta1_Volt_f32(FPM_FixedToFloat_m(MtrPos_SinTheta1_Volts_G_s2p13,
s2p13_T))

IdleDblBuf_Cnt_T_u08 = (MtrPos2_LearnedParamBfr_Cnt_M_u08 & 1)\^1

MtrPos2_Cos1RTAmpRec_Uls_M_u3p13\[IdleDblBuf_Cnt_T_u08\] =
FPM_FloatToFixed_m(MtrPos2_Cos1RTAmpRec_Uls_M_f32, u3p13_T)

MtrPos2_Cos1RTOffset_Volts_M_u3p13\[IdleDblBuf_Cnt_T_u08\] =
FPM_FloatToFixed_m(MtrPos2_Cos1RTOffset_Volt_M_f32, u3p13_T)

MtrPos2_Sin1RTAmpRec_Uls_M_u3p13\[IdleDblBuf_Cnt_T_u08\] =
FPM_FloatToFixed_m(MtrPos2_Sin1RTAmpRec_Uls_M_f32, u3p13_T)

MtrPos2_Sin1RTOffset_Volts_M_u3p13\[IdleDblBuf_Cnt_T_u08\] =
FPM_FloatToFixed_m(MtrPos2_Sin1RTOffset_Volt_M_f32, u3p13_T)

MtrPos2_LearnedParamBfr_Cnt_M_u08 = IdleDblBuf_Cnt_T_u08

#### Program Flow End

Rte_Call_MtrPos2_Per1_CP1_CheckpointReached()

##  Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

### SCom: \_SCom_ReadEOLMtrCals

| **Arguments Passed** | Type                  |
|----------------------|-----------------------|
| MtrCalDataPtr        | MtrPosCal_DataType \* |

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

None

#### Processing of function

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image17.emf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

### SCom: \_SCom_SetEOLMtrCals

| **Arguments Passed** | Type                  |
|----------------------|-----------------------|
| MtrCalDataPtr        | MtrPosCal_DataType \* |

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

None

#### Processing of function

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrPos/doc/mediax/media/image18.emf)

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_MtrPos2_SCom_SetEOLMtrCals_EOLBEMF_Rev_f32(FPM_FixedToFloat_m(Rte_Pim_MtrPosSnsr_EOLData()-\>BEMFCal_Rev_u0p16,
u0p16_T))

#### Program Flow End

N/A

##  

# Execution Requirements

## Execution Sequence of the Module

See section 6.3.1.1 for details on task ordering.

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name | Calling Frequency | System State(s) in which the function is called |
|--------------------------|-----------------|------------------------------|
| MtrPos2_Init1 | On Event          | On Init                                         |
| MtrPos2_Per1  | 2 ms              | ALL                                             |

## Execution Requirements for Serial Communication Functions 

| Function Name               | Sub-Module called by (Serial Comm Function Name) |
|-----------------------------|-------------------------------------------|
| MtrPos2_SCom_ReadEOLMtrCals |                                                  |
| MtrPos2_SCom_SetEOLMtrCals  |                                                  |

#  [section-2]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module | Software Segment                   |
|--------------------|------------------------------------|
| MtrPos2_Init1      | RTE_START_SEC_SA_MTRPOS2_APPL_CODE |
| MtrPos2_Per1       | RTE_START_SEC_SA_MTRPOS2_APPL_CODE |

##  [section-3]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module   | Software Segment |
|----------------------|------------------|
| OffsetInit           |                  |
| RunTimeFilter        |                  |
| CalcOffsetFromMinMax |                  |
| CalcSinAmpRec        |                  |
| CalcCosAmpRec        |                  |

#  [section-4]

#  Known Issues / Limitations With Design

1.  INLINE functions defined in GlobalMacro.h are not unit tested.

#  Revision Control Log

| **Item \#** | **Rev \#** | **Change Description**    | **Date**   | **Author Initials** |
|------|------|--------------------------------------------|---------|---------|
| 1           | 1.0        | Initial Version           | 23-Oct-12  | OT                  |
| 2           | 2.0        | UTP updates               | 18-Dec-12  | OT                  |
| 3           | 3.0        | MDD Catchup for SRC Ver 4 | 13-June-13 | NRAR                |

{% endraw %}