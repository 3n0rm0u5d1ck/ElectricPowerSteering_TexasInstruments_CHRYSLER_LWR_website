---
layout: default
title: Metrics_Integration_Manual
nav_order: 2
parent: Metrics
---
{% raw %}
# Contents [contents]

[1 Dependencies [1](#dependencies)](#dependencies)

[2 Configuration [1](#configuration)](#configuration)

[2.1 Build Time Config [1](#build-time-config)](#build-time-config)

[2.2 Generator Config [2](#generator-config)](#generator-config)

[3 Memory Mapping
[2](#integration-project-changes)](#integration-project-changes)

[3.1 Mapping [2](#mapping)](#mapping)

[3.2 Usage [2](#usage)](#usage)

# Dependencies

<table>
<caption><p>: ARM Cortex R4 Memory Usage<br />
Revision Control Log</p></caption>
<colgroup>
<col style="width: 36%" />
<col style="width: 63%" />
</colgroup>
<thead>
<tr class="header">
<th>Module</th>
<th>Required Feature</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Rte</td>
<td><p>Rte_Task_Dispatch() hooks</p>
<p>VFB Trace hooks</p></td>
</tr>
<tr class="even">
<td>Dio</td>
<td>Dio_WriteChannel()</td>
</tr>
<tr class="odd">
<td>Port</td>
<td>Port_SetPinDirection()</td>
</tr>
<tr class="even">
<td>NxtrLib</td>
<td><p>DtrmnElapsedTime_uS_u32()</p>
<p>GetSystemTime_uS_u32()</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Os</td>
<td><p>osdNumberOfAllTasks constant value</p>
<p>osGetStackUsage</p>
<p>oskTcbStackTop</p>
<p>oskTcbStackBottom</p></td>
</tr>
</tbody>
</table>

: ARM Cortex R4 Memory Usage  
Revision Control Log

# Configuration

## Build Time Config

| Constant                  | Notes                                                                                                                                         | SWC     |
|-----------------------------|------------------------------------|--------|
| BC_METRICS_TASKCPUUSEMASK | STD_ON enables build of the task use masking functionality to excluded a user defined set of task CPU use times from the CPU use calculation. |         |
| BC_METRICS_STACKUSE       | STD_ON enables build of the Stack Use monitoring                                                                                              | Metrics |
| BC_METRICS_CPUUSEDIO      | STD_ON enables build of the CPU Use digital output based monitoring                                                                           | Metrics |
| BC_METRICS_CPUUSETMR      | STD_ON enables build of the CPU Use timer based monitoring                                                                                    | Metrics |
|                           |                                                                                                                                               |         |
| ENABLE_CPUUSE_DIO         | If defined then CPU usage is output via a DIO where the DIO is high while the CPU is not in the background task.                              | Metrics |
| RTE_VFB_TRACE=1           | Enable Rte’s VFB trace functionality to support Rte_Task_Dispatch() hooks                                                                     | Rte     |
| Rte_Task_Dispatch         | Enable Rte’s Rte_Task_Dispatch() hooks                                                                                                        | Rte     |

## Generator Config

<table>
<colgroup>
<col style="width: 36%" />
<col style="width: 53%" />
<col style="width: 9%" />
</colgroup>
<thead>
<tr class="header">
<th>Constant</th>
<th>Notes</th>
<th>SWC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Dio Channel Name: “Metrics”</td>
<td>Required when ENABLE_CPUUSE_DIO is defined</td>
<td>Dio</td>
</tr>
<tr class="even">
<td>RTE VFB Trace Hooks</td>
<td><ol type="1">
<li><p>Enable the option “Enable VFB Tracing” under Generation
Parameters.</p></li>
<li><p>Define/Import task wait event, and wait event return hooks.
Insert task start into the wait event return hook, and task end into
wait the wait event hook.</p></li>
<li><p>Define/Import all desired runnable Start and Return hooks in the
“Trace function“ dialog.</p></li>
</ol>
<p>Caveats:</p>
<ul>
<li><p>The runnable runtime metrics methodology requires all preemption
entry and exit points are instrumented with Metrics_TaskStart/End to
provide the ability to measure and subsequently account for preemption
time in the preempted entity.</p>
<ul>
<li><p>Basic Tasks do not provide an Rte Exit hook, therefore the
Metrics_TaskEnd( Id ) must be integrated in the return hook of the last
runnable in the Task list.</p></li>
<li><p>Extended Tasks do provide start and end hooks and therefore do
not require the integrator to place the Metrics_TaskEnd( Id ) in any
runnable end hook.</p></li>
</ul></li>
<li><p><strong>Tracking all runnables is likely to impact task run times
significantly.</strong> <strong>It may make more sense to enable
runnable trace hooks only as necessary.</strong></p></li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>MPU Global Read Access</td>
<td>GetSystemTime and Dio_WriteChannel Metrics Channel accessed
registers must be readable across all application and ISR contexts.</td>
<td>Os</td>
</tr>
<tr class="even">
<td>MPU Global Read/Write Access</td>
<td><p>Metrics data structures must be R/W across all application and
ISR contexts.</p>
<p>ATTENTION! The metrics data structures are very large, so ensure that
adequate memory is allocated to the Global Shared region</p></td>
<td>OS</td>
</tr>
</tbody>
</table>

## Integration Project Changes

1.  Modify the required BSW Irq source functions to place the
    Metrics_TaskStart and Metrics_TaskEnd hooks around the ISR’s. The
    recommended practice is to make a copy of the delivered source file
    renamed to \*\_NxtrMetrics.c and conditionaly build the altered file
    in place of the delivered file for Metrics builds.

2.  Modify SchM.c to place the Metrics_TaskStart hook and
    Metrics_TaskEnd calls appropriately at around the tasks. Note that
    it might be necessary to place the hooks at a point in the task that
    will be overwritten when the SchM.c is generated. Diligence will
    need to used after generation to ensure that the hooks are not
    inadvertently removed.

3.  Modify ApplCallbacks.c to place Metrics_TaskStart and
    Metrics_TaskEnd calls appropriately around tasks. Dilligence will be
    required to ensure the hooks are not removed.

# Memory Mapping

## Mapping

| Constant                                  | Notes                            |
|--------------------------------------------|----------------------------|
| METRICS_START_SEC_VAR_CLEARED_UNSPECIFIED | Writable across all applications |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature                                       | RAM | ROM |
|-----------------------------------------------|-----|-----|
| Software task time stamping of task execution |     |     |
| Stack usage monitoring                        |     |     |

| **Item \#** | **Rev \#** | **Change Description** | **Date** | **Author Initials** |
|------|------|--------------------------------------------|---------|---------|
| 1           |            |                        |          |                     |

{% endraw %}