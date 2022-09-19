
CephMonHighNumberOfLeaderChanges
================================

Check Description
-----------------

**Severity:** Warning

**Potential Customer Impact:** Medium

Overview
--------

The Ceph monitor leader is being changed an unusual number of times.

In a Ceph cluster there is a redundant set of monitors that store critical information about the storage cluster. 
Monitors synchronize periodically to obtain information about the storage cluster. The first monitor to get the most updated information become leader and other monitors will start their synchronization process asking the leader.
An unusual change of leader is usually produced by a problem in network connection, or another kind of problem in one or more monitor pods.
This situation can affect negatively to the storage cluster performance.

Prerequisites
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----

The alert produced indicates the monitor pod with the problem:

    Ceph Monitor <rook-ceph-mon-X... pod> on host <hostX> has seen <X> leader changes per minute recently.

### Check if it is a Network Issue
Check if it is a network issue by following the steps in this [SOP](check-ceph-network-connectivity.md). 
We cannot do much about the possible causes of network issues e.g. misconfigured AWS security group. Therefore, if it 
is a network issue, escalate to the ODF team by following the steps [here](sre-to-engineering-escalation.md#procedure).

### The affected monitor logs can provide more information about the problem
Use the Openshift console to open the logs of the monitor pod affected. More information about possible causes can be reflected in the log.

### Follow the general pod debug workflow outlined below.

[pod debug](helpers/pod_debug.md) [gather_logs](helpers/gather_logs.md)

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
