
CephOSDFlapping
===============

Check Description
-----------------

**Severity:** Error

**Potential Customer Impact:** Medium

Overview
--------

Ceph storage osd flapping.

A storage daemon has restarted 5 times in last 5 minutes. Please check the pod events or ceph status to find out the cause.

Prerequisites
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----

Follow the link to follow procedures for flapping OSDs

*   [troubleshoot flapping OSDs](https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/2/html/troubleshooting_guide/troubleshooting-osds#flapping-osds)
    

Follow the general pod debug workflow outlined below.

[pod debug](helpers/pod_debug.md) [gather_logs](helpers/gather_logs.md)

### Check if it is a Network Issue
Check if it is a network issue by following the steps in this [SOP](check-ceph-network-connectivity.md). 
We cannot do much about the possible causes of network issues e.g. misconfigured AWS security group. Therefore, if it 
is a network issue, escalate to the ODF team by following the steps [here](sre-to-engineering-escalation.md#procedure).

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
