---
layout: default
title: MotorVelocity_MDD
nav_order: 4
parent: Motor Velocity
---
{% raw %}
# Module -- Motor Velocity [module----motor-velocity]

# High-Level Description

This function is responsible for calculating motor velocity from the
sine and cosine motor position sensor signals.

Based on HighLevelDesignDocument (**State Dependant
Runnables_BMW_Future.xlsx)**, Runnables shown in different application
segments are placed in different source files. For MtrVel, FDD Ver 007,
HLDD has 4 runnables, two of which are in ASILD listed as MtrVel_Per1()
and MtrVel_Per2(). And two of them are in ASILB’(D) listed as
MtrVel2_Per1() and MtrVel2_Per2(). This document is responsible for
ASILD runnables.

# Figures

## Diagram – Function Data Sharing

This diagram shows all data that is shared between functions within the
module.

No Shared Data

### Diagram – MtrVel_Per1

This diagram describes the functional characteristics and data flow of a
given function.

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image1.png"
style="width:3.03125in;height:2.66667in" />

# Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be
shown here)

|                                          |                                       |
|-------------------------------------|-----------------------------------|
| Module Inputs (Global Variable Name)     | Module Outputs (Global Variable Name) |
| VehicleSpeed_Kph_f32                     | CRFMotorVel_MtrRadpS_f32              |
| AsstAssemPol_Cnt_s08                     | MRFMotorVel_MtrRadpS_f32              |
| MtrVel3_SinBuffer_Uls_M_s2p13\[4\]\[8\]  | HandwheelVel_HwRadpS_f32              |
| MtrVel3_CosBuffer_Uls_M_s2p13\[4\]\[8\]  | HwVelValid_Cnt_lgc                    |
| MtrVel3_PosBuffer_Rev_M_u0p16 \[4\]\[8\] | MRFMotorVelUnfiltered_MtrRadpS_f32    |
| MtrVel3_TimeBuffer_uS_M_u16p0\[4\]\[8\]  | SysCHandwheelVel_HwRadpS_f32          |
| MtrVel3_OsBufPos_Cnt_M_u08\[4\]          | SysCMotorVelMRF_MtrRadpS_f32          |
| SysCDiagHandWheelVel_HwRadpS_f32         |                                       |
| SysCDiagMtrVelMRF_MtrRadpS_f32           |                                       |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table style="width:100%;">
<colgroup>
<col style="width: 41%" />
<col style="width: 12%" />
<col style="width: 13%" />
<col style="width: 13%" />
<col style="width: 18%" />
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
<td>CrsMtrVel_MtrRadpS_D_f32[2]</td>
<td>Single Precision Floating Point</td>
<td>-1350</td>
<td>1350</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>DeltaTheta_Uls_D_s18p13[2][8]</td>
<td>2^-13</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>HwVel_HwRadpS_M_f32</td>
<td>Single Precision Floating Point</td>
<td>-42</td>
<td>42</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>HwVelCorrLimDiff_HwRadpS_D_f32</td>
<td>Single Precision Floating Point</td>
<td>0</td>
<td>84</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>HwVelDiffAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>255</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>MtrVel_ActiveBufSet_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>MtrVel_AvgDeltaT_uS_D_u16p0[2]</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>MtrVel_DeltaThetaIntercept_Uls_D_s7p24[2]</td>
<td>2^-24</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>MtrVel_MtrRadpS_M_f32</td>
<td>Single Precision Floating Point</td>
<td>-1350</td>
<td>1350</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>MtrVel_OldPosBuf_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>3</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>MtrVel_OsBufSelect_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>4</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="odd">
<td>MtrVel_Slope_puS_D_sm11p42[2]</td>
<td>2^-42</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>MtrVel_SnapShotSet_Cnt_G_u08</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_8_GLOBALSHARED</td>
</tr>
<tr class="odd">
<td>MtrVelCorrLimDiff_MtrRadpS_D_f32</td>
<td>Single Precision Floating Point</td>
<td>0</td>
<td>2700</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>MtrVelDelta_MtrRadpS_M_u12p4</td>
<td>2<sup>-4</sup></td>
<td>0</td>
<td>1350</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>MtrVelDiffAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>255</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>MtrVelFiltSV_MtrRadpS_M_s11p20</td>
<td>2^-20</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>OldMtrVel_MtrRadpS_M_s11p4</td>
<td>2<sup>-4</sup></td>
<td>-1350</td>
<td>1350</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>PosAvg_Rev_M_u0p16</td>
<td>2<sup>-16</sup></td>
<td>FULL</td>
<td>FULL</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>PredDeltaTheta_Uls_D_f32[2]</td>
<td>Single Precision Floating Point</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>PredDeltaThetaCor_Uls_D_f32[2]</td>
<td>Single Precision Floating Point</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>WestBlendedMtrVel_MtrRadpS_D_f32[2]</td>
<td>Single Precision Floating Point</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>WestVelocity_MtrRadpS_D_f32[2]</td>
<td>Single Precision Floating Point</td>
<td>FULL</td>
<td>FULL</td>
<td>MTRVEL_START_SEC_VAR_CLEARED_32</td>
</tr>
</tbody>
</table>

