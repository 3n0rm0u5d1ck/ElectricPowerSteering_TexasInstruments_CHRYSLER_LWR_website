---
layout: default
title: Damping_MDD
nav_order: 2
parent: Damping
---
{% raw %}
# Module --  [module---]

# High-Level Description

Damping function computes the Total damping Torque. The total damping
command is calculated from two terms, Active Damping Term and the HPS
Damping Command.

# Figures

## Component Diagram

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Damping/doc/mediax/media/image2.png"
style="width:2.59375in;height:2.57292in" />

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs              | Module Outputs |                      |
|----------------------------|----------------|----------------------|
| MotorVelCRF_MtrRadpS_f32   |                | DampingCmd_MtrNm_f32 |
| HwTorque_HwNm_f32          |                |                      |
| VehicleSpeed_Kph_f32       |                |                      |
| DampingDDFactor_Uls_f32    |                |                      |
| AssistMechTempEst_DegC_f32 |                |                      |
| AssistCmp_MtrNm_f32        |                |                      |
| DefeatDampingSvc_Cnt_lgc   |                |                      |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table>
<colgroup>
<col style="width: 31%" />
<col style="width: 15%" />
<col style="width: 13%" />
<col style="width: 13%" />
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
<td>QDDHwTorqueLPFKSV_Cnt_M_str</td>
<td>LPF32KSV_Str</td>
<td>N/A</td>
<td>N/A</td>
<td>DAMPING_START_SEC_VAR_CLEARED_UNSPECIFIED</td>
</tr>
<tr class="even">
<td>QDDMtrVelLPFKSV_Cnt_M_str</td>
<td>LPF32KSV_Str</td>
<td>N/A</td>
<td>N/A</td>
<td>DAMPING_START_SEC_VAR_CLEARED_UNSPECIFIED</td>
</tr>
<tr class="odd">
<td>QDDStFilt_Cnt_M_str</td>
<td>LPF32KSV_Str</td>
<td>N/A</td>
<td>N/A</td>
<td>DAMPING_START_SEC_VAR_CLEARED_UNSPECIFIED</td>
</tr>
<tr class="even">
<td>MtrVelLPFKSV_Cnt_M_str</td>
<td>LPF32KSV_Str</td>
<td>N/A</td>
<td>N/A</td>
<td>DAMPING_START_SEC_VAR_CLEARED_UNSPECIFIED</td>
</tr>
<tr class="odd">
<td>QDDHwTrqBkLash_HwNm_M_f32</td>
<td>Single Precision Float</td>
<td>-10</td>
<td>10</td>
<td>DAMPING_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>QDDMtrVelBckLash_MtrRadpS_M_f32</td>
<td>Single Precision Float</td>
<td>-1118</td>
<td>1118</td>
<td>DAMPING_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>QDDStFilt_Uls_D_f32</td>
<td>Single Precision Float</td>
<td>FULL</td>
<td>FULL</td>
<td>DAMPING_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>DampTrqScale_Uls_D_u1p15</td>
<td>2^-15</td>
<td>FULL</td>
<td>FULL</td>
<td>DAMPING_STOP_SEC_VAR_CLEARED _16</td>
</tr>
<tr class="odd">
<td>DampTempScale_Uls_D_u4p12</td>
<td>2^-12</td>
<td>FULL</td>
<td>FULL</td>
<td>DAMPING_STOP_SEC_VAR_CLEARED _16</td>
</tr>
<tr class="even">
<td>DampMtrVelDmp_MtrNm_D_f32</td>
<td>Single Precision Float</td>
<td>FULL</td>
<td>FULL</td>
<td>DAMPING_STOP_SEC_VAR_CLEARED _32</td>
</tr>
<tr class="odd">
<td>DampHPSDmp_MtrNm_D_f32</td>
<td>Single Precision Float</td>
<td>FULL</td>
<td>FULL</td>
<td>DAMPING_STOP_SEC_VAR_CLEARED _32</td>
</tr>
<tr class="even">
<td>DampHPSc1_Uls_D_f32</td>
<td>Single Precision Float</td>
<td>FULL</td>
<td>FULL</td>
<td>DAMPING_STOP_SEC_VAR_CLEARED _32</td>
</tr>
<tr class="odd">
<td>DampHPSc2_Uls_D_f32</td>
<td>Single Precision Float</td>
<td>FULL</td>
<td>FULL</td>
<td>DAMPING_STOP_SEC_VAR_CLEARED _32</td>
</tr>
<tr class="even">
<td>DampHPSc3_Uls_D_f32</td>
<td>Single Precision Float</td>
<td>FULL</td>
<td>FULL</td>
<td>DAMPING_STOP_SEC_VAR_CLEARED _32</td>
</tr>
<tr class="odd">
<td>DampHPSc4_Uls_D_f32</td>
<td>Single Precision Float</td>
<td>FULL</td>
<td>FULL</td>
<td>DAMPING_STOP_SEC_VAR_CLEARED _32</td>
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

