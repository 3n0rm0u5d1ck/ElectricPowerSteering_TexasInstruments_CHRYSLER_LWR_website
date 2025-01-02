---
layout: default
title: Serial_Communication_Input_MDD
nav_order: 16
parent: Chrysler TMS570 Project
---
{% raw %}
# Module – Serial Communications Input [module-serial-communications-input]

# High-Level Description

The **Serial Communications** **Input** module provides a signal level
interface between the EPS application layer and the serial
communications software. Provide for the network management
functionality for the serial communications interface. This module will
be customized for each distinct vehicle platform. This module will be
responsible for converting the range and resolution of the Application
Layer variables to the range and resolution of the associated serial
communications signals.

This module processes the data for signals that are received by the EPS
controller from other ECUs on the communication bus. Serial
Communications signal input data is scaled appropriately and then
transferred to the global application data for use by the EPS
application software. Similarly, the Serial Communications **Output**
module, takes the global data to the EPS application software scales the
data as required by the serial communication transmit signal and
transfers the updated signal to the communication bus.

# Figures

## Component Diagram 

<img
src="ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image1.png"
style="width:1.41667in;height:7.83333in" />

# Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs (Global Variable Name) | Module Outputs (Global Variable Name) |
|---------------------------------|---------------------------------------|
| DSTSlewStart_Cnt_lgc                 | BattVolt_Volt_f32                     |
| DSTState_Cnt_u08                     | CMDIgnStat_Cnt_u08                    |
| DefaultVehSpd_Cnt_lgc                | CanMsgReceived_Cnt_lgc                |
| HaLFState_Cnt_u08(                   | DSTEOLDisable_Cnt_lgc                 |
| HaLFSuspend_Cnt_lgc                  | DSTEnableRqst_Cnt_lgc                 |
| HandsOnDetect_Cnt_lgc                | DSTErrCntrRecvLevel_Cnt_u08           |
| PABoostCurveSwitch_Cnt_lgc           | DSTExtSystemFltActive_Cnt_lgc         |
| PrkAssistState_Cnt_u08               | DSTFuncPresent_Cnt_lgc                |
| PrkAssistSuspend_Cnt_lgc             |                                       |
| StrClmTrq_HwNm_f32                   | DSTTOCState_Uls_enum                  |
| RxMsgsSrlComSvcDft_Cnt_lgc           | DSTTrqOvCmdRqst_HwNm_f32              |
| MEC_Cnt_enum                         | DSTTrqOvRqstValid_Cnt_lgc             |
| EstFric_HwNm_f32                     | EssEngStop_Cnt_lgc                    |
|                                      | DesiredTunPers_Cnt_u16                |
|                                      | DesiredTunSet_Cnt_u16                 |
|                                      | EngRPM_Cnt_u16                        |
|                                      | HaLFEnableRqst_Cnt_lgc                |
|                                      | HaLFErrInterfaceActive_Cnt_lgc        |
|                                      | HaLFExtSystemFltActive_Cnt_lgc        |
|                                      | HaLFFuncPresent_Cnt_lgc               |
|                                      | HaLFIntSystemFltActive_Cnt_lgc        |
|                                      | HaLFSWATrqFail_Cnt_lgc                |
| ..                                   |                                       |
|                                      | HaLFState_Cnt_T_u8                    |
|                                      | HaLFTrqOvCmdRqst_MtrNm_f32            |
|                                      | IWSSCalcVspd_Kph_f32                  |
|                                      | ODO_HwNmSq_f32                        |
|                                      | PAEnableRqst_Cnt_lgc                  |
|                                      | PAErrInterfaceActive_Cnt_lgc          |
|                                      | PAExtSystemFltActive_Cnt_lgc          |
|                                      | PAIntSystemFltActive_Cnt_lgc          |
|                                      | PAManoeuvrePhase_Cnt_u08              |
|                                      | PATrqOvCmdRqst_HwNm_f32               |
|                                      | PAWheelCriteriaMet_Cnt_lgc            |
|                                      | PAWhlDirRLStat_Cnt_u08                |
|                                      | PAWhlDirRRStat_Cnt_u08                |
|                                      | PAWhlPlsCntRLValid_Cnt_lgc            |
|                                      | PAWhlPlsCntRRValid_Cnt_lgc            |
|                                      | PrkAssistState_Cnt_T_u8               |
|                                      | PrkAsstFuncPresent_Cnt_lgc            |
|                                      |                                       |
|                                      | SpStPrsnt_Cnt_lgc                     |
|                                      | SrlComVehSpd_Kph_f32                  |
|                                      | SrlComVehSpdValid_Cnt_lgc             |
|                                      | StrgWhlAngl_HwDeg_f32                 |
|                                      | StrgWhlAnglValid_Cnt_lgc              |
|                                      | TrqOvReverseGearEngage_Cnt_lgc        |
|                                      | VehAccel_KphpS_f32                    |
|                                      | Nvm_VehicleInfo_Cnt_u8\[4\]           |
|                                      | AirTempOutside_DegC_f32               |
|                                      | AmbTempAvg_DegC_f32                   |
|                                      | SrlComLWhlSpdVld_Cnt_lgc              |
|                                      | SrlComRWhlSpdVld_Cnt_lgc              |
|                                      | SrlComLWhlSpd_Hz_f32                  |
|                                      | SrlComRWhlSpd_Hz_f32                  |
|                                      | EngOilTemp_DegC_f32                   |
|                                      | NET_CFG_STAT_PT_Cnt_u16               |
|                                      | LongAcceleration_Cnt_u16              |
|                                      | CfgStatRQ_Cnt_T_u8                    |
|                                      | EPS_Mode_Req_Cnt_T_u8                 |
|                                      | PrevHaLFTrqOvRqst_MtrNm_f32           |
|                                      | PrevHaLFEnableRqst_Cnt_lgc            |

**Note:** Any input signals that are not listed in the ‘Module Inputs’
section above but shown in the component diagram as a receiver port are
dummy signals which are used to determine loss of a certain message when
data receive error event is triggered.

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table style="width:100%;">
<colgroup>
<col style="width: 39%" />
<col style="width: 10%" />
<col style="width: 13%" />
<col style="width: 12%" />
<col style="width: 22%" />
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
<td></td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevDSTState_Cnt_M_u8</td>
<td>1</td>
<td>0</td>
<td>8</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>DSTActiveStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>DSTXorCptNTC18F_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td></td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevHaLFState_Cnt_M_u8</td>
<td>1</td>
<td>0</td>
<td>3</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td></td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevPAState_Cnt_M_u8</td>
<td>1</td>
<td>0</td>
<td>3</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>VehSpdVldStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>VehSpdMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>IgnStatVldStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>IgnStatMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>EngRPMVldStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>EngRPMMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>SWAVldStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>SWAMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>DSTTOCMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>NETCFGPTMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>HalfMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PTSMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevMC_29Fh_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PTSTrqOverlayAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PSTTrqOvrlChngeLmt_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevVC_PPPA_PrsntTypH_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>DSTTOCMsgCntAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>DSTTOCMsgTmrAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>MC_29Fh_Bad_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>MC_292h_Bad_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevMC_292h_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevMtrTorqOverlayStrReq_Cnt_M_f32</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevVC_TIRE_CIRCUMF_mm_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>VC_TIRE_CIRCUMF_mm_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevWhlPlsCnt_RL_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>254</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevWhlPlsCnt_RR_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>254</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevMC_292h_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>MC_292h_Bad_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>HalfMaxTrqStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevHaLFPresent_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PASlewStep_Nm_M_f32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>HaLFSlewStep_Nm_M_f32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PAIntSystemFltActive_Cnt_M_bit</td>
<td>2^x</td>
<td>0</td>
<td>2048</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>HaLFIntSystemFltActive_Cnt_M_bit</td>
<td>2^x</td>
<td>0</td>
<td>2048</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevMC_11Ch_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>MC_11Ch_Bad_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PAErrInterfaceActive_Cnt_M_bit</td>
<td>2^x</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>HaLFErrInterfaceActive_Cnt_M_bit</td>
<td>2^x</td>
<td>0</td>
<td>2048</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>DSTRevGearValid_Cnt_M_bit</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>NetCfg_HaLF_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>NetCfg_PTS_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevNetCfg_HaLF_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevNetCfg_PTS_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevNetCfg_TCM_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>HaLFTrqOvrlChngeAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>CRC294DiagAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PSTTrqOvrlSlewLmt_Nm_M_f32</td>
<td>0.1</td>
<td>-8.8</td>
<td>8.8</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>HaLFTrqOvrlSlewLmt_Nm_M_f32</td>
<td>0.1</td>
<td>-8.8</td>
<td>8.8</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>DSTTrqOvrlSlewLmt_Nm_M_f32</td>
<td>0.1</td>
<td>-8.8</td>
<td>8.8</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>CRC11CDiagAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>CRC29FDiagAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>CRC292DiagAcc_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevMC_294h_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>DSTErrCntrRecvLevel_Cnt_M_bit</td>
<td>2^x</td>
<td>0</td>
<td>2048</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>NetCfg_ESC_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevNetCfg_ESC_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>HaLFTrqOvCmdRqst_MtrNm_M_f32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PATrqOvCmdRqst_HwNm_M_f32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>TO_Req_HwNm_M_f32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevDSTPresent_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>ESP4AMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>BattVoltInvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>ECMA3MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>ESP4AInvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>IC1AInvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>IC1AMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>NET_CFG_STAT_PT_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>NetCfg_CBC_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>NetCfg_ECM_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>NetCfg_IC_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>NetCfg_SCCM_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevNetCfg_CBC_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevNetCfg_ECM_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevNetCfg_IC_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevNetCfg_SCCM_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>BattVoltMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevVCBodyStyle_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>0x0F</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevVCCountry_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>0x1F</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevVCModelYear_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>0x3F</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevVCVehLine_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>0xFF</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>VehCfg1InvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>VehCfg1MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>VINInvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>VINMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>CBCNodeAbsStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>BattVoltHighRecTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>BattVoltHighStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>BattVoltLowRecTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>BattVoltLowStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>DSLNodeAbsStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>StrWhlAnglRatStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>VehAccel_Y_Cnt_M_f32</td>
<td>0.08</td>
<td>-10.24</td>
<td>10.08</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>VehAccel_X_Cnt_M_f32</td>
<td>0.08</td>
<td>-10.24</td>
<td>10.08</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>VehCfg3InvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>VehSpd_Kph_M_f32</td>
<td>1</td>
<td>0</td>
<td>255</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevHALFSystemSts_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>3</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevVINData_Cnt_M_u08[7]</td>
<td>1</td>
<td>0</td>
<td>2^56</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>StrgWhlAngl_M_f32</td>
<td>0.5</td>
<td>-1024</td>
<td>1024</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>VINRxCount_Cnt_M_u08[3]</td>
<td>1</td>
<td>0</td>
<td>2</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>EnableTorqueOverlay_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>CurrentVINPending_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>StartVinOdo_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>CurrentVinPendingStart_Km_M_f32</td>
<td>0.1</td>
<td>0</td>
<td>429496729.6</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevEngON_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>WHEELSPEED2MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>WHEELSPEED2InvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>WRSFaultStatus_Cnt_M_b16</td>
<td>1</td>
<td>0</td>
<td>65535</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevWheelFreqFL_Hz_T_f32</td>
<td>0.001953125</td>
<td>0</td>
<td>0.2499923828125</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevWheelFreqFR_Hz_T_f32</td>
<td>0.001953125</td>
<td>0</td>
<td>0.2499923828125</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>EngCfgMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>EngOilTempMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>TrnsmsnType_Cnt_M_u8</td>
<td>1</td>
<td>0</td>
<td>2</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>TRNSSTATMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>TRNSSTATInvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevDesiredTunSet_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>256</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>RevGearTempMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>VehCfg5MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>VehCfg5MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>VehCfg5MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>VehCfg5MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>VehCfg5MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>VCTireCircRcvd_Cnt_M_Lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>ESPA6MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>ESPA6MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>ESPA6MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>ESPA6MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>ESPA6MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>ESPA6MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>ESPA6MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>CfgRQCMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>CfgRQMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>EcuCfg6InvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>GWLINIC2InvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>GWLINIC2MisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>PrevTOReq_HwNm_M_f32</td>
<td>0.01</td>
<td>18.0</td>
<td>-18.0</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>TrqBandHi_Nm_M_f32</td>
<td>0.01</td>
<td>18.0</td>
<td>-18.0</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>TrqBandLow_Nm_M_f32</td>
<td>0.01</td>
<td>18.0</td>
<td>-18.0</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>TrqBndEstab_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>TrqStckStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>DSTTOCInvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>DSTExtSystemFltActive_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>DSTTOCInvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PerMisMchFlt_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>PrevMtrTrqOvrlyStrngReq_Nm_M_f32</td>
<td>0.01</td>
<td>18.0</td>
<td>-18.0</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>MtrTrqOvrlyStrRqMax_Nm_M_f32</td>
<td>0.01</td>
<td>18.0</td>
<td>-18.0</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>ManualVehSpd_Kph_M_f32</td>
<td>1</td>
<td>0</td>
<td>255</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>ManualVehSpdOvrRide_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>HaLFFuncPresentTypH_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>SRLCOMINPUT_START_SEC_VAR_SAVED_ZONEH_8</td>
</tr>
<tr class="even">
<td>DSTFuncPresentTypH_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>SRLCOMINPUT_START_SEC_VAR_SAVED_ZONEH_8</td>
</tr>
<tr class="odd">
<td>VC_PPPA_PrsntTypH_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>SRLCOMINPUT_START_SEC_VAR_SAVED_ZONEH_8</td>
</tr>
<tr class="even">
<td>TuningSetForNextCycleTypH_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>SRLCOMINPUT_START_SEC_VAR_SAVED_ZONEH_16</td>
</tr>
<tr class="odd">
<td>TOC_Sts_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>15</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>PrevDesiredTunPers_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>15</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>HalfTrqMax_Nm_M_f32</td>
<td>0.1</td>
<td>-8.8</td>
<td>8.8</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>HndsOnDrngPPAStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>TuningPerformedStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>EC_SteeringIvld_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT)</td>
</tr>
<tr class="odd">
<td>TuningPerformedTypH_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>15</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>NetCfg_PTSTypH_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT)</td>
</tr>
<tr class="odd">
<td>NetCfg_HaLFTypH_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT)</td>
</tr>
<tr class="even">
<td>NetCfg_ESCTypH_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT)</td>
</tr>
<tr class="odd">
<td>NetCfg_CBCTypH_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT)</td>
</tr>
<tr class="even">
<td>NetCfg_ECMTypH_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT)</td>
</tr>
<tr class="odd">
<td>NetCfg_ICTypH_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT)</td>
</tr>
<tr class="even">
<td>NetCfg_SCCMTypH_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT)</td>
</tr>
<tr class="odd">
<td>SpStPrsnt_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT)</td>
</tr>
<tr class="even">
<td>Gear_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>2^16</td>
<td>1</td>
</tr>
<tr class="odd">
<td>TRNSSPDMisMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="even">
<td>GrInvMsgStartTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>2^32</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>DiagNTC124Set_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT)</td>
</tr>
<tr class="even">
<td>DSTState_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>0xFF</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
<tr class="odd">
<td>EnableRqst_Cnt_M_lgc</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>AP_SRLCOMINPUT_VAR_INIT</td>
</tr>
</tbody>
</table>

