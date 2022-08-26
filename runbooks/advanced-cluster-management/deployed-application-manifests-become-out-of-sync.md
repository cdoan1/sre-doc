# Cleaning up deployed manifests that become out of sync with the hub cluster

# Problem

* after upgrading between releases, a deployed application can become out of sync.
* The manifestwork for the managed cluster no longer exists on the hub side.
* However, the managed clusters still have artifacts of the application deployed.
