
CephOSDSlowOps
===============

Check Description
-----------------

**Severity:** Warning

**Potential Customer Impact:** Medium

Overview
--------

OSD requests are taking too long to process.

An OSD with slow requests is every OSD that is not able to service the I/O operations per second (IOPS) in the queue within the time defined by the `osd_op_complaint_time` parameter. By default, this parameter is set to 30 seconds.

Prerequisites
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----
More information about the slow requests can be obtained using the Openshift console. Access to the OSD pod terminal and issue the following commands:

    ceph daemon osd.<id> ops

    ceph daemon osd.<id> dump_historic_ops

* note: Where <id> is the number of the OSD. it can be seen in the pod name, for example, in `rook-ceph-osd-0-5d86d4d8d4-zlqkx`, <0> is the OSD <id>


The main causes of OSDs having slow requests are:

- Problems with the underlying hardware/infrastructure, such as disk drives, hosts, racks, or network switches
Use the Openshift monitoring console to find alerts/errors about cluster resources. This can give clues about the root problem of the OSD slow operations.  

- Problems with network. These problems are usually connected with flapping OSDs.
[See troubleshoot flapping OSDs](https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/2/html/troubleshooting_guide/troubleshooting-osds#flapping-osds).
 Check if it is a network issue by following the steps in this [SOP](check-ceph-network-connectivity.md).

- Other Problems with network.
 We cannot do much about the possible causes of network issues e.g. misconfigured AWS security group. Therefore, if it
 is a network issue, escalate to the ODF team by following the steps [here](sre-to-engineering-escalation.md#procedure)

- System load
Use Openshift console to review the metrics of the OSD pod and the Node which is running the OSD. Adding/assign more resources can be a possible solution.   

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
