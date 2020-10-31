# wakeup\_vbox\_hostadapters

When Virtualbox is installed on linux and VMs created with networking using the host-only adapter to communicate with each other, it has been discovered that after the host wakes up from sleep, the host-only adapter appears to be UP on the host, however the VMs cannot ping each other.

This script, `kickHostAdapter`, can be placed in any directory that is part of `PATH` and run when you encounter the issue.

The script uses `VBoxManage` to get a list of host-only interfaces, then finds the VMs using it, then sets the interface off, then on for each.