### User defined typedef definition/declaration 

This section documents any user types uniquely used for the module.

<table>
<colgroup>
<col style="width: 34%" />
<col style="width: 25%" />
<col style="width: 21%" />
<col style="width: 9%" />
<col style="width: 0%" />
<col style="width: 8%" />
</colgroup>
<thead>
<tr class="header">
<th>Typedef Name</th>
<th>Element Name</th>
<th>User Defined Type</th>
<th colspan="2"><p>Legal Range</p>
<p>(min)</p></th>
<th><p>Legal Range</p>
<p>(max)</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td colspan="2"></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td colspan="2"></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td colspan="2"></td>
</tr>
</tbody>
</table>

#  [section]

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

| Constant Name                      |
|------------------------------------|
| k_VehSpdMisMsgTimeOut_mS_u16p0     |
| k_VehSpdValTimeOut_mS_u16p0        |
| k_IgnStatMisMsgTimeOut_mS_u16p0    |
| k_IgnStatValTimeOut_mS_u16p0       |
| k_EngRPMMisMsgTimeOut_mS_u16p0     |
| k_EngRPMValTimeOut_mS_u16p0        |
| k_SWAValTimeOut_mS_u16p0           |
| k_StrgWhlAnglPol_s08               |
| k_SWAMisMsgTimeOut_mS_u16p0        |
| k_PSTMisMsgTimeOut_mS_u16p0        |
| k_VehCfg5MisMsgTimeOut_mS_u16p0    |
| k_HalfMsgTimeOut_mS_u16p0          |
| k_NETCFGMsgTimeOut_mS_u16p0        |
| k_EcuCfg6MsgTimeOut_mS_u16p0       |
| k_PSTTrqOverlayDiag_Cnt_str        |
| k_PSTTrqOverlayLmt_Cnt_f32         |
| k_MC292hMsg_Cnt_u16                |
| k_MC11ChMsg_Cnt_u16                |
| k_DSTTOCProgCnt1Diag_Cnt_str       |
| k_DSTTOCProgCnt2Diag_Cnt_str       |
| k_MC29FhMsg_Cnt_u16                |
| k_HalfTrqMax_Nm_f32                |
| k_MsgMaxHalfTorqTO_mS_u32p0        |
| k_PASlewRate_NmpS_f32              |
| k_PSTTrqOvrlChngeLmt_NmpS_f32      |
| k_PSTTrqOvrlChngeLmtDiag_Cnt_str   |
| k_HaLFSlewRate_NmpS_f32            |
| k_HaLFTrqOvrlChngeLmt_NmpS_f32     |
| k_HaLFTrqOverlayDiag_Cnt_str       |
| k_CRC292DiagMsg_Cnt_u16            |
| k_CRC29FDiagMsg_Cnt_u16            |
| k_CRC11CDiagMsg_Cnt_u16            |
| k_IWSSVSpdConst_Cnt_f32            |
| k_BattVoltInvTimeOut_mS_u16p0      |
| k_BattVoltMsgTimeOut_mS_u16p0      |
| k_ECMA3MsgTimeOut_mS_u16p0         |
| k_ESP4AInvTimeOut_mS_u16p0         |
| k_ESP4AMsgTimeOut_mS_u16p0         |
| k_IC1AAInvTimeOut_mS_u16p0         |
| k_IC1AMsgTimeOut_mS_u16p0          |
| k_VehCfg1AInvTimeOut_mS_u16p0      |
| k_VehCfg1MsgTimeOut_mS_u16p0       |
| k_VINInvTimeOut_mS_u16p0           |
| k_VINMsgTimeOut_mS_u16p0           |
| k_BattMsgVoltHighTimeOut_mS_u16p0  |
| k_BattMsgVoltLowTimeOut_mS_u16p0   |
| k_CBCNodeAbsTime_mS_u16p0          |
| k_DSLNodeAbsTime_mS_u16p0          |
| k_StrWhlAnglRatTime_mS_u16p0       |
| k_VehCfg3InvMsgTimeOut_mS_u16p0    |
| k_CRC294DiagThr1_Cnt_u16           |
| k_CRC294DiagThr2_Cnt_str           |
| k_DSTMisMsgThr0_ms_u16             |
| k_DSTTOCActMisMsgThr1_Cnt_u16p0    |
| k_DSTTOCActMisMsgThr2_Cnt_str      |
| k_DSTTOCNotActMisMsgThr1_Cnt_u16p0 |
| k_DSTTOCNotActMisMsgThr2_Cnt_str   |
| k_DSTTOCProgCntDiagThr2_Cnt_str    |
| k_DSTTOCProgCntThr1_Cnt_u16        |
| k_MsgMaxHalfTorqTO_Nm_f32          |
| k_DSTTrqMax_HwNm_f32               |
| k_DSTTrqOvrlSlewLmt_NmpS_f32       |
| k_MaxDSTActiveTime_mS_u32p0        |
| k_MaxDSTXorCptNTC18F_Cnt_u16       |
| k_maxFreqChg_RevpSec_f32           |
| k_WSP2AInvTimeOut_mS_u16p0         |
| k_WSP2TimeOut_mS_u16p0             |
| k_EngCfgMisMsgTimeOut_mS_u16p0     |
| k_EngOilTempMsgTimeOut_mS_u16p0    |
| k_ECMA3InvTimeOut_mS_u16p0         |
| k_RevGearMsgTimeOut_mS_u16p0       |
| k_TrnsStatInvTimeOut_mS_u16p0      |
| k_TrnsStatTimeOut_mS_u16p0         |
| k_VehCfg5MsgTimeOut_mS_u16p0       |
| k_ESPA5MsgTimeOut_mS_u16p0         |
| k_ESPA5ValTimeOut_mS_u16p0         |
| k_ESPA6MsgTimeOut_mS_u16p0         |
| k_ESPA6ValTimeOut_mS_u16p0         |
| k_TireCircRcvdTimeOut_mS_u16p0     |
| k_TrqOvrlMaxSlewDiag_Cnt_str       |
| k_CfgRQCMisMsgTimeOut_mS_u16p0     |
| k_CfgRQMisMsgTimeOut_mS_u16p0      |
| k_EcuCfg6InvMsgTimeOut_mS_u16p0    |
| k_ESPA5MsgTimeOut_mS_u16p0         |
| k_ESPA5ValTimeOut_mS_u16p0         |
| k_ESPA6MsgTimeOut_mS_u16p0         |
| k_ESPA6ValTimeOut_mS_u16p0         |
| k_GWLINIC2InvMsgTimeOut_mS_u16p0   |
| k_GWLINIC2MsgTimeOut_mS_u16p0      |
| k_VehCfg7InvMsgTimeOut_mS_u16p0    |
| k_VehCfg7MsgTimeOut_mS_u16p0       |
| k_StuckTrqBnd_Nm_f32               |
| k_TrqStckActv_HwNm_M_f32           |
| k_TrqStckHiSWATime_mS_u16p0        |
| k_TrqStckLowSWATime_mS_u16p0       |
| k_TrqStckSWA_HwDeg_f32             |
| k_DSTTOCInvMsgTimeOut_mS_u16p0     |
| k_MaxHlfRmpOutRt_Nm_F32            |
| k_MtrTrqOvrlyStrRqMax_Nm_f32       |
| k_PerMisMchCntLmt_Cnt_u16          |
| k_PerMisMchFltThr_Cnt_u08          |
| k_AnaHwTorquePerLim_HwNm_f32       |
| k_HaLFTrqPerLim_HwNm_f32           |
| k_DesiredTuning_Cnt_u16\[2\]\[15\] |
| k_TuningPerformedTimeOut_mS_u16p0  |
| k_AnaHwTorquePerLim_HwNm_f32       |
| k_HaLFTrqPerLim_HwNm_f32           |
| k_HalfTrqMaxSpt_Nm_f32             |
| k_HaLFTrqOvrlSlewLmtSpt_NmpS_f32   |
| k_HalfTrqMaxNrm_Nm_f32             |
| k_HaLFTrqOvrlSlewLmtNrm_NmpS_f32   |
| k_EstFricLim_HwNm_T_f32            |
| k_HndsOnDrngPAA_mS_u16             |
| k_PTSDrStylTunSet_Cnt_u16          |
| k_MtrTorqOvrlStrReqPol_Cnt_f32     |
| k_TOReqPol_Cnt_f32                 |
| k_TorqOvrlStrReqPol_Cnt_f32        |
| k_GrInvTimeOut_mS_u16p0            |
| k_TRNSSPMsgTimeOut_mS_u16p0        |