\* Note: These ranges are based on the range of the normalized sine and
cosine global inputs, which in turn are based on the maximum amount of
signal variation that can be caused by temperature changes on the MSB
signals.

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
<td><p>(Name given for the user defined typdef of type struct/union)</p>
<p>(Variable name qualified similar to all other variables)</p></td>
<td>(Variable name qualified similar to all other variables)</td>
<td>as other variables</td>
<td></td>
<td></td>
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
| t_MtrVelDeltaKpTblX_MtrRadpS_u12p4 |
| t_MtrVelDeltaKpTblY_Cnt_u16        |
| t_MtrVelFiltKpTblX_Kph_u9p7        |
| t_MtrVelFiltKpYTbl_Cnt_u16         |
| t_MtrVelBlendTblX_MtrRadpS_u12p4   |
| k_MtrVelFiltEn_Cnt_lgc             |
| k_GearRatio_Uls_f32                |
| k_MtrVelCorrLim_Cnt_Str            |
| k_HwVelCorrLim_Cnt_Str             |
| k_MtrVelCorrLim_MtrRadpS_f32       |
| k_HwVelCorrLim_HwRadpS_f32         |
| t_MtrVelTimeOffsetTblX_Kph_u9p7    |
| t_MtrVelTimeOffsetYTbl_uS_u16      |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

|                                 |                                 |                  |
|--------------------------------|---------------|--------------------------|
| Constant Name                   | Resolution                      | Value            |
| D_CORRTERMA0_ULS_F32            | Single Precision Floating Point | 0.5240920730306  |
| D_CORRTERMN1P_ULS_F32           | Single Precision Floating Point | 0.09361941664774 |
| D_CORRTERMN2P_ULS_F32           | Single Precision Floating Point | 1.488737214789   |
| D_CORRTERME1P_ULS_F32           | Single Precision Floating Point | 1.27106431778    |
| D_CORRTERME2P_ULS_F32           | Single Precision Floating Point | 3.700991517299   |
| D_USECPERSEC_ULS_F32            | Single Precision Floating Point | 1000000.0        |
| D_MTRVELOSBUFNUM_CNT_U08        | 1                               | 4                |
| D_MTRVELOSBUFSZ_CNT_U08         | 1                               | 8                |
| D_SNAPSHOTBUF_CNT_U08           | 1                               | 2                |
| D_MTRVELLOLMT_MTRRADPS_F32      | Single Precision Floating Point | -1350            |
| D_MTRVELLOLMT_MTRRADPS_F32      | Single Precision Floating Point | 1350             |
| D_B1NUMLIMIT_US_S7P24           | 2^-24^                          | 0.0625 – 1count  |
| D_HWVELLOLMT_HWRADPS_F32        | Single Precision Floating Point | -42              |
| D_HWVELHILMT_HWRADPS_F32        | Single Precision Floating Point | 42               |
| D_FIXPTMTRVELHILMT_MTRRADPS_F32 | Single Precision Floating Point | 2047.9375        |
| D_FIXPTMTRVELLOLMT_MTRRADPS_F32 | Single Precision Floating Point | -2048.0          |

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

|                     |
|---------------------|
| Constant Name       |
| D_RADPERREV_ULS_F32 |

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as
other tables)

|                             |            |        |                  |
|-----------------------------|------------|--------|------------------|
| Constant Name               | Resolution | Value  | Software Segment |
| T_MtrVelBlendTblY_Uls_u2p14 | 2\^-14     | {0, 1} |                  |

# Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library functions / Macros that are called by the various sub
modules are identified below,

1.  FPM_FixedToFloat_m()

