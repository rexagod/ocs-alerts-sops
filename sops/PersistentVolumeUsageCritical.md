PersistentVolumeUsageCritical
=============================

Check Description
-----------------

**Severity:** Error

**Potential Customer Impact:** High

Overview
--------

Persistent Volume Claim usage has exceeded more than 85% of its capacity.

Detailed Description: This alert reflects that a PVC is nearing its full capacity and may lead to data loss if not attended to timely.

Prerequisites
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----

### Expand the PVC size to increase the capacity

![](helpers/visuals/expand-pvc-dropdown.png)
![](helpers/visuals/expand-pvc-dialog.png)

Alternatively, you can also delete unnecessary data that may be taking up space.

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
