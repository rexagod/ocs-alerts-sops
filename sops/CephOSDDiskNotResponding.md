
CephOSDDiskNotResponding
========================

Check Description
-----------------

**Severity:** Error

**Potential Customer Impact:** Medium

Overview
--------

A disk device is not responding on one of the host.

Detailed Description: A disk device is not responding. Check whether all the OSDs are up and running.

Prerequsities
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----

### Check if it is a Network Issue
Check if it is a network issue by following the steps in this [SOP](check-ceph-network-connectivity.md). 
We cannot do much about the possible causes of network issues e.g. misconfigured AWS security group. Therefore, if it 
is a network issue, escalate to the ODF team by following the steps [here](sre-to-engineering-escalation.md#procedure).

### Generic Debugging

Follow the general pod debug workflow outlined below.

[pod debug](helpers/pod_debug.md) [gather_logs](helpers/gather_logs.md)

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
