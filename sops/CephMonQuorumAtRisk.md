
CephMonQuorumAtRisk
===================

Check Description
-----------------

**Severity:** Error

**Potential Customer Impact:** High

Overview
--------

Storage cluster quorum is low.

Multiple mons work together to provide redundancy by each keeping a copy of the metadata. Cluster is deployed with 3 mons, and require 2 or more mons to be up and running for quorum and for the storage operations to run. If quorum is lost, access to data is at risk.

Prerequisites
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----

Follow the link to follow procedures for quorum recovery

*   [Restore Ceph Mon Quorum](https://access.redhat.com/solutions/5898541)
    

Follow the general pod debug workflow outlined below.

[pod debug](helpers/pod_debug.md) [gather_logs](helpers/gather_logs.md)

### Check if it is a Network Issue
Check if it is a network issue by following the steps in this [SOP](check-ceph-network-connectivity.md). 
We cannot do much about the possible causes of network issues e.g. misconfigured AWS security group. Therefore, if it 
is a network issue, escalate to the ODF team by following the steps [here](sre-to-engineering-escalation.md#procedure).


Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
