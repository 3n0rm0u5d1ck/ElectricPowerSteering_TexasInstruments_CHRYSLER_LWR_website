---
layout: default
title: Serial_Communication_Output_MDD
nav_order: 17
parent: Chrysler TMS570 Project
---
{% raw %}
# Module – Serial Communications Output [module-serial-communications-output]

# High-Level Description

The **Serial Communications** **Output** module provides a signal level
interface between the EPS application layer and the serial
communications software. Provide for the network management
functionality for the serial communications interface. This module will
be customized for each distinct vehicle platform. This module will be
responsible for converting the range and resolution of the Application
Layer variables to the range and resolution of the associated serial
communications signals.

This module processes the data for transmit signals that are sent from
the EPS controller to other ECUs on the communication bus. Global
application input data is scaled appropriately and then transferred to
the serial communications Interaction Layer using function calls or
macros provided. Similarly, the Serial Communications **Input** module,
takes the signal data that is received from the Interaction Layer,
scales the data as required by the EPS controller and transfers the
updated global data to the EPS application software.

# Figures

## Component Diagram

This diagram shows all data that is shared between functions within the
module.

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image1.png"
style="width:2.51528in;height:4.2in" />

# Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

(Note: Full variable names required in table.)

|                                       |                                       |
|-----------------------------------|-------------------------------------|
| Module Inputs (Global Variable Name)  | Module Outputs (Global Variable Name) |
| ATermActive_Cnt_lgc                   |                                       |
| ActiveFunctionBits_Cnt_u08            |                                       |
| ActiveTunSet_Cnt_u16                  |                                       |
| CanMsgReceived_Cnt_lgc                |                                       |
| DSTEOLDisable_Cnt_lgc                 |                                       |
| DSTExtSystemFltActive_Cnt_lgc         |                                       |
| SystemState_Mode                      |                                       |
| DSTState_Cnt_u08                      |                                       |
| DiagStsRecRmpToZeroFltPres_Cnt_lgc(   |                                       |
| DiagStsNonRecRmpToZeroFltPres_Cnt_lgc |                                       |
| RampDwnStatusComplete_Cnt_lgc         |                                       |
| EngRPM_Cnt_u16                        |                                       |
| HaLFState_Cnt_u08                     |                                       |
| HaLFSuspend_Cnt_lgc                   |                                       |
| HandsOnDetect_Cnt_lgc                 |                                       |
| HwTrq_HwNm_f32                        |                                       |
| PrkAssistState_Cnt_u08                |                                       |
| PrkAssistSuspend_Cnt_lgc              |                                       |
| SrlComHwTrqValid_Cnt_lgc              |                                       |
| SrlComVehSpdValid_Cnt_lgc             |                                       |
| SumLmtTrqCmd_MtrNm_f32                |                                       |
| SupplyCurrent_Amp_f32                 |                                       |
| VehicleSpeed_Kph_f32                  |                                       |
| CFG_STAT_RQ_Cnt_u16                   |                                       |
| EPS_MODE_REQ_Cnt_u16                  |                                       |
| CTermActive_Cnt_lgc                   |                                       |
| SpStPrsnt_Cnt_lgc                     |                                       |
| OutputRampMult_Uls_f32;               |                                       |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table style="width:100%;">
<colgroup>
<col style="width: 35%" />
<col style="width: 14%" />
<col style="width: 13%" />
<col style="width: 12%" />
<col style="width: 22%" />
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
<td>NMBusWaitSleepCancel_Cnt_M_lgc</td>
<td>1</td>
<td>FALSE</td>
<td>TRUE</td>
<td>SRLCOMOUTPUT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>CanMsgReceived_Cnt_M_lgc</td>
<td>1</td>
<td>FALSE</td>
<td>TRUE</td>
<td>SRLCOMOUTPUT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>MtrTrqValid_Cnt_M_lgc</td>
<td>1</td>
<td>FALSE</td>
<td>TRUE</td>
<td>SRLCOMOUTPUT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>MCEPS1_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>SRLCOMOUTPUT_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>NMFirstMsg_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>SRLCOMOUTPUT_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>NMBusWaitSleepCancel_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>SRLCOMOUTPUT_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>EPS1_M_str</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>SRLCOMOUTPUT_START_SEC_VAR_CLEARED_32</td>
</tr>
</tbody>
</table>

### User defined typedef definition/declaration 

This section documents any user types uniquely used for the module.

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 29%" />
<col style="width: 21%" />
<col style="width: 10%" />
<col style="width: 10%" />
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
</tbody>
</table>

#   [section]

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

|                             |
|-----------------------------|
| Constant Name               |
| k_VehSpdAstLmt_Kph_f32      |
| k_StrClmTrqPolarity_Cnt_s08 |
| k_InvGearRatio_Uls_f32      |
| k_StrClmTrqPolarity_Cnt_s08 |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

|                                    |             |
|------------------------------------|-------------|
| Constant Name                      | Value       |
| D_SUPPLYCURROFFSET_ULS_F32         | 50.0        |
| D_EPSCURR_HILMT_AMP_F32            | 203.0       |
| D_EPSCURR_LOLMT_AMP_F32            | -50.0       |
| D_CRCINIT_CNT_U8                   | 0xFF        |
| D_CRCXORVALUE_CNT_U8               | 0xFF        |
| D_COUNTERCYCLE16_CNT_U16           | 0x10        |
| D_UNUSED0MSG221_CNT_U8             | 0xFF        |
| D_STRCLMTRQLOLIMIT_HWNM_F32        | -8.0        |
| D_STRCLMTRQHILIMIT_HWNM_F32        | 7\. 9765625 |
| D_STRCLMTRQOFFSET_HWNM_F32         | 8.0         |
| D_STRCLMTRQ_SIGNOTAVAL_CNTS_U16    | 0x07FF      |
| D_ASSTTRQ_HILMT_HWNM_F32           | 104.65      |
| D_ASSTTRQ_LOLMT_HWNM_F32           | -100.0      |
| D_ASSTTRQ_OFFSET_HWNM_F32          | 100.0       |
| D_ASSTTRQ_ENGTOCNTS_SCALE_HWNM_F32 | 20.0        |
| D_HALFSTATEINACTIVE_CNT_U08        | 0           |
| D_HALFSTATEACTIVE_CNT_U08          | 1           |
| D_HALFSTATEINHIBITED_CNT_U08       | 2           |
| D_HALFSTATERECOVERABLE_CNT_U08     | 3           |
| D_PPPAFUNCBIT_CNT_U08              | 1           |
| D_DSTFUNCBIT_CNT_U08               | 2           |
| D_HALFFUNCBIT_CNT_U08              | 4           |
| D_PASTATEINACTIVE_CNT_U08          | 0           |
| D_PASTATEACTIVE_CNT_U08            | 1           |
| D_PASTATEINHIBITED_CNT_U08         | 2           |
| D_PASTATERECOVERABLE_CNT_U08       | 3           |
| D_EPSMTRTRQ_HILMT_MTRNM_F32        | 1.998046875 |
| D_EPSMTRTRQ_LOLMT_MTRNM_F32        | -2.0        |
| D_EPSMTRTRQ_OFFSET_ULS_F32         | 2.0         |
| D_EPSMTRTRQ_SIGNOTAVAL_CNT_U16     | 0xFFFF      |
| D_NMAWAKENWST_CNT_U08              | 0x01U       |
| D_NMAWAKEDIAGACTV_CNT_U08          | 0x02        |
| D_NMAWAKERAMPOUT_CNT_U08           | 0x04        |
| D_NMAWAKEVSSHIGH_CNT_U08           | 0x08        |
| D_NMAWAKEENGRPMHIGH_CNT_U08        | 0x10        |
| D_NMAWAKEIGNHIGH_CNT_U08           | 0x20        |
| D_NMSTARTUPSLEEPDELAY_MS_U32       | 0x50000     |
| D_NMWAKEUPREASONIGN_CNT_U08        | 0x01        |
| D_ENGONRPM_CNT_U16                 | 0x12        |
| D_ENGRPMINVLD_CNT_U16              | 0xFFFF      |
| EPSA1_AsstStat                     |             |
| *EPSA1_AsstStat_Active*            | 0x00        |
| *EPSA1_AsstStat_Off*               | 0x01        |
| *EPSA1_AsstStat_ThrmRed*           | 0x02        |
| *EPSA1_AsstStat_SigNotAval*        | 0x07        |
| EPSA1_WarnDisp                     |             |
| *EPSA1_WarnDisp_FuncActive*        | 0x00        |
| *EPSA1_WarnDisp_ServPwrSteer*      | 0x01        |
| *EPSA1_WarnDisp_PwrSteerOvTmp*     | 0x02        |
| *EPSA1_WarnDisp_ServReqdHighPri*   | 0x03        |
| *EPSA1_WarnDisp_SigNotAval*        | 0x07        |
| kDescStateSessionDefault           | 0x01        |
| D_TXAWAKE_NWST_CNT_U08             | 0x01        |
| D_TXAWAKE_DIAGACTIVE_CNT_U08       | 0x02        |
| D_TXAWAKE_RAMPOUT_CNT_U08          | 0x04        |
| D_TXAWAKE_VSSHIGH_CNT_U08          | 0x08        |
| D_TXAWAKE_ENGRPM_CNT_U08           | 0x10        |
| D_TXAWAKE_IGNHIGH_CNT_U08          | 0x20        |
| D_SLEEPINDICATORCLEAR_U08          | 0x40        |
| D_SLEEPSTATE_U08                   | 0x00U       |
| D_ENGONRPM_CNT_U16                 | 0x12C       |
| D_ENGRPMINVLD_CNT_U16              | 0xFFFF      |
| TOCSTATE_PNA                       | 2           |

####   [section-1]

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

|               |
|---------------|
| Constant Name |
|               |
|               |
|               |
|               |
|               |

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as
other tables)

