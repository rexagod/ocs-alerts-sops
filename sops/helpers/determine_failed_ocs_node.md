Run the following to get the list of worker nodes and check for the node status:

    oc get nodes --selector='node-role.kubernetes.io/worker','!node-role.kubernetes.io/infra'

Describe the node which is of NotReady status to get more information on the failure:

    oc describe node <node_name>