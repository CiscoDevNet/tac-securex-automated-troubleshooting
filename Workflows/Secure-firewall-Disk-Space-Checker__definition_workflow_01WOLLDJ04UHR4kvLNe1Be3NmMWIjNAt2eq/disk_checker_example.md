# Disk Space Checker Result
## Large Amount of Update files
This FMC has 5GB or more of files in the /var/sf/updates directory. You should consider removing old updates that are no longer needed.
## Large Amount of Cloud Download files
This FMC has 5GB or more of files in the /ngfw/var/sf/cloud_download directory. This could mean the device is possibly hitting bug [CSCwb78323](https://bst.cisco.com/quickview/bug/CSCwb78323). Files may build up in here if the SFDataCorrelator process is not running. See the [bug notes](https://bst.cisco.com/quickview/bug/CSCwb78323) for additional information and a workaround which will help clear space