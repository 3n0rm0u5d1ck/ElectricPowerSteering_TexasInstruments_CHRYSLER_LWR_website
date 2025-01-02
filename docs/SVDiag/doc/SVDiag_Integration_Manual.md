---
layout: default
title: SVDiag_Integration_Manual
nav_order: 5
parent: Component
---
{% raw %}
[1 Dependencies [2](#dependencies)](#dependencies)

[1.1 SWCs [2](#swcs)](#swcs)

[1.2 Functions to be provided to Integration Project
[2](#global-functionsnon-rte-to-be-provided-to-integration-project)](#global-functionsnon-rte-to-be-provided-to-integration-project)

[2 Configuration [3](#configuration)](#configuration)

[2.1 Build Time Config [3](#build-time-config)](#build-time-config)

[2.2 Configuration Files to be provided by Integration Project
[3](#section)](#section)

[2.2.1 Da Vinci Config generation
[3](#da-vinci-parameter-configuration-changes)](#da-vinci-parameter-configuration-changes)

[2.2.2 Manual Configuration Changes
[3](#da-vinci-parameter-configuration-changes)](#da-vinci-parameter-configuration-changes)

[3 Integration [4](#integration)](#integration)

[3.1 Required Global Data Inputs
[4](#required-global-data-inputs)](#required-global-data-inputs)

[3.2 Optional Global Data Inputs [4](#_Toc357692828)](#_Toc357692828)

[3.3 Specific Include Path present
[4](#specific-include-path-present)](#specific-include-path-present)

[4 Runnable Scheduling [5](#runnable-scheduling)](#runnable-scheduling)

[5 Memory Mapping [6](#memory-mapping)](#memory-mapping)

[5.1 Mapping [6](#mapping)](#mapping)

[5.2 Usage [6](#usage)](#usage)

[5.3 NvM Blocks [6](#non-rte-nvm-blocks)](#non-rte-nvm-blocks)

[6 Compiler Settings [6](#compiler-settings)](#compiler-settings)

[6.1 Preprocessor MACRO [6](#preprocessor-macro)](#preprocessor-macro)

[6.2 Optimization Settings
[6](#optimization-settings)](#optimization-settings)

[7 Revision Control Log
[7](#revision-control-log)](#revision-control-log)

# Dependencies

## SWCs

| Module | Required Feature |
|--------|------------------|
| None   |                  |

## Global Functions(Non RTE) to be provided to Integration Project

\< Global function (except the ones that are defined in RTE modules)
that is defined in this component but used by other function\>

# Configuration

## Build Time Config

| Modules | Notes |     |
|---------|-------|-----|
| None    |       |     |

##  [section]

## Configuration Files to be provided by Integration Project

\<Configuration file that will generated from this components that will
require Da Vinci Config generation or manual generation. Describe each
parameter \>

### Da Vinci Parameter Configuration Changes

| Parameter | Notes | SWC |
|-----------|-------|-----|
| None      |       |     |

### DaVinci Interrupt Configuration Changes

| ISR Name | VIM \# | Priority Dependency | Notes |
|----------|--------|---------------------|-------|
| None     |        |                     |       |

### Manual Configuration Changes

| Constant | Notes | SWC |
|----------|-------|-----|
| None     |       |     |

# Integration

## Required Global Data Inputs

ExpectedOnTimeA_Cnt_u32

ExpectedOnTimeB_Cnt_u32

ExpectedOnTimeC_Cnt_u32

LRPRCorrectedMtrPosCaptured_Rev_f32

LRPRModulationIndexCaptured_Uls_f32

LRPRPhaseadvanceCaptured_Cnt_s16

MeasuredOnTimeA_Cnt_u32

MeasuredOnTimeB_Cnt_u32

MeasuredOnTimeC_Cnt_u32

MotorVelMRFUnfiltered_MtrRadpS_f32

MtrElecMechPolarity_Cnt_s08

PDActivateTest_Cnt_lgc

MtrDrvrInitStart_Cnt_lgc

VswitchClosed_Cnt_lgc

## Required Global Data Outputs

SVDiag_LowPhReasErrorAcc_Cnt_u16

SVDiag_HighResPhsReasDisable_u8

SVDiag_LowResPhsReasDisable_u8

SVDiag_MtrDrvInitComp_Cnt_lgc

SVDiag_GateDriveFltAcc_Cnt_u16

SVDiag_GenGateDriveFltAcc_Cnt_u16

SVDiag_OnStateFltAcc_Cnt_u16

## Specific Include Path present

None

# Runnable Scheduling 

This section specifies the required runnable scheduling.

| Init                | Scheduling Requirements                                                     | Trigger          |
|-------------------|---------------------------------------|---------------|
| DigPhsReasDiag_Init | Executed once after the RTE is started before first call of MtrDrvDiag_Per1 | RTE (at Startup) |

| Runnable              | Scheduling Requirements                | Trigger          |
|-------------------|---------------------------------------|---------------|
| DigPhsReasDiag_Per1   | Not in OFF, DISABLE, or WARMINIT modes | Rte 2ms task     |
| DigPhsReasDiag_Trans1 | In OPERATE mode                        | On entering mode |
| MtrDrvDiag_Per1       | Not in DISABLE or OFF modes            | Rte 2ms task     |
| MtrDrvDiag_Per2       | Not in OPERATE or WARMINIT modes       | Rte 2ms task     |
| MtrDrvDiag_Trns1      | In WARMINIT mode                       | On entering mode |

# Memory Mapping

## Mapping

| Memory Section                               | Contents | Notes |
|----------------------------------------------|----------|-------|
| \< Memory mapping Info\>                     |          |       |
| DIGPHSREASDIAG_START_SEC_VAR_CLEARED_32      |          |       |
| DIGPHSREASDIAG_START_SEC_VAR_CLEARED_BOOLEAN |          |       |
| DIGPHSREASDIAG_START_SEC_VAR_CLEARED_16      |          |       |
| DIGPHSREASDIAG_START_SEC_VAR_CLEARED_8       |          |       |
| MTRDRVDIAG_START_SEC_VAR_CLEARED_32          |          |       |
| MTRDRVDIAG_START_SEC_VAR_CLEARED_16          |          |       |
| MTRDRVDIAG_START_SEC_VAR_CLEARED_BOOLEAN     |          |       |
| MTRDRVDIAG_START_SEC_VAR_CLEARED_UNSPECIFIED |          |       |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature | RAM | ROM |
|---------|-----|-----|
| Full    |     |     |

Table 1: ARM Cortex R4 Memory Usage

## Non RTE NvM Blocks

| Block Name |
|------------|
| None       |

Note : Size of the NVM block if configured in developer

##  RTE NvM Blocks

| Block Name |
|------------|
| None       |

Note : Size of the NVM block if configured in developer

# Compiler Settings

##  Preprocessor MACRO

\<Define all the preprocessor Macros needed and conditions when
needed\>.

## Optimization Settings

\<Define Optimization levels that are needed and conditions when
needed\>.

# Revision Control Log

|            |                        |          |            |
|------------|------------------------|----------|------------|
| **Rev \#** | **Change Description** | **Date** | **Author** |
| 1          | Initial version        | 3-Oct-13 | VT         |

{% endraw %}