2.  FPM_FloatToFixed_m()

3.  FMP_Fix_m()

4.  Max_m()

5.  Abs_s16_m()

6.  Abs_f32_m()

7.  IntplVarXY_u16_u16Xu16Y_Cnt()

8.  LPF_SvUpdate_s16InFixKTrunc_m()

9.  LPF_OpUpdate_s16InFixKTrunc_m()

10. Rte_Call_NxtrDiagMgr_GetNTCFailed

11. Rte_Call_NxtrDiagMgr_SetNTCStatus

12. TableSize_m()

## Data Hiding Functions

The data hiding functions / macros used in this module are identified
below,

## Local Functions/Macros Used by this MDD only

(Note if they are defined in another source file, then reference the
appropriate header file)

The local functions/macros in this module are identified below,

1.  Square_m(x) ((x)\*(x))

2.  CalcCoarseVel()

3.  CorrectVel()

4.  MtrVelBlend()

5.  RegressionFit()

# Software Module Implementation

## Initialization Functions

### Init: MtrVel_Init1

#### Design Rationale

None

#### Module Outputs

None

#### Module Internal 

None

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image2.wmf)

## Periodic Functions

### Per: MtrVel_Per1

#### Design Rationale

##### Coarse and Fine Velocity Calculations

A “coarse” motor velocity signal is calculated which is simply
calculated from (change in averaged motor position) / (change in
averaged time).

The “fine” motor velocity signal has inherent error at high speeds due
to the nature of the algorithm. Because of the way the calculation is
done and the fact that the samples are done every 1mS, the maximum
velocity that this algorithm can calculate is +/-pi rad/ms \~ +/- 3142
rad/sec. Additionally, there is significant error in the calculation as
velocity increases to this limit. For this reason, a correction is
calculated and applied to the fine velocity to increase the accuracy up
to a certain speed, and a blending is done so that “fine” velocity is
used at lower speeds when it is accurate, and “coarse” velocity is used
at high speeds.

##### Unit Testing Considerations

The design of this module was done with physical motor velocity
considerations taken into account. For example, the limits on the inputs
to some of the local functions are based on the physical system.
Assuming the motor can rotate at a maximum of +/- 1350 Rads/Sec, the
design only needs to accommodate a certain “change in position” from the
last loop. Similarly, a “change in time” from the last loop will always
correspond to the calculation loop rate within a tolerance. This was
where the limits for the Coarse and Fine velocity functions were
derived. All unit-testing test vectors should be designed in such a way
as to conform to these physical limitations. Additionally, for any use
of combinations of the sin and cos signals, the standard sin vs cos
relationship may need to be followed (e.g. sin and cos are never both
“0” at the same point in time).

#### Program Flow Start

####  Rte_Call_MtrVel_Per1_CP0_CheckpointReached()Store Module Inputs to Local copies

SinAvg_Uls_T_s2p13 as sint16

CosAvg_Uls_T_s2p13 as sint16

PosAvg_Rev_T_u0p16 as uint16

TimeAvg_uS_T_u16p0 as uint16

MtrVel_ActiveBufSet_Cnt_M_u08 = (MtrVel_SnapShotSet_Cnt_G_u08 \^ 1u) &
1u

AsstAssemPol_Cnt_T_s08 = Rte_IRead_MtrVel_Per1_AsstAssemPol_Cnt_s08()

VehSpd_Kph_T_f32 = Rte_IRead_MtrVel_Per1_VehSpd_Kph_f32()

VehSpd_Kph_T_u9p7 = FPM_FloatToFixed_m(VehSpd_Kph_T_f32, u9p7_T);

Rte_Call_NxtrDiagMgr_GetNTCFailed(NTC_Num_PriMSB_SinCosCorr,&MtrPosFault1_Cnt_T_lgc)

Rte_Call_NxtrDiagMgr_GetNTCFailed(NTC_Num_PriVsSec_SinCosCorr,
&MtrPosFault2_Cnt_T_lgc)

#### Calculate Raw Motor Velocity

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image3.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image4.wmf)

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_MtrVel_Per1_MRFMtrVel_MtrRadpS_f32(MtrVel_MtrRadpS_T_f32)

MtrVel_MtrRadpS_T_f32 = AsstAssemPol_Cnt_T_s08 \* MtrVel_MtrRadpS_T_f32