##  [section-1]

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name                    | Resolution  | Value                          |
|------------------------------------|-----------------|-------------------|
| D_TUNNINGSETOFFSET_CNT_U16       | 1           | 0x1EU                          |
| D_CRCINIT_CNT_U8                 | 1           | 0xFFu                          |
| D_CRCXORVALUE_CNT_U8             | 1           | 0xFFu                          |
| D_COUNTERCYCLE16_CNT_U16         | 1           | 0x10u                          |
| D_VEHSPEEDNOTAVAILABLE_CNT_U16   | 1           | 0xFFFFu                        |
| D_VEHSPEEDSCALE_KPH_F32          |             | 0.0078125f                     |
| D_LRWSCALE_HWDEG_F32             |             | 0.5f                           |
| D_LRWOFFSET_HWDEG_F32            |             | 2048.0f                        |
| D_LRWRHPSCALE_HWDEG_F32          |             | 0.1f                           |
| D_LRWRHPOFFSET_HWDEG_F32         |             | 0.4f                           |
| D_TORQOVERLAYSTRREQOFF_CNT_F32   |             | 8.0f                           |
| D_MTRTORQOVERLAYSTRREQ_CNT_F32   |             | 2.0f                           |
| D_LRWOFF_CNT_F32                 |             | 2048.0f                        |
| D_LRWRHPOFF_CNT_F32              |             | 0.4f                           |
| D_TOREQOFF_CNT_F32               |             | 8.0f                           |
| D_VEHCFGSTATPROG_CNT_U16         | 1           | 0x01u                          |
| D_IWSSALCVSPD_CNT_F32            |             | (3.6f/k_IWSSVSpdConst_Cnt_f32) |
| D_VEHCFG4STATPROG_CNT_U16        | 1           | 1U                             |
| D_NETCFGSTATPROG_CNT_U16         | 1           | 1U                             |
| D_ODOSCALE_CNT_F32               |             | ((float32).1)                  |
| D_INVALIDODO_U32                 | 1           | 0x00FFFFFFU                    |
| D_SYSFLTACTNTCCLR_CNT_U16        | 1           | 0x0000U                        |
| D_SYSFLTACTNTC13A_CNT_U16        | 1           | (0x0001U \<\< 0)               |
| D_SYSFLTACTNTC13B_CNT_U16        | 1           | (0x0001U \<\< 1)               |
| D_SYSFLTACTNTC192_CNT_U16        | 1           | (0x0001U \<\< 2)               |
| D_SYSFLTACTNTC194_CNT_U16        | 1           | (0x0001U \<\< 3)               |
| D_SYSFLTACTNTC193_CNT_U16        | 1           | 0x0001U \<\< 4)                |
| D_SYSFLTACTNTC195_CNT_U16        | 1           | (0x0001U \<\< 5)               |
| D_SYSFLTACTNTC196_CNT_U16        | 1           | (0x0001U \<\< 6)               |
| D_SYSFLTACTNTC1C6_CNT_U16        | 1           | (0x0001U \<\< 7)               |
| D_SYSFLTACTNTC19A_CNT_U16        | 1           | (0x0001U \<\< 8)               |
| D_SYSFLTACTNTC19B_CNT_U16        | 1           | (0x0001U \<\< 9)               |
| D_SYSFLTACTNTC19C_CNT_U16        | 1           | (0x0001U \<\< 10)              |
| D_SYSFLTACTNTC19D_CNT_U16        | 1           | (0x0001U \<\< 11)              |
| D_SYSFLTACTNTC1B6_CNT_U16        | 1           | (0x0001U \<\< 12)              |
| D_SYSFLTACTNTC0EE_CNT_U16        | 1           | (0x0001U \<\< 13)              |
| D_SYSFLTACTNTC0E9_CNT_U16        | 1           | (0x0001U \<\< 14)              |
| D_ERRINTACTNTCCLR_CNT_U32        | 1           | 0x0000U                        |
| D_ERRINTACTNTC100_CNT_U32        | 1           | (0x0001U \<\< 1)               |
| D_ERRINTACTNTC138_CNT_U32        | 1           | (0x0001U \<\< 2)               |
| D_ERRINTACTNTC190_CNT_U32        | 1           | (0x0001U \<\< 3)               |
| D_ERRINTACTNTC191_CNT_U32        | 1           | (0x0001U \<\< 4)               |
| D_ERRINTACTNTC199_CNT_U32        | 1           | (0x0001U \<\< 5)               |
| D_ERRINTACTNTC120_CNT_U32        | 1           | (0x0001U \<\< 6)               |
| D_ERRINTACTNTC121_CNT_U32        | 1           | (0x0001U \<\< 7)               |
| D_ERRINTACTNTC139_CNT_U32        | 1           | (0x0001U \<\< 8)               |
| D_ERRINTACTNTC124_CNT_U32        | 1           | (0x0001U \<\< 9)               |
| D_ERRINTACTNTC1B9_CNT_U32        | 1           | (0x0001U \<\< 10)              |
| D_ERRINTACTNTC1A8_CNT_U32        | 1           | (0x0001U \<\< 11)              |
| D_ERRINTACTNTC1DE_CNT_U32        | 1           | (0x0001U \<\< 12)              |
| D_ERRINTACTNTC1DF_CNT_U32        | 1           | (0x0001U \<\< 13)              |
| D_ERRINTACTNTC1C8_CNT_U32        | 1           | (0x0001U \<\< 14)              |
| D_ERRINTACTNTC1D0_CNT_U32        | 1           | (0x0001U \<\< 15)              |
| D_ERRINTACTNTC170_CNT_U32        | 1           | (0x0001U \<\< 16)              |
| D_ERRINTACTNTC1A9_CNT_U32        | 1           | (0x0001U \<\< 17)              |
| D_DSTREVGRVLDCNTLCLR_CNT_u16     | 1           | 0x0000U                        |
| D_DSTREVGRVLDCNTL1B9_CNT_u16     | 1           | (0x0001U \<\< 0)               |
| D_DSTREVGRVLDCNTL1A8_CNT_u16     | 1           | (0x0001U \<\< 1)               |
| D_DSTREVGRVLDCNTL1A9_CNT_u16     | 1           | (0x0001U \<\< 2)               |
| D_DSTERRCNTRCLCLR_CNT_u16        | 1           | 0x0000U                        |
| D_DSTERRCNTRCLGR0_CNT_u16        | 1           | 0x0001U                        |
| D_DSTERRCNTRCLTH1_CNT_u16        | 1           | 0x0002U                        |
| D_DSTERRCNTRCLTH2_CNT_u16        | 1           | 0x0004U                        |
| D_DSTERRCPTLEV0_CNT_U8           | 1           | 0U                             |
| D_DSTERRCPTLEV1_CNT_U8           | 1           | 1U                             |
| D_DSTERRCPTLEV2_CNT_U8           | 1           | 2U                             |
| D_DSTERRCPTLEV3_CNT_U8           | 1           | 3U                             |
| D_PASTATEINACTIVE_CNT_U08        | 1           | ((uint8)0U)                    |
| D_PASTATEACTIVE_CNT_U08          | 1           | ((uint8)1U)                    |
| D_PASTATEINHIBITED_CNT_U08       | 1           | ((uint8)2U)                    |
| D_PASTATERECOVERABLE_CNT_U08     | 1           | ((uint8)3U)                    |
| D_HALFSYSSTSNOTFAULTED_U16       | 1           | 0U                             |
| D_HALFSYSSTSFAULTED_U16          | 1           | 1U                             |
| D_HALFSTATEINACTIVE_CNT_U08      | 1           | ((uint8)0U)                    |
| D_HALFSTATEACTIVE_CNT_U08        | 1           | ((uint8)1U)                    |
| D_HALFSTATEINHIBITED_CNT_U08     | 1           | ((uint8)2U)                    |
| D_HALFSTATERECOVERABLE_CNT_U08   | 1           | ((uint8)3U)                    |
| TOCSTATE_OFF                     | 1           | (0U)                           |
| TOCSTATE_TNA                     | 1           | (1U)                           |
| TOCSTATE_PNA                     | 1           | (2U)                           |
| TOCSTATE_READY                   | 1           | (3U)                           |
| TOCSTATE_REQUESTDENIED           | 1           | (4U)                           |
| TOCSTATE_ACTIVEMODE05            | 1           | (5U)                           |
| TOCSTATE_ACTIVEMODE06            | 1           | (6U)                           |
| TOCSTATE_ACTIVEMODE07            | 1           | (7U)                           |
| TOCSTATE_NOTAVAILABLE            | 1           | (8U)                           |
| D_VCMODELYEARSNA_CNT_U08         | 1           | ((uint8)0x3FU)                 |
| D_VCVEHLINESNA_CNT_U08           | 1           | ((uint8)0xFFU)                 |
| D_VCCOUNTRYSNA_CNT_U08           | 1           | ((uint8)0x1FU)                 |
| D_VCBODYSTYLESNA_CNT_U08         | 1           | ((uint8)0x0FU)                 |
| D_ESSENGSTDSBL_CNT_U08           | 1           | ((uint8)0x07U)                 |
| D_ESSENGSTSTPRTCT_CNT_U08        | 1           | ((uint8)0x05U)                 |
| D_ESSENGSTSNA_CNT_U08            | 1           | ((uint8)0x0FU)                 |
| RESET_RESPONSE_ECURESET_REQUIRED | 1           | ((uint8)2U)                    |
| RESET_RESPONSE_NOT_REQUIRED      | 1           | ((uint8)0U)                    |
| D_TESTMODE_CNT_U08               | 1           | 0xFFU                          |
| D_MTRTQOVLYSTRREQRES_f32         | 0.001953125 | 0.001953125                    |
| D_VINSIZE_CNT_U08                | 1           | 17                             |
| D_ERRINTACTNTC139_CNT_U16        | 1           | 0x0080                         |
| D_ERRINTACTNTC124_CNT_U16        | 1           | 0x0100                         |
| D_CFGSETHI_CNT_U08               | 1           | 0x02                           |
| D_WHLRPMVEHSPLIM_KPH_F32         | 0.1         | 0.4                            |
| D_TUNINGPERFORMED_CNT_U16        | 1           | 0xA5A5                         |
| D_TIRECIRCUMFSAVD_CNT_U16        | 1           | 0xA5A5                         |
| D_AUTOTRANS_CNT_U8               | 1           | 1                              |
| D_MANTRANS_CNT_U8                | 1           | 0                              |

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name |
|---------------|
|               |
|               |
|               |
|               |
|               |

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as
other tables)

