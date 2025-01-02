---
layout: default
title: ePWM_Integration_Manual
nav_order: 4
parent: Enhanced Pwm (TMS570)
---
{% raw %}
[1 Dependencies [2](#dependencies)](#dependencies)

[1.1 SWCs [2](#swcs)](#swcs)

[1.2 Configuration Files to be provided by Integration Project
[2](#configuration-files-to-be-provided-by-integration-project)](#configuration-files-to-be-provided-by-integration-project)

[1.3 Functions to be provided by Integration Project
[2](#functions-to-be-provided-by-integration-project)](#functions-to-be-provided-by-integration-project)

[2 Configuration [3](#configuration)](#configuration)

[2.1 Build Time Config [3](#build-time-config)](#build-time-config)

[2.2 Generator Config [3](#generator-config)](#generator-config)

[3 Integration [4](#integration)](#integration)

[3.1 Global Data [4](#global-data)](#global-data)

[3.2 Component Conflicts
[4](#component-conflicts)](#component-conflicts)

[3.3 Include Path [4](#include-path)](#include-path)

[3.4 ADC2 Changes [4](#adc2-changes)](#adc2-changes)

[3.5 Configurator Changes
[4](#configurator-changes)](#configurator-changes)

[3.5.1 DIO [4](#dio-and-iohwab)](#dio-and-iohwab)

[3.5.2 Port [5](#port)](#port)

[4 Runnable Scheduling [6](#runnable-scheduling)](#runnable-scheduling)

[5 Memory Mapping [7](#memory-mapping)](#memory-mapping)

[5.1 Mapping [7](#mapping)](#mapping)

[5.2 Usage [7](#usage)](#usage)

[6 Revision Control Log
[8](#revision-control-log)](#revision-control-log)

# Dependencies

## SWCs

| Module   | Required Feature                               |
|----------|------------------------------------------------|
| CDD_Data | Global variables for DC Phs Comp (from PwmCdd) |

## Configuration Files to be provided by Integration Project

None

## Functions to be provided by Integration Project

None

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

This component replaces an existing NHET component. The ePWM component
contains the NHET program specific to ePWM operation. In addition, the
Ap_ePWM2 developer component replaces the Ap_Nhet2 component.

## Include Path

The “include” directory of this SWC needs to be included in the
integration project include search path.

## ADC2 Changes

The ePWM module must be configured to start ADC conversions for the ADC2
module. This is configured by setting the following register values for
the ADC2 module:

-   G0SRC = 3 (EPWM_A1)

-   G1SRC = 1 (EPWM_B)

This is done in parallel with pin multiplexing changes to route the
appropriate SOCA and SOCB signals to the ADC2 module. See FDD 33E for
more information.

## Configurator Changes

### DIO and IOHwAb

If NHET was previously used to generate PWM signals, reassignments are
required (as the ePWM outputs will conflict with assigned DIO pins).
This is hardware-dependent; refer to the program’s Resource Allocation
sheet or schematic. The following pins are used by ePWM and the
ePWM-specific NHET on the TMS570LS1227 PGE (144 pin) package (see the
datasheet for more information):

| Pin | Function                                                     |
|-----|--------------------------------------------------------------|
| 6   | N2HET1\[11\], MIBSPI3NCS\[4\], **N2HET2\[18\]**, ETPWM1SYNCO |
| 14  | GIOA\[5\], EXTCLKIN, **ETPWM1A**                             |
| 15  | GIOA\[6\], N2HET2\[4\], **ETPWM1B**                          |
| 22  | GIOA\[7\], N2HET2\[6\], **ETPWM2A**                          |
| 23  | N2HET1\[1\], SPI4ENA, **N2HET2\[8\]**                        |
| 24  | N2HET1\[3\], SPI4NCS\[0\], **N2HET2\[10\]**                  |
| 25  | N2HET1\[0\], SPI4CLK, **ETPWM2B**                            |
| 30  | N2HET1\[2\], SPI4SIMO, **ETPWM3A**                           |
| 31  | N2HET1\[5\], SPI4SOMI, N2HET2\[12\], **ETPWM3B**             |
| 33  | N2HET1\[7\], N2HET2\[14\], **ETPWM7B**                       |

### Port

#### Pin Direction Settings

The changes in DIO (hardware-dependent) may require updates to the pin
direction and other settings for the newly configured DIO signals.

#### Multiplexing Changes

Several multiplexing options must be configured for both external
routing (peripherals to pins) and internal routing (peripherals to
peripherals).

The following changes must be made within configurator:

-   Multiplexing for DIO changes (hardware-dependent)

-   Multiplexing for NHET component change

    -   This should result in PINMUX1\[8-15\] being set to 0x04

    -   While N2HET2\[8\] and \[10\] can be configured, configurator
        does not generate these values correctly (see the manual
        configuration below)

-   ADC Trigger Table – select ADC Trigger Table 2

    -   This should result in PINMUX30\[0-7\] being set to 0x02

The following changes must be made with manual edits to Port_PBcfg.c:

| Register   | Bits  | Value      | Selected Option                                |
|---------------|-----------|--------------|----------------------------------|
| PINMUX2    | 24-31 | 0x04       | ETPWM1A                                        |
| PINMUX3    | 16-23 | 0x04       | ETPWM1B                                        |
| PINMUX4    | 0-7   | 0x04       | ETPWM2A                                        |
| PINMUX4    | 16-23 | 0x10       | N2HET2\[8\] (configurator errata)              |
| PINMUX4    | 24-31 | 0x10       | N2HET2\[10\] (configurator errata)             |
| PINMUX5    | 0-7   | 0x04       | ETPWM2B                                        |
| PINMUX5    | 8-15  | 0x04       | ETPWM3A                                        |
| PINMUX5    | 16-23 | 0x08       | ETPWM3B                                        |
| PINMUX6    | 0-7   | 0x10       | ETPWM7B                                        |
| PINMUX31\* | 16-31 | 0x0202     | ADC2 Trigger Event Selection                   |
| PINMUX35\* | 24-31 | 0x00       | SOC4A_SEL cleared                              |
| PINMUX37\* | 0-31  | 0x01010102 | Sync time bases, enable clocks for ePWM 0 to 3 |
| PINMUX38\* | 0-31  | 0x01000001 | Enable clocks for ePWM 4 and 7                 |

> \* Configurator does not define symbols for these registers. Define
> the following symbols manually:
>
> \#define PORT_BASE_ADDR_PINMUX_31 ((Port_RegisterPtrType)(0xFFFFEB8C))
>
> \#define PORT_BASE_ADDR_PINMUX_35 ((Port_RegisterPtrType)(0xFFFFEB9C))
>
> \#define PORT_BASE_ADDR_PINMUX_37 ((Port_RegisterPtrType)(0xFFFFEBA4))
>
> \#define PORT_BASE_ADDR_PINMUX_38 ((Port_RegisterPtrType)(0xFFFFEBA8))
>
> A default value of 0x01 should be used for bytes not otherwise
> defined.

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Runnable    | Scheduling Requirements                                                                                                        | Trigger      |
|-----------------|----------------------------------------|----------------|
| Nhet_Init1  | Place in EcuStartup_Init1 (EcuStartup.c) along with ePWM_Init1, following the memory initialization routine SchM_InitMemory.   | Init         |
| ePWM_Init1  | Place in EcuStartup_Init1 (EcuStartup.c) along with Nhet_Init1, following the memory initialization routine SchM_InitMemory.   | Init         |
| ePWM_Per1   | Must be placed in the motor control ISR, following PwmCdd (or whichever function populates the global variables used by ePWM). | Cyclic (ISR) |
| ePWM2_Trns1 | Schedule on transition into the WARMINIT state                                                                                 | Event (RTE)  |
| ePWM2_Trns2 | Schedule on transition into the DISABLE state                                                                                  | Event (RTE)  |

# Memory Mapping

## Mapping

| Memory Section      | Contents      | Notes |
|---------------------|---------------|-------|
| EPWM_START_SEC_CODE | Runnable Code |       |
| NHET_START_SEC_CODE | Runnable Code |       |

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
| 1          | Initial version        | 15-Feb-13 | OT         |

{% endraw %}