|               |            |       |                  |
|---------------|------------|-------|------------------|
| Constant Name | Resolution | Value | Software Segment |
| none          |            |       |                  |

# Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library functions / Macros that are called by the various sub
modules are identified below,

1.  None

## Data Hiding Functions

The data hiding functions / macros used in this module are identified
below,

## Local Functions/Macros Used by this MDD only

(Note if they are defined in another source file, then reference the
appropriate header file)

The local functions/macros in this module are identified below,

1.  CalcCRC_EPS_1( void)

2.  DetermineWarnDisp(void)

3.  ScaleSignal_u16( float32 Signal_Uls_T_f32, float32 LoLmt_Uls_T_f32,
    float32 HiLmt_Uls_T_f32, float32 Scale_Uls_T_f32, Offset_Uls_T_f32)

4.  SrlComOutput_WriteBits(uint32 Data_T_Cnt_u32, uint8\*
    Buffer_T_Cnt_u08, uint16 StartBit_Cnt_T_u16, uint16
    EndBit_Cnt_T_u16)

#   [section-2]

# Software Module Implementation

## Initialization Functions

### Init: SrlComOutput_Init1

#### Design Rationale

#### Module Outputs

#### Module Internal 

##### Set Default Messages

EPSA1_T_str.s.unused0 = 0x00

