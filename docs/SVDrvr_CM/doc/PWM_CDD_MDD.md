---
layout: default
title: PWM_CDD_MDD
nav_order: 2
parent: Component
---
{% raw %}
# Module –  [module]

# High-Level Description

Non-AUTOSAR PWM driver required to perform EPS motor control PWM
profiles.

# Figures

## Component Diagram

This diagram shows all data that is shared between functions within the
module.

No data sharing

### Diagram – Function (Per1)

None (For more refer section 6)

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs (Global Variable Name) | Module Outputs (Global Variable Name) |
|----------------------------------|--------------------------------------|
| CDD_PhaseAdvFinal_Cnt_G_u16\[2\]     | CDD_DutyCycleSmall_Cnt_G_u16\[2\]     |
| CDD_CommOffset_Cnt_G_u16\[2\]        | CDD_PWMDutyCycleASum_Cnt_G_u32\[2\]   |
| CDD_MtrPosElec_Rev_G_u0p16\[2\]      | CDD_PWMDutyCycleBSum_Cnt_G_u32\[2\]   |
| CDD_PwmDisable_Cnt_G_lgc\[2\]        | CDD_PWMDutyCycleCSum_Cnt_G_u32\[2\]   |
| CDD_MtrTrqCmdSign_Cnt_G_s16\[2\]     | CDD_PWMPeriodSum_Cnt_G_u32\[2\]       |
| CDD_DeadTimeComp_Uls_G_u8p8\[2\]     | CDD_PhsReasA_Cnt_G_u16\[2\]           |
| CDD_ModIdxFinal_Uls_G_u16p16\[2\]    | CDD_PhsReasB_Cnt_G_u16\[2\]           |
| CDD_CDDDataAccessBfr_Cnt_G_u16       | CDD_PhsReasC_Cnt_G_u16\[2\]           |
| CDD_AppDataFwdPthAccessBfr_Cnt_G_u16 | CDD_DCPhsComp_Cnt_G_u16\[3\]          |
| CDD_AppDataFbkPthAccessBfr_Cnt_G_u16 | CDD_PWMPeriod_Cnt_G_u16               |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table style="width:100%;">
<colgroup>
<col style="width: 36%" />
<col style="width: 12%" />
<col style="width: 13%" />
<col style="width: 12%" />
<col style="width: 24%" />
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
<td>CDD_SeedPWMDither_Cnt_M_u16</td>
<td>N/A </td>
<td>N/A </td>
<td>N/A </td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>CDD_DitherFlt1SV_Cnt_M_u16</td>
<td>N/A </td>
<td>N/A </td>
<td>N/A </td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>CDD_DitherFlt2SV_Cnt_M_u16</td>
<td>N/A </td>
<td>N/A </td>
<td>N/A </td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>CDD_PhaseOffset_Rev_M_u0p16[3]</td>
<td>N/A </td>
<td>N/A </td>
<td>N/A </td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>CDD_NextDCSmall_Cnt_M_u16</td>
<td>N/A </td>
<td>N/A </td>
<td>N/A </td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>PrevDCPhsAComp_Cnt_M_u16p0</td>
<td>1</td>
<td>0</td>
<td>7150</td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>PrevDCPhsBComp_Cnt_M_u16p0</td>
<td>1</td>
<td>0</td>
<td>7150</td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>PrevDCPhsCComp_Cnt_M_u16p0</td>
<td>1</td>
<td>0</td>
<td>7150</td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DCPhsAComp_Cnt_M_u16p0</td>
<td>1</td>
<td>0</td>
<td>7150</td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>DCPhsBComp_Cnt_M_u16p0</td>
<td>1</td>
<td>0</td>
<td>7150</td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DCPhsCComp_Cnt_M_u16p0</td>
<td>1</td>
<td>0</td>
<td>7150</td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>PrevPWMPeriod_Cnt_M_u16</td>
<td>1</td>
<td>2950</td>
<td>7150</td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>PWMPeriod_Cnt_M_u16</td>
<td>1</td>
<td>2950</td>
<td>7150</td>
<td>PWMCDD_START_SEC_VAR_CLEARED_16</td>
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

