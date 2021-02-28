# Working with Storage
## Perform a disk migration from standard Magnetic Disks to Solid State Drives

## Learning Outcomes
1.  Create a blank storage drive
2.  Mount and unmount a blank drive to and from a GCE instance
3.  Format a new disk for usage
4.  Create and schedule disk snapshotsProprietary content. ©Great Learning. All Rights Reserved. Unauthorized use or distribution prohibited


## How To Do It ?

1)  Create a Ubuntu VM in Compute Engine with disk size 10GB.
2)  Navigate to disks and create a standard magnetic disk with the followingparametersa)Size : 15GBb)Location : US Central 1
c)  Type : Standard Persistent Disk
d)  Source Type : Blank
e)  Snapshots taken daily between 2 a.m. - 3 a.m and stored in Asia Pacific
f)  Snapshots deleted after 48 hours of creation
3)  Attach the created disk to the VM created in step 1
4)  Connect to the VM using SSH
5)  Format the attached disk to Ext4 and mount it to the folder ./testGCP
6)  Create a text file with text of your choice on the mounted disk.
7)  Unmount the disk and unattach it from the VM (Try unmounting the disk while working inside the folder ./testGCP to see what happens)
8)   Take a manual snapshot of the unattached disk and name it testsnapshot.
9)   Create a new disk with the following parameters :
a)  Size : 20GBb)Source Type : testsnapshot
c)  Type : SSD Persistent Disk
d)  Snapshots taken daily between 2 a.m. - 3 a.m and stored in Asia Pacific
e)  Snapshots deleted after 48 hours of creation
10) Attach the new SSD created to the VM.
11)Mount it to the same folder ./GCP12)Confirm that the file created in  step 6 is present in the new disk.


## Command Reference
1)  Mount the drive /dev/sda to /examplemount /dev/sdb ./example
2)  Format the drive /dev/sdb to Ext4mkfs -t ext4 /dev/sda
3)  Check the list of attached diskslsblk
4)  Unmount the drive /dev/sdaumount /dev/sda
