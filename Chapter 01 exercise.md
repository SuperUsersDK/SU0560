>   **Chapter 1 exercise – Installing Server 2019**

>   In this chapter exercise, you will learn how to do the following:

>   Create a Virtual Machine and install Server 2019

Before running this exercise you need to create a new Virtual Machine

1.  Open Hyper-v Manager

2.  Klik **New** below Actions in the right side and select **Virtual Machine…**

3.  Select **Next** on “Before You Begin” screen.

4.  Type **SVR10** in the Name field on the “Specify Name and Location” screen
    and press **Next**.

5.  Select **Generation 2** on the “Specify Generation” screen and press
    **Next**.

6.  Type in **2048 MB** as Startup memory, and **select** “Use Dynamic Memory
    for this virtual machine” and press **Next**.

7.  Select “Internal Network” from the drop-down box, on the “Configure
    Networking” screen and press **Next**.

8.  Type **50** GB in the Size field and press **Next**.

9.  Select “Install an operation system from a bootable image file” and type in
    C:\\ISO\\Server2019.iso as the location and press **Next**.

10. Press **Finish** on the “Completing the new Virtual Machine Wizard” screen.

11. From Hyper-V Manager, right click **SVR10** and select **Connect**.

12. After pressing Start be ready to “press any key” when you see the text
    “Press any key to boot on dvd….”

13. Select Language - **English**, Time and currency format – **Danish** and
    Keyboard or input method – **Danish** and press **Next**.

14. Select **Install now.**

15. Select “Windows Server 2019 Datacenter (Desktop Experience)” and press
    **Next**.

16. Select “I accept the license terms” and press **next**.

17. Select “Custom: Install Windows on (advanced)”

18. Select **Next** on the “Where do you want to install Windows?” screen.

19. After restart of the virtual machine you need to disconnect the
    Server2019.ISO file by selecting **Media – DVD Drive – Eject
    Server2019.iso** on the top portion window of the new virtual machine.

20. When restarting you will be prompted for a password. At this point
    Right-click SVR10 virtual machine and select checkpoint to create a
    production checkpoint of the server. At this point don´t go any further with
    the initial setup. We will be continuing this configuration in exercise 4.

21. Leave SVR10 virtual machine running.