| Constant Name | Resolution | Value | Software Segment |
|---------------|------------|-------|------------------|
| none          |            |       |                  |

# Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library functions / Macros that are called by the various sub
modules are identified below,

## Data Hiding Functions

The data hiding functions / macros used in this module are identified
below,

1.  None

## Local Functions/Macros Used by this MDD only

(Note if they are defined in another source file, then reference the
appropriate header file)

The local functions/macros in this module are identified below,

1.  ReadSCCM_STW_ANGL_STAT()

2.  ReadECM_A1()

3.  ReadCBC_PT2()

4.  ReadPTS_StrCtrl()

5.  ReadESP_A8()

6.  ReadESP_A5()

7.  ReadESP_A6()

8.  ReadVehCfg5()

9.  ReadHALF_MTO_SteerControl()

10. ReadNET_CFG_PT()

11. ReadEcuCfg6()

12. ReadDST_TOC()

13. ReadTRNSSTAT()

14. ReadVehCfg4()

15. ReadBATTVOLT()

16. ReadVehCfg1()

17. ReadENGCFG()

18. ReadVIN()

19. ReadICA1()

20. ReadECMA3()

21. ReadESPA4()

22. ReadWHEELSPEED2()

23. ReadCfgRQ()

24. ReadCfgRQC()

25. ReadGWLinIC2()

26. ReadEcmIndicators()

27. ReadVehCfg7()

28. ReadCBC_PT1()

29. DiagNTC189()

30. DiagCRC294()

31. DiagNTC18B()

32. DSTDiagNTC18CReqOutOfRange()

33. DSTDiagNTC18DDeltaOutOfRange()

34. DSTDiagNTC18EMaxActiveTime()

35. DSTDiagNTC18FRawXORTest()

36. DSTDiagCondtions18CDF()

37. DiagCRC292()

38. DiagNTC190()

39. DiagNTC193()

40. DiagNTC194()

41. DiagNTC195()

42. DiagNTC196()

43. DiagNTC1C6()

44. DiagCRC11C()

45. DiagNTC13B_MC11C()

46. DiagCRC29F()

47. DiagNTC19B()

48. DiagNTC19C()

49. DiagNTC19D()

50. DiagNTC1B6()

51. DiagNTC14E()

52. DiagNTC14F()

53. DiagNTC102()

54. DiagNTC104()

55. DiagNTC124()

56. DiagNTC170()

57. SrlComInput_WriteBits()

58. ResetTimers()

59. DSTDiagNTC188()

60. DiagNTC0EE()

61. DiagNTC0E9()

62. VehSpdOverRide()

63. DiagNTC091()

64. ClearHALFNTC_MessageNotRcvd()

65. ClearHALFNTC_RcvdMesgNotValid()

66. ClearPTSNTC_MessageNotRcvd()

67. ClearPTSNTC_RcvdMesgNotValid()

68. ClearDSTTOCNTC_MessageNotRcvd()

69. ClearDSTTOCNTC_RcvdMesgNotValid()

70. <span class="mark">ReadTRNSSPD</span>()

#   [section-2]

# Software Module Implementation

## Initialization Functions

### Init: SrlComInput_Init1 

#### Design Rationale

None

#### Module Internal 

Rte_Call_SystemTime_GetSystemTime_mS_u32(&SystemTime_mS_T_u32)

DSTActiveStartTime_mS_M_u32 = SystemTime_mS_T_u32

