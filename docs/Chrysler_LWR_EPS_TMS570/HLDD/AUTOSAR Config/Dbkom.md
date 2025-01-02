---
layout: default
title: Dbkom
nav_order: 3
parent: Chrysler TMS570 Project
---
{% raw %}
**Module -- Dbkom**

[1 References [2](#references)](#references)

[2 Configuration Settings
[2](#configuration-settings)](#configuration-settings)

[2.1 Il_Dbkom Configuration
[2](#il_dbkom-configuration)](#il_dbkom-configuration)

[2.2 Tx Messages [2](#tx-messages)](#tx-messages)

[3 Known Issues / Limitations With Configuration
[3](#known-issues-limitations-with-configuration)](#known-issues-limitations-with-configuration)

[4 Revision Control Log
[4](#revision-control-log)](#revision-control-log)

# References

1.  DBKOM Technical Reference v2.08.00
    ([TechnicalReference_DBKOM_2_xx.pdf](../../../../../../../Vector/CBD1210021_D01_Tmsx70/external/Doc/TechnicalReferences/TechnicalReference_DBKOM_2_xx.pdf))

2.  TMS570LS Series Microcontroller Technical Reference Manual (TMS570
    Tech Ref_spnu489.pdf)

# Configuration Settings

## Il_Dbkom Configuration

| **Attribute Name**           | **Value** | **Rationale**                                                                                                                                       |
|-----------------|--------------------------|------------------------------|
| Configurable Options         |           |                                                                                                                                                     |
| User Config File             | None      | Default setting                                                                                                                                     |
| Write access to rx buffer    |           |                                                                                                                                                     |
| Byte                         | No        | Default setting                                                                                                                                     |
| Word                         | No        | Default setting                                                                                                                                     |
| nByte                        | No        | Default setting                                                                                                                                     |
| Timing parameters            |           |                                                                                                                                                     |
| Start Delay Time Area \[ms\] | 200       | Default setting                                                                                                                                     |
| Channel0                     |           |                                                                                                                                                     |
| TxCycle                      | 2         | 2ms is a common factor of the transmission rates 10ms and 100ms and also ensures that the message trigger jitter is less than the required +/- 5ms. |
| RxCycle                      | 10        | Default setting                                                                                                                                     |
| Transceiver Settings         |           |                                                                                                                                                     |
| Transceiver Config File      | None      | Default setting                                                                                                                                     |

## Tx Messages

### D_RS_EPS

| **Attribute Name**      | **Value** | **Rationale**                                                                                                                                                                                           |
|-----------------|--------------------------|------------------------------|
| D_RS_EPS                |           |                                                                                                                                                                                                         |
| Generate                | Yes       | Default setting                                                                                                                                                                                         |
| Start delay time \[ms\] | n/a       |                                                                                                                                                                                                         |
| ECU_APPL_EPS            |           |                                                                                                                                                                                                         |
| Generate                | Yes       | Default setting                                                                                                                                                                                         |
| Start delay time \[ms\] | n/a       |                                                                                                                                                                                                         |
| EPS_1                   |           |                                                                                                                                                                                                         |
| Generate                | Yes       | Required tx message                                                                                                                                                                                     |
| Start delay time \[ms\] | 0         | Arbitrarily set to 0, however, the time between this 10ms cyclic message and the EPS_A1 100ms cyclic message must be greater than 2 ms.                                                                 |
| EPS_A1                  |           |                                                                                                                                                                                                         |
| Generate                | Yes       | Required tx message                                                                                                                                                                                     |
| Start delay time \[ms\] | 4         | 5ms offset is the optimal spacing for offsetting this message from EPS_1. The current system tick is 2ms, so 4ms was selected. 4ms provides a guaranteed 2ms message spacing even under extreme jitter. |
| NM_EPS                  |           |                                                                                                                                                                                                         |
| Generate                | Yes       | Default setting                                                                                                                                                                                         |
| Start delay time \[ms\] | n/a       |                                                                                                                                                                                                         |
| SD_RS_EPS               |           |                                                                                                                                                                                                         |
| Generate                | Yes       | Default setting                                                                                                                                                                                         |
| Start delay time \[ms\] | 0         | Default setting                                                                                                                                                                                         |

# Known Issues / Limitations With Configuration

1.  The configuration is only partially documented due to lack of time.

#  Revision Control Log

| **Item \#** | **Rev \#** | **Change Description** | **Date** | **Author Initials** |
|------|------|--------------------------------------------|---------|---------|
| 1           | 1.0        | Initial Creation       | 30JUL13  | JJW                 |
|             |            |                        |          |                     |

{% endraw %}