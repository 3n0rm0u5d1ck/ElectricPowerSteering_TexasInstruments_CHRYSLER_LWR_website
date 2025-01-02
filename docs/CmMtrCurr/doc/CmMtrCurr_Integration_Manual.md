---
layout: default
title: CmMtrCurr_Integration_Manual
nav_order: 2
parent: Component
---
{% raw %}
[1 Dependencies [2](#dependencies)](#dependencies)

[1.1 SWCs [2](#swcs)](#swcs)

[1.2 Functions to be provided to Integration Project
[2](#functions-to-be-provided-to-integration-project)](#functions-to-be-provided-to-integration-project)

[2 Configuration [3](#configuration)](#configuration)

[2.1 Build Time Config [3](#build-time-config)](#build-time-config)

[2.2 Configuration Files to be provided by Integration Project
[3](#configuration-files-to-be-provided-by-integration-project)](#configuration-files-to-be-provided-by-integration-project)

[2.2.1 Da Vinci Config Configuration Changes
[3](#da-vinci-config-configuration-changes)](#da-vinci-config-configuration-changes)

[2.2.2 Manual Configuration Changes
[3](#manual-configuration-changes)](#manual-configuration-changes)

[3 Integration [5](#integration)](#integration)

[3.1 Required Global Data Inputs
[5](#required-global-data-inputs)](#required-global-data-inputs)

[3.2 Specific Include Path present
[5](#specific-include-path-present)](#specific-include-path-present)

[4 Runnable Scheduling [6](#runnable-scheduling)](#runnable-scheduling)

[5 Memory Mapping [7](#memory-mapping)](#memory-mapping)

[5.1 Mapping [7](#mapping)](#mapping)

[5.2 Usage [7](#usage)](#usage)

[5.3 RTE NvM Blocks [7](#rte-nvm-blocks)](#rte-nvm-blocks)

[5.4 Non RTE NvM Blocks [7](#non-rte-nvm-blocks)](#non-rte-nvm-blocks)

[6 Compiler Settings [7](#compiler-settings)](#compiler-settings)

[6.1 Preprocessor MACRO [7](#preprocessor-macro)](#preprocessor-macro)

[6.2 Optimization Settings
[7](#optimization-settings)](#optimization-settings)

[7 Revision Control Log
[8](#revision-control-log)](#revision-control-log)

# Dependencies

## SWCs

| Module | Required Feature |
|--------|------------------|
|        |                  |

Note : Referencing the external components should be avoided in most
cases. Only in unavoidable circumstance external components should be
refered. Developer should track the references.

## Functions to be provided to Integration Project

CurrDQPer1

# Configuration

## Build Time Config

| Modules | Notes |     |
|---------|-------|-----|
| None    |       |     |

## Configuration Files to be provided by Integration Project

##  [section]

CmMtrCurr_Cfg.h ( Refer CmMtrCurr_Cfg_Template.h in tools folder)

(Data synchronization must be provided at the integration level between
2 ms periodic and Motor Control ISR Periodic’s)

Outputs from the CmMtrCurr (Motor Control ISR) periodic must be
synchronized with the outputs from

ES51 Signal correction outputs (Motor Control ISR) and buffered and
mapped to 2 ms Task.

### Da Vinci Config Configuration Changes

| Constant       | Notes                                       | SWC |
|----------------|---------------------------------------------|-----|
| MTRCURRPHASEBC | PhaseB and Phase C used in Curr Measurement |     |
| MTRCURRPHASECB | PhaseC and Phase B used in Curr Measurement |     |
| MTRCURRPHASEAC | PhaseA and Phase C used in Curr Measurement |     |
| MTRCURRPHASECA | PhaseC and Phase A used in Curr Measurement |     |
| MTRCURRPHASEAB | PhaseA and Phase B used in Curr Measurement |     |
| MTRCURRPHASEBA | PhaseB and Phase A used in Curr Measurement |     |

Note: Only one of the configuration can be selected based on the
requirements. Make sure order matches oreder in ADC data read ie
MTRCURRPHASEBC - “BC” represents current_1 is phase B and current_2 is
phase C .

### Manual Configuration Changes

| Constant | Notes | SWC |
|----------|-------|-----|
| none     |       |     |
|          |       |     |
|          |       |     |
|          |       |     |
|          |       |     |
|          |       |     |

# Integration

## Required Global Data Inputs

## Specific Include Path present

Yes

# Runnable Scheduling 

This section specifies the required runnable scheduling.

| Init           | Scheduling Requirements | Trigger |
|----------------|-------------------------|---------|
| CmMtrCurr_Init | None                    | RTE     |

| Runnable       | Scheduling Requirements        | Trigger         |
|----------------|--------------------------------|-----------------|
| CmMtrCurr_Per2 | None                           | RTE(2MilliS)    |
| CmMtrCurr_Per1 | None                           | RTE(100 MilliS) |
| CurrDQPer1     | After DigMSB Signal processing | ISR (50MicroS)  |
|                |                                |                 |
|                |                                |                 |

**.**

# Memory Mapping

## Mapping

| Memory Section                          | Contents | Notes |
|-----------------------------------------|----------|-------|
| CMMTRCURR_START_SEC_VAR_CLEARED_16      |          |       |
| CMMTRCURR_START_SEC_VAR_CLEARED_8       |          |       |
| CMMTRCURR_START_SEC_VAR_CLEARED_BOOLEAN |          |       |
| CMMTRCURR_START_SEC_VAR_CLEARED_32      |          |       |
| SA_CMMTRCURR_CODE                       |          |       |
| RTE_START_SEC_SA_CMMTRCURR_APPL_CODE    |          |       |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature | RAM | ROM |
|---------|-----|-----|
|         |     |     |

Table 1: ARM Cortex R4 Memory Usage

## RTE NvM Blocks

| Block Name |
|------------|
| None       |

Note : Size of the NVM block if configured in developer

## Non RTE NvM Blocks

| Block Name |
|------------|
| None       |

Note : Size of the NVM block if configured in developer

# Compiler Settings

##  Preprocessor MACRO

None

## Optimization Settings

None

##  [section-1]

# Revision Control Log

| **Rev \#** | **Change Description** | **Date**  | **Author** |
|------------|------------------------|-----------|------------|
| 1          | Initial version        | 7-Sep- 13 | nzt9hv     |
|            |                        |           |            |
|            |                        |           |            |
|            |                        |           |            |

{% endraw %}