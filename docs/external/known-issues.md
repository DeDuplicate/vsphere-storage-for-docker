---
title: Known Issues
---

This section lists the major known issues with vSphere Docker Volume Service. For a complete list of issues, please check our Github issues(https://github.com/vmware/vsphere-storage-for-docker/issues) page. If you notice an issue not listed in Github issues page, please do file a bug on the [Github repo](https://github.com/vmware/vsphere-storage-for-docker/issues)

-  Volume metadata file got deleted while removing volume from VM(placed on Esx2) which is in use by another VM(placed on Esx1) [#1191](https://github.com/vmware/vsphere-storage-for-docker/issues/1191). It's an ESX issue and will be available in the next vSphere release.
-  Currently "vmdk-opsd stop" just stops (exits) the service forcefully. If there are operations in flight it could kill them in the middle of execution. This can potentially create inconsistencies in VM attachement, KV files or auth-db. [#1073](https://github.com/vmware/vsphere-storage-for-docker/issues/1073)
- VDVS volume that has already been created cannot be resized or it's size cannot be updated.

## Windows Plugin Known issues

- Volume creation initiated by Windows Container Hosts is slow. [#2010](https://github.com/vmware/vsphere-storage-for-docker/issues/2010)

## Known Differences Between Linux And Windows Plugin
- Docker, by default, converts volume names to lower-case on Windows. Therefore, volume operations involving case-sensitive names will always be handled in lower case.