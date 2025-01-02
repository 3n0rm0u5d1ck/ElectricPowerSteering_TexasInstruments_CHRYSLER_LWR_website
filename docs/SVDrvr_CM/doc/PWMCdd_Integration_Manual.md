---
layout: default
title: PWMCdd_Integration_Manual
nav_order: 3
parent: Component
---
{% raw %}
# Contents [contents]

[1 Dependencies [2](#dependencies)](#dependencies)

[1.1 SWCs [2](#swcs)](#swcs)

[1.2 Configuration Files to be provided by Integration Project (Project
Specific)
[2](#configuration-files-to-be-provided-by-integration-project-project-specific)](#configuration-files-to-be-provided-by-integration-project-project-specific)

[1.3 Functions provided to Integration Project
[2](#functions-provided-to-integration-project)](#functions-provided-to-integration-project)

[2 Configuration [3](#configuration)](#configuration)

[2.1 Build Time Config [3](#build-time-config)](#build-time-config)

[2.2 Generator Config [3](#generator-config)](#generator-config)

[3 Integration [4](#integration)](#integration)

[3.1 Global Data [4](#global-data)](#global-data)

[3.2 Component Conflicts
[4](#component-conflicts)](#component-conflicts)

[3.2.1 Project Specific [4](#project-specific)](#project-specific)

[3.3 Include Path [4](#include-path)](#include-path)

[4 Runnable Scheduling [5](#runnable-scheduling)](#runnable-scheduling)

[5 Memory Mapping [5](#memory-mapping)](#memory-mapping)

[5.1 Mapping [5](#mapping)](#mapping)

[5.2 Usage [5](#usage)](#usage)

[6 Revision Control Log
[6](#revision-control-log)](#revision-control-log)

# Dependencies

## SWCs

| Module   | Required Feature                                      |
|----------|-------------------------------------------------------|
| CDD_Data | Global variables for DC Phs Comp (for using in Nhet/) |

## Configuration Files to be provided by Integration Project (Project Specific)

PWMCdd_Cfg.h ( Note : Make sure Macro assignments match correct global
variable included in PWMCdd_Cfg.h . File below is a template. Necessary
definition changes needs to be made to template before integration).

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/SVDrvr_CM/doc/mediax/media/image1.emf)

## Functions provided to Integration Project

CDDPorts_ClearPhsReasSum(uint16 DataAccessBfr_Cnt_T_u16)

CDD_ApplyPWMMtrElecMechPol(sint8 MtrElecMechPol_Cnt_s8)

# Configuration

## Build Time Config

| Constant | Notes | SWC |
|----------|-------|-----|
|          |       |     |

## Generator Config

| Constant | Notes | SWC |
|----------|-------|-----|
|          |       |     |

# Integration

## Global Data

The following global symbols must be defined in CDD_Data.c and .h
(populated by PwmCdd):

-   uint16: CDD_DCPhsComp_Cnt_G_u16\[3\]

-   uint16: CDD_PWMPeriod_Cnt_G_u16

## Component Conflicts

### Project Specific 

-   **NHET/EPWM** version corresponding PWMCdd component spilt and using
    global variables CDD_DCPhsComp_Cnt_G_u16 and CDD_PWMPeriod_Cnt_G_u16
    should be used.

## Include Path

The “include” directory of this SWC needs to be included in the
integration project include search path.

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Runnable    | Scheduling Requirements                                                                                                  | Trigger         |
|------------------------|---------------------------------|----------------|
| PwmCdd_Init | Place in EcuStartup. Execute along with NHET initialization.                                                             | Init            |
| PwmCdd_Per1 | Must be placed in the motor control ISR, before Nhet (or whichever function populates the global variables used byNhet). | Cyclic (ISR) \* |

\*Note: don’t forget include header file from PWMCDD where PwmCdd_Per1
is called

# Memory Mapping

## Mapping

| Memory Section                  | Contents             | Notes |
|---------------------------------|----------------------|-------|
| PWMCDD_START_SEC_VAR_CLEARED_16 | Variable Definitions |       |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature     | RAM | ROM |
|-------------|-----|-----|
| Full driver |     |     |

Table 1: ARM Cortex R4 Memory Usage

# Revision Control Log

| **Rev \#** | **Change Description** | **Date**  | **Author** |
|------------|------------------------|-----------|------------|
| 1          | Initial version        | 14-Feb-13 | Selva      |

{% endraw %}