| Constant Name            |
|--------------------------|
| k_ADCTrig1Offset_Cnt_s16 |
| k_ADCTrig2Offset_Cnt_s16 |
| k_DitherLPFKn_Cnt_u16    |
| k_PwmDeadBand_Cnt_u16    |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 8%" />
<col style="width: 21%" />
<col style="width: 41%" />
</colgroup>
<thead>
<tr class="header">
<th>Constant Name</th>
<th>Resolution</th>
<th>Units</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>d_NhetFreq_Hz_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>75000000UL</td>
</tr>
<tr class="even">
<td>d_HalfPrec8_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>128U</td>
</tr>
<tr class="odd">
<td>d_HalfPrec16_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>32768UL</td>
</tr>
<tr class="even">
<td>d_Scaler1_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>1U</td>
</tr>
<tr class="odd">
<td>d_Scaler8_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>8U</td>
</tr>
<tr class="even">
<td>d_Scaler16_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>16U</td>
</tr>
<tr class="odd">
<td>d_SeedInitial_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>10U</td>
</tr>
<tr class="even">
<td>d_SeedMultiplier_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>57U</td>
</tr>
<tr class="odd">
<td>d_SeedOffset_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>1U</td>
</tr>
<tr class="even">
<td>d_PWMClockFreq_Hz_u32</td>
<td>1</td>
<td>U32</td>
<td>75000000UL</td>
</tr>
<tr class="odd">
<td>d_PWMFreqBase_Hz_u16</td>
<td>1</td>
<td>u16</td>
<td>16000U</td>
</tr>
<tr class="even">
<td>d_PWMFreqDither_Hz_u16</td>
<td>1</td>
<td>u16</td>
<td>2000U</td>
</tr>
<tr class="odd">
<td>d_PwmPrdMax_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>(d_PwmFreq_Hz_Cnt_u16 /(uint32)(d_PWMFreqBase_Hz_u16 -
d_PWMFreqDither_Hz_u16))</td>
</tr>
<tr class="even">
<td>d_PwmPrdMin_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td><p>d_PwmFreq_Hz_Cnt_u16 /(uint32)(d_PWMFreqBase_Hz_u16 )</p>
<p>+ d_PWMFreqDither_Hz_u16)</p></td>
</tr>
<tr class="odd">
<td>d_PwmPrdRange_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>(d_PwmPrdMax_Cnt_u16-(uint16)d_PwmPrdMin_Cnt_u16)</td>
</tr>
<tr class="even">
<td>d_PwmPrdInitVal_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>((uint16)(d_PWMClockFreq_Hz_u32/(uint32)d_PWMFreqBase_Hz_u16))</td>
</tr>
<tr class="odd">
<td>d_FilterKdBits_Cnt_U16</td>
<td>1</td>
<td>u16</td>
<td>5U</td>
</tr>
<tr class="even">
<td>d_MaxModIdx_Uls_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>(FPM_InitFixedPoint_m(0.9999847412109375,u0p16_T))</td>
</tr>
<tr class="odd">
<td>d_MinModIdx_Uls_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>(FPM_InitFixedPoint_m(0.0,u0p16_T))</td>
</tr>
<tr class="even">
<td>d_120Deg_Rev_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>(FPM_InitFixedPoint_m(0.3333333333,u0p16_T))</td>
</tr>
<tr class="odd">
<td>d_0Deg_Rev_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>(FPM_InitFixedPoint_m(0.0,u0p16_T))</td>
</tr>
<tr class="even">
<td>d_30Deg_Rev_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>(FPM_InitFixedPoint_m(0.0833333333,u0p16_T))</td>
</tr>
<tr class="odd">
<td>d_60Deg_Rev_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>(FPM_InitFixedPoint_m(0.1666666666,u0p16_T))</td>
</tr>
<tr class="even">
<td>d_240Deg_Rev_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>(FPM_InitFixedPoint_m(0.6666666666,u0p16_T))</td>
</tr>
<tr class="odd">
<td>d_180Deg_Rev_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>(FPM_InitFixedPoint_m(0.5,u0p16_T))</td>
</tr>
<tr class="even">
<td>d_PhaseAOffsetNrm_Rev_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>d_0Deg_Rev_u0p16</td>
</tr>
<tr class="odd">
<td>d_PhaseBOffsetNrm_Rev_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>((uint16)(d_PhaseAOffsetNrm_Rev_u0p16-d_120Deg_Rev_u0p16))</td>
</tr>
<tr class="even">
<td>d_PhaseCOffsetNrm_Rev_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>(d_PhaseAOffsetNrm_Rev_u0p16+d_120Deg_Rev_u0p16)</td>
</tr>
<tr class="odd">
<td>d_PhaseAOffsetInv_Rev_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>d_60Deg_Rev_u0p16</td>
</tr>
<tr class="even">
<td>d_PhaseBOffsetInv_Rev_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>(d_PhaseAOffsetInv_Rev_u0p16+d_120Deg_Rev_u0p16)</td>
</tr>
<tr class="odd">
<td>d_PhaseCOffsetInv_Rev_u0p16</td>
<td>2<sup>-16</sup></td>
<td>u0p16</td>
<td>((uint16)(d_PhaseAOffsetInv_Rev_u0p16-d_120Deg_Rev_u0p16))</td>
</tr>
<tr class="even">
<td>d_RevpCnt_Uls_u0p32</td>
<td>2<sup>-32</sup></td>
<td>u0p32</td>
<td>699051UL/*(FPM_InitFixedPoint_m(1/d_PACntspRev_Uls_u16p0,u0p32_T))*/</td>
</tr>
<tr class="odd">
<td>d_PACntspRev_Uls_u16p0</td>
<td>1</td>
<td>u16p0</td>
<td>6144U</td>
</tr>
<tr class="even">
<td>d_SinePhsToGndTblSize_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>2049U</td>
</tr>
<tr class="odd">
<td>d_MSBMask_Cnt_u16</td>
<td>1</td>
<td>u16</td>
<td>0x8000U</td>
</tr>
<tr class="even">
<td>D_POSITIVEONE_CNT_S8</td>
<td>1</td>
<td>s8</td>
<td>1</td>
</tr>
<tr class="odd">
<td>D_PHSAIDX_CNT_U16</td>
<td>1</td>
<td>u16</td>
<td>0U</td>
</tr>
<tr class="even">
<td>D_PHSBIDX_CNT_ U16</td>
<td>1</td>
<td>u16</td>
<td>1U</td>
</tr>
<tr class="odd">
<td>D_PHSCIDX_CNT_ U16</td>
<td>1</td>
<td>u16</td>
<td>2U</td>
</tr>
</tbody>
</table>