| Constant Name                              |
|--------------------------------------------|
| k_MtrVelDampLPFKn_Hz_f32                   |
| t_HwTrqDmpTblX_HwNm_u8p8 \[\]              |
| t_VSpdDmpTblBS_Kph_u9p7 \[\]               |
| t_HwTrqDmpTblY_Uls_u1p15\[ \]              |
| t2_MtrVelDmpTblX_MtrRadpS_u12p4\[ \] \[ \] |
| t2_MtrVelDmpTblY_MtrNm_u5p11\[ \] \[ \]    |
| t_TempScaleX_DegC_s8p7\[ \]                |
| t_TempScaleY_Uls_u4p12\[ \]                |
| t_HPSscaleC1Y_Uls_u4p12\[ \]               |
| t_HPSscaleC2Y_Uls_u4p12\[ \]               |
| t_HPSscaleC3Y_Uls_u4p12\[ \]               |
| t_HPSscaleC4Y_Uls_u4p12\[ \]               |
| t_HPSAsstLimY_MtrNm_u4p12\[ \]             |
| k_HPSOutLimit_MtrNm_f32                    |
| k_Quad13DmpMult_Uls_f32                    |
| k_Quad24DmpMult_Uls_f32                    |
| k_QddHwTrqDampKn_Hz_f32                    |
| k_QddMtrVelDampKn_Hz_f32                   |
| k_QDDHwTrqBckLash_HwNm_f32                 |
| k_QDDMtrVelBckLash_MtrRadpS_f32            |
| k_QddSfLFPKn_Hz_f32                        |
| k_HPSbaseC1_MtrNmpMtrRadpS_f32             |
| k_HPSbaseC2_MtrNmpMtrRadpS_f32             |
| k_HPSbaseC3_MtrNmpMtrRadpS_f32             |
| k_HPSbaseC4_MtrNmpMtrRadpS_f32             |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name             | Resolution                      | Units | Value |
|---------------------------|---------------------------------|-------|-------|
| D_DAMPINGCMDMIN_MTRNM_F32 | Single Precision Floating Point | MtrNm | -8.8  |
| D_DAMPINGCMDMAX_MTRNM_F32 | Single Precision Floating Point | MtrNm | 8.8   |

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name                  |
|--------------------------------|
| BC_DAMPING_FAULTINJECTIONPOINT |
| STD_ON                         |
| FLTINJ_DAMPING                 |
| D_2MS_SEC_F32                  |
| D_ZERO_ULS_F32                 |

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

3.  Limit_m

4.  Abs_f32_m

5.  Abs_s16_m

6.  Sign_f32_m

7.  IntplVarXY_u16_u16Xu16Y_Cnt

8.  IntplVarXY_u16_s16Xu16Y_Cnt

9.  TableSize_m

10. LPF_KUpdate_f32_m

11. LPF_OpUpdate_f32_m

## Data Hiding Functions

1.  \<None\>

## Global Functions/Macros Defined by this Module

None

## Local Functions/Macros Used by this MDD only

### MtrVelDepDampScale

| **Function Name**    | MtrVelDepDampScale         | Type    | Min   | Max  | UTP Tol. |
|-------------|-----------------------------|--------|--------|--------|--------|
| **Arguments Passed** | MotorVelCRF_MtrRadpS_T_f32 | Float32 | -1118 | 1118 |          |
|                      | VehicleSpeed_Kph_T_f32     | Float32 | 0     | 512  |          |
|                      | HwTorque_HwNm_T_f32        | Float32 | -10   | 10   |          |
|                      | TempScale_Uls_T_f32        | Float32 | 0     | 10   |          |
| **Return Value**     | ActiveDamping_MtrNm_T_f32  | Float32 | -8.8  | 8.8  | 4.89E-4  |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Damping/doc/mediax/media/image3.emf)

### HPSDampingFn

| **Function Name**    | HPSDampingFn                | Type    | Min   | Max  | UTP Tol.   |
|-------------|-----------------------------|--------|--------|--------|--------|
| **Arguments Passed** | MotorVelCRF_MtrRadpS_T_f32  | Float32 | -1118 | 1118 |            |
|                      | TempScale_Uls_T_f32         | Float32 | 0     | 10   |            |
|                      | VehicleSpeed_Kph_T_f32      | Float32 | 0     | 512  |            |
|                      | BaseAssistStCmp_MtrNm_T_f32 | Float32 | -8.8  | 8.8  |            |
| **Return Value**     | DampingForce_MtrNm_T_f32    | Float32 | -8.8  | 8.8  | 4.89 e^-4^ |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Damping/doc/mediax/media/image4.emf)

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data                       | Value |
|----------------------------|-------|
| MotorVelCRF_MtrRadpS_f32   | 0     |
| HwTorque_HwNm_f32          | 0     |
| VehicleSpeed_Kph_f32       | 0     |
| DampingCmd_MtrNm_f32       | 0     |
| AssistMechTempEst_DegC_f32 | 0     |
| BaseAssistStCmp_MtrNm_f32  | 0     |
| DampingDDFactor_Uls_f32    | 1     |
| DefeatDampingSvc_Cnt_lgc   | FALSE |

