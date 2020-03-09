>   **Chapter 8 exercise – installing Hyper-V on Windows Server 2019**

>   In this exercise, you will learn how to install the Hyper-V role on Windows
>   Server 2019.

Prepare for Nested Virtualization.
----------------------------------

1.  On the physical computer open an administrative PowerShell prompt by right
    clicking the Windows button on the host machine and choose “Windows
    PowerShell (Admin).

2.  In the PowerShell prompt, write in one command:  
    *Set-VMProcessor -VMName SVR1 -ExposeVirtualizationExtensions \$true*

3.  In the PowerShell prompt, write in one command: *get-VMNetworkAdapter
    -VMName SVR1 \| Set-VMNetworkAdapter – MacAddressSpoofing On*

4.  Start SVR1.

5.  Signin to SVR1 with myorg\\administrator and Pa55w.rd

Installing the Hyper-V role on Windows Server 2019
--------------------------------------------------

>   To install the Hyper-V role on Windows Server 2019 using the Server Manager,
>   complete the following steps:

1.  Click the Start button, and then, in the Start menu, click **Server
    Manager**.

2.  In the **Server Manager** window, click the **Add roles and features**
    hyperlink.

3.  In the **Before You Begin** option, click **Next**.

4.  In the **Installation Type** option, click **Next**.

5.  In the **Server Selection** option, click **Next**.

6.  Select the **Hyper-V** role.

7.  Click the **Add Features** button to add features that are required for
    Hyper-V.

8.  There is no feature to add, so click **Next**.

9.  In the Hyper-V definition option, click **Next**.

10. Select the available network adapter, and then click **Next**.

11. Select **Allow this server to send and receive live migrations of virtual
    machines** and click **Next**.

12. Set up the path where you will store the VMs and click **Next**.

13. Confirm the installation selections for the Hyper-V role by clicking
    **Install**.

14. When the installation process completes, click **Close**.  
    The server will restart automatically.

15. After restart, sign in and open Hyper-V Manager.

16. If time permits – install a nested virtual Server 2019 (SVR1 has an ISO
    folder on C:\\)

17. Shutdown all virtual machines after this exercise.
