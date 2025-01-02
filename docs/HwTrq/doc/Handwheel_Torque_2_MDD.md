---
layout: default
title: Handwheel_Torque_2_MDD
nav_order: 2
parent: Handwheel Torque
---
{% raw %}
# Module – Handwheel Torque 2 [module-handwheel-torque-2]

# High-Level Description

This module serves as the implementation of the systematic coverage
requirements for the handwheel torque module. Several signals are
calculated in parallel with Handwheel Torque.

# Figures

## Component Diagram

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image1.png"
style="width:2.34792in;height:2.21736in" />

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs                 | Module Outputs |                            |
|-----------------------------------|--|------------------------------------|
| SysCT1ADC_Volt_f32            |                | SysCHwTorqueSqd_HwNmSq_f32 |
| SysCT2ADC_Volt_f32            |                |                            |
| AnaHwTorque_HwNm_f32          |                |                            |
| AnaDiffHwTrq_Volt_f32         |                |                            |
| HwTrqScaleVal_VoltsPerDeg_f32 |                |                            |
| T1TrimVal_Volt_f32            |                |                            |
| T2TrimVal_Volt_f32            |                |                            |

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
<td>SysCHwTorqueSqd_HwNmSq_M_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>100</td>
<td>HWTRQ2_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>SysCTDiagFiltSV_Volt_M_s4p27</td>
<td>2<sup>-27</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ2_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>SysCSSDiagFiltSV_Volt_M_s4p27</td>
<td>2<sup>-27</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ2_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>SysCHwTorqCorrLimErrAcc_Cnt_M_u16</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>HWTRQ2_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>SysCCorrDiagFiltOut_Volt_M_s4p11</td>
<td>2<sup>-11</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ2_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>SysCTDiagFiltOut_Volt_M_s4p11</td>
<td>2<sup>-11</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ2_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>SysCTrqSum_Volt_M_s4p11</td>
<td>2<sup>-11</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ2_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>SysCSumFltOut_Volt_M_u5p11</td>
<td>2<sup>-11</sup></td>
<td>0</td>
<td>5.0</td>
<td>HWTRQ2_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>SysCSSDiagFiltOut_Volt_M_s4p11</td>
<td>2<sup>-11</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ2_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>SysCCorrDiagFiltSV_Volt_M_s4p27</td>
<td>2<sup>-11</sup></td>
<td>-5.0</td>
<td>5.0</td>
<td>HWTRQ2_START_SEC_VAR_SAVED_ZONEH_32</td>
</tr>
<tr class="odd">
<td>SysCAnaHwTorqueSqd_HwNmSq_D_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>100</td>
<td>HWTRQ2_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>SysCHWTorqCorrLimDiff_HwNmSq_D_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>100</td>
<td>HWTRQ2_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>SysCHwTorqCh1vsCh2CorrLim_HwNmSq_D_f32</td>
<td>Single Precision Float</td>
<td>0</td>
<td>100</td>
<td>HWTRQ2_START_SEC_VAR_CLEARED_32</td>
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

| Constant Name                            |
|------------------------------------------|
| k_TbarStiff_NmpDeg_f32                   |
| k_MaxTrqSumLmt_Volts_f32                 |
| k_TdiagLim_Volts_u5p11                   |
| k_CorrDiagFiltActiv_Volts_u5p11          |
| k_CorrDiagKn_Cnts_u16                    |
| k_TdiagCorrLim_Volts_u5p11               |
| k_SSDiagKn_Cnts_u16                      |
| k_SSDiagLim_Volts_u5p11                  |
| t_TDiagFiltKnTbl_Cnt_u16\[\]             |
| k_SSFiltRecLim_Volt_u5p11                |
| t_TDiagIndptTbl_Volts_u5p11\[\]          |
| t_SysCHwTorqCorrLimXAxis_HwNm_u4p12\[\]  |
| t_SysCHwTorqCorrLimYAxis_HwNmSq_u7p9\[\] |
| k_SysCHwTorqCorrLimDiag_Cnt_str          |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name                 | Resolution             | Units    | Value                                                               |
|--------------------------|---------------|--------|------------------------|
| D_SSDIAGNFILTSVLMT_VOLT_S4P27 | 2^-27^                 | Volts    | FPM_Fix_m((uint32)(k_SSDiagLim_Volts_u5p11 + 1), u21p11_T, s4p27_T) |
| D_TWO_ULS_F32                 | Single Precision Float | Unitless | 2                                                                   |
| D_HWTRQLMT_HWNMSQ_F32         | Single Precision Float | HWNMSQ   | 100                                                                 |