Rte_IWrite_MtrVel_Per1_CRFMtrVel_MtrRadpS_f32(MtrVel_MtrRadpS_T_f32)

HwVel_HwRadpS_T_f32 = MtrVel_MtrRadpS_T_f32 \* k_GearRatio_Uls_f32

HwVel_HwRadpS_M_f32 = Limit_m(HwVel_HwRadpS_T_f32,
D_HWVELLOLMT_HWRADPS_F32, D_HWVELHILMT_HWRADPS_F32)

Rte_IWrite_MtrVel_Per1_HandwheelVel_HwRadpS_f32 (MtrVel_MtrRadpS_T_f32)

Rte_IWrite_MtrVel_Per1_HwVelValid_Cnt_lgc(HwVelValid_Cnt_T_lgc)

Rte_IWrite_MtrVel_Per1_MRFMotorVelUnfiltered_MtrRadpS_f32(WestBlendedMtrVel_MtrRadpS_D_f32)

Rte_IWrite_MtrVel_Per1_SysCMotorVelMRF_MtrRadpS_f32(MtrVel_MtrRadpS_M_f32)

Rte_IWrite_MtrVel_Per1_SysCHandwheelVel_HwRadpS_f32(HwVel_HwRadpS_M_f32)

#### Program Flow End

Rte_Call_MtrVel_Per1_CP1_CheckpointReached()

## Periodic Functions

### Per: MtrVel_Per2

#### Design Rationale

#### Program Flow Start

####  Rte_Call_MtrVel_Per2_CP0_CheckpointReached()Store Module Inputs to Local copies

SysC_DiagMtrVelMRF_MtrRadpS_T_f32 =
Rte_IRead_MtrVel_Per2_SysCDiagMtrVelMRF_MtrRadpS_f32()

SysC_DiagHandWheelVel_HwRadpS_T_f32 =
Rte_IRead_MtrVel_Per2_SysCDiagHandWheelVel_HwRadpS_f32()

#### Calculate Raw Motor Velocity

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image5.wmf)

#### Program Flow End

Rte_Call_MtrVel_Per2_CP1_CheckpointReached()

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

## Local Function/Macro Definitions

If these are numerous and defined in a separate source file then
reference the source file only.

### Calculation Coarse Velocity

|                      |                       |                                 |      |       |      |          |
|--------------|-----------------------|--------|-----|--------|--------|--------|
| **Function Name**    | CalcCoarseVel         | Type                            | Dir. | Min   | Max  | UTP Tol. |
| **Arguments Passed** | DeltaPos_Rev_T_f32    | Single Precision Floating Point | I    | -0.2  | 0.2  |          |
|                      | DeltaTime_uS_T_f32    | Single Precision Floating Point | I    | 900   | 1100 |          |
| **Return Value**     | MtrVel_MtrRadpS_T_f32 | Single Precision Floating Point | O    | -1350 | 1350 | 6.25E-2  |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image6.wmf)

### Correct Velocity

|                      |                       |                                 |      |       |      |          |
|--------------|-----------------------|--------|-----|--------|--------|--------|
| **Function Name**    | CorrectVel            | Type                            | Dir. | Min   | Max  | UTP Tol. |
| **Arguments Passed** | MtrVel_MtrRadpS_T_f32 | Single Precision Floating Point | I    | -1350 | 1350 |          |
| **Return Value**     | MtrVel_MtrRadpS_T_f32 | Single Precision Floating Point | O    | -1350 | 1350 | 6.25E-2  |

#### Design Rationale

This function will calculate and apply a correction factor to the fine
motor velocity. This will increase the range of speeds over which the
fine motor velocity is accurate. The calculation of the correction term
is shown below:

**Correction Term = A0 + N_1P/(E_1P - w\^2) + N_2P/(E_2P - w\^2)**

A0 = 0.5249978317

N_1P = 0.09425018578 / SampleTime\^2 = 94250.18578

E_1P = 3 1.270451499 / SampleTime\^2 = 1270451.499

N_2P = 1.484093006 / SampleTime\^2 = 1484093.006

E_2P = 3.702672882 / SampleTime\^2 = 3702672.882

w = Calculated Fine Motor Velocity

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image7.wmf)

### Motor Velocity Blend

