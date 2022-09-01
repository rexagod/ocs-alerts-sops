
CephPGRepairTakingTooLong
=========================

Check Description
-----------------

**Severity:** Warning

**Potential Customer Impact:** High

Overview
--------

Self heal operations taking too long.

Prerequsities
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----

### Make changes to solve alert

The self healing problems have been detected. Check for inconsistent placement groups and repair using KCS - [KCS with PGRepair details](https://access.redhat.com/solutions/1589113)

[gather_logs](helpers/gather_logs.md)

### Check if it is a Network Issue
Check if it is a network issue by following the steps in this [SOP](check-ceph-network-connectivity.md). 
We cannot do much about the possible causes of network issues e.g. misconfigured AWS security group. Therefore, if it 
is a network issue, escalate to the ODF team by following the steps [here](sre-to-engineering-escalation.md#procedure).

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