####  [section]

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name  |
|----------------|
| D_ZERO_CNT_U16 |

### Module specific Lookup Tables Constants

| Constant Name | Resolution | Value | Software Segment |
|---------------|------------|-------|------------------|
| None          |            |       |                  |

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

1.  FPM_Fix_m

2.  FPM_FloatToFixed_m

3.  FPM_FixedToFloat_m

4.  Abs_f32_m

5.  Abs_s16_m

6.  Limit_m

7.  IntplVarXY_u16_u16Xu16Y_Cnt

8.  TableSize_m

9.  DiagPStep_m

10. DiagNStep_m

11. DiagFailed_m

12. LPF_SvUpdate_s16InFixKTrunc_m

13. LPF_OpUpdate_s16InFixKTrunc_m

## Data Hiding Functions

1.  None

## Global Functions/Macros Defined by this Module

None

## Local Functions/Macros Used by this MDD only

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data                                        | Value |
|---------------------------------------------|-------|
| Rte_InitValue_AnaDiffHwTrq_Volt_f32         | 0     |
| Rte_InitValue_AnaHwTorque_HwNm_f32          | 0     |
| Rte_InitValue_HwTrqScaleVal_VoltsPerDeg_f32 | 0     |
| Rte_InitValue_SysCHwTorqueSqd_HwNmSq_f32    | 0     |
| Rte_InitValue_SysCT1ADC_Volt_f32            | 0     |
| Rte_InitValue_SysCT2ADC_Volt_f32            | 0     |
| Rte_InitValue_T1TrimVal_Volt_f32            | 0     |
| Rte_InitValue_T2TrimVal_Volt_f32            | 0     |

## Initialization Functions

### Init: \_Init1

#### Design Rationale

None

#### Module Outputs

None

#### Module Internal

SysCCorrDiagFiltOut_Volt_M_s4p11= 0

##  Periodic Functions

### Per: \_Per1

#### Design Rationale

None

#### Program Flow Start

Rte_Call_HwTrq2_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

SysCT1ADC_Volt_T_f32 = Rte_IRead_HwTrq2_Per1_SysCT1ADC_Volt_f32()

SysCT2ADC_Volt_T_f32 = Rte_IRead_HwTrq2_Per1_SysCT2ADC_Volt_f32()

#### Compute Alternate Diff Torque

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image2.emf)

#### Store Local copy of outputs into Module Outputs

SysCHwTorqueSqd_HwNmSq_M_f32 = SysCHwTorqueSqd_HwNmSq_T_f32

Rte_IWrite_HwTrq2_Per1_SysCHwTorqueSqd_HwNmSq_f32(SysCHwTorqueSqd_HwNmSq_T_f32)

#### Program Flow End

Rte_Call_HwTrq2_Per1_CP1_CheckpointReached()

### Per: \_Per2

#### Design Rationale

None

#### Program Flow Start

Rte_Call_HwTrq2_Per2_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

AnaHwTorque_HwNm_T_f32 = Rte_IRead_HwTrq2_Per2_AnaHwTorque_HwNm_f32()

Torque1_Volt_T_f32 = Rte_IRead_HwTrq2_Per2_SysCT1ADC_Volt_f32()

Torque2_Volt_T_f32 = Rte_IRead_HwTrq2_Per2_SysCT2ADC_Volt_f32()

SysCHwTorqueSqd_HwNmSq_T_f32 = SysCHwTorqueSqd_HwNmSq_M_f32

T1Trim_Volt_T_f32 = Rte_IRead_HwTrq2_Per2_T1TrimVal_Volt_f32()

T2Trim_Volt_T_f32 = Rte_IRead_HwTrq2_Per2_T2TrimVal_Volt_f32()

CorrDiagFiltOut_Volt_T_s4p11 = SysCCorrDiagFiltOut_Volt_M_s4p11

