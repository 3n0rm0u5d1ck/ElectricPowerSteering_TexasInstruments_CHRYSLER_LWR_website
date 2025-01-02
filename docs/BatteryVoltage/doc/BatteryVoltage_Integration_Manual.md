---
layout: default
title: BatteryVoltage_Integration_Manual
nav_order: 2
parent: Battery Voltage
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

[5.3 NvM Blocks [6](#nvm-blocks)](#nvm-blocks)

[6 Revision Control Log
[7](#revision-control-log)](#revision-control-log)

# Dependencies

## SWCs

| Module | Required Feature |
|--------|------------------|
| None   |                  |

## Configuration Files to be provided by Integration Project

None

## Functions to be provided to Integration Project

None

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

None

## Include Path

None

## Configurator Changes

None

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
|------|-------------------------|---------|
| None | None                    | None    |

| Runnable            | Scheduling Requirements | Trigger    |
|---------------------|-------------------------|------------|
| BatteryVoltage_Per1 | None                    | RTE (2 ms) |
| BatteryVoltage_Per2 | None                    | RTE (4 ms) |

\*Note: ECU Voltage Determination sub-function (BatteryVoltage_Per1)
must execute prior to the Battery Overvoltage Monitoring Sub-function
(ADC ISR).

**.**

# Memory Mapping

## Mapping

| Memory Section     | Contents | Notes |
|--------------------|----------|-------|
| RTE Memory Mapping |          |       |
|                    |          |       |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature     | RAM | ROM |
|-------------|-----|-----|
| Full driver |     |     |

Table 1: ARM Cortex R4 Memory Usage

## NvM Blocks

| Block Name      |
|-----------------|
| OvervoltageData |

# Revision Control Log

| **Rev \#** | **Change Description** | **Date**  | **Author** |
|------------|------------------------|-----------|------------|
| 1          | Initial version        | 16-Apr-13 | Jared      |

{% endraw %}