
CephOSDDiskUnavailable
======================

Check Description
-----------------

**Severity:** Error

**Potential Customer Impact:** High

Overview
--------

A disk device is not accessible on one of the host.

Detailed Description: A disk device is not accessible on one of the host and its corresponding OSD is marked out by the ceph cluster. This alert is raised when a ceph node failed to recover within 10 mins.

Prerequsities
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----

### Make changes to solve alert

This alert is raised when a ceph node failed to recover within 10 mins. This procedure determines which node has failures.

#### Determine failed OCS Node

[determine_failed_ocs_node](helpers/determine_failed_ocs_node.md)

[gather logs](helpers/gather_logs.md)

### Check if it is a Network Issue
Check if it is a network issue by following the steps in this [SOP](check-ceph-network-connectivity.md). 
We cannot do much about the possible causes of network issues e.g. misconfigured AWS security group. Therefore, if it 
is a network issue, escalate to the ODF team by following the steps [here](sre-to-engineering-escalation.md#procedure).

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
