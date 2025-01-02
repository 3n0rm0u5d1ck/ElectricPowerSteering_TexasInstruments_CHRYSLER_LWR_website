---
layout: default
title: DrvCan
nav_order: 4
parent: Chrysler TMS570 Project
---
{% raw %}
**Module -- DrvCan**

[1 References [2](#references)](#references)

[2 Configuration Settings
[2](#configuration-settings)](#configuration-settings)

[2.1 DrvCan Configuration
[2](#drvcan-configuration)](#drvcan-configuration)

[2.2 Hw Configuration [5](#hw-configuration)](#hw-configuration)

[3 Known Issues / Limitations With Configuration
[6](#known-issues-limitations-with-configuration)](#known-issues-limitations-with-configuration)

[4 Revision Control Log
[7](#revision-control-log)](#revision-control-log)

# References

1.  Vector CAN Driver Technical Reference V3.01.01
    ([TechnicalReference_CanDriver.pdf](C://Vector/CBD1210021_D00_Tmsx70/Doc/TechnicalReferences/TechnicalReference_CanDriver.pdf))

2.  Vector CAN Driver Technical Reference TI TMS470 DCAN v 1.03.02
    ([TechnicalReference_CAN_TMS470DCAN.pdf](C://Vector/CBD1210021_D00_Tmsx70/Doc/TechnicalReferences/TechnicalReference_CAN_TMS470DCAN.pdf))

3.  TMS570LS Series Microcontroller Technical Reference Manual (TMS570
    Tech Ref_spnu489.pdf)

# Configuration Settings

## DrvCan Configuration

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
<td colspan="3">Hw_Tms470DcanCpuCan</td>
</tr>
<tr class="even">
<td>Errata Dcan22 iterations</td>
<td>255</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td colspan="3">Common Driver Parameters</td>
</tr>
<tr class="even">
<td>CANOnline / CANOffline Notification</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>DLC Check</td>
<td>Against minimum acceptance length</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Copy Mechanism</td>
<td>Copy all received bytes</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Sleep / Wake-up Functionality</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>FullCAN Overrun Notification</td>
<td>Yes</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Use Tx BitQueue</td>
<td>Yes</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Can Interrupt Control Callbacks</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Common Confirmation Function</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Rx Notification</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Active / Passive State</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Extended Status</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Transmit Queue</td>
<td>Yes</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Tx Observation</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Message Not Matched Notification</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Overrun Notification</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Hardware Loop Check</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Partial Offline Mode</td>
<td>Yes</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Generic Precopy</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>CopyToCAN / CopyFromCAN Service</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>CAN Cancel Notification</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">Offline Modes</td>
</tr>
<tr class="odd">
<td>To be completed</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td colspan="3">OSEK OS</td>
</tr>
<tr class="odd">
<td>OSEK OS Cat. 2 Interrupt</td>
<td>No</td>
<td><p>This setting should be “Yes” because the driver is QM software,
which means in the EPS system that it must be run in a user mode
application. In order for the Os to appropriately configure the MPU and
switch to user mode a category 2 interrupt is required.</p>
<p>This setting is “grayed out” and set to “No”. The current software
implementation configures a Cat2 interrupt function which then simply
calls the interrupt function as a workaround.</p></td>
</tr>
<tr class="even">
<td colspan="3">Polling</td>
</tr>
<tr class="odd">
<td>Polling Type</td>
<td>Type Specific</td>
<td><p>Desired configuration is to provide interrupt processing only on
Tx messages. The “Type Specific” setting provides a polling
configuration granularity that allows this configuration.</p>
<p>“Individual” would also work, but has a finer configuration
granularity that is more complex and is not necessary for this use
case.</p></td>
</tr>
<tr class="even">
<td>Rx BasicCAN Polling</td>
<td>Yes</td>
<td>In order to prevent excessive interrupt overhead, all Rx messages
are to be processed on a polled basis.</td>
</tr>
<tr class="odd">
<td>Rx FullCAN Polling</td>
<td>Yes</td>
<td>In order to prevent excessive interrupt overhead, all Rx messages
are to be processed on a polled basis.</td>
</tr>
<tr class="even">
<td>Tx Polling</td>
<td>No</td>
<td>In order to provide maximum Tx bandwidth for XCP DAQ lists, Tx
processing is performed on an interrupt basis.</td>
</tr>
<tr class="odd">
<td>Error Polling</td>
<td>Yes</td>
<td>Poll the CAN controller for error indications in order to set an
appropriate DTC and perform error recovery processing. Polling does no
violate any known error reaction/error recovery response time
requirement. Elimination of unnecessary ISR sources eliminates
application issues arising from excessive IRQ’s pre-empting critical
control processing tasks.</td>
</tr>
<tr class="even">
<td colspan="3">Low Level Messages Transmission</td>
</tr>
<tr class="odd">
<td>Low Level Transmit Cancel Notification</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Low Level Transmission</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Low Level Transmission Confirmation Function</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">API</td>
</tr>
<tr class="odd">
<td>Symbolic Names for Signal Values</td>
<td>Yes</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Indexed Component</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td colspan="3">General Settings</td>
</tr>
<tr class="even">
<td>Security Level</td>
<td>30</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>User Config File</td>
<td>user.cfg</td>
<td>Name of the file containing Nexteer user configuration settings for
GENy generation.</td>
</tr>
<tr class="even">
<td colspan="3">Debug Support</td>
</tr>
<tr class="odd">
<td>Assertions</td>
<td>None</td>
<td><p>Nexteer has no design in place to log the fatal failures in the
event an assertion is triggered during development. Perhaps the
assertions should be mapped to the Autosar Det. Until a design use case
is determined, this feature is being disabled.</p>
<p>The production intended setting is “None” to reduce the driver
operating overhead (i.e. runtime and program space) by eliminating
unnecessary error checking in the final tested configuration.</p></td>
</tr>
<tr class="even">
<td colspan="3">Dynamic Tx Objects</td>
</tr>
<tr class="odd">
<td>ID</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>DLC</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Data Pointer</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Confirmation</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Pretransmit</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">ID Search Algorithm</td>
</tr>
<tr class="odd">
<td>Search Algorithm</td>
<td>Linear</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Addtiional Memory [byte]</td>
<td>0</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Maximum Search Steps</td>
<td>2</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">Rx Queue</td>
</tr>
<tr class="odd">
<td>Overrun Notification</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Rx Queue</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Pre Rx Queue Notification</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Size</td>
<td>3</td>
<td>Default setting</td>
</tr>
</tbody>
</table>

## Hw Configuration

<table>
<colgroup>
<col style="width: 24%" />
<col style="width: 24%" />
<col style="width: 51%" />
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
<td>Compiler</td>
<td>TexasInstruments</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Derivative</td>
<td>TMS570PSFC66</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">General Settings</td>
</tr>
<tr class="odd">
<td>User Config File</td>
<td>None</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">CPU Settings</td>
</tr>
<tr class="odd">
<td>CPU Type</td>
<td>32 Bit</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Byte Order</td>
<td>Big Endian</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Bit Order</td>
<td>MSB to LSB</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Definition of ‘Define C_COMP_xxx’</td>
<td>TI_TMS470_DCAN</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Definition of ‘Define C_PROCESSOR_xxx’</td>
<td>TI_TMS470_PFSC66</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">Generation Additions</td>
</tr>
<tr class="odd">
<td>Dummy Functions</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Dummy Statement</td>
<td>Yes</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td colspan="3">OS</td>
</tr>
<tr class="even">
<td>OS Type</td>
<td>Autosar</td>
<td>An Autosar Os is used in this project.</td>
</tr>
<tr class="odd">
<td colspan="3">Optimization</td>
</tr>
<tr class="even">
<td>Atomic Bit Access in Bitfield</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Atomic Variable Access</td>
<td>Atomic32BitAccess</td>
<td>The TMS570 microcontroller performs 32 bit atomic data
accesses.</td>
</tr>
<tr class="even">
<td colspan="3">Multiple GENy Projects</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>Default setting</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td colspan="3">Generation Options</td>
</tr>
<tr class="even">
<td>Disable generation of #error directives</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Conditional Generation</td>
<td>No</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">VStdLib</td>
</tr>
<tr class="odd">
<td colspan="3"><ul>
<li><p>Synch Mechanism</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Lock Mechanism</td>
<td>OSEK</td>
<td><p>“Default” handling is NOT selected because the VStdLib default
interrupt handling requires a privileged CPU mode of execution. The
Nexteer use case is placing the Can drivers in a user mode application
because they are QM rated drivers. Therefore the “Default” interrupt
handling will not function properly and cannot be used.</p>
<p>“OSEK” Handling selected for compatibility with the Nexteer use
case.</p></td>
</tr>
<tr class="odd">
<td>Lock Level</td>
<td>Global</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td>Nested Disable</td>
<td>None</td>
<td>Default setting</td>
</tr>
<tr class="odd">
<td>Nested Restore</td>
<td>None</td>
<td>Default setting</td>
</tr>
<tr class="even">
<td colspan="3">Debug Support</td>
</tr>
<tr class="odd">
<td>Assertions</td>
<td>no</td>
<td>Default setting</td>
</tr>
</tbody>
</table>

# Known Issues / Limitations With Configuration

1.  None .

#  Revision Control Log

| **Item \#** | **Rev \#** | **Change Description** | **Date** | **Author Initials** |
|------|------|--------------------------------------------|---------|---------|
| 1           | 1.0        | Initial Creation       | 30JUL13  | JJW                 |
|             |            |                        |          |                     |

{% endraw %}