SWAVldStartTime_mS_M_u32 = SystemTime_mS_T_u32

SWAMisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

EngRPMVldStartTime_mS_M_u32 = SystemTime_mS_T_u32

EngRPMMisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

IgnStatVldStartTime_mS_M_u32 = SystemTime_mS_T_u32

IgnStatMisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

VehSpdVldStartTime_mS_M_u32 = SystemTime_mS_T_u32

VehSpdMisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

PTSMisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

HalfMisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

NETCFGPTMisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

DSTTOCMisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

HalfMaxTrqStartTime_mS_M_u32 = SystemTime_mS_T_u32

ESP4AMisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

EcuCfg6MsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

VehCfg7MisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

CfgRQCMisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

CfgRQMisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

EcuCfg6InvMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

GWLINIC2InvMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

GWLINIC2MisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32

HndsOnDrngPPAStartTime_mS_M_u32 = SystemTime_mS_T_u32.

TuningPerformedStartTime_mS_M_u32 = SystemTime_mS_T_u32;

TRNSSPDMisMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32;

GrInvMsgStartTime_mS_M_u32 = SystemTime_mS_T_u32;

PSTTrqOvrlSlewLmt_Nm_M_f32 = k_PSTTrqOvrlSlewLmt_NmpS_f32/100.0f

HaLFTrqOvrlSlewLmt_Nm_M_f32 = k_HaLFTrqOvrlSlewLmtNrm_NmpS_f32/100.0f

DSTTrqOvrlSlewLmt_Nm_M_f32 = k_DSTTrqOvrlSlewLmt_NmpS_f32/100.0f

MC_292h_Bad_Cnt_M_u16 = 0U

PAIntSystemFltActive_Cnt_M_bit = D_SYSFLTACTNTCCLR_CNT_U16

PAErrInterfaceActive_Cnt_M_bit = D_ERRINTACTNTCCLR_CNT_U32

HaLFErrInterfaceActive_Cnt_M_bit = D_ERRINTACTNTCCLR_CNT_U32

HaLFIntSystemFltActive_Cnt_M_bit = D_SYSFLTACTNTCCLR_CNT_U16

DSTErrCntrRecvLevel_Cnt_M_bit = D_DSTERRCNTRCLCLR_CNT_u16

DSTRevGearValid_Cnt_M_bit = D_DSTREVGRVLDCNTLCLR_CNT_u16

PrevVCModelYear_Cnt_M_u08 = D_VCMODELYEARSNA_CNT_U08

PrevVCVehLine_Cnt_M_u08 = D_VCVEHLINESNA_CNT_U08

PrevVCCountry_Cnt_M_u08 = D_VCCOUNTRYSNA_CNT_U08

PrevVCBodyStyle_Cnt_M_u08 = D_VCBODYSTYLESNA_CNT_U08

EnableTorqueOverlay_Cnt_M_lgc = TRUE

PrevHaLFState_Cnt_M_u8 = TOCSTATE_OFF

PrevHaLFState_Cnt_M_u8 = D_HALFSTATEINACTIVE_CNT_U08

PrevPAState_Cnt_M_u8 = D_PASTATEINACTIVE_CNT_U08

VCTireCircRcvd_Cnt_M_Lgc = FALSE

MtrTrqOvrlyStrRqMax_Nm_M_f32 = k_MtrTrqOvrlyStrRqMax_Nm_f32

PrevDesiredTunPers_Cnt_M_u16 = DesiredTunPersTypH_Cnt_M_u08

if(VCTireCircSavedTypH_Cnt_U16 == D_TIRECIRCUMFSAVD_CNT_U16)

{

VC_TIRE_CIRCUMF_mm_M_u16 = VC_TIRE_CIRCUMFTypH_mm_u16;

}

if(Nvm_VINOdometer_Cnt_u8\[1\] != TRUE)

{

StartVinOdo_Cnt_M_lgc = TRUE;

}

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_DataRateFltMsg_Z, 0x01,
NTC_STATUS_PASSED)

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_DataRngFltMsg_Z, 0x01,
NTC_STATUS_PASSED)

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_DSTXORActive, 0x01,
NTC_STATUS_PASSED)

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_DataOtherFltMsg_Z, 0x01,
NTC_STATUS_PASSED)

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_InvalidMsg_Z, 0x01,
NTC_STATUS_PASSED)

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_PgrsCntFltMsg_Z, 0x01,
NTC_STATUS_PASSED)

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_CRCFltMsg_Z, 0x01,
NTC_STATUS_PASSED)

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_VLF_14, 0x01,
NTC_STATUS_PASSED)

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_DataOtherFltMsg_AA, 0x01,
NTC_STATUS_PASSED)

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_VLF_09, 0x01,
NTC_STATUS_PASSED)

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_DataRngFltMsg_AA, 0x01,
NTC_STATUS_PASSED)

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_DataRngFltMsg_AB, 0x01,
NTC_STATUS_PASSED)

Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_DataRateFltMsg_AB, 0x01,
NTC_STATUS_PASSED)

#### Store Local copy of outputs into Module Outputs

Rte_Write_Ap_SrlComInput_HaLFFuncPresent_Cnt_lgc(HaLFFuncPresentTypH_Cnt_M_lgc)

Rte_Write_Ap_SrlComInput_PrkAsstFuncPresent_Cnt_lgc(VC_PPPA_PrsntTypH_Cnt_M_lgc)

Rte_Write_Ap_SrlComInput_DSTFuncPresent_Cnt_lgc(DSTFuncPresentTypH_Cnt_M_lgc)

if (TuningSetForNextCycleTypH_Cnt_M_u16 \> D_NUMOFTUNSETS_CNT_U16)

{

TuningSetForNextCycleTypH_Cnt_M_u16 = 0

}

SrlComInput_WriteBits(TuningSetForNextCycleTypH_Cnt_M_u16,T_A001InternalBusSig_Cnt_u8,196U,199U)

Rte_Write_Ap_SrlComInput_DesiredTunSet_Cnt_u16(TuningSetForNextCycleTypH_Cnt_M_u16)

Rte_Write_DesiredTunPers_Cnt_u16(DesiredTunPersTypH_Cnt_M_u08)

DescEnableCommunication()

####  Program Flow End

N/A

## Periodic Functions

None

## Periodic Event Triggered Functions

#### Design Rationale

This is a high level design of the module. The entire module is not
represented in this document. It is intended to show inputs, outputs and
constant values, plus a high level understanding of the code.

### SrlComInput_Per1

#### Design Rationale

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

\*See below

#### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image2.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image3.wmf)![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image4.wmf)

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image5.wmf)

#### Store Local copy of outputs into Module Outputs

See section above.

#### Program Flow End

N/A

#### Store Local copy of outputs into Module Outputs

See section above.

#### Program Flow End

N/A

## Periodic Event Triggered Functions

##  Fault Recovery Functions

None

##  Shutdown Functions

None

##  Interrupt Functions

None

##  Serial Communication Functions

## Local Function/Macro Definitions [local-functionmacro-definitions]

If these are numerous and defined in a separate source file then
reference the source file only.

### ReadECM_A1

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | ReadECM_A1 | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image6.wmf)

### CBC_PT2

|                      |         |      |     |     |
|----------------------|---------|------|-----|-----|
| **Function Name**    | CBC_PT2 | Type | Min | Max |
| **Arguments Passed** |         |      |     |     |
| **Return Value**     |         |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image7.wmf)

### ReadESP_A8

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | ReadESP_A8 | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image8.wmf)

### IsCRC8Valid

|                      |                      |         |      |      |
|----------------------|----------------------|---------|------|------|
| **Function Name**    | IsCRC8Valid          | Type    | Min  | Max  |
| **Arguments Passed** | Buffer_Ptr_T_u8      | uint8   | Full | Full |
|                      | BufferSize_Cnt_T_u32 | uint32  | Full | Full |
|                      | ExpectedCRC_Cnt_T_u8 | uint8   | Full | Full |
| **Return Value**     | IsCRCOK_Cnt_T_lgc    | boolean | 0    | 1    |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image9.wmf)

### CalcSlewCmd

|                      |                         |         |      |      |
|----------------------|-------------------------|---------|------|------|
| **Function Name**    | CalcSlewCmd             | Type    | Min  | Max  |
| **Arguments Passed** | CurrentCmd_Ptr_T_f32    | float32 | Full | Full |
|                      | SlewRate_Cnt_T_f32      | float32 | Full | Full |
| **Return Value**     | SlewCompleted_Cnt_T_lgc | boolean | 0    | 1    |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image10.wmf)

### DiagCRC11C

|                      |                             |                |      |      |
|---------------|---------------------------|-------------|---------|----------|
| **Function Name**    | DiagCRC11C                  | Type           | Min  | Max  |
| **Arguments Passed** | ESPA8_T_str                 | tVEH_SPEED_PKT | Full | Full |
| **Return Value**     | ReceivedDataValid_Cnt_T_lgc | boolean        | 0    | 1    |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image11.wmf)

### ReadPTS_StrCtrl

|                      |                 |      |     |     |
|----------------------|-----------------|------|-----|-----|
| **Function Name**    | ReadPTS_StrCtrl | Type | Min | Max |
| **Arguments Passed** |                 |      |     |     |
| **Return Value**     |                 |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image12.wmf)

### DiagNTC19C

|                      |                                     |         |     |     |
|---------------|---------------------------|-------------|---------|----------|
| **Function Name**    | DiagNTC19C                          | Type    | Min | Max |
| **Arguments Passed** | TorqueOverlaySteeringReq_HwNm_T_f32 | float32 | -8  | 8   |
| **Return Value**     | IsCmdValid_Cnt_T_lgc                | boolean | 0   | 1   |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image13.wmf)

