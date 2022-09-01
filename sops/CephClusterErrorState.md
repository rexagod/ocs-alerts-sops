
CephClusterErrorState
=====================

Check Description
-----------------

**Severity:** Error

**Potential Customer Impact:** Critical

Overview
--------

Storage cluster is in error state for more than 10m.

Detailed Description: This alert reflects that the storage cluster is in \*ERROR\* state for an unacceptable amount of time and this impacts the storage availability. Check for other alerts that would have triggered prior to this one and troubleshoot those alerts first.

Prerequisites
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----

### Check if it is a Network Issue
Check if it is a network issue by following the steps in this [SOP](check-ceph-network-connectivity.md). 
We cannot do much about the possible causes of network issues e.g. misconfigured AWS security group. Therefore, if it 
is a network issue, escalate to the ODF team by following the steps [here](sre-to-engineering-escalation.md#procedure).

### Make changes to solve alert

General troubleshooting will be required in order to determine the cause of this alert. This alert will trigger along with other (usually many other) alerts. Please view and troubleshoot the other alerts first.

[pod debug](helpers/pod_debug.md)

If the basic health of the running pods, node affinity and resource availability on the nodes have been verified, run Ceph tools for status of the storage components.

[troubleshoot_ceph_err](helpers/troubleshoot_ceph_err.md) [gather_logs](helpers/gather_logs.md)

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
