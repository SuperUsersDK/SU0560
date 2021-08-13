---
abstract: "Workshop part 3 of 4\nConfigure Storage Spaces and Tiered Storage Windows Server 2019"
---

>   In this Workshop, you will test functionality of Storage Spaces and the
>   creation of Tiered Storage in Windows Server 2019.

Storage Spaces and Tiered Storage
---------------------------------

>   You have decided to test the way that you can use Storage Spaces in Server
>   2019 on a single server to make sure that you can tolerate at least two disk
>   failures without losing any data. At the same time, you want to set up a
>   Tiered Storage with both SSD´s and HDD´s so that you have a server that
>   supports both reliability and performance. You are using a virtual machine
>   for this test and will be using a PowerShell script on this page for adding
>   the extra disk to svr1.

-   Configure server SVR1 with Storage Spaces and Tiered Storage.

-   Modify and use the script below to add SSD and HDD disks to your virtual
    machine.

-   Add enough HDD disks to make sure that you can tolerate two disk failures
    without losing data.

-   Add enough SSD disks to make sure that you can set up a Tiered storage.

-   Add extra HDD´s that are not part of your storage space that you can add
    when testing disk disaster.

-   Test disk disaster by removing a disk from the virtual machine and then add
    a new.

-   If able to try to use PowerShell commands when working with your disks on
    the server.

-   If you have the time, try to manage your Storage Space from Windows Admin
    Center.

>   Inspiration on how to accomplish this can be found on:

<https://docs.microsoft.com/en-us/windows-server/storage/storage-spaces/deploy-standalone-storage-spaces>

<https://nedimmehic.org/2017/05/01/how-to-configure-storage-spaces-and-tiered-storage-windows-server-2016/>

After this workshop make sure that you remove the created disks from SVR1 and
delete the VHDX files.

#______________________________________________________________________________________

#Make sure that SVR1 has been shut down before running this section

#This section must be run from the host (Copy into Powershell ISE)

$VMName = "SVR1"

$VMPath = "C:\Hyper-V"

[bool]$AddStorageDisks = $true

function AddStorageDisks

{

###############################################################

# Create the Storage Disk VHDs and attach to Storage Server VM

$VHDPath = $VMPath

$i=0

ForEach ($_ in 1..5)

{

$i++

$DiskName = $VMName + "HDDDisk0" + $i + ".vhdx"

$VHDFile = "$VHDPath\$DiskName"

Write-Verbose "New-VHD - Creating VHDFile [$VHDFile] Size 10GB"

New-VHD -path $VHDFile -Size 10GB -Fixed | Out-Null

Write-Verbose "Add-VMHardDiskDrive - Attaching [$VHDFile] to VM $VMName"

Add-VMHardDiskDrive -VMName $VMName -Path $VHDFile -ControllerType SCSI

}

$i=0

ForEach ($_ in 1..5)

{

$i++

$DiskName = $VMName + "SSDDisk0" + $i + ".vhdx"

$VHDFile = "$VHDPath\$DiskName"

Write-Verbose "New-VHD - Creating VHDFile [$VHDFile] Size 5GB"

New-VHD -path $VHDFile -Size 5GB -Fixed | Out-Null

Write-Verbose "Add-VMHardDiskDrive - Attaching [$VHDFile] to VM $VMName"

Add-VMHardDiskDrive -VMName $VMName -Path $VHDFile -ControllerType SCSI

}
}
Write-Verbose "Set VM DynamicMemory and ProcessorCount 2"

Set-VM -Name $VMName -DynamicMemory -ProcessorCount 2

Write-Verbose "Set VM for Virtualization Extensions"

Set-VMProcessor -VMName $VMName -ExposeVirtualizationExtensions $true

Write-Verbose "Enable Mac Address Spoofing"

Get-VMNetworkAdapter -VMName $VMName | Set-VMNetworkAdapter -MacAddressSpoofing On

if ($AddStorageDisks)

{

Write-Verbose "Adding Storage Disks to VM"

AddStorageDisks

}

#______________________________________________________________________________

# Start svr1 and sign in with myorg.local\administrator Pa55w.rd

# Open up Powershell Ise as administrator

# Run this commands from within SVR1 vm

Get-PhysicalDisk | ? Size -lt 6GB | Set-PhysicalDisk –Usage Retired

Get-PhysicalDisk -Usage Retired | Set-PhysicalDisk –MediaType SSD

Get-PhysicalDisk -Usage Retired | Set-PhysicalDisk -Usage AutoSelect

Get-PhysicalDisk | ? Size -lt 11GB |? Size -gt 6GB | Set-PhysicalDisk –Usage Retired

Get-PhysicalDisk -Usage Retired | Set-PhysicalDisk –MediaType HDD

Get-PhysicalDisk -Usage Retired | Set-PhysicalDisk -Usage AutoSelect

#______________________________________________________________________________

# you are now ready for trying out the workshop creating a tired storage space with ssd and hdd

#For more info

#https://docs.microsoft.com/en-us/windows-server/storage/storage-spaces/deploy-standalone-storage-spaces
