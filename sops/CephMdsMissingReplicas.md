
CephMdsMissingReplicas
======================

Check Description
-----------------

**Severity:** Warning

**Potential Customer Impact:** High

Overview
--------

Minimum required replicas for storage metadata service not available. Might affect the working of storage cluster.

Detailed Description: Minimum required replicas for the storage metadata service (MDS) are not available. MDS is responsible for file metadata. Degradation of the MDS service can affect the working of the storage cluster (related to cephfs storage class) and should be fixed as soon as possible.

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

Follow the general pod debug workflow outlined below.

[pod debug](helpers/pod_debug.md) [gather_logs](helpers/gather_logs.md)

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