|                      |                          |                                 |      |       |      |          |
|--------------|-----------------------|--------|-----|--------|--------|--------|
| **Function Name**    | MtrVelBlend              | Type                            | Dir. | Min   | Max  | UTP Tol. |
| **Arguments Passed** | FinMtrVel_MtrRadpS_T_f32 | Single Precision Floating Point | I    | -1350 | 1350 |          |
|                      | CrsMtrVel_MtrRadpS_T_f32 | Single Precision Floating Point | I    | -1350 | 1350 |          |
| **Return Value**     | MtrVel_MtrRadpS_T_f32    | Single Precision Floating Point | O    | -1350 | 1350 | 6.25E-2  |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image8.wmf)

### Regression Fit

|                      |                               |               |      |      |      |          |
|--------------|-----------------------|--------|-----|--------|--------|--------|
| **Function Name**    | Regression Fit                | Type          | Dir. | Min  | Max  | UTP Tol. |
| **Arguments Passed** | VehSpd_Kph_T_u9p7             | uint16        | I    | 0    | 512  |          |
|                      | PredDeltaThetaPtr_Uls_T_s1p14 | P2VAR, sint16 | O    | FULL | FULL | 6.11E-05 |
|                      | PosAvgPtr_Rev_T_u0p16         | P2VAR, uint16 | O    | FULL | FULL | 1.53E-05 |
|                      | AvgDeltaTPtr_uS_T_u16p0       | P2VAR, uint16 | O    | 250  | 2000 | 1        |
| **Return**           | None                          |               |      |      |      |          |

\*
200000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image9.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image10.wmf)

# Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the
different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

|               |                   |                                                 |
|---------------------------|----------------|-----------------------------|
| Function Name | Calling Frequency | System State(s) in which the function is called |
| MtrVel_Init1  | Once              | ALL STATES                                      |
| MtrVel_Per1   | 1ms               | ALL STATES                                      |
| MtrVel_Per2   | 4ms               | ALL STATES                                      |

## Execution Requirements for Serial Communication Functions 

|               |                                                  |
|---------------|--------------------------------------------------|
| Function Name | Sub-Module called by (Serial Comm Function Name) |
| N/A           |                                                  |

#   [section]

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

|                    |                         |
|--------------------|-------------------------|
| Name of Sub Module | Software Segment        |
| MtrVel_Per1        | RTE_SA_MTRVEL_APPL_CODE |
| MtrVel_Per2        | RTE_SA_MTRVEL_APPL_CODE |

## Local Functions

This table identifies the software segments for local functions
identified in this module.

|                      |                  |
|----------------------|------------------|
| Name of Sub Module   | Software Segment |
| CalcCoarseVel        | AP_MTRVEL_CODE   |
| CalcVel              | AP_MTRVEL_CODE   |
| CorrectVel           | AP_MTRVEL_CODE   |
| MtrVelBlend          | AP_MTRVEL_CODE   |
| CalcAvgMtrVelSignals | AP_MTRVEL_CODE   |

#   [section-1]

# Known Issues / Limitations With Design

1.  In this design, MtrVel3_TimeBuffer_uS_M_u16p0\[\]\[\] represents a
    set of independent circular buffers. Each buffer contains a set of
    continuous timestamps with the most recent timestamp index of each
    sample set stored in the associated index of
    MtrVel3_OsBufPos_Cnt_M_u08\[\] . The design requires monotonically
    increasing timestamps relative to the starting index value in
    MtrVel3_OsBufPos_Cnt_M_u08\[\]. Due to the modulo 65536 behavior of
    the timestamp, a single timestamp rollover within the active sample
    set pair is correctly handled by the design. Simultaneous sample
    points (e.g. ∆t = 0 for consecutive timestamps) are invalid and will
    result in a divide by zero in the current design. Unit Test vectors
    for functions which have MtrVel3_TimeBuffer_uS_M_u16p0\[4\]\[8\] as
    an input (MtrVel_Per1 and RegressionFit) must provide an input
    vector value set which conforms to the set of rules in the following
    table:

