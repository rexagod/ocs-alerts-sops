
CephPoolQuotaBytesNearExhaustion
================================

Check Description
-----------------

**Severity:** Warning

**Potential Customer Impact:** High

Overview
--------

Storage pool quota usage has crossed 70%.

Detailed Description: One or more pools is approaching a configured fullness threshold. One threshold that can trigger this warning condition is the `mon_pool_quota_warn_threshold` configuration option.

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

Setting the quota value to 0 will disable the quota. Other thresholds that can trigger the above two warning conditions are `mon_osd_nearfull_ratio` and `mon_osd_full_ratio.`

Troubleshooting
---------------

[troubleshooting](helpers/troubleshooting.md)
