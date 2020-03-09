>   **Chapter 7 exercise – examples of GPOs for system admins**

>   In this chapter exercise, you will get acquainted with some GPOs that may be
>   of interest to system admins:

>   The local administrator account and Guest account is by default disabled on
>   CL1 but you want to restrict the use by applying the following settings:

>   Renaming the administrator account

>   Disabling the guest account

>   Blocking Microsoft accounts

>   Prohibiting access to the Control Panel and PC settings

>   Denying access to all removable media drives

Check settings before GPO is applied.
-------------------------------------

To check default Windows settings ,do the following:

1.  Start CL1, logon with administrator and Pa55w.rd

2.  Right click Windows button and choose Computer Management.

3.  Click “Local Users and Groups, then Users and see that the Administrator
    account is named Administrator.

4.  Check to see if you can get access to Settings from the Start Menu and
    Control Panel by searching in the Start Menu. Both should work.

Disabling the guest account and rename administrator
----------------------------------------------------

>   To rename the guest account using the GPO in Windows Server 2019, complete
>   the following steps:

1.  Sign in to DC1 virtual maching.

2.  From tools menu in server manager select and open “Active Directory Users
    and Computers”.

3.  Right-click Myorg.local domain and create a new ou called Client computers

4.  Right-click on CL1 computer object in the computers folder and select
    **move** to move cl1 to the new OU you have just created.

5.  Close “Active Directory Users and Computers” tool

6.  Select tools on the menun bar in the server manager and open “Group Policy
    Management” tool.

7.  Right-click the new **Client computers** OU an select “**create a GPO in
    this domain and link it here…**” and name it “Client Restrictions”.

8.  Right-click Client Restrictions GPO and select Edit. Navigate to the
    following path to reach the GPO setting: **Computer
    Configuration\\Policies\\Windows Settings\\Security Settings\\Local
    Policies\\Security Options**

9.  Double click at **Accounts: Guest account status**

10. In the *Properties* dialog box, check the box for **Define this policy
    setting**, and select Disabled.

11. Click **OK** to close the *Properties* dialog box

12. Double click at **Accounts: Rename Administrator account**

13. In the *Properties* dialog box, check the box for **Define this policy
    setting**, and type in **Admin** as the new administrator name.

14. Click **OK** to close the *Properties* dialog box

>   This policy is being applied to computer configuration settings. For
>   security reasons, to minimize the chance of misusing the guest account, you
>   may want to change the name of the guest account. So let us block the
>   Microsoft account using the GPO.

Blocking the Microsoft accounts
-------------------------------

>   To block the Microsoft accounts using the GPO in Windows Server 2019,
>   complete the following steps:

1.  Navigate to the following path to reach the GPO: **Computer
    Configuration\\Policies\\Windows Settings\\Security Settings\\Local
    Policies\\Security Options**

2.  Double click at **Accounts: Block Microsoft accounts**

3.  In the *Properties* dialog box, check the box for **Define this policy
    setting**, and then select **Users can't add or log on with Microsoft
    accounts** from the dropdown combo list.

4.  Click **OK** to close the *Properties* dialog box

>   This policy is being applied to user configuration settings.

>   For security reasons, to prevent users from adding and login into
>   organization's computers with their Microsoft accounts, system administrator
>   have the option of blocking the usage of Microsoft accounts. So let us deny
>   access to the Control Panel and PC settings using the

>   GPO.

Prohibiting access to the Control Panel and PC settings
-------------------------------------------------------

>   To prohibit access to the Control Panel and PC settings using the GPO in
>   Windows Server 2019, complete the following steps:

1.  Navigate to the following path to reach the GPO: **User
    Configuration\\Policies\\AdministrativeTemplates\\Control Panel**

2.  Double click at **Prohibit access to the Control Panel and PC settings**

3.  In the dialog box, select the **Enable** option, and then click **OK** to
    close the dialog box

>   This policy is being applied to users configuration settings.

>   If you wish that users in your organization's network would not be able to
>   make changes to their computers, then you can deny their access to the
>   Control Panel and PC settings. So let us learn to deny access to all
>   removable media drives.

Denying access to all removable storage classes
-----------------------------------------------

>   To deny access to all removable storage classes using the GPO in Windows
>   Server 2019, complete the following steps:

1.  Navigate the following path to reach the GPO settings: **User
    Configuration\\Policies\\AdministrativeTemplates\\System\\Removable Storage
    Access**

2.  Double click at **All the removable storage classes: Deny all access**

3.  In the dialog box, select the **Enable** option, and then click **OK** to
    close the dialog box

>   This policy is being applied to users configuration settings.

Check settings after GPO is applied.
------------------------------------

To check default Windows settings ,do the following:

1.  Restart CL1, logon with administrator and Pa55w.rd

2.  Right click Windows button and choose Computer Management.

3.  Click “Local Users and Groups, then Users and see that the Guest account is
    named the new name that you applied earlier, and that the Administrator
    account is named the new name that you applied earlier.

4.  Check to see if you can get access to Settings from the Start Menu and
    Control Panel by searching in the Start Menu. Both should not work.

>   System administrators have the ability to completely restrict the use of
>   removable storage by enabling Prohibiting access to the Control Panel and PC
>   settings. These were examples of configuring GPOs from many that are
>   supported by Windows Server 2019. Although only a few, these GPOs are
>   important as they highlight some of the most commonly used GPOs in a
>   production environment. With this we have come to an end of the chapter
>   exercise.
