# Application Topology View Becomes Out of Sync

* In some cases, the application topology view of deploy application does not reflect the current status of applications on remote managed clusters.
* This can happen when the managed cluster is deleted outside the context of ACM, and the klusterlet does not have a chance to report that its state has changed.

# Resolution

* We can manually clean up any invalid artifacts by editing/deleting the SubscriptionReports CR in the managed cluster namespace on the ACM Hub.
* If there are multiple applications subscribed to the managed cluster, you can edit and manually remove any invalide entries in the SubscriptionReport CR.

Edit/Delete CR
```bash
oc edit subscriptionreports.apps.open-cluster-management.io dev-aks-central -n dev-aks-central
# or
oc delete subscriptionreports.apps.open-cluster-management.io dev-aks-central -n dev-aks-central
```
