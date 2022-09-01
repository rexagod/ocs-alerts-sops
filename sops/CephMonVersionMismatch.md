
CephMonVersionMismatch
======================

Check Description
-----------------

**Severity:** Warning

**Potential Customer Impact:** Medium

Overview
--------

There are different versions of Ceph Mon components running.

Detailed Description: Typically this alert triggers during an upgrade that is taking a long time.

Prerequsities
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----

### Make changes to solve alert

Check if an operator upgrade is in progress.

[Check operator](helpers/check_operator.md) [gather_logs](helpers/gather_logs.md)

### Check if it is a Network Issue
Check if it is a network issue by following the steps in this [SOP](check-ceph-network-connectivity.md). 
We cannot do much about the possible causes of network issues e.g. misconfigured AWS security group. Therefore, if it 
is a network issue, escalate to the ODF team by following the steps [here](sre-to-engineering-escalation.md#procedure).

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