### DiagNTC19D

|                      |                                     |         |     |     |
|-------------|---------------------------------|------------|--------|--------|
| **Function Name**    | DiagNTC19D                          | Type    | Min | Max |
| **Arguments Passed** | TorqueOverlaySteeringReq_HwNm_T_f32 | float32 | -8  | 8   |
| **Return Value**     | PATrqOvCmdRqst_HwNm_T_f32           | float   | -8  | 8   |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image14.wmf)

### DiagNTC19B

|                      |                        |         |     |       |
|----------------------|------------------------|---------|-----|-------|
| **Function Name**    | DiagNTC19B             | Type    | Min | Max   |
| **Arguments Passed** | MC_29Fh_Cnt_T_u16      | uint16  | 0   | 65535 |
| **Return Value**     | CounterValid_T_Cnt_lgc | boolean | 0   | 1     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image15.wmf)

### DiagNTC1B6

|                      |                                      |         |     |     |
|---------------|---------------------------|-------------|---------|----------|
| **Function Name**    | DiagNTC1B6                           | Type    | Min | Max |
| **Arguments Passed** | TorqueOverlayIntActivation_Cnt_T_lgc | boolean | 0   | 1   |
| **Return Value**     |                                      |         |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image16.wmf)

### DiagCRC29F

|                      |                             |         |      |      |
|----------------------|-----------------------------|---------|------|------|
| **Function Name**    | DiagCRC29F                  | Type    | Min  | Max  |
| **Arguments Passed** | PTS_StrCtrl_T_str           |         | Full | Full |
| **Return Value**     | ReceivedDataValid_Cnt_T_lgc | boolean | 0    | 1    |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image17.wmf)

### ReadVehCfg4

|                      |             |      |     |     |
|----------------------|-------------|------|-----|-----|
| **Function Name**    | ReadVehCfg4 | Type | Min | Max |
| **Arguments Passed** |             |      |     |     |
| **Return Value**     |             |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image18.wmf)

### DiagNTC170

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | DiagNTC170 | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image19.wmf)

### ReadESP_A5

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | ReadESP_A5 | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image20.wmf)

### ReadESP_A6

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | ReadESP_A6 | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image21.wmf)

### ReadVehCfg5

|                      |             |      |     |     |
|----------------------|-------------|------|-----|-----|
| **Function Name**    | ReadVehCfg5 | Type | Min | Max |
| **Arguments Passed** |             |      |     |     |
| **Return Value**     |             |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image22.wmf)

|                      |                           |      |     |     |
|----------------------|---------------------------|------|-----|-----|
| **Function Name**    | ReadHALF_MTO_SteerControl | Type | Min | Max |
| **Arguments Passed** |                           |      |     |     |
| **Return Value**     |                           |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image23.wmf)

|                      |                                        |         |     |     |
|------------|-------------------------------------|----------|-------|--------|
| **Function Name**    | DiagNTC0E9                             | Type    | Min | Max |
| **Arguments Passed** | MotorTorqueOverlaySteeringReq_Nm_T_f32 | Float32 | -8  | 8   |
|                      |                                        |         |     |     |
| **Return Value**     |                                        |         |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image24.wmf)

|                      |                             |       |      |      |
|----------------------|-----------------------------|-------|------|------|
| **Function Name**    | DiagNTC0EE                  | Type  | Min  | Max  |
| **Arguments Passed** | HALFDriveStyleSts_Cnt_T_u08 | Uint8 | full | full |
|                      |                             |       |      |      |
| **Return Value**     |                             |       |      |      |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image25.wmf)

|                      |                       |         |     |     |
|----------------------|-----------------------|---------|-----|-----|
| **Function Name**    | DiagNTC196            | Type    | Min | Max |
| **Arguments Passed** | HaLFState_Cnt_T_u08   | Uint8   | 0   | 255 |
|                      | HaLFStateReq_Nm_T_f32 | Float32 | -8  | 8   |
| **Return Value**     |                       |         |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image26.wmf)

|                      |                                          |         |     |     |
|---------------|----------------------------|-------------|---------|---------|
| **Function Name**    | DiagNTC195                               | Type    | Min | Max |
| **Arguments Passed** | HaLFState_Cnt_T_u08                      | Uint8   | 0   | 255 |
|                      | MotorTorqueOverlaySteeringReq_HwNm_T_f32 | float32 | -8  | 8   |
| **Return Value**     | HaLFTrqOvCmdRqst_MtrNm_T_f32             | float32 | -8  | 8   |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image27.wmf)

|                      |                                         |         |     |     |
|---------------|---------------------------|-------------|---------|----------|
| **Function Name**    | DiagNTC194                              | Type    | Min | Max |
| **Arguments Passed** | HaLFState_Cnt_T_u08                     | Uint8   | 0   | 255 |
|                      | MotorTorqueOverlaySteeringReq_Cnt_T_f32 | Float32 | -8  | 8   |
| **Return Value**     | IsCmdValid_Cnt_T_lgc                    | boolean | 0   | 1   |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image28.wmf)

|                      |                                           |         |     |     |
|---------------|------------------------------------|---------|------|-------|
| **Function Name**    | DiagNTC1C6                                | Type    | Min | Max |
| **Arguments Passed** | MotorTorqueOverlayIntActivation_Cnt_T_lgc | boolean | 0   | 1   |
| **Return Value**     |                                           |         |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image29.wmf)

|                      |                        |         |      |      |
|----------------------|------------------------|---------|------|------|
| **Function Name**    | DiagNTC193             | Type    | Min  | Max  |
| **Arguments Passed** | MC_292h_Cnt_T_u16      | Uint16  | Full | Full |
| **Return Value**     | CounterValid_T_Cnt_lgc | boolean | 0    | 1    |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image30.wmf)

|                      |                        |         |      |      |
|----------------------|------------------------|---------|------|------|
| **Function Name**    | DiagNTC13B_MC11C       | Type    | Min  | Max  |
| **Arguments Passed** | MC_11Ch_Cnt_T_u16      | Uint16  | Full | Full |
| **Return Value**     | CounterValid_T_Cnt_lgc | boolean | 0    | 1    |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image31.wmf)

|                      |                             |        |      |      |
|----------------------|-----------------------------|--------|------|------|
| **Function Name**    | DiagNTC190                  | Type   | Min  | Max  |
| **Arguments Passed** | MTO_HALFSystemSts_Cnt_T_u16 | Uint16 | Full | Full |
| **Return Value**     |                             |        |      |      |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image32.wmf)

|                      |                             |               |      |      |
|-----------------|---------------------------------|----------|------|-------|
| **Function Name**    | DiagCRC292                  | Type          | Min  | Max  |
| **Arguments Passed** | HaLF_StrCtrl_T_str          | tHaLF_StrCtrl | Full | Full |
| **Return Value**     | ReceivedDataValid_Cnt_T_lgc | boolean       | 0    | 1    |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image33.wmf)

|                      |                |      |     |     |
|----------------------|----------------|------|-----|-----|
| **Function Name**    | ReadNET_CFG_PT | Type | Min | Max |
| **Arguments Passed** |                |      |     |     |
| **Return Value**     |                |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image34.wmf)

|                      |                        |      |     |     |
|----------------------|------------------------|------|-----|-----|
| **Function Name**    | ReadSCCM_STW_ANGL_STAT | Type | Min | Max |
| **Arguments Passed** |                        |      |     |     |
| **Return Value**     |                        |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image35.wmf)

|                      |             |      |     |     |
|----------------------|-------------|------|-----|-----|
| **Function Name**    | ReadEcuCfg6 | Type | Min | Max |
| **Arguments Passed** |             |      |     |     |
| **Return Value**     |             |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image36.wmf)

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | DiagNTC1F5 | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image37.wmf)

|                      |             |      |     |     |
|----------------------|-------------|------|-----|-----|
| **Function Name**    | ReadDST_TOC | Type | Min | Max |
| **Arguments Passed** |             |      |     |     |
| **Return Value**     |             |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image38.wmf)

|                      |                   |         |     |     |
|----------------------|-------------------|---------|-----|-----|
| **Function Name**    | DSTDiagNTC188     | Type    | Min | Max |
| **Arguments Passed** | TO_Req_HwNm_T_f32 | float32 | -16 | 16  |
| **Return Value**     |                   |         |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image39.wmf)

|                      |                            |         |     |     |
|----------------------|----------------------------|---------|-----|-----|
| **Function Name**    | DSTDiagNTC18CReqOutOfRange | Type    | Min | Max |
| **Arguments Passed** | TO_Req_HwNm_T_f32          | float32 | -16 | 16  |
| **Return Value**     | IsCmdValid_Cnt_T_lgc       | boolean | 0   | 1   |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image40.wmf)

|                      |                              |         |     |     |
|----------------------|------------------------------|---------|-----|-----|
| **Function Name**    | DSTDiagNTC18DDeltaOutOfRange | Type    | Min | Max |
| **Arguments Passed** | TO_Req_HwNm_T_f32            | float32 | -16 | 16  |
| **Return Value**     | TO_Req_HwNm_T_f32            | float32 | -16 | 16  |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image41.wmf)

