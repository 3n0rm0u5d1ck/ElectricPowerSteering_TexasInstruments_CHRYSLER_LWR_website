---
layout: default
title: Adc_MDD
nav_order: 3
parent: Adc Driver
---
{% raw %}
# Module -- ADC [module----adc]

# High-Level Description

The ADC module shall control sampling and conversion of voltages from
the hardware layer into digital signals. The ADC Register definition has
been captured from the TMS570LS31x/21x 16/32-Bit RISC Flash
Microcontroller Technical Reference Manual (SPNU499 – September 2011).

# Figures

## Component Diagram

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs | Module Outputs |
|---------------|----------------|
| None          | None           |

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
<col style="width: 26%" />
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
<td>None</td>
<td></td>
<td></td>
<td></td>
<td></td>
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
<td>Adc_GroupType</td>
<td>N/A</td>
<td>uint8</td>
<td>0</td>
<td>2</td>
</tr>
<tr class="even">
<td>Adc_GroupConfigDataType</td>
<td><p>uint8 NumOfChannels,</p>
<p>uint32 ChannelSelect,</p>
<p>uint32* ResultBuf</p></td>
<td>struct</td>
<td>FULL</td>
<td>FULL</td>
</tr>
<tr class="odd">
<td>Adc_StatusType</td>
<td><p>ADC_IDLE,</p>
<p>ADC_BUSY,</p>
<p>ADC_COMPLETED,</p>
<p>ADC_STREAM_COMPLETED</p></td>
<td>enum</td>
<td>0</td>
<td>3</td>
</tr>
<tr class="even">
<td>Adc_ValueGroupType</td>
<td>N/A</td>
<td>uint16</td>
<td>0</td>
<td>4095</td>
</tr>
<tr class="odd">
<td>Adc_ValueGroupType</td>
<td>N/A</td>
<td>uint16*</td>
<td>FULL</td>
<td>FULL</td>
</tr>
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

| Constant Name                   |
|---------------------------------|
| k_VbattOVTransIntConfig_Cnt_u32 |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name              | Resolution | Units   | Value                                |
|----------------------------|-----------------|--------------|--------------|
| D_NUMOFGROUPS_CNT_U8       | 1          | Counts  | 3                                    |
| D_GROUPEV_CNT_U8           | 1          | Counts  | 0                                    |
| D_GROUP1_CNT_U8            | 1          | Counts  | 1                                    |
| D_GROUP2_CNT_U8            | 1          | Counts  | 2                                    |
| D_NUMOFADCCALREADS_CNT_U8  | 1          | Counts  | 8                                    |
| D_NTCPARMBIT0_CNT_U8       | 1          | Counts  | 1                                    |
| D_NTCPARMBIT1_CNT_U8       | 1          | Counts  | 2                                    |
| D_NTCPARMBIT2_CNT_U8       | 1          | Counts  | 4                                    |
| D_ADC1RSLTBASEADR_CNT_U32  | 1          | Counts  | 0xFF3E0000U                          |
| D_ADC1NUMRSLTBUF_CNT_U08   | 1          | Counts  | 64                                   |
| D_ADC1CURRENTMODE_ULS_LGC  | 1          | BOOLEAN | Generated in Adc_Cfg.h.              |
| D_ADC1MAGINTMASK1_CNT_U16  | 1          | Counts  | 0/0\*                                |
| D_ADC1MAGINTASET_CNT_U16   | 1          | Counts  | 1/0\*                                |
| D_ADC1MAGINTCR1_CNT_U32    | 1          | Counts  | k_VbattOVTransIntConfig_Cnt_u32/ 0\* |
| D_ADC1THRINTENACLR_CNT_U16 | 1          | Counts  | 6/7\*                                |
| D_ADC1EVTBUFSZ_CNT_U08     | 1          | Counts  | Generated in Adc_Cfg.h.              |
| D_ADC1G1BUFSZ_CNT_U08      | 1          | Counts  | Generated in Adc_Cfg.h.              |
| D_ADC1G2BUFSZ_CNT_U08      | 1          | Counts  | Generated in Adc_Cfg.h.              |
| D_GROUPEND_CNT_U32         | 1          | Counts  | Generated in Adc_Cfg.h.              |
| D_GROUPBUSY_CNT_U32        | 1          | Counts  | Generated in Adc_Cfg.h.              |

#### D_ADC1CURRENTMODE_ULS_LGC if True value 1 is selected to proceed. If not value 2 will be used, [d_adc1currentmode_uls_lgc-if-true-value-1-is-selected-to-proceed.-if-not-value-2-will-be-used]

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name                                         |
|-------------------------------------------------------|
| T_Adc1GroupConfigData_Cnt_Str\[D_NUMOFGROUPS_CNT_U8\] |
|                                                       |

### Module specific Lookup Tables Constants

| Constant Name | Resolution | Value | Software Segment |
|---------------|------------|-------|------------------|
| None          |            |       |                  |

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

1.  None

## Data Hiding Functions

1.  \<None\>

## Global Functions/Macros Defined by this Module

### ADC Init

<table>
<colgroup>
<col style="width: 22%" />
<col style="width: 41%" />
<col style="width: 16%" />
<col style="width: 6%" />
<col style="width: 6%" />
<col style="width: 6%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Function Name</strong></th>
<th><p>Adc_Init_FixedCfg</p>
<p>( macro aliased is Adc_Init(x) )</p></th>
<th>Type</th>
<th>Min</th>
<th>Max</th>
<th>UTP Tol.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Arguments Passed</strong></td>
<td>None</td>
<td>N/A</td>
<td>N/A</td>
<td>N/A</td>
<td></td>
</tr>
<tr class="even">
<td><strong>Return Value</strong></td>
<td>N/A</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

