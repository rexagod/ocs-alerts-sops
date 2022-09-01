
CephMgrIsAbsent
===============

Check Description
-----------------

**Severity:** Warning

**Potential Customer Impact:** High

Overview
--------

Ceph Manager has disappeared from Prometheus target discovery.

Not having a Ceph manager running impacts the monitoring of the cluster, PVC creation and deletion requests and should be resolved as soon as possible.

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

Verify the rook-ceph-mgr pod is failing and restart if necessary. If the ceph mgr pod restart fails, use general basic pod troubleshooting to resolve.

Verify the ceph mgr pod is failing:

    oc get pods -n openshift-storage | grep mgr

Describe the ceph mgr pod for more detail:

    oc describe -n openshift-storage pods/<rook-ceph-mgr pod name from previous step>

Analyze errors (i.e. resource issues?)

Try deleting the pod and watch for a successful restart:

    oc get pods -n openshift-storage | grep mgr

If above fails, follow general pod troubleshooting procedures.

[pod debug](helpers/pod_debug.md) [gather_logs](helpers/gather_logs.md)

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
