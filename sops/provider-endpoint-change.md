# ODF Consumer losing connection on change to ODF Provider endpoint

## Severity: High

## Impact

ODF Consumer clusters losing connections to the provider therefore hampering the usage of ODF.

## Summary

Whenever the ODF Provider cluster's node, whose IP is being used as Provider endpoint, is turned off or replaced, the provider endpoint/IP is changed. Unfortunately, this endpoint/IP change is not communicated to the ODF Consumer clusters causing them to continue using the old Provider endpoint. This will cause those Consumer clusters to encounter multiple errors associated with interacting with the Provider API.

## Steps

### Getting the new provider endpoint

1. Backplane access the ODF Provider cluster of the customer. 
2. `oc get nodes -o wide | grep "worker" | grep -v "infra"`.
3. Pick the IP address of any one of those "worker" nodes. Say, it's 18.17.16.15.
4. The Provider endpoint would be the `<IP>:31659` or as per the above example, `18.17.16.15:31659`.

### Sending the new Provider endpoint to the user

The fix requires the AddonParameters of the customer's ODF installation to be updated with the new Provider API endpoint. This is something which only the customer can do:

1. Follow the [MT-SRE Customer Notification SOP](#https://gitlab.cee.redhat.com/service/managed-tenants-sops/-/blob/main/MT-SRE/sops/mt-sre-customer-notification.md) to a send a notification (E-mail) to the customer containing the new Provider API endpoint and the steps/reference to update the AddonParameters of their ODF installation with this new endpoint.
2. Update the add-on parameters with this new provider endpoint.
3. In extreme cases, uninstall this addon on the customer's cluster and restart the addon installation with the new provider endpoint. This new provider endpoint would be fetched and fed in the same way the previous endpoint was fetched from CEE and fed to the addon parameters.
