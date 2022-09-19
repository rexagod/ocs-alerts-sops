
CephPoolQuotaBytesCriticallyExhausted
=====================================

Check Description
-----------------

**Severity:** Critical

**Potential Customer Impact:** High

Overview
--------

Storage pool quota usage has crossed 90%.

Detailed Description: One or more pools has reached (or is very close to reaching) its quota. The threshold to trigger this error condition is controlled by the `mon_pool_quota_crit_threshold` configuration option.

Prerequsities
-------------

[prerequisites](helpers/prerequisites.md)

Alert
-----

### Adjust pool quotas

Pool quotas can be adjusted up or down (or removed) with:

```console
ceph osd pool set-quota <pool> max_bytes <bytes>
ceph osd pool set-quota <pool> max_objects <objects>
```

Setting the quota value to 0 will disable the quota.

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
