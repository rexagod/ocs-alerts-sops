
CephMgrIsMissingReplicas
========================

Check Description
-----------------

**Severity:** Warning

**Potential Customer Impact:** High

Overview
--------

Ceph Manager is missing replicas. This impacts health status reporting and will cause some of the information reported by \`ceph status\` to be missing or stale. In addition, the ceph manager is responsible for a Manager framework aimed at expanding the Ceph existing capabilities.

Detailed Description: To resolve this alert, you will need to determine the cause of the disappearance of the Ceph Manager and restart if necessary.

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