<table>
<colgroup>
<col style="width: 34%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 44%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Parameter</td>
<td>Min</td>
<td>Max</td>
<td>Notes</td>
</tr>
<tr class="even">
<td><p>Buffer consecutive timestamp value ∆</p>
<p>i.e. MtrVel3_TimeBuffer_uS_M_u16p0 [i][k] -
MtrVel3_TimeBuffer_uS_M_u16p0 [i][k+1]</p></td>
<td>10 uS</td>
<td>125 uS</td>
<td><p>Monotonically increasing in a modulo 65536 fashion (e.g. testing
of the 16 bit rollover point allows for a single rollover point within
the data buffer that is not monotonically increasing).</p>
<p>The UTP MUST provide at least 1 test vector that provides a data set
with a time stamp rollover (See Table 2).</p>
<p>10 uS is the worst case minimum sampling period based on the MtrCtrl
ISR runtime.</p>
<p>125uS is twice the nominal execution rate for MtrCtrl ISR. This is to
account for a worst case delay scenario.</p></td>
</tr>
<tr class="odd">
<td><p>Cross buffer set timestamp pair ∆</p>
<p>(e.g the ∆ between the oldest samples in each buffer, the ∆ between
the second oldest oldest samples in each buffer, etc)</p>
<p>i.e. MtrVel3_TimeBuffer_uS_M_u16p0 [MtrVel_OsBufSelect_M_u08][i] -
MtrVel3_TimeBuffer_uS_M_u16p0 [MtrVel_OldPosBuf_M_u08][k]</p>
<p>where k = i + (MtrVel3_OsBufPos_Cnt_M_u08[MtrVel_OldPosBuf_M_u08] -
MtrVel3_OsBufPos_Cnt_M_u08[MtrVel_OsBufSelect_M_u08]) modulo 8</p></td>
<td>250 uS</td>
<td>2000 uS</td>
<td><p>250 uS is the minimum required time to guarantee 8 samples at a
nominal 62.5 uS sample rate have been completed.</p>
<p>2000 uS is twice the execution rate for MtrVel_Per1. This is to
account for a worst case delay scenario.</p>
<p>When computing the delta it is necessary to perform modulo 65536 math
compensation to account for rollover situations (e.g. Table 2 [z-7]
samples depict a rollover case where the natural delta is 1764 – 65300 =
-63536, however this is not the correct delta result for the strictly
increasing modulo 65536 accumulator. Since the natural result is
negative, 65536 must be added to obtain the actual delta, -63536 + 65536
= 2000.</p>
<p>See Table 2 for a complete example conforming to this rule.</p></td>
</tr>
</tbody>
</table>

Table 1: Time Buffer UTP Constraints

The following \*.bas is a VBA function to validate the timestamp data
sets.

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/MtrVel/doc/mediax/media/image11.wmf)

**<u>EXAMPLE TimeStamp Buffer Data Set:</u>**

The following buffer timestamp data set provides an example when buffers
0 and 1 are active. Values for buffers 2 and 3 are don’t care values for
this example and shown as “X” or “Don’t Care”. The samples within the
buffers have subscripts which describe the samples order relative to the
newest sample in the buffer (e.g. z-1 indicates that the sample is 1
sample period old, z-2 indicates the sample is 2 sample periods old,
etc). Samples of the same relative order within each buffer have the
same cell shading applied to aid the reader in locating cross buffer
sample pairs.

MtrVel_OldPosBuf_M_u08 = 0

MtrVel_OsBufSelect_M_u08 = 1

MtrVel3_OsBufPos_Cnt_M_u08\[0\] = 0

MtrVel3_OsBufPos_Cnt_M_u08\[1\] = 2

MtrVel3_OsBufPos_Cnt_M_u08\[2\] = Don’t Care

MtrVel3_OsBufPos_Cnt_M_u08\[3\] = Don’t Care

|       |           |            |            |            |            |           |           |           |
|-------|---------|---------|---------|---------|---------|---------|---------|---------|
| Index | 0         | 1          | 2          | 3          | 4          | 5         | 6         | 7         |
| 0     | 198       | 65300~z-7~ | 65362~z-6~ | 65424~z-5~ | 65486~z-4~ | 12~z-3~   | 74~z-2~   | 136~z-1~  |
| 1     | 2074~z-2~ | 2136~z-1~  | 2198       | 1764~z-7~  | 1826~z-6~  | 1888~z-5~ | 1950~z-4~ | 2012~z-3~ |
| 2     | X         | X          | X          | X          | X          | X         | X         | X         |
| 3     | X         | X          | X          | X          | X          | X         | X         | X         |

Table 2: Example UTP TimeBuffer Roll-Over Sample Set