|                      |                            |         |     |     |
|----------------------|----------------------------|---------|-----|-----|
| **Function Name**    | DSTDiagNTC18EMaxActiveTime | Type    | Min | Max |
| **Arguments Passed** | TOCSts_T_Cnt_u8            | uint8   | 0   | 255 |
| **Return Value**     | IsNTCFailed_Cnt_T_lgc      | boolean | 0   | 1   |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image42.wmf)

|                      |                         |         |     |     |
|----------------------|-------------------------|---------|-----|-----|
| **Function Name**    | DSTDiagNTC18FRawXORTest | Type    | Min | Max |
| **Arguments Passed** | RawTO_Req_Nm_T_u16      | Uint16  | -16 | 16  |
| **Return Value**     | IsCmdValid_Cnt_T_lgc    | boolean | 0   | 1   |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image43.wmf)

|                      |                       |         |     |     |
|----------------------|-----------------------|---------|-----|-----|
| **Function Name**    | DSTDiagCondtions18CDF | Type    | Min | Max |
| **Arguments Passed** | DSTState_T_Cnt_u8     | uint8   | 0   | 255 |
|                      | DST_TOCState_T_Cnt_u8 | uint8   | 0   | 255 |
| **Return Value**     | MakeDiag18C_Cnt_T_lgc | boolean | 0   | 1   |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image44.wmf)

|                      |                             |          |      |      |
|----------------------|-----------------------------|----------|------|------|
| **Function Name**    | DiagCRC294                  | Type     | Min  | Max  |
| **Arguments Passed** | DST_TOC_T_str               | tDST_TOC | Full | Full |
| **Return Value**     | ReceivedDataValid_Cnt_T_lgc | boolean  | 0    | 1    |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image45.wmf)

|                      |                        |         |      |      |
|----------------------|------------------------|---------|------|------|
| **Function Name**    | DiagNTC18B             | Type    | Min  | Max  |
| **Arguments Passed** | MC_294h_Cnt_T_u16      | uint16  | Full | Full |
| **Return Value**     | CounterValid_T_Cnt_lgc | boolean | 0    | 1    |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image46.wmf)

|                      |                      |        |      |      |
|----------------------|----------------------|--------|------|------|
| **Function Name**    | DiagNTC189           | Type   | Min  | Max  |
| **Arguments Passed** | ElapsedTime_mS_T_u16 | uint16 | Full | Full |
| **Return Value**     |                      |        |      |      |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image47.wmf)

|                      |              |      |     |     |
|----------------------|--------------|------|-----|-----|
| **Function Name**    | ReadTRNSSTAT | Type | Min | Max |
| **Arguments Passed** |              |      |     |     |
| **Return Value**     |              |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image48.wmf)

|                      |                 |      |     |     |
|----------------------|-----------------|------|-----|-----|
| **Function Name**    | ReadWHEELSPEED2 | Type | Min | Max |
| **Arguments Passed** |                 |      |     |     |
| **Return Value**     |                 |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image49.wmf)

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | ReadESP_A4 | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image50.wmf)

|                      |           |      |     |     |
|----------------------|-----------|------|-----|-----|
| **Function Name**    | ReadECMA3 | Type | Min | Max |
| **Arguments Passed** |           |      |     |     |
| **Return Value**     |           |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image51.wmf)

|                      |          |      |     |     |
|----------------------|----------|------|-----|-----|
| **Function Name**    | ReadICA1 | Type | Min | Max |
| **Arguments Passed** |          |      |     |     |
| **Return Value**     |          |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image52.wmf)

|                      |         |      |     |     |
|----------------------|---------|------|-----|-----|
| **Function Name**    | ReadVIN | Type | Min | Max |
| **Arguments Passed** |         |      |     |     |
| **Return Value**     |         |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image53.wmf)

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | ReadENGCFG | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image54.wmf)

|                      |             |      |     |     |
|----------------------|-------------|------|-----|-----|
| **Function Name**    | ReadVehCfg1 | Type | Min | Max |
| **Arguments Passed** |             |      |     |     |
| **Return Value**     |             |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image55.wmf)

|                      |              |      |     |     |
|----------------------|--------------|------|-----|-----|
| **Function Name**    | ReadBATTVOLT | Type | Min | Max |
| **Arguments Passed** |              |      |     |     |
| **Return Value**     |              |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image56.wmf)

|                      |             |      |     |     |
|----------------------|-------------|------|-----|-----|
| **Function Name**    | ReadVehCfg3 | Type | Min | Max |
| **Arguments Passed** |             |      |     |     |
| **Return Value**     |             |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image57.wmf)

|                      |           |      |     |     |
|----------------------|-----------|------|-----|-----|
| **Function Name**    | ReadCfgRQ | Type | Min | Max |
| **Arguments Passed** |           |      |     |     |
| **Return Value**     |           |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image58.wmf)

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | ReadCfgRQC | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image59.wmf)

|                      |              |      |     |     |
|----------------------|--------------|------|-----|-----|
| **Function Name**    | ReadGWLinIC2 | Type | Min | Max |
| **Arguments Passed** |              |      |     |     |
| **Return Value**     |              |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image60.wmf)

|                      |                   |      |     |     |
|----------------------|-------------------|------|-----|-----|
| **Function Name**    | ReadEcmIndicators | Type | Min | Max |
| **Arguments Passed** |                   |      |     |     |
| **Return Value**     |                   |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image61.wmf)

|                      |             |      |     |     |
|----------------------|-------------|------|-----|-----|
| **Function Name**    | ReadCBC_PT1 | Type | Min | Max |
| **Arguments Passed** |             |      |     |     |
| **Return Value**     |             |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image62.wmf)

|                      |             |      |     |     |
|----------------------|-------------|------|-----|-----|
| **Function Name**    | ReadVehCfg7 | Type | Min | Max |
| **Arguments Passed** |             |      |     |     |
| **Return Value**     |             |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image63.wmf)

|                      |             |      |     |     |
|----------------------|-------------|------|-----|-----|
| **Function Name**    | ReadTRNSSPD | Type | Min | Max |
| **Arguments Passed** |             |      |     |     |
| **Return Value**     |             |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image64.wmf)

|                      |                     |         |     |     |
|----------------------|---------------------|---------|-----|-----|
| **Function Name**    | DiagNTC14E          | Type    | Min | Max |
| **Arguments Passed** | BattVolt_Volt_T_f32 | float32 | 0   | 18  |
| **Return Value**     |                     |         |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image65.wmf)

|                      |                     |         |     |     |
|----------------------|---------------------|---------|-----|-----|
| **Function Name**    | DiagNTC14F          | Type    | Min | Max |
| **Arguments Passed** | BattVolt_Volt_T_f32 | float32 | 0   | 18  |
| **Return Value**     |                     |         |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image66.wmf)

.

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | DiagNTC102 | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image67.wmf)

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | DiagNTC104 | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image68.wmf)

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | DiagNTC124 | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image69.wmf)

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | DiagNTC091 | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image70.wmf)

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | DiagNTC0EF | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image71.wmf)

|                      |                       |        |      |      |
|----------------------|-----------------------|--------|------|------|
| **Function Name**    | SrlComInput_WriteBits | Type   | Min  | Max  |
| **Arguments Passed** | Data_T_Cnt_u32        | uint32 | Full | Full |
|                      | Buffer_T_Cnt_u08      | uint8  | Full | Full |
|                      | StartBit_Cnt_T_u16    | uint16 | Full | Full |
|                      | EndBit_Cnt_T_u16      | uint16 | Full | Full |
| **Return Value**     |                       |        |      |      |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image72.wmf)

|                      |             |      |     |     |
|----------------------|-------------|------|-----|-----|
| **Function Name**    | ResetTimers | Type | Min | Max |
| **Arguments Passed** |             |      |     |     |
| **Return Value**     |             |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image73.wmf)

|                      |                                   |         |     |     |
|----------------------|-----------------------------------|---------|-----|-----|
| **Function Name**    | **SrlComInput_SCom_ManualVehSpd** | Type    | Min | Max |
| **Arguments Passed** | VehSpd_Kph_f32                    | float32 | 0   | 255 |
| **Return Value**     |                                   |         |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image74.wmf)

|                      |                |      |     |     |
|----------------------|----------------|------|-----|-----|
| **Function Name**    | VehSpdOverRide | Type | Min | Max |
| **Arguments Passed** |                |      |     |     |
| **Return Value**     |                |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image75.wmf)

|                      |            |      |     |     |
|----------------------|------------|------|-----|-----|
| **Function Name**    | DiagNTC091 | Type | Min | Max |
| **Arguments Passed** |            |      |     |     |
| **Return Value**     |            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image76.wmf)

|                      |                             |      |     |     |
|----------------------|-----------------------------|------|-----|-----|
| **Function Name**    | ClearHALFNTC_MessageNotRcvd | Type | Min | Max |
| **Arguments Passed** |                             |      |     |     |
| **Return Value**     |                             |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image77.wmf)

|                      |                               |      |     |     |
|----------------------|-------------------------------|------|-----|-----|
| **Function Name**    | ClearHALFNTC_RcvdMesgNotValid | Type | Min | Max |
| **Arguments Passed** |                               |      |     |     |
| **Return Value**     |                               |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image78.wmf)

|                      |                            |      |     |     |
|----------------------|----------------------------|------|-----|-----|
| **Function Name**    | ClearPTSNTC_MessageNotRcvd | Type | Min | Max |
| **Arguments Passed** |                            |      |     |     |
| **Return Value**     |                            |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image79.wmf)

|                      |                              |      |     |     |
|----------------------|------------------------------|------|-----|-----|
| **Function Name**    | ClearPTSNTC_RcvdMesgNotValid | Type | Min | Max |
| **Arguments Passed** |                              |      |     |     |
| **Return Value**     |                              |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image80.wmf)

