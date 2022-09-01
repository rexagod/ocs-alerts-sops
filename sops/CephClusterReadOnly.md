
CephClusterReadOnly
=========================

Check Description
-----------------

**Severity:** Critical

**Potential Customer Impact:** Critical

Overview
--------

Storage cluster is read-only now and needs immediate data deletion or cluster expansion.

Detailed Description: Storage cluster utilization has crossed 85% and will become read-only now. Free up some space or expand the storage cluster immediately.

Prerequisites
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----

### Make changes to solve alert

Two options:
- [Scale storage](https://access.redhat.com/documentation/en-us/red_hat_openshift_data_foundation/4.11/html/scaling_storage/index): Depending on the type of cluster it will be needed to add storage devices and/or nodes.
- Delete information: If not is possible to scale up the cluster it will be needed to delete information in order to free space. 

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
