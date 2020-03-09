>   **Chapter 4 exercise – performing an initial Windows Server configuration**

>   In this chapter exercise, you will learn how to do the following:

>   Perform Windows Server initial configuration using Server Manager

>   Perform Windows Server initial configuration using Server Configuration

Before running this exercise, you need to create a new Virtual Machine SVR10 if
not already created in the first lab. If already created you can jump to next
section to perform initial configuration.

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

20. Now make sure that DC1 virtual machine has already been started from
    previous labs. If not, start DC1.

21. (now you are ready for the initial configuration.)

Performing Windows Server initial configuration using Server Manager
--------------------------------------------------------------------

>   The following section provides explanations regarding the initial
>   configuration of Windows Server 2019 DataCenter (Desktop Experience) by
>   using Server Manager.

1.  From Hyper-V Manager, start SVR10 and connect to it.  
    Accept location and keyboard or change if necessary.

2.  Type password Pa55w.rd twice.

3.  Sign in with Administrator and Pa55w.rd as password.

### Changing the server name

>   To change the server name, take the following steps:

1.  In Server Manager, click **Local Server** on dashboard in the left side.

2.  In Server Manager, in the **Properties** section, click the highlighted
    default computer name.

3.  In the **System Properties** window, click the **Change** button.

4.  In the **Computer Name/Domain Changes** window, delete the existing computer
    name and type **SVR10** for your server, and then click **OK**:

5.  Click **OK** to confirm that you will restart your server to apply these
    changes.

6.  In the **System Properties** window, click the **Close** button.

7.  In the Microsoft Windows dialog box, click **Restart Now**.

8.  Sign in with Administrator and Pa55w.rd as password.

>   Now let's learn how to join the server to a domain.

### Joining a domain

>   Before joining the server to a domain, evaluate the role of your server. If
>   your server is going to be a **Domain Controller** (**DC**), then there is
>   no need for it to join a domain, as adding the AD DS role will automatically
>   make your server a domain controller. Otherwise, if your server is going to
>   have a role other than AD DS, then, as a domain member, it must join the
>   domain. To do so, take the following steps:

1.  In Server Manager, click **Local Server** on dashboard in the left side.

2.  In the **Properties** section, click the highlighted workgroup.

3.  In the **System Properties** window, click the **Change** button.

4.  In the **Computer Name/Domain Changes** window, select the **Domain:**
    option and click the textbox to provide the domain name: **myorg.local**,
    and then click **OK**:

>   Joining a server to a domain

1.  In the **Windows Security** window, enter the name **myorg\\administrator**
    and **Pa55w.rd** of an account with a permission to join the domain, and
    then click **OK**.

2.  The **Computer Name/Domain Changes** dialog box welcomes your server to your
    organization's domain. Click **OK** to close it.

3.  Click **OK** to confirm that you will restart your server to apply these
    changes.

4.  In the **System Properties** window, click the **Close** button.

5.  In the **Microsoft Windows** dialog box, click **Restart Now**.

6.  After the restart select **Other User** and sign in with
    **myorg\\administrator** and **Pa55w.rd**.

7.  In Server Manager, click **Local Server** on dashboard in the left side.

>   Now let's learn how to enable Remote Desktop.

### Enabling Remote Desktop

>   To enable Remote Desktop, take the following steps:

1.  In the **Properties** section, click the highlighted Remote Desktop setting.

2.  In the **System Properties** window, select or confirm the **Allow remote
    connections to this computer** option.

3.  The **Remote Desktop Connection** dialog box informs you that the Remote
    Desktop firewall exception will be enabled. Click **OK** to close it:

4.  To add Remote Desktop users, click the **Select Users...** button.

5.  In the **Remote Desktop Users** window, click the **Add** button to add
    users. Select “Domain Users” from your AD DS. When you have finished adding
    Remote Desktop users, click **OK** to close the **Remote Desktop Users**
    window.

6.  Again, click **OK** to close the **System Properties** window.

7.  Server Manager will now show Enabled for Remote Desktop, If not, Refresh
    Server Manager by pressing the round symbol in the top menubar.

>   Now let's learn how to set up the IP address.

### Setting up the IP address

>   To set up the IP address, take the following steps:

1.  In the **Properties** section, click the highlighted Ethernet setting:

2.  In the **Network Connections** window, right-click your server's Ethernet
    and select **Properties**.

3.  In the **Ethernet Properties** window, select **Internet Protocol Version 4
    (TCP/IPv4),** and click the **Properties** button.

4.  In the **Internet Protocol Version 4 (TCP/IPv4) Properties** window, select
    the **Use the following IP address:** option and enter the **IP address**,
    **Subnet mask**, and **Default gateway** fields.

5.  IP Address: 172.16.0.29  
    Subnet Mask: 255.255.255.0  
    Default Gateway: 172.16.0.1

