
CephNodeDown
============

Check Description
-----------------

**Severity:** Error

**Potential Customer Impact:** Medium

Overview
--------

A storage node went down. Please check the node immediately. The alert should contain the node name.

A node running Ceph pods is down. While storage operations will continue to function as Ceph is designed to deal with a node failure, it is recommended to resolve the issue to minimise risk of another node going down and affecting storage functions.

Prerequisites
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----

### Make changes to solve alert

Document the current OCS pods (running and failing):

    oc -n openshift-storage get pods

The OCS resource requirements must be met in order for the osd pods to be scheduled on the new node. This may take a few minutes as the ceph cluster recovers data for the failing but now recovering osd.

To watch this recovery in action ensure the osd pods were actually placed on the new worker node.

Check if the previous failing osd pods are now running:

    oc -n openshift-storage get pods

If the previously failing osd pods have not been scheduled, use describe and check events for reasons the pods were not rescheduled.

Describe events for failing osd pod:

    oc -n openshift-storage get pods | grep osd

Find a failing osd pod(s):

    oc -n openshift-storage describe pods/<osd podname from previous step>

In the event section look for failure reasons, such as resources not being met.

In addition, you may use the rook-ceph-toolbox to watch the recovery. This step is optional but can be helpful for large Ceph clusters.

**Determine failed OCS Node** [determine_failed_ocs_node](helpers/determine_failed_ocs_node.md)

[access toolbox](helpers/access_toolbox.md)

From the rsh command prompt, run the following and watch for "recovery" under the io section:

    ceph status

[gather logs](helpers/gather_logs.md)

### Check if it is a Network Issue
Check if it is a network issue by following the steps in this [SOP](check-ceph-network-connectivity.md). 
We cannot do much about the possible causes of network issues e.g. misconfigured AWS security group. Therefore, if it 
is a network issue, escalate to the ODF team by following the steps [here](sre-to-engineering-escalation.md#procedure).


Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
