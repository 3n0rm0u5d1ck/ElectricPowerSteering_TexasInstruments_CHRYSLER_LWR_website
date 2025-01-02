---
layout: default
title: Os
nav_order: 6
parent: Chrysler TMS570 Project
---
{% raw %}
**Module -- Os**

[1 References 2](#references)

[2 ISR Configuration 3](#isr-configuration)

[2.1 Gpt_IsrInt0 3](#gpt_isrint0)

[2.2 Isr_ESMH 4](#isr_esmh)

[2.3 Isr_MtrCtrl 5](#isr_mtrctrl)

[2.4 Spi_IrqUnit0TxRx 6](#spi_irqunit0txrx)

[2.5 Spi_IrqUnit0TxRxERR 7](#spi_irqunit0txrxerr)

[3 Task Configuration 7](#task-configuration)

[4 Os Configuration 7](#os-configuration)

[4.1 OsOSAPIOptimization 7](#ososapioptimization)

[5 Applications Configuration 7](#applications-configuration)

[6 Assist Primary Control Task Scheduling
7](#assist-primary-control-task-scheduling)

[7 Known Issues / Limitations With Configuration
8](#known-issues-limitations-with-configuration)

[8 Code Alterations 8](#code-alterations)

[8.1 Generated Code 8](#generated-code)

[8.2 Static Code 8](#static-code)

[9 Revision Control Log 10](#revision-control-log)

11

# References

1.  MICROSAR OS OSEK/Autosar Realtime Operating System Technical
    Reference
    ([TechnicalReference_osCAN4.pdf](../../../../../../Vector/CBD1000133_D00_Tmsx70/Doc/TechnicalReferences/TechnicalReference_osCAN4.pdf))

2.  AUTOSAR realtime operating system MICROSAR OS TMS570 User’s Manual
    ([MicrosarOS_TMS570.pdf](../../../../../../Vector/CBD1000133_D01_Tmsx70/Doc/UserManuals/MicrosarOS_TMS570.pdf))

3.  TMS570LS3137PGE 16/32-Bit RISC Flash Microcontroller
    (SPNS166_TMS570LS3137SPGE Prelim.pdf)

4.  Cortex-R4 and Cortex-R4F Technical Reference Manual
    (DDIO363E_cortexr4_r1p3_trm.pdf)

# ISR Configuration

## Gpt_IsrInt0

|                             |            |                                                                                                                                                                                                                   |
|----------------------|--------------------|-------------------------------|
| **Attribute Name**          | **Value**  | **Rationale**                                                                                                                                                                                                     |
| General Settings            |            |                                                                                                                                                                                                                   |
| OsIsrCategory               | Category_2 | Category 2 configured to allow preemption concerns to be handled by the Os,                                                                                                                                       |
| OsIsrEnableNesting          | TRUE       | Allow the Motor control ISR to preempt.                                                                                                                                                                           |
| OsIsrAnalysisPriority       | 0          | Default value same as other Demo project ISR’s, this value is used for correctly configuring the osCAN external timing analysis tool. At some point in the future, a correct value should be determined for this. |
| OsIsrComputationTime        | 0          | See above rationale                                                                                                                                                                                               |
| OsIsrPeriod                 | 0          | See above rationale                                                                                                                                                                                               |
| OsIsrDeadline               | 0          | See above rationale                                                                                                                                                                                               |
| OsIsrInterruptTarget        | IRQ        | Cat2 requires IRQ. FIQ not required to meet the ISR execution deadline.                                                                                                                                           |
| OsIsrInterruptSource        | INTR2      | “RTI compare interrupt 0” is default VIM interrupt request 2 per \[3\]                                                                                                                                            |
| OsIsrResourceRef            | \<Empty\>  | **TBD**                                                                                                                                                                                                           |
| OsIsrMESSAGE                | \<Empty\>  | **TBD**                                                                                                                                                                                                           |
| OsIsrInterruptPriority      | 4          | In order to ensure that this Isr does not interfere with the Motor control its priority is being placed below the MtrCtrl interrupt.                                                                              |
| OsIsrUseSpecialFunctionName | FALSE      |                                                                                                                                                                                                                   |

## Isr_ESMH

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 26%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Attribute Name</strong></td>
<td><strong>Value</strong></td>
<td><strong>Rationale</strong></td>
</tr>
<tr class="even">
<td colspan="3">General Settings</td>
</tr>
<tr class="odd">
<td>OsIsrCategory</td>
<td>Category_1</td>
<td>Fast ISR service desired, OS services not required</td>
</tr>
<tr class="even">
<td>OsIsrEnableNesting</td>
<td>FALSE</td>
<td><p>Prevent Interrupt preemption while serving ESM interrupt.</p>
<p>Although it seems that this parameter does not apply to a Category 1
interrupt since the OS is not involved with the assertion of the ISR. So
the value of this parameter should have no effect.</p></td>
</tr>
<tr class="odd">
<td>OsIsrAnalysisPriority</td>
<td>0</td>
<td>Default value same as other Demo project ISR’s, this value is used
for correctly configuring the osCAN external timing analysis tool. At
some point in the future, a correct value should be determined for
this.</td>
</tr>
<tr class="even">
<td>OsIsrComputationTime</td>
<td>0</td>
<td>See above rationale</td>
</tr>
<tr class="odd">
<td>OsIsrPeriod</td>
<td>0</td>
<td>See above rationale</td>
</tr>
<tr class="even">
<td>OsIsrDeadline</td>
<td>0</td>
<td>See above rationale</td>
</tr>
<tr class="odd">
<td>OsIsrInterruptTarget</td>
<td>FIQ</td>
<td>ESMH interrupt is by nature a Non Maskable Interrupt and is service
through FIQ.</td>
</tr>
<tr class="even">
<td>OsIsrInterruptSource</td>
<td>INTR0</td>
<td>Trigger is the ESM High Level Interrupt</td>
</tr>
<tr class="odd">
<td>OsIsrResourceRef</td>
<td>&lt;Empty&gt;</td>
<td><strong>TBD</strong></td>
</tr>
<tr class="even">
<td>OsIsrMESSAGE</td>
<td>&lt;Empty&gt;</td>
<td><strong>TBD</strong></td>
</tr>
<tr class="odd">
<td>OsIsrInterruptPriority</td>
<td>0</td>
<td>VIM priority “0” is reserved for ESM module. Default value is
desired.</td>
</tr>
<tr class="even">
<td>OsIsrUseSpecialFunctionName</td>
<td>FALSE</td>
<td>Single interrupt source for the ESM ISR, so using the name of this
ISR container is fine.</td>
</tr>
</tbody>
</table>

## Isr_MtrCtrl

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 26%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Attribute Name</strong></td>
<td><strong>Value</strong></td>
<td><strong>Rationale</strong></td>
</tr>
<tr class="even">
<td colspan="3">General Settings</td>
</tr>
<tr class="odd">
<td>OsIsrCategory</td>
<td>Category_1</td>
<td>Fast ISR service desired, OS services not required</td>
</tr>
<tr class="even">
<td>OsIsrEnableNesting</td>
<td>FALSE</td>
<td><p>Prevent Interrupt preemption while serving motor control.</p>
<p>Although it seems that this parameter does not apply to a Category 1
interrupt since the OS is not involved with the assertion of the ISR. So
the value of this parameter should have no effect.</p></td>
</tr>
<tr class="odd">
<td>OsIsrAnalysisPriority</td>
<td>0</td>
<td>Default value same as other Demo project ISR’s, this value is used
for correctly configuring the osCAN external timing analysis tool. At
some point in the future, a correct value should be determined for
this.</td>
</tr>
<tr class="even">
<td>OsIsrComputationTime</td>
<td>0</td>
<td>See above rationale</td>
</tr>
<tr class="odd">
<td>OsIsrPeriod</td>
<td>0</td>
<td>See above rationale</td>
</tr>
<tr class="even">
<td>OsIsrDeadline</td>
<td>0</td>
<td>See above rationale</td>
</tr>
<tr class="odd">
<td>OsIsrInterruptTarget</td>
<td>IRQ</td>
<td><p>FIQ desired since this ISR is high priority and is not to be
preempted by any other source.</p>
<p>Due to unexplained missed FlexRay interrupts when an FIQ is
configured, this is being configured as an IRQ as a workaround.</p></td>
</tr>
<tr class="even">
<td>OsIsrInterruptSource</td>
<td>INTR50</td>
<td>Trigger for motor control ISR is the completion of the ADC2 group 1
conversion triggered by the NHET.</td>
</tr>
<tr class="odd">
<td>OsIsrResourceRef</td>
<td>&lt;Empty&gt;</td>
<td><strong>TBD</strong></td>
</tr>
<tr class="even">
<td>OsIsrMESSAGE</td>
<td>&lt;Empty&gt;</td>
<td><strong>TBD</strong></td>
</tr>
<tr class="odd">
<td>OsIsrInterruptPriority</td>
<td>2</td>
<td>This is the highest priority interrupt in the system. VIM priority
scheme reserves priorities 0 and 1. 2 is the highest priority assignment
available.</td>
</tr>
<tr class="even">
<td>OsIsrUseSpecialFunctionName</td>
<td>FALSE</td>
<td>Single interrupt source for the motor control ISR, so using the name
of this ISR container is fine.</td>
</tr>
</tbody>
</table>

## Spi_IrqUnit0TxRx

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 26%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Attribute Name</strong></td>
<td><strong>Value</strong></td>
<td><strong>Rationale</strong></td>
</tr>
<tr class="even">
<td colspan="3">General Settings</td>
</tr>
<tr class="odd">
<td>OsIsrCategory</td>
<td>Category_2</td>
<td>Category 2 configured to allow preemption concerns to be handled by
the Os,</td>
</tr>
<tr class="even">
<td>OsIsrEnableNesting</td>
<td>TRUE</td>
<td><p>The SPI communication is only used for EEPROM servicing and is
low priority. Allow the CAN interrupt, System Tick, and Motor Control to
preempt.</p>
<p><strong>TBD</strong> if Category_1 interrupts can always preempt
Category_2..</p></td>
</tr>
<tr class="odd">
<td>OsIsrAnalysisPriority</td>
<td>0</td>
<td>Default value same as other Demo project ISR’s, this value is used
for correctly configuring the osCAN external timing analysis tool. At
some point in the future, a correct value should be determined for
this.</td>
</tr>
<tr class="even">
<td>OsIsrComputationTime</td>
<td>0</td>
<td>See above rationale</td>
</tr>
<tr class="odd">
<td>OsIsrPeriod</td>
<td>0</td>
<td>See above rationale</td>
</tr>
<tr class="even">
<td>OsIsrDeadline</td>
<td>0</td>
<td>See above rationale</td>
</tr>
<tr class="odd">
<td>OsIsrInterruptTarget</td>
<td>IRQ</td>
<td>Cat2 requires IRQ. FIQ not required to meet the ISR execution
deadline.</td>
</tr>
<tr class="even">
<td>OsIsrInterruptSource</td>
<td>INTR26</td>
<td>Trigger for EEPROM SPI MIBSPI1 per CCA schematic.</td>
</tr>
<tr class="odd">
<td>OsIsrResourceRef</td>
<td>&lt;Empty&gt;</td>
<td><strong>TBD</strong></td>
</tr>
<tr class="even">
<td>OsIsrMESSAGE</td>
<td>&lt;Empty&gt;</td>
<td><strong>TBD</strong></td>
</tr>
<tr class="odd">
<td>OsIsrInterruptPriority</td>
<td>26</td>
<td><strong>TBD</strong></td>
</tr>
<tr class="even">
<td>OsIsrUseSpecialFunctionName</td>
<td>FALSE</td>
<td><strong>TBD</strong></td>
</tr>
</tbody>
</table>

## Spi_IrqUnit0TxRxERR

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 26%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Attribute Name</strong></td>
<td><strong>Value</strong></td>
<td><strong>Rationale</strong></td>
</tr>
<tr class="even">
<td colspan="3">General Settings</td>
</tr>
<tr class="odd">
<td>OsIsrCategory</td>
<td>Category_2</td>
<td>Category 2 configured to allow preemption concerns to be handled by
the Os,</td>
</tr>
<tr class="even">
<td>OsIsrEnableNesting</td>
<td>TRUE</td>
<td><p>The SPI communication is only used for EEPROM servicing and is
low priority. Allow the CAN interrupt, System Tick, and Motor Control to
preempt.</p>
<p><strong>TBD</strong> if Category_1 interrupts can always preempt
Category_2..</p></td>
</tr>
<tr class="odd">
<td>OsIsrAnalysisPriority</td>
<td>0</td>
<td>Default value same as other Demo project ISR’s, this value is used
for correctly configuring the osCAN external timing analysis tool. At
some point in the future, a correct value should be determined for
this.</td>
</tr>
<tr class="even">
<td>OsIsrComputationTime</td>
<td>0</td>
<td>See above rationale</td>
</tr>
<tr class="odd">
<td>OsIsrPeriod</td>
<td>0</td>
<td>See above rationale</td>
</tr>
<tr class="even">
<td>OsIsrDeadline</td>
<td>0</td>
<td>See above rationale</td>
</tr>
<tr class="odd">
<td>OsIsrInterruptTarget</td>
<td>IRQ</td>
<td>Cat2 requires IRQ. FIQ not required to meet the ISR execution
deadline.</td>
</tr>
<tr class="even">
<td>OsIsrInterruptSource</td>
<td>INTR12</td>
<td>Trigger for EEPROM SPI MIBSPI1 per CCA schematic.</td>
</tr>
<tr class="odd">
<td>OsIsrResourceRef</td>
<td>&lt;Empty&gt;</td>
<td><strong>TBD</strong></td>
</tr>
<tr class="even">
<td>OsIsrMESSAGE</td>
<td>&lt;Empty&gt;</td>
<td><strong>TBD</strong></td>
</tr>
<tr class="odd">
<td>OsIsrInterruptPriority</td>
<td>12</td>
<td><strong>TBD</strong></td>
</tr>
<tr class="even">
<td>OsIsrUseSpecialFunctionName</td>
<td>FALSE</td>
<td><strong>TBD</strong></td>
</tr>
</tbody>
</table>

# Task Configuration

# Os Configuration

## OsOSAPIOptimization

# Applications Configuration

# Assist Primary Control Task Scheduling

The assist primary control task scheduling requires both low execution
period jitter and low latency relative to the ADC measurements on the
signals required for the control computations.

> TO BE COMPLETED

# Known Issues / Limitations With Configuration

1.  Configuration has not been fully reviewed and is based on the Vector
    Demo project delivered with the SIP.

# Code Alterations

## Generated Code

> The generated configuration requires modifications to be suitable for
> the Nexteer project. The following table lists the changes required
> and the rationale.
>
> Included in the GenDataOs folder are a set of scripts and unified diff
> files to assist in automatically performing the modifications to the
> generated files. At this time, execution of the Os_Patch.bat script
> has not been added to the Vector Configurator Os generation step. The
> user generating the new Os configuration is responsible for launching
> the Os_Patch.bat script after Os generation and ensuring that the
> modifications are performed correctly. A future improvement is to
> further automate the process of applying the modifications.

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 57%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>File(line)</strong></td>
<td><strong>Change description</strong></td>
<td><strong>Os_Patch.bat Automation</strong></td>
</tr>
<tr class="even">
<td>intvect.asm</td>
<td><p>Removal of the generated assembler error directive. The error
directive is unconditionally inserted by the Vector generator to ensure
the output from the generator is reviewed prior to being built into a
system. During Os configuration development at Nexteer it is necessary
for the developer to build and test the generated configurations many
times while implementing a change request.</p>
<p>Nexteer’s process of reviewing the Os generated configuration does
not rely on a generated error directive and thus it is removed.</p></td>
<td>GNU patch utility invoked with invect.diff input.</td>
</tr>
<tr class="odd">
<td>Os_MemMap.h</td>
<td>Inclusion of #undef MEMMAP_ERROR in each memory mapping block to
meet the AUTOSAR MemMap requirements</td>
<td>GNU sed utility invoked with find and replace</td>
</tr>
</tbody>
</table>

\* Os_Diff.bat can be invoked to update the \*.diff files. It generates
the \*.diff based on the differences it detects between the primary file
in the directory and the \*.bak version of the file in the directory.

## Static Code

This section describes alterations to the delivered static code files
provided by the software supplier. The pertinent source file should be
inspected to see the exact change. Line numbers are relative to the
altered file line numbering and not the originally delivered file.

<table>
<colgroup>
<col style="width: 22%" />
<col style="width: 77%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>File(line)</strong></td>
<td><strong>Change description</strong></td>
</tr>
<tr class="even">
<td>osekasm.asm(1374)</td>
<td><p>Per Error: Reference source not found Sec. 4.1.3.3 an application
Prefetch Abort handler is required.</p>
<p>Affected Function: osPrefetchAbort</p>
<p>The branch instruction is changed to branch to the Nexteer handler in
place of the “osUnhandledException” handler. External declaration of
function added at line 134.</p></td>
</tr>
<tr class="odd">
<td>osekasm.asm(1402)</td>
<td><p>Per Error: Reference source not found Sec. 4.1.3.3 an application
Data Abort handler is required.</p>
<p>Affected Function: osDataAbort</p>
<p>The branch instruction is changed to branch to the Nexteer handler in
place of the “osUnhandledException” handler. External declaration of
function added at line 135.</p></td>
</tr>
</tbody>
</table>

#  Revision Control Log

|             |            |                        |          |                     |
|------|------|--------------------------------------------|---------|---------|
| **Item \#** | **Rev \#** | **Change Description** | **Date** | **Author Initials** |
| 1           | 1.0        | Initial Creation       | 01MAR13  | JJW                 |

{% endraw %}