TDiagFiltSV_Volt_T_s4p27 = SysCTDiagFiltSV_Volt_M_s4p27

#### Systematic Cross Check Hw Diff Torque

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image3.emf)

#### T1 vs T2 Comparison Diagnostic

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image4.emf)

#### Store Local copy of outputs into Module Outputs

SysCAnaHwTorqueSqd_HwNmSq_D_f32 = AnaHwTorqueSqd_HwNmSq_T_f32

SysCHWTorqCorrLimDiff_HwNmSq_D_f32 = SysCHwTorqCorrLimDiff_HwNmSq_T_f32

SysCHwTorqCh1vsCh2CorrLim_HwNmSq_D_f32 =
SysCHwTorqCh1vsCh2CorrLim_HwNmSq_T_f32

#### Program Flow End

Rte_Call_HwTrq2_Per2_CP1_CheckpointReached()

### Per: \_Per3

#### Design Rationale

None

#### Program Flow Start

Rte_Call_HwTrq2_Per3_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

HwTrqComp_Volt_T_f32 = Rte_IRead_HwTrq2_Per3_AnaDiffHwTrq_Volt_f32()

TDiagFiltOut_Volt_T_s4p11 = SysCTDiagFiltOut_Volt_M_s4p11

TrqSum_Volt_T_s4p11 = SysCTrqSum_Volt_M_s4p11

CorrDiagFiltOut_Volt_T_s4p11 = SysCCorrDiagFiltOut_Volt_M_s4p11

SSDiagFiltSV_Volt_T_s4p27 = SysCSSDiagFiltSV_Volt_M_s4p27

CorrDiagFiltSV_Volt_T_s4p27 = SysCCorrDiagFiltSV_Volt_M_s4p27

#### Steady State Fault Detection, Common Mode Compensation Function

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/HwTrq/doc/mediax/media/image5.emf)

#### Store Local copy of outputs into Module Outputs

SysCCorrDiagFiltOut_Volt_M_s4p11 = CorrDiagFiltOut_Volt_T_s4p11

#### Program Flow End

Rte_Call_HwTrq2_Per3_CP1_CheckpointReached()

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
| HwTrq2_Init1  | On Event          | On Init                                         |
| HwTrq2_Per1   | 2 ms              | ALL                                             |
| HwTrq2_Per2   | 4 ms              | ALL                                             |
| HwTrq2_Per3   | 100 ms            | ALL                                             |

## Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| None          |                                                  |

#  [section-2]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module | Software Segment                  |
|--------------------|-----------------------------------|
| HwTrq2_Init1       | RTE_START_SEC_SA_HWTRQ2_APPL_CODE |
| HwTrq2_Per1        | RTE_START_SEC_SA_HWTRQ2_APPL_CODE |
| HwTrq2_Per2        | RTE_START_SEC_SA_HWTRQ2_APPL_CODE |
| HwTrq2_Per3        | RTE_START_SEC_SA_HWTRQ2_APPL_CODE |

##  [section-3]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module | Software Segment |
|--------------------|------------------|
| None               |                  |

#  [section-4]

#  Known Issues / Limitations With Design

1.  INLINE functions defined in GlobalMacro.h are not unit tested.

#  Revision Control Log

| **Item \#** | **Rev \#** | **Change Description**                                                           | **Date**  | **Author Initials** |
|------|------|--------------------------------------------|---------|---------|
| 1           | 1.0        | Initial Version                                                                  | 12-Oct-12 | OT                  |
| 2           | 2.0        | Anomaly 2824 – T1 vs T2 comparison cal usage                                     | 24-Oct-12 | OT                  |
| 3           | 3.0        | Updates for Trim and Scale values, update for anomaly 3994                       | 30-Oct-12 | OT                  |
| 4           | 4.0        | ICR \# 3928: Software range limit applied for SysCHwTorqueSqd_HwNmSq_T_f32       | 06-Feb-13 | SP                  |
| 5           | 5.0        | ICR \#7140: Store the values of steady state filter and Common Mode Compensation | 22-Apr-13 | SP                  |
| 6           | 6.0        | Update to initialize Corr Filter output to zero instead of EEPROM value.         | 01-May-13 | LWW                 |

{% endraw %}