|                      |                               |      |     |     |
|----------------------|-------------------------------|------|-----|-----|
| **Function Name**    | ClearDSTTOCNTC_MessageNotRcvd | Type | Min | Max |
| **Arguments Passed** |                               |      |     |     |
| **Return Value**     |                               |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image81.wmf)

|                      |                                 |      |     |     |
|----------------------|---------------------------------|------|-----|-----|
| **Function Name**    | ClearDSTTOCNTC_RcvdMesgNotValid | Type | Min | Max |
| **Arguments Passed** |                                 |      |     |     |
| **Return Value**     |                                 |      |     |     |

### Description

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/doc/mediax/media/image82.wmf)

# Execution Requirements [execution-requirements]

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the
different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name       | Task List | Calling Frequency | System State(s) in which the function is called |
|--------------------------|----------------|----------------|----------------|
| SrlComInput_Init () |           | On Event (Once)   | On Entering WARMINIT                            |
| SrlComInput_Per1 () |           | 10mS              | WARMINIT, OPERATE, DISABLE                      |

## Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| N/A           |                                                  |

#   [section-3]

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module              | Software Segment             |
|---------------------------------|------------------------------|
| SrlComInput_Init ()             | RTE_AP_SRLCOMINPUT_APPL_CODE |
| SrlComInput_Per1 ()             | RTE_AP_SRLCOMINPUT_APPL_CODE |
| SrlComInput_Scom_ManualVehSpd() | RTE_AP_SRLCOMINPUT_APPL_CODE |

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module           | Software Segment             |
|------------------------------|------------------------------|
| ReadSCCM_STW_ANGL_STAT       | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadECM_A1                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadCBC_PT2                  | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadPTS_StrCtrl              | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadESP_A8                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadESP_A5                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadESP_A6                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadVehCfg5                  | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadHALF_MTO_SteerControl    | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadNET_CFG_PT               | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadEcuCfg6                  | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadDST_TOC                  | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadTRNSSTAT                 | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadVehCfg4                  | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadBATTVOLT                 | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadVehCfg1                  | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadENGCFG                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadVIN                      | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadICA1                     | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadECMA3                    | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadESPA4                    | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadVehCfg3                  | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadWHEELSPEED2              | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadCfgRQ                    | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadCfgRQC                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadGWLinIC2                 | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadEcmIndicators            | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadVehCfg7                  | RTE_AP_SRLCOMINPUT_APPL_CODE |
| ReadCBC_PT1                  | RTE_AP_SRLCOMINPUT_APPL_CODE |
|                              |                              |
| DiagNTC189                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagCRC294                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC18B                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DSTDiagNTC18CreqOutOfRange   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DSTDiagNTC18DdeltaOutOfRange | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DSTDiagNTC18EmaxActiveTime   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DSTDiagNTC18FRawXORTest      | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DSTDiagCondtions18CDF        | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagCRC292                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC190                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC193                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC194                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC195                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC196                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC1C6                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagCRC11C                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC13B_MC11C             | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagCRC29F                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC19B                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC19C                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC19D                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC1B6                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC14E                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC14F                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC102                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC104                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC124                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DiagNTC170                   | RTE_AP_SRLCOMINPUT_APPL_CODE |
|                              |                              |
| SrlComInput_WriteBits        | RTE_AP_SRLCOMINPUT_APPL_CODE |
|                              |                              |
| ResetTimers                  | RTE_AP_SRLCOMINPUT_APPL_CODE |
| DSTDiagNTC188                | RTE_AP_SRLCOMINPUT_APPL_CODE |
| VehSpdOverRide               | RTE_AP_SRLCOMINPUT_APPL_CODE |

#  [section-4]

# Known Issues / Limitations With Design

1.  INLINE functions defined in “GlobalMacro.h” are not unit tested

# Revision Control Log [revision-control-log]

<table style="width:100%;">
<colgroup>
<col style="width: 6%" />
<col style="width: 6%" />
<col style="width: 65%" />
<col style="width: 11%" />
<col style="width: 9%" />
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
<td>Initial Version</td>
<td>05June13</td>
<td>M. Story</td>
</tr>
<tr class="odd">
<td>2</td>
<td>2.0</td>
<td>Anomaly 4866 and the addition of NTC188</td>
<td>11June13</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>3</td>
<td>3.0</td>
<td>Added NTC 1C0, NTC0E9, NTC0EC, NTC0EA and NTC0EB</td>
<td>21June13</td>
<td>M. Story</td>
</tr>
<tr class="odd">
<td>4</td>
<td>4.0</td>
<td>Anomaly 5189</td>
<td>27JUN13</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>5</td>
<td>5.0</td>
<td>Anomaly 5197</td>
<td>09JUL13</td>
<td>M. Story</td>
</tr>
<tr class="odd">
<td>6</td>
<td>6.0</td>
<td>Add FD1B manual VehSpeed</td>
<td>11JUL13</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>7</td>
<td>7.0</td>
<td>Removed Slew</td>
<td>12JUL13</td>
<td>M. Story</td>
</tr>
<tr class="odd">
<td>8</td>
<td>8.0</td>
<td>Anomaly 5245, 5262</td>
<td>17JUL13</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>9</td>
<td>9.0</td>
<td>Anomaly 4603</td>
<td>25JUL13</td>
<td>M. Story</td>
</tr>
<tr class="odd">
<td>10</td>
<td>10</td>
<td>Anomaly 5266</td>
<td>30JUL13</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>11</td>
<td>11</td>
<td>Anomaly 5324, 5339</td>
<td>31JUL13</td>
<td>M. Story</td>
</tr>
<tr class="odd">
<td>12</td>
<td>12</td>
<td>Anomaly 5269, 5356, 5357, 5359, 5358</td>
<td>02AUG13</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>13</td>
<td>13</td>
<td>Anomaly 5373</td>
<td>03AUG13</td>
<td>M. Story</td>
</tr>
<tr class="odd">
<td>14</td>
<td>14</td>
<td>Anomaly 5405, 5420, 5431, 5434, 5446, 5459, 5460, 5476, 5474, 5474
,5477, 5478, 5479</td>
<td>15AUG13</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>15</td>
<td>15</td>
<td>Anomaly 5400, changes for A001, A002, A003, A004</td>
<td>05SEP13</td>
<td>M. Story</td>
</tr>
<tr class="odd">
<td>16</td>
<td>16</td>
<td>Changes for 01.00.02 release of CL</td>
<td>02OCT13</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>20</td>
<td>20</td>
<td><p>Changes made for Anomalies related to CTC not going to history
with NTC in history.Ref Anom 5463.</p>
<p>MDD Version number is changed to 20 from 16 to match synergy
version</p></td>
<td>07Oct 13</td>
<td>NRAR</td>
</tr>
<tr class="odd">
<td>21</td>
<td>21</td>
<td>18C,18D,18E,188,18F NTC’s are set to PASSED when fails enable
criteria</td>
<td>11OCT13</td>
<td>NRAR</td>
</tr>
<tr class="even">
<td>22</td>
<td>22</td>
<td>NTC 189 set to PASSED when DSTFUNC present is false</td>
<td>14OCT13</td>
<td>NRAR</td>
</tr>
<tr class="odd">
<td>23</td>
<td>23</td>
<td>Updated for changes in version L 01.00.04</td>
<td>24OCT13</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>24</td>
<td>24</td>
<td></td>
<td>04NOV13</td>
<td>M. Story</td>
</tr>
<tr class="odd">
<td>25</td>
<td>25</td>
<td>Anomaly 5959</td>
<td>06NOV13</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>26</td>
<td>26</td>
<td>Fixes for DST and HALF NTC’s</td>
<td>08NOV13</td>
<td>NRAR</td>
</tr>
<tr class="odd">
<td>27</td>
<td>27</td>
<td>Changes for L02.00.00 and CW 01.00.04</td>
<td>21NOV13</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>28</td>
<td>28</td>
<td>Anomaly 6128</td>
<td>04Dec13</td>
<td>M. Story</td>
</tr>
<tr class="odd">
<td>29</td>
<td>29</td>
<td>Anomaly 6192 6193</td>
<td>08JAN14</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>30</td>
<td>30</td>
<td>Anomaly 6209 6207</td>
<td>16JAN14</td>
<td>M. Story</td>
</tr>
<tr class="odd">
<td>31</td>
<td>31</td>
<td>Updates for SER 7A</td>
<td>10FEB14</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>32</td>
<td>32</td>
<td>Anomalies 6355, 6358, 6364, 6365, 6366, 6386, 6392,</td>
<td>26FEB14</td>
<td>M. Story</td>
</tr>
<tr class="odd">
<td>33</td>
<td>33</td>
<td>Anomalies 6434, 6436</td>
<td>06MAR14</td>
<td>M. Story</td>
</tr>
<tr class="even">
<td>34</td>
<td>33.1.1</td>
<td>Added DST logic to NTC 194</td>
<td>15MAY14</td>
<td>SAH</td>
</tr>
<tr class="odd">
<td>35</td>
<td>33.1.2</td>
<td>Anomaly 6806, added prev values for HaLF enable and trqovrqst as
outputs</td>
<td>20MAY14</td>
<td>SAH</td>
</tr>
<tr class="even">
<td>36</td>
<td>33.1.3</td>
<td>Updated NTC 0x1DF to clear bit from HaLFErrInterfaceActive_Cnt_M_bit
when message is received.</td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

{% endraw %}