####  [section]

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name |
|---------------|
|               |
|               |

### Module specific Lookup Tables Constants

| Constant Name                         | Resolution | Value                                                                                                       | Software Segment |
|-----------------------|---------|-----------------------------|------------|
| t_S_SinePhsToGndTbl_Cnt_u0p16\[2049\] | 2^-16^     | ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/SVDrvr_CM/doc/mediax/media/image1.emf) | None             |

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

The library functions / Macros that are called by the various sub
modules are identified below,

1.  FPM_FloatToFixed_m()

2.  FPM_FixedToFloat_m()

3.  Limit_m()

4.  Max_m()

5.  Min_m()

6.  CDD_Read_PhaseAdvanceFinal_Rev_u0p16()

## Data Hiding Functions

1.  None

## Global Functions/Macros Defined by this Module

### Global Function \#1

| **Function Name**    | CDD_ApplyPWMMtrElecMechPol  | Type   | Min | Max | UTP Tol. |
|----------------|------------------------------|----------|------|------|------|
| **Arguments Passed** | MtrElecMechPol_Cnt_s8       | Sint 8 |     |     |          |
|                      |                             |        |     |     |          |
| **Return Value**     | CDD_PhaseOffset_Rev_M_u0p16 | Uint16 |     |     |          |

#### Description

Applies the offsets needed for MtrElecMech Polarity Setting

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/SVDrvr_CM/doc/mediax/media/image2.emf)

### Global Function \#2

| **Function Name**    | CDDPorts_ClearPhsReasSum       | Type   | Min | Max | UTP Tol. |
|---------------|------------------------------|----------|------|------|------|
| **Arguments Passed** | DataAccessBfr_Cnt_T_u16        | Uint16 |     |     |          |
| **Return Value**     | CDD_PWMDutyCycleASum_Cnt_G_u32 | Uint32 |     |     |          |
|                      | CDD_PWMDutyCycleBSum_Cnt_G_u32 | Uint32 |     |     |          |
|                      | CDD_PWMDutyCycleCSum_Cnt_G_u32 | Uint32 |     |     |          |
|                      | CDD_PWMPeriodSum_Cnt_G_u32     | Uint32 |     |     |          |

#### Description

## ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/SVDrvr_CM/doc/mediax/media/image3.emf) [section-1]

## Local Functions/Macros Used by this MDD only

> Local Macros are defined in PWMCDD_Cfg.h file as the return
> values/calculation of return values are more project specific

### Local Function \#1

| **Function Name**    | PwmPeriodDither_u16 | Type   | Min | Max | UTP Tol. |
|----------------------|---------------------|--------|-----|-----|----------|
| **Arguments Passed** | None                |        |     |     |          |
|                      |                     |        |     |     |          |
| **Return Value**     | PWMPeriod_Cnt_T_u16 | Unit16 |     |     |          |

#### Description

Generates the next PWM Period  
![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/SVDrvr_CM/doc/mediax/media/image4.emf)

### Local Function \#2

| **Function Name**    | DeadTimeComp_u16p0      | Type | Min | Max | UTP Tol. |
|----------------------|-------------------------|------|-----|-----|----------|
| **Arguments Passed** | DCPhsUnComp_Cnt_T_u24p8 |      |     |     |          |
|                      | Phase_Rev_T_u0p16       |      |     |     |          |
| **Return Value**     | DCPhsComp_Cnt_T_u16p0   |      |     |     |          |