**SetValueTxEPS_AsstStat**(EPSA1_T_str, 0x01)

**SetValueTxEPS_Warn_Disp_Rq**(EPSA1_T_str, 0x00)

EPSA1_T_str.s.unused1 = 0x00

EPSA1_T_str.s.unused2 = 0x00

**SetValueTxEPS_Curr**(EPSA1_T_str, 0xFF)

EPSA1_T_str.s.unused3 = 0x00

EPSA1_T_str.s.unused4 = 0x00

EPSA1_T_str.s.unused5 = 0x00

EPSA1_T_str.s.unused6 = 0x00

**dbkPutTxEPS_A1_PKT**(EPSA1_T_str)

**CclEnableCommunication**()

**DpmExternalRequest**(DPM_EPS)

**SetValueTxWakeupRsn_EPS**(WakeupEPS_T_str,
D_NMWAKEUPREASONIGN_CNT_U08)

**SetValueTxWakeupCnt**(WakeupEPS_T_str, 0x00)

WakeupEPS_T_str.s.unused0 = 0x00

**nmpduPutWakeup_EPS**(WakeupEPS_T_str)

**SetValueTxTOI_Act_Sts**(EPS1_M_str, 0x00)

**SetValueTxStrClmTrqVD**(EPS1_M_str, 0x00)

**SetValueTxStrClmTrq**(EPS1_M_str, 0x07FF)

**SetValueTxAssistanceTorque**(EPS1_M_str, 0x00)

**SetValueTxPTSDriveStyleSts**(EPS1_M_str, 0x00)

**SetValueTxDSTTorqueOverlayFault**(EPS1_M_str, 0x00)

