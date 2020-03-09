>   **Chapter 9 exercise – enabling dedup on Windows Server 2019**

>   In this chapter's exercise, you will learn how to enable dedup on Windows
>   Server 2019.

Enabling dedup on Windows Server 2019
-------------------------------------

>   This exercise will be done on the host computer. To enable dedup in Windows
>   Server 2019, complete the following steps:

1.  Right-click on start and select **Disk Management**.

2.  Click Action on the tools bar and Create VHD.

3.  Select VHDX for hard disk format and Dynamically expanding (Recomented)

4.  In the Location field Type C:\\Diskpart and select 200 GB hard disk size.

5.  Select OK.

6.  Right-click the new hard disk select Initialize and select OK to bring the
    new harddisk online.

7.  Right-click the new harddisk, select **New simple volume** and select
    **Next** several times and finish to format the disk.

8.  Copy the C:\\Hyper-v folder from C:\\ to D:\\

9.  Click **Add roles and features** within the **Server Manager** \| **WELCOME
    TO SERVER MANAGER** section.

10. On the **Before You Begin** window, click **Next.**

11. Click **Next** on the **Installation Type** window.

12. On the **Server Selection** window, click **Next.**

13. On the **Server Roles** window, expand **File and Storage Services.**

14. Then, expand **File and iSCSI Services.**

15. Select **Data Deduplication**.

16. On the **Features** window, click **Next.**

17. On the **Confirmation** window, click **Install.**

18. When you see the installation has completed, click **Close**.

19. From Server Manager Select File and Storage Services select Disk – and
    select disk number 1 in the details section.

20. Right-click D: in Volumes section and select “**Configure Data
    Deduplication…”** Enable Data Deduplication by selecting “Virtual Desktop
    Infrastructure (VDI) in the Drop-down box.

21. Select 0 in the Deduplicate files older than (in days) and press the **Set
    Deduplication Schedule** button.

22. Make a checkmark in the **Enable Throughput optimization** and press OK.

23. You can optionally use powershell commands to control the deduplication.

24. Find the powershell command my typing get-command \*dedup\* in powershell

25. You can also in server manager window monitor the Deduplication Rate.

>   This exercise has shown us how dedup can be installed on Windows Server
>   2019.