1.  The state variables MtrVel_OldPosBuf_M_u08 and
    MtrVel_OsBufSelect_Cnt_M_u08 have a relationship that is maintained
    by logic that is executed after their use in RegressionFit(). The
    RegressionFit() function design requires a valid set of state
    variables to function properly. Therefore, it is possible to provide
    an illegal value set for the related state variables in a unit
    testing environment that will cause an illegal execution of
    RegressionFit(). All unit test vectors must ensure that
    MtrVel_OldPosBuf_M_u08 ≠ MtrVel_OsBufSelect_Cnt_M_u08. Failure to do
    so will result in a divide by 0 exception.

2.  1.  
    2.  
    3.  

# Revision Control Log

<table style="width:100%;">
<colgroup>
<col style="width: 6%" />
<col style="width: 6%" />
<col style="width: 64%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Item #</strong></td>
<td><strong>Rev #</strong></td>
<td><strong>Change Description</strong></td>
<td><strong>Date</strong></td>
<td><strong>Author Initials</strong></td>
</tr>
<tr class="even">
<td>1</td>
<td>1.0</td>
<td>Initial AutoSAR release.</td>
<td>31JAN11</td>
<td>L.N.</td>
</tr>
<tr class="odd">
<td>2</td>
<td>2</td>
<td>Created new handwheel velocity output.</td>
<td>01-Jun-11</td>
<td>YY</td>
</tr>
<tr class="even">
<td>3</td>
<td>3</td>
<td>Fixed filter time constant anomaly. Update rationale and ranges for
current implementation.</td>
<td>16-Jun-11</td>
<td>LWW</td>
</tr>
<tr class="odd">
<td>4</td>
<td>4</td>
<td>Component created</td>
<td>11-July-12</td>
<td>NRAR</td>
</tr>
<tr class="even">
<td>5</td>
<td>5</td>
<td>Updated to ver 007 – Safety stuff added</td>
<td>5-OCT-12</td>
<td>NRAR</td>
</tr>
<tr class="odd">
<td>6</td>
<td>6</td>
<td>Updated to v010</td>
<td>6-FEB-13</td>
<td>JWJ</td>
</tr>
<tr class="even">
<td>7</td>
<td>7</td>
<td>Corrected RegressionFit truncation and calculation errors</td>
<td>8-FEB-13</td>
<td>JJW</td>
</tr>
<tr class="odd">
<td>8</td>
<td>8</td>
<td>Corrected FPM resolution of Slope in RegressionFit function</td>
<td>14-FEB-13</td>
<td>JJW</td>
</tr>
<tr class="even">
<td>9</td>
<td>9</td>
<td>Added missing module level variables per UTP feedback</td>
<td>04-APR-13</td>
<td>JJW</td>
</tr>
<tr class="odd">
<td>10</td>
<td>10</td>
<td><p>Corrected MtrVel_Init1 variable name typo</p>
<p>Added “UTP Tol.” Field to all local functions</p>
<p>Updated range of MtrVel Rad/S signals to FDD specified +/-1350</p>
<p>Added “Dir.” Field to all local functions to specify the direction of
the data in the case of values passed by reference.</p>
<p>Added missing limit on HwVel output</p></td>
<td>08-APR-13</td>
<td>JJW</td>
</tr>
<tr class="even">
<td>11</td>
<td>11</td>
<td>Corrected range of MtrVel_OldPosBuf_Cnt_M_u08 and
MtrVel_OsBufSelect_Cnt_M_u08</td>
<td>10-APR-13</td>
<td>JJW</td>
</tr>
<tr class="odd">
<td>12</td>
<td>12</td>
<td>Corrected range of MtrVel_OsBufSelect_Cnt_M_u08</td>
<td>17-APR-13</td>
<td>JJW</td>
</tr>
<tr class="even">
<td>13</td>
<td>13</td>
<td><p>Updated “Known Issues/Limitations with Design” section to provide
direction for UTP development with regard to selecting vectors for the
TimeStamp buffer and buffer selection variables.</p>
<p>Added explicit 0xFFFF masking to result of PosBuffer_Rev_M_u0p16
delta and PosAvg_Rev_T_u0p16 delta.</p>
<p>Added description of design limitations due to anomaly 5048</p></td>
<td>07-MAY-13</td>
<td>JJW</td>
</tr>
<tr class="odd">
<td>14</td>
<td>14</td>
<td>Added limit macro support for Per1 if the filter is enabled to
correct anomaly 5048, removed comment in design limitations pertaining
to this anomaly.</td>
<td>13-Jun-13</td>
<td>KJS</td>
</tr>
</tbody>
</table>

{% endraw %}