**SetValueTxHALFTorqueOverlayFault**(EPS1_M_str, 0x00)

**SetValueTxHALFTorqueOverlayIntActivated**(EPS1_M_str, 0x00)

**SetValueTxEPSMotorTorque**(EPS1_M_str, 0x00)

**SetValueTxEPSMotorTorqueValidData**(EPS1_M_str, 0x00)

**SetValueTxEPSHandsOnRecognition**(EPS1_M_str, 0x00)

**SetValueTxEPSTemporaryDeactivationLDW**(EPS1_M_str, 0x00)

**SetValueTxPTSTorqueOverlayFault**(EPS1_M_str, 0x00)

**SetValueTxPTSTorqueOverlayIntActivated**(EPS1_M_str, 0x00)

**SetValueTxMC_EPS_1**(EPS1_M_str, MCEPS1_Cnt_M_u08)

**CalcCRC_EPS_1**()

**dbkPutTxEPS_1_PKT**(EPS1_M_str)

**Rte_Call_SystemTime_GetSystemTime_mS_u32**(&NMFirstMsg_mS_M_u32)

## Periodic Functions

### Per: SrlComOutput_Per1 

#### Design Rationale

Process and update Transmit signal data.

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

**Rte_Read_ATermActive_Cnt_lgc**(&ATermActive_Cnt_T_lgc)

**Rte_Read_EngRPM_Cnt_u16**(&EngRPM_Cnt_T_u16)

**Rte_Read_VehicleSpeed_Kph_f32**(&VehSpd_Kph_T_f32)

**Rte_Read_SrlComVehSpdValid_Cnt_lgc**(&VehSpdValid_Cnt_T_lgc)

**Rte_Read_RampDwnStatusComplete_Cnt_lgc**(&RampStatusComplete_T_Cnt_lgc)

**Rte_Read_Ap_SrlComOutput_CanMsgReceived_Cnt_lgc**(&CanMsgReceived_Cnt_T_lgc)

Rte_Read_Ap_SrlComOutput_OutputRampMult_Uls_f32(&OutputRampMult_Uls_T_f32)

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image2.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image3.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image4.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image5.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image6.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image7.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image8.wmf)

#### Store Local copy of outputs into Module Outputs

See section above.

#### Program Flow End

N/A

##  [section-3]

##  Fault Recovery Functions

None

##  Shutdown Functions

None

##  Interrupt Functions

None

##  Serial Communication Functions

None

## Transition Functions

### SrlComOutput\_

#### Design Rationale

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

\*See below

#### Description

#### Store Local copy of outputs into Module Outputs

See section above.

#### Program Flow End

N/A

## Local Function/Macro Definitions

If these are numerous and defined in a separate source file then
reference the source file only.

### CalcCRC_EPS_1

|                      |               |      |     |     |
|----------------------|---------------|------|-----|-----|
| **Function Name**    | CalcCRC_EPS_1 | Type | Min | Max |
| **Arguments Passed** |               |      |     |     |
| **Return Value**     |               |      |     |     |

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image9.wmf)

### DetermineWarnDisp

|                      |                       |       |     |     |
|----------------------|-----------------------|-------|-----|-----|
| **Function Name**    | DetermineWarnDisp     | Type  | Min | Max |
| **Arguments Passed** |                       |       |     |     |
| **Return Value**     | FinalOutput_Cnt_T_u08 | uint8 | 0   | 7   |

#### Description

# ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image10.wmf)  [section-4]

#  [section-5]

### ScaleSignal_u16

|                      |                  |         |      |      |
|----------------------|------------------|---------|------|------|
| **Function Name**    | ScaleSignal_u16  | Type    | Min  | Max  |
| **Arguments Passed** | Signal_Uls_T_f32 | float32 | Full | Full |
|                      | LoLmt_Uls_T_f32  | float32 | Full | Full |
|                      | HiLmt_Uls_T_f32  | float32 | Full | Full |
|                      | Scale_Uls_T_f32  | float32 | Full | Full |
|                      | Offset_Uls_T_f32 | float32 | Full | Full |
| **Return Value**     | Signal_Cnt_T_u16 | Uint16  | 0    | Full |

#### Description

# ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image11.wmf)  [section-6]

### EPS1_PKTConfirmation

