---
layout: default
title: Integration_Manual_ADC
nav_order: 5
parent: Adc Driver
---
{% raw %}
[1 Dependencies [2](#dependencies)](#dependencies)

[1.1 SWCs [2](#swcs)](#swcs)

[1.2 Configuration Files to be provided by Integration Project
[2](#configuration-files-to-be-provided-by-integration-project)](#configuration-files-to-be-provided-by-integration-project)

[1.3 Functions to be provided to Integration Project
[2](#functions-to-be-provided-to-integration-project)](#functions-to-be-provided-to-integration-project)

[2 Configuration [3](#configuration)](#configuration)

[2.1 Build Time Config [3](#build-time-config)](#build-time-config)

[2.2 Generator Config [3](#generator-config)](#generator-config)

[3 Integration [4](#integration)](#integration)

[3.1 Global Data [4](#global-data)](#global-data)

[3.2 Component Conflicts
[4](#component-conflicts)](#component-conflicts)

[3.3 Include Path [4](#include-path)](#include-path)

[3.4 Configurator Changes
[4](#configurator-changes)](#configurator-changes)

[4 Runnable Scheduling [5](#runnable-scheduling)](#runnable-scheduling)

[5 Memory Mapping [6](#memory-mapping)](#memory-mapping)

[5.1 Mapping [6](#mapping)](#mapping)

[5.2 Usage [6](#usage)](#usage)

[6 Revision Control Log
[7](#revision-control-log)](#revision-control-log)

# Dependencies

## SWCs

| Module | Required Feature |
|--------|------------------|
|        |                  |

## Configuration Files to be provided by Integration Project

NOTE:

For Projects using 33E, make sure “D_ADC1CURRENTMODE_ULS_LGC” is defined
Adc_Cfg.h file.

For Projects using 33C, make sure “D_ADC1CURRENTMODE_ULS_LGC” is **NOT**
defined Adc_Cfg.h file.

Template for Configuration file:

Adc_Cfg.h

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Adc/doc/mediax/media/image1.emf)

Adc2_Cfg.h

![](ElectricPowerSteering_TexasInstruments_CHRYSLER_LWR_website/docs/Adc/doc/mediax/media/image2.emf)

## Functions to be provided to Integration Project

Adc2_ReadConversion

Adc2_Init1

Adc2_StartGroupConversion

Adc2_EnableGroupNotification

Adc_Init_FixedCfg

Adc_StartGroupConversion

Adc_ReadGroup

Adc_GetGroupStatus

# Configuration

## Build Time Config

| Modules | Notes |     |
|---------|-------|-----|
| None    |       |     |

## Generator Config

| Constant | Notes | SWC |
|----------|-------|-----|
| None     |       |     |

# Integration

## Global Data

None

## Component Conflicts

IoHwAb

## Include Path

\$PROJECTPATH\$\Adc\include

Adc.h, Adc2.h, Adc_Common.h

## Configurator Changes

None

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init         | Scheduling Requirements              | Trigger     |
|--------------|--------------------------------------|-------------|
| Adc_Init()   | Before **Adc2_Init1** initialization | ECU Startup |
| Adc2_Init1() | Before **PWMCdd** initialization     | ECU Startup |

| Runnable                 | Scheduling Requirements | Trigger |
|--------------------------|-------------------------|---------|
| Adc_StartGroupConversion | None                    | ISR     |

\*Note:

**.**

# Memory Mapping

## Mapping

| Memory Section          | Contents | Notes |
|-------------------------|----------|-------|
| ADC2_START_SEC_CODE     |          |       |
| ADC2_START_SEC_CONST_32 |          |       |
| ADC_START_SEC_CONST_32  |          |       |
| ADC_START_SEC_CODE      |          |       |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature                | RAM | ROM |
|------------------------|-----|-----|
| \<Memmap usuage info\> |     |     |

Table 1: ARM Cortex R4 Memory Usage

# Revision Control Log

| **Rev \#** | **Change Description** | **Date**  | **Author** |
|------------|------------------------|-----------|------------|
| 1          | Initial version        | 09-Apr-13 | Selva      |

{% endraw %}