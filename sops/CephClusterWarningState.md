
CephClusterWarningState
=======================

Check Description
-----------------

**Severity:** Warning

**Potential Customer Impact:** High

Overview
--------

Storage cluster is in warning state for more than 10m.

The Storage cluster has been in a warning state for an unacceptable amount of time. While the storage operations will continue to function in this state, it is recommended to fix errors so that the cluster does not get into error state impacting operations. Check for other alerts that would have triggered prior to this one and troubleshoot those alerts first.

Prerequisites
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----
### Check if it is a Network Issue
Check if it is a network issue by following the steps in this [SOP](check-ceph-network-connectivity.md). 
We cannot do much about the possible causes of network issues e.g. misconfigured AWS security group. Therefore, if it 
is a network issue, escalate to the ODF team by following the steps [here](sre-to-engineering-escalation.md#procedure).

### Generic Debugging

General troubleshooting will be required in order to determine the cause of this alert. This alert will trigger along with other (usually many other) alerts. Please view and troubleshoot the other alerts first.

[pod debug](helpers/pod_debug.md) [gather_logs](helpers/gather_logs.md)

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