|                      |                      |      |     |     |
|----------------------|----------------------|------|-----|-----|
| **Function Name**    | EPS1_PKTConfirmation | Type | Min | Max |
| **Arguments Passed** |                      |      |     |     |
|                      |                      |      |     |     |
| **Return Value**     |                      |      |     |     |

#### Description

# ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image12.wmf)  [section-7]

#  [section-8]

### ApplCclComStart

|                      |                 |      |     |     |
|----------------------|-----------------|------|-----|-----|
| **Function Name**    | ApplCclComStart | Type | Min | Max |
| **Arguments Passed** |                 |      |     |     |
|                      |                 |      |     |     |
| **Return Value**     |                 |      |     |     |

#### Description

# ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image13.wmf)  [section-9]

### SrlComOutput_WriteBits

|                      |                        |        |      |      |
|----------------------|------------------------|--------|------|------|
| **Function Name**    | SrlComOutput_WriteBits | Type   | Min  | Max  |
| **Arguments Passed** | Data_T_Cnt_u32         | uint32 | Full | Full |
|                      | Buffer_T_Cnt_u08       | uint8  | Full | Full |
|                      | StartBit_Cnt_T_u16     | uint16 | Full | Full |
|                      | EndBit_Cnt_T_u16       | uint16 | Full | Full |
| **Return Value**     |                        |        |      |      |

#### Description

# ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/doc/mediax/media/image14.wmf)  [section-10]

# Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the
different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

|                      |                   |                                                 |
|----------------------------------|-------------------|-------------------|
| Function Name        | Calling Frequency | System State(s) in which the function is called |
| SrlComOutput_Init1() | Once              | START UP                                        |
| SrlComOutput_Per1()  | 10ms              | WARM INIT, OPERATE, DISABLE                     |
|                      |                   |                                                 |

## Execution Requirements for Serial Communication Functions 

|               |                                                  |
|---------------|--------------------------------------------------|
| Function Name | Sub-Module called by (Serial Comm Function Name) |
| N/A           |                                                  |

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

|                      |                               |
|----------------------|-------------------------------|
| Name of Sub Module   | Software Segment              |
| SrlComOutput_Init1() | RTE_AP_SRLCOMOUTPUT_APPL_CODE |
| SrlComOutput_Per1()  | RTE_AP_SRLCOMOUTPUT_APPL_CODE |
| SrlComOutput_Trns1() | RTE_AP_SRLCOMOUTPUT_APPL_CODE |

## Local Functions

This table identifies the software segments for local functions
identified in this module.

|                        |                              |
|------------------------|------------------------------|
| Name of Sub Module     | Software Segment             |
| CalcCRC_EPS_1 ()       | AP_SRLCOMOUTPUT_CODE         |
| DetermineWarnDisp      | AP_SRLCOMOUTPUT_CODE         |
| ScaleSignal_u16        | AP_SRLCOMOUTPUT_CODE         |
| EPS1_PKTConfirmation   | AP_SRLCOMOUTPUT_CODE         |
| ApplCclComStart        | AP_SRLCOMOUTPUT_CODE         |
| SrlComOutput_WriteBits | RTE_AP_SRLCOMINPUT_APPL_CODE |

#  Known Issues / Limitations With Design

1.  INLINE functions defined in “GlobalMacro.h” are not unit tested

# Revision Control Log

|             |            |                                       |          |                     |
|------|------|---------------------------------------------|---------|--------|
| **Item \#** | **Rev \#** | **Change Description**                | **Date** | **Author Initials** |
| 1           | 1.0        | Initial Version                       | 29May13  | M. Story            |
| 2           | 2.0        | Anomaly 5014 DetermineWarnDisp        | 16JUN13  | M. Story            |
| 3           | 3.0        | Anomaly 5416                          | 12AUG13  | M. Story            |
| 4           | 4.0        | Fully implemented A001 A002 A003 A004 | 13SEP13  | M. Story            |
| 5           | 5.0        | Changes for 01.00.01 version of CL    | 30SEP13  | M. Story            |
| 6           | 6.0        | Changes for 01.00.03 version of CL    | 25OCT13  | M. Story            |
| 7           | 7.0        | Changes for NM anomaly 5911           | 31OCT13  | M. Story            |
| 8           | 8.0        | Import prior changes to L path        | 20NOV13  | M. Story            |
| 9           | 9.0        | Anomaly 6408                          | 10APR14  | M. Story            |

{% endraw %}