6.  Additionally, select the **Use the following DNS server addresses:** option
    and fill in the **Preferred DNS server** and **Alternate DNS server**
    fields. Click **OK** to close.  
    DNS Server: 172.16.0.10

7.  Click the **Close** button to close the **Ethernet Properties** window.

8.  In the upper-right corner, click the Close button (the red X) to close the
    **Network Connections** window.

>   Now let's learn how to turn off the IE enhanced security settings.

### Turning off IE enhanced security

>   To turn off the IE enhanced security settings, take the following steps:

1.  In the **Properties** section, click the highlighted IE enhanced security
    configuration setting.

2.  In the **Internet Explorer Enhanced Security Configuration** window within
    the **Administrators:** section, select the **Off** option.

3.  Click **OK** to close the **Internet Explorer Enhanced Security
    Configuration** window:

>   Turning off IE enhanced security

>   Now let's learn how to change the time zone.

### Changing the time zone

>   To change the time zone, take the following steps:

1.  In the **Properties** section, click the highlighted time zone setting.

2.  In the **Date and Time** window, click the **Change time zone...** button.

3.  In the **Time Zone Settings** window, click the drop-down list to select
    your time zone.

4.  Click **OK** to close the **Time Zone Settings** window.

5.  Again, click **OK** to close the **Date and Time** window:

Performing Windows Server initial configuration using Server Configuration
--------------------------------------------------------------------------

>   The following section explains the initial configuration of Windows Server
>   2019 DataCenter (Server Core) using Server Configuration.

1.  Start SVRCORE3, press Ctrl, Alt, Del and sign in with Pa55w.rd.

2.  Type **Sconfig** and press Enter.

### Changing the server name

>   To change the server name, take the following steps:

1.  Enter 2 as a selected option and press *Enter*.

2.  Enter the new server name, SVRCORE4 and press *Enter*.

3.  In the **Restart** dialog box, click **Yes** to restart the server:

>   Changing the server name

1.  Your server will restart so it can apply the server name change.

>   Now let's learn how to join the server to a domain.

### Joining the domain

>   Before joining the domain, take into consideration the notes provided
>   earlier, when we were performing configuration using Server Manager. To join
>   the domain, take the following steps:

1.  Press Ctrl, Alt, Del and sign in with Pa55w.rd.

2.  Type **Sconfig** and press Enter.

3.  Enter 1 as a selected option and press *Enter*.

4.  To join your server to your organization domain, enter D and press *Enter*.

5.  Enter your organization domain, myorg.local, and press *Enter*.

6.  Enter myorg\\administrator and press *Enter*.

7.  Enter the password Pa55w.rd and press *Enter*.

8.  In the **Change Computer Name** dialog box,  
    click **No** when asked to change the name of your server:

9.  Select **Yes** to restart the server.

10. Press Ctrl, Alt, Del and sign in with Pa55w.rd.

11. Type **Sconfig** and press Enter.

>   Joining the domain

>   Now let's learn how to enable Remote Desktop.

### Enabling Remote Desktop

>   To enable Remote Desktop, take the following steps:

1.  Enter 7 as a selected option and press *Enter*.

2.  To enable Remote Desktop, enter E and press *Enter*.

3.  Enter 1 and press *Enter* for more secure access.

4.  In the **Remote Desktop** dialog box, click **OK** to confirm Remote Desktop
    enabling:

>   Now let's learn how to set up the IP address.

### Setting up the IP address

>   To set up the IP address, take the following steps:

1.  Enter 8 as a selected option and press *Enter*.

2.  Enter the number of the network adapter that you want to set up the IP
    address for and press *Enter*.

3.  Enter 1 in the sub-menu to set the network adapter address and press
    *Enter*.

4.  Enter S for the static IP address and press *Enter*.

5.  Enter the static IP address 172.16.0.39 and press *Enter*.

6.  Enter the subnet mask 255.255.255.0 and press *Enter*.

7.  Enter the default gateway 172.16.0.1 and press *Enter*.

8.  Enter 2 in the sub-menu to set the DNS servers and press *Enter*.

9.  Enter the new preferred DNS server 172.16.0.10 and press *Enter*.

10. In the **Network Settings** dialog box, click **OK** to close it.

11. Enter the alternate DNS server and press *Enter*.

12. Enter 4 in the sub-menu to exit and **Return to Main Menu**:

>   Now let's learn how to change the time zone.

### Changing the time zone

>   To change the time zone, take the following steps:

1.  Enter 9 as a selected option and press *Enter*.

2.  In the **Date and Time** window, click the **Change time zone...** button.

3.  In the **Time Zone Settings** window, click the drop-down list to select
    your time zone.

4.  Click **OK** to close the **Time Zone Settings** window.

5.  Again, click **OK** to close the **Date and Time** window.

6.  Shut down SVR10 and SVRCORE3