#### Description

Applies the dead time compensation

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/SVDrvr_CM/doc/mediax/media/image5.wmf)

### Local Function \#3

| **Function Name**    | ModIndxPhase_u0p16     | Type | Min | Max | UTP Tol. |
|----------------------|------------------------|------|-----|-----|----------|
| **Arguments Passed** | PhaseIndex_Rev_T_u0p16 |      |     |     |          |
|                      |                        |      |     |     |          |
| **Return Value**     | ModIdxPhs_Cnt_T_u0p16  |      |     |     |          |

#### Description

Calculates ModIndx for each phase

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/SVDrvr_CM/doc/mediax/media/image6.emf)

### Local Macro \#1

| **Function Name**    | CDD_Read_PhaseAdvanceFinal_Rev_u0p16 | Type  | Min | Max | UTP Tol. |
|-----------------|------------------------------|----------|------|------|------|
| **Arguments Passed** | &PhaseAdvFinal_Rev_T_u0p16           | U0p16 | 0   | 1   |          |
|                      |                                      |       |     |     |          |
| **Return Value**     | none                                 |       |     |     |          |

#### Description

Converts phase advance final from count units to rev units. (Units type
conversion)

### Local Macro \#2

| **Function Name**    | CDD_Read_CorrectedMtrPos_Rev_u0p16 | Type  | Min | Max | UTP Tol. |
|-----------------|------------------------------|----------|------|------|------|
| **Arguments Passed** | & CorrectedMtrPos_Rev_T_u0p16      | U0p16 | 0   | 1   |          |
|                      |                                    |       |     |     |          |
| **Return Value**     | none                               |       |     |     |          |

#### Description

Reads the Motor position global variable and assign it to
“CorrectedMtrPos_Rev_T_u0p16”

### Local Macro \#3

| **Function Name**    | CDD_Read_CommOffset_Cnt_u16 | Type | Min | Max   | UTP Tol. |
|-----------------|------------------------------|----------|------|------|------|
| **Arguments Passed** | &CommOffset_Cnt_T_u16       | U16  | 0   | 2\^16 |          |
|                      |                             |      |     |       |          |
| **Return Value**     | none                        |      |     |       |          |

#### Description

Reads the Commutation offset and assign it global variable and assign it
to “CommOffset_Cnt_T_u16”

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data | Value |
|------|-------|
| None |       |

## Initialization Functions

### Init: \_Init

#### Design Rationale

None

#### Module Outputs

None

#### Module Internal 

CDD_DutyCycleSmall_Cnt_G_u16\[CDD_CDDDataAccessBfr_Cnt_G_u16\] = 0U;

CDD_SeedPWMDither_Cnt_M_u16 = d_SeedInitial_Cnt_u16

##  Periodic Functions

### Per: \_Per1

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

None

#### Processing of function

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/SVDrvr_CM/doc/mediax/media/image7.emf)![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/SVDrvr_CM/doc/mediax/media/image8.emf)![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/SVDrvr_CM/doc/mediax/media/image9.emf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

### SCom: \_Scom\_

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

None

#### Processing of function

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

##  

# Execution Requirements

## Execution Sequence of the Module

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name | Calling Frequency | System State(s) in which the function is called |
|--------------------------|-----------------|------------------------------|
| PwmCdd_Init   | Once              | EcuStartup                                      |
| PwmCdd_Per1   | Motor control ISR | All states                                      |

## Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| None          |                                                  |

#  [section-3]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module | Software Segment |
|--------------------|------------------|
| None               |                  |

##  [section-4]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module | Software Segment |
|--------------------|------------------|
| None               |                  |

#  [section-5]

#  Known Issues / Limitations With Design

1.  INLINE functions defined in GlobalMacro.h are not unit tested.

#  Revision Control Log

| **Item \#** | **Rev \#** | **Change Description**                                                                                                                                          | **Date**    | **Author Initials** |
|------|------|--------------------------------------------|---------|---------|
| 1           | 1.0        | Initial Version                                                                                                                                                 | 17 Oct 2012 | Selva               |
| 2           | 2.0        | Nhet specific names are changed to common names and project specific variables assignment are moved to configuration Macros to keep PWMCdd same across projects | 15-Feb-12   | Selva               |
| 3           | 3.0        | Changed the Buffer index of CDD_ModIdxFinal_Uls_G_u16p16 from "CDD_AppDataFwdPthAccessBfr_Cnt_G_u16" to "CDD_CDDDataAccessBfr_Cnt_G_u16"                        | 19-Apr-13   | Selva               |

\\

{% endraw %}