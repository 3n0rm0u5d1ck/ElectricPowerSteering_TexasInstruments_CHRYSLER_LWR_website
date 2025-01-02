---
layout: default
title: Ccl
nav_order: 1
parent: Chrysler TMS570 Project
---
{% raw %}
**Module -- Ccl**

[1 References [2](#references)](#references)

[2 Configuration Settings
[2](#configuration-settings)](#configuration-settings)

[2.1 Ccl\_\_core Configuration
[2](#ccl__core-configuration)](#ccl__core-configuration)

[2.2 Advanced Task Settings Configuration
[3](#advanced-task-settings-configuration)](#advanced-task-settings-configuration)

[3 Known Issues / Limitations With Configuration
[4](#known-issues-limitations-with-configuration)](#known-issues-limitations-with-configuration)

[4 Revision Control Log
[5](#revision-control-log)](#revision-control-log)

# References

1.  Communication Control LayerTechnical Reference v1.8
    ([TechnicalReference_CCL.pdf](../../../../../../../Vector/CBD1210021_D01_Tmsx70/external/Doc/TechnicalReferences/TechnicalReference_CCL.pdf))

2.  TMS570LS Series Microcontroller Technical Reference Manual (TMS570
    Tech Ref_spnu489.pdf)

# Configuration Settings

## Ccl\_\_core Configuration

<table>
<colgroup>
<col style="width: 22%" />
<col style="width: 35%" />
<col style="width: 42%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Attribute Name</strong></th>
<th><strong>Value</strong></th>
<th><strong>Rationale</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td colspan="3">Configurable Options</td>
</tr>
<tr class="even">
<td>CCL Canbedded Handling</td>
<td>Yes</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Emc Wake Up Timeout (ms)</td>
<td>500</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Ecu Mode</td>
<td>Stop mode ECU</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Enable Transceiver In Wake Up Interrupt</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">Naming Conventions</td>
</tr>
<tr class="odd">
<td>CCL Task Prefix</td>
<td>Ccl</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">Advanced Task settings</td>
</tr>
<tr class="odd">
<td>Scheduler Base Time (ms)</td>
<td>10</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>CANbedded Tasks</td>
<td>Task Container</td>
<td>”Task Container” allows separate generated scheduling functions per
timebase and offset that can be scheduled in separate tasks. Separate
task scheduling is used to properly prioritize the ComStack cyclic main
functions with the system control tasks.</td>
</tr>
<tr class="odd">
<td>CCL Task Mode</td>
<td>Function Call</td>
<td>”Function Call” provides generation of functions that provide
scheduling flexibility among separate tasks which is required in the EPS
system to properly prioritize the cyclic functions with the system
control tasks.</td>
</tr>
<tr class="even">
<td colspan="3">Debug handling</td>
</tr>
<tr class="odd">
<td>Internal Debug</td>
<td>No</td>
<td><p>Nexteer has no design in place to log the fatal failures in the
event an assertion is triggered during development. Perhaps the
assertions should be mapped to the Autosar Det. Until a design use case
is determined, this feature is being disabled,</p>
<p>The production intended setting is “None” to reduce the driver
operating overhead (i.e. runtime and program space) by eliminating
unnecessary error checking in the final tested configuration.</p></td>
</tr>
<tr class="even">
<td>Use CCL Error Hook</td>
<td>No</td>
<td>See above.</td>
</tr>
<tr class="odd">
<td colspan="3">Transceiver Settings</td>
</tr>
<tr class="even">
<td>Transceiver Config File</td>
<td>None</td>
<td>Default setting</td>
</tr>
</tbody>
</table>

## Advanced Task Settings Configuration

<table>
<colgroup>
<col style="width: 22%" />
<col style="width: 35%" />
<col style="width: 42%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Attribute Name</strong></th>
<th><strong>Value</strong></th>
<th><strong>Rationale</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td colspan="3">CANdesc Task</td>
</tr>
<tr class="even">
<td>Cycle Time (ms)</td>
<td>10</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Offset Time (ms)</td>
<td>2</td>
<td><p>”Offset” is used for the purposes of grouping cyclic functions
into a generated “Task Container” in order to group cyclic functions
together of a determined priority into a generated schedulable function.
An offset is not actually used in scheduling.</p>
<p>The diagnostic service handler is run in a low priority task in the
system, offset 0 items run at 10ms are run at a higher
priority.</p></td>
</tr>
<tr class="even">
<td>Pre Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Post Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">XCP Task</td>
</tr>
<tr class="odd">
<td>Cycle Time (ms)</td>
<td>0</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Offset Time (ms)</td>
<td>0</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Pre Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Post Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td colspan="3">DPM Task</td>
</tr>
<tr class="even">
<td>Cycle Time (ms)</td>
<td>20</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Offset Time (ms)</td>
<td>0</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Pre Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Post Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">TP Tx Task</td>
</tr>
<tr class="odd">
<td>Cycle Time (ms)</td>
<td>10</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Offset Time (ms)</td>
<td>0</td>
<td></td>
</tr>
<tr class="odd">
<td>Pre Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Post Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td colspan="3">TP Rx Task</td>
</tr>
<tr class="even">
<td>Cycle Time (ms)</td>
<td>10</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Offset Time (ms)</td>
<td>0</td>
<td></td>
</tr>
<tr class="even">
<td>Pre Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Post Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">FRFM Task</td>
</tr>
<tr class="odd">
<td>Cycle Time (ms)</td>
<td>10</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Offset Time (ms)</td>
<td>2</td>
<td><p>”Offset” is used for the purposes of grouping cyclic functions
into a generated “Task Container” in order to group cyclic functions
together of a determined priority into a generated schedulable function.
An offset is not actually used in scheduling.</p>
<p>The FRFM is run in a low priority task in the system, offset 0 items
run at 10ms are run at a higher priority.</p></td>
</tr>
<tr class="odd">
<td>Pre Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Post Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td colspan="3">DBKOM Tx Task</td>
</tr>
<tr class="even">
<td>Cycle Time (ms)</td>
<td>10</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Offset Time (ms)</td>
<td>0</td>
<td></td>
</tr>
<tr class="even">
<td>Pre Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Post Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">DBKOM Rx Task</td>
</tr>
<tr class="odd">
<td>Cycle Time (ms)</td>
<td>10</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Offset Time (ms)</td>
<td>0</td>
<td></td>
</tr>
<tr class="odd">
<td>Pre Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Post Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td colspan="3">NM OSEK Task</td>
</tr>
<tr class="even">
<td>Cycle Time (ms)</td>
<td>10</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Offset Time (ms)</td>
<td>0</td>
<td></td>
</tr>
<tr class="even">
<td>Pre Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Post Task</td>
<td>No</td>
<td>Default setting</td>
</tr>
</tbody>
</table>

# Known Issues / Limitations With Configuration

1.  The Ccl generator generates the DescTask() and does not provide a
    mechanism to generate the DescStateTask() and DescTimerTask() in
    separate function containers. A patch is made and commented in
    ccl_par.c

#  Revision Control Log

| **Item \#** | **Rev \#** | **Change Description**                                                                                                        | **Date** | **Author Initials** |
|------|------|--------------------------------------------|---------|---------|
| 1           | 1.0        | Initial Creation                                                                                                              | 30JUL13  | JJW                 |
| 2           |            | Updated for Task Container generation and rationale for offset usage to group cyclic functions of the same priority together. | 08AUG13  | JJW                 |

{% endraw %}