This function is used to initialize each of the ADC1 Groups (Event,
Group1, and Group2).

#### Initialize Module Internal Variables

None

#### Register Configuration

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Adc/doc/mediax/media/image1.emf)

### Setup Result Buffer

| **Function Name**    | Adc_SetupResultBuffer | Type                  | Min  | Max  | UTP Tol. |
|--------------|--------------------------|----------------|------|------|------|
| **Arguments Passed** | Group                 | Adc_GroupType         | 0    | 2    |          |
|                      | DataBufferPtr         | Adc_ValueGroupRefType | FULL | FULL |          |
| **Return Value**     | N/A                   | Std_ReturnType        | 0    | 0    | 0        |

This function is the Adc group result buffer setup service. It is
responsible for setting up the result buffer pointer of the group.

This Api is provided to support for the standard Autosar API, however
the design of this driver does not buffer an intermediate copy of the
results and therefore does not require a result buffer. The hardware
provides a sufficient Adc results buffer.

For optimization purposes, this function could be defined as a macro.

#### Setup Group’s Result Buffer

return E_OK

### Start Group Conversion

| **Function Name**    | Adc_StartGroupConversion | Type                  | Min  | Max  | UTP Tol. |
|--------------|--------------------------|----------------|------|------|------|
| **Arguments Passed** | Group                    | Adc_GroupType         | 0    | 2    |          |
|                      | DataBufferPtr            | Adc_ValueGroupRefType | FULL | FULL |          |
| **Return Value**     | N/A                      | Std_ReturnType        | 0    | 0    | 0        |

This function starts a software triggered conversion of all channels of
the requested Adc channel group.

In order to provide optimized execution of this single line function,
this API should be defined as a macro, however, due to timing it is at
the moment defined as a function. The need for minimal runtime is driven
by a Nexteer use case which executes this in the context of the MtrCtrl
ISR in some EPS systems.

#### Select Channels to Convert

adcREG1-\>GxSEL\[Group\] =
T_Adc1GroupConfigData_Cnt_Str\[Group\].ChannelSelect

### Get Group Status

| **Function Name**    | Adc_GetGroupStatus   | Type           | Min | Max | UTP Tol. |
|--------------|--------------------------|----------------|------|------|------|
| **Arguments Passed** | Group                | Adc_GroupType  | 0   | 2   |          |
| **Return Value**     | ReturnVal_Cnt_T_Enum | Adc_StatusType | 0   | 3   | 0        |

Returns the conversion status of the requested ADC1 channel group.

#### Get Status

> ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Adc/doc/mediax/media/image2.emf)

### Read Group Conversions

| **Function Name**    | Adc_ReadGroup        | Type           | Min | Max | UTP Tol. |
|--------------|--------------------------|----------------|------|------|------|
| **Arguments Passed** | Group                | Adc_GroupType  | 0   | 2   |          |
| **Return Value**     | ReturnVal_Cnt_T_Enum | Adc_StatusType | 0   | 3   | 0        |

Reads the group conversion result of the last completed conversion round
of the requested group and

stores the channel values starting at the DataBufferPtr address. The
group channel values are stored in ascending channel number order (in
contrast to the storage layout of the result buffer if streaming access
is configured).

Per the design direction in FDD33, direct ADC result buffer acces is
used instead of using the hardware FIFO access register.

#### Read Group

> ![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Adc/doc/mediax/media/image3.emf)

## Local Functions/Macros Used by this MDD only

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

None

## Initialization Functions

None

## Periodic Functions

None

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

## Transition Functions

None

##  

# Execution Requirements

## Execution Sequence of the Module

Adc_Init should be called after SystemTime_Init due to the use of the uS
System Time.

Adc_Init should be called prior to IoHwAb_Init to ensure registers are
configured prior to triggering initial conversions.

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name | Calling Frequency        | System State(s) in which the function is called |
|--------------------------|-----------------|------------------------------|
| Adc_Init      | Once (at initialization) | STARTUP                                         |

## Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| N/A           |                                                  |

#  [section-1]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module       | Software Segment   |
|--------------------------|--------------------|
| Adc_Init                 | ADC_START_SEC_CODE |
| Adc_SetupResultBuffer    | ADC_START_SEC_CODE |
| Adc_StartGroupConversion | ADC_START_SEC_CODE |
| Adc_ReadGroup            | ADC_START_SEC_CODE |
| Adc_GetGroupStatus       | ADC_START_SEC_CODE |
| ADCOffsetCalibration     | ADC_START_SEC_CODE |

##  [section-2]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module | Software Segment |
|--------------------|------------------|
|                    |                  |

#  [section-3]

#  Known Issues / Limitations With Design

1.  INLINE functions defined in “GlobalMacro.h” are not unit tested

#  Revision Control Log

<table style="width:100%;">
<colgroup>
<col style="width: 6%" />
<col style="width: 6%" />
<col style="width: 63%" />
<col style="width: 12%" />
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
<td>Initial version based on FDD 33C rev 006</td>
<td>05Nov12</td>
<td>LN</td>
</tr>
<tr class="even">
<td>2</td>
<td>2</td>
<td><p>Constant confiuguration tables renamed to start with “T_”</p>
<p>Rewored Adc_ReadGroup to provide direct fixed memory access as
required in the FDD</p></td>
<td>15Jan13</td>
<td>JJW</td>
</tr>
<tr class="odd">
<td>3</td>
<td>3</td>
<td>Updated FDD 33C rev 007 and FDD33E rev2</td>
<td>25-April-13</td>
<td>Selva</td>
</tr>
</tbody>
</table>

{% endraw %}