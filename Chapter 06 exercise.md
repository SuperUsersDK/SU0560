>   **Chapter 6 exercise – installing web server (IIS) and PDS roles**

>   In this chapter exercise, you will learn how to do the following:

>   How to install a web server (IIS) role

>   How to install a PDS role

Installing the web server (IIS) role
------------------------------------

>   To install the web server (IIS) role in Windows Server 2019, complete the
>   following steps:

1.  Log on to SVR1 with myorg\\administrator and Pa55w.rd.

2.  Click the **Start** button and then, in the **Start** menu, click on
    **Server Manager**.

3.  In the Server Manager window, click on the **Add roles and features**
    hyperlink.

4.  Shortly, the **Add Roles and Features Wizard** will open:

5.  Accept the **Role-based or feature-based installation** option and click the
    **Next** button.

6.  Ensure that the right server is highlighted from the server pool, then
    accept the **Select a server from the server pool** option and click
    **Next**.

7.  From the list of the roles, select the **Web Server (IIS)** role.

8.  Click the **Add Features** button when the **Add features that are required
    for Web Server (IIS)?** popup appears.

9.  If there is no feature required for adding the web server (IIS) role at this
    stage, so just click the **Next** button.

10. In the web server (IIS) definition and the things to note regarding web
    server (IIS) installation, click **Next** to proceed.

11. Either accept the web server (IIS) role services or customize them to your
    needs.

12. Confirm installation selections for the web server (IIS) role by clicking
    the **Install** button.

13. When installation progress reaches the end, click the **Close** button to
    close the *Add Roles and Features Wizard*.

14. A server restart is not required.

>   The web server (IIS) role will now get installed.

1.  Now try to access the default website from the client CL1.

2.  Sign in to CL1 and open Edge browser.

3.  Type HTTP://SVR1.myorg.local

Installing a PDS role
---------------------

>   To install a PDS role in Windows Server 2019, complete the following steps:

1.  Log on to SVR2 with myorg\\administrator and Pa55w.rd if not signed in.

2.  Click the **Start** button and then, in the **Start** menu, click on
    **Server Manager**.

3.  In the Server Manager window, click on the **Add roles and features**
    hyperlink.

4.  Shortly, the **Add Roles and Features Wizard** will open.

5.  Accept the **Role-based or feature-based installation** option and click the
    **Next** button.

6.  Ensure that the right server is highlighted from the server pool, and then
    accept the **Select a server from the server pool** option and click
    **Next**:

7.  From the list of the roles, select the **Print and Document Services** role.

8.  Click the **Add Features** button when the **Add features that are required
    for Print and Document Services?** dialog pops up.

9.  There is no feature required for adding PDS role at this stage, so just
    click the **Next** button.

10. In the PDS definition and the things to note regarding PDS installation,
    click **Next** to proceed.

11. Either accept the PDS role services or customize it to your needs.

12. Confirm the installation selections for the PDS role by clicking the
    **Install** button.

13. When installation progress reaches the end, click the **Close** button to
    close the **Add Roles and Features Wizard**.

14. A server restart is not required.

-   The PDS role will now get installed.

1.  Shutdown SVR1 and SVR2 after this exercise.