## Initialization Functions

### Init: \_Init1

#### Design Rationale

None

#### Module Outputs

None

#### Module Internal 

LPF_KUpdate_f32_m(k_QddHwTrqDampKn_Hz_f32, D_2MS_SEC_F32,
&QDDHwTorqueLPFKSV_Cnt_M_str)

LPF_KUpdate_f32_m(k_QddMtrVelDampKn_Hz_f32, D_2MS_SEC_F32,
&QDDMtrVelLPFKSV_Cnt_M_str)

LPF_KUpdate_f32_m(k_QddSfLFPKn_Hz_f32, D_2MS_SEC_F32,
&QDDStFilt_Cnt_M_str)

LPF_KUpdate_f32_m(k_MtrVelDampLPFKn_Hz_f32, D_2MS_SEC_F32,
&MtrVelLPFKSV_Cnt_M_str)

## Periodic Functions

### Per: \_Per1

#### Design Rationale

None

#### Program Flow Start

Rte_Call_Damping_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

AssistMechTempEst_DegC_T_f32 =
Rte_IRead_Damping_Per1_AssistMechTempEst_DegC_f32()

BaseAssistStCmp_MtrNm_T_f32 =
Rte_IRead_Damping_Per1_AssistCmd_MtrNm_f32()

DampingDDFactor_Uls_T_f32 =
Rte_IRead_Damping_Per1_DampingDDFactor_Uls_f32()

DefeatDampingSvc_Cnt_T_lgc =
Rte_Iread_Damping_Per1_DefeatDampingSvc_Cnt_lgc()

HwTorque_HwNm_T_f32 = Rte_Iread_Damping_Per1_HwTorque_HwNm_f32()

MotorVelCRF_MtrRadpS_T_f32 =
Rte_Iread_Damping_Per1_MotorVelCRF_MtrRadpS_f32()

VehicleSpeed_Kph_T_f32 = Rte_Iread_Damping_Per1_VehicleSpeed_Kph_f32()

#### Calculate Damping Command

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Damping/doc/mediax/media/image5.emf)

#### Store Local copy of outputs into Module Outputs

Rte_Iwrite_Damping_Per1_DampingCmd_MtrNm_f32(DampingCmd_MtrNm_T_f32)

#### Program Flow End

Rte_Call_Damping_Per1_CP1_CheckpointReached()

##  Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

# Execution Requirements

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name | Calling Frequency | System State(s) in which the function is called |
|--------------------------|-----------------|------------------------------|
| Damping_Init1 | On Event          | On Init                                         |
| Damping_Per1  | 2ms               | ALL STATES                                      |

## Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| \<None\>      |                                                  |

#  [section]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module | Software Segment                   |
|--------------------|------------------------------------|
| Damping_Init1      | RTE_START_SEC_AP_DAMPING_APPL_CODE |
| Damping_Per1       | RTE_START_SEC_AP_DAMPING_APPL_CODE |

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module | Software Segment |
|--------------------|------------------|
| MtrVelDepDampScale |                  |
| HPSDampingFn       |                  |

#  [section-1]

#  Known Issues / Limitations With Design

1.  INLINE functions in GlobalMacro.h are not unit tested

#  Revision Control Log

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
<td>Initial MDD</td>
<td>20May11</td>
<td>NRAR</td>
</tr>
<tr class="even">
<td>2</td>
<td>2</td>
<td>Included scaling from driving dynamics.</td>
<td>02-Jun-11</td>
<td>YY</td>
</tr>
<tr class="odd">
<td>3</td>
<td>3</td>
<td>Added Rolling Assist Damping and Filter Kp Blending Interface</td>
<td>14-Jul-11</td>
<td>LWW</td>
</tr>
<tr class="even">
<td>4</td>
<td>4</td>
<td>Made changes to match FDD SF#03 001a</td>
<td>18-Nov-11</td>
<td>VK</td>
</tr>
<tr class="odd">
<td>5</td>
<td>5</td>
<td>Changes done as per FaultInjectionTechnique</td>
<td>1-May-12</td>
<td>NRAR</td>
</tr>
<tr class="even">
<td>6</td>
<td>6</td>
<td>Software segment for internal variable used in the module addd</td>
<td>19-Sep-12</td>
<td>SSK</td>
</tr>
<tr class="odd">
<td>7</td>
<td>7</td>
<td>Implemented SF-03 v006</td>
<td>25-Oct-12</td>
<td>OT</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>9</td>
<td>9</td>
<td>Implemented SF-03 v007</td>
<td>21-Feb-13</td>
<td>Selva</td>
</tr>
<tr class="even">
<td>9</td>
<td>9.1.1</td>
<td><p>Changed the range of</p>
<p>MotorVelCRF_MtrRadpS_T_f32 from +/- 1100 to +/-1118</p></td>
<td>02-May-13</td>
<td>Selva</td>
</tr>
</tbody>
</table>

{% endraw %}