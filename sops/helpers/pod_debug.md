pod status: pending → Check for resource issues, pending pvcs, node assignment, kubelet problems.

    oc project openshift-storage
    oc get pod | grep {ceph-component}

Set MYPOD for convenience:

    # Examine the output for a {ceph-component} that is in the pending state, not running or not ready
    MYPOD=<pod identified as the problem pod>

Look for resource limitations or pending pvcs. Otherwise, check for node assignment.

    oc get pod/${MYPOD} -o wide

pod status: NOT pending, running, but NOT ready → Check readiness probe.

    oc describe pod/${MYPOD}

pod status: NOT pending, but NOT running → Check for app or image issues.

    oc logs pod/${MYPOD}

If a node was assigned, check kubelet on the node.