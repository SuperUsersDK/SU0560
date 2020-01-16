>   **Workshop part 3 of 4**  
>   **Using Storage Migration Service on Server 2019**

>   In this Workshop, you will test functionality of Storage Migration Service.
>   Use SVR9 as your Orchestrator/Destination server.
>   Use SVR1 as your source server. Use Server Manager or Disk Management to take the offline disks online and create one or more volumes     on these.
>   Use FSUTIL on SVR1 to create files for testing, using the command: fsutil file createnew test1.txt 1000000.
>   Change the values for filename and size to your own values

Storage Migration Service
-------------------------

>   You are to make sure that one virtual member server is running as a file
>   server with shares, permissions and files. Configure another member server
>   as both destination and orchestrator server. Run everything through Windows
>   Admin Center. Test after migration that permissions on shares and file
>   system is correct on destination server.

>   When done – do **not** revert virtual machines to Checkpoint.

>   Inspiration on how to accomplish this can be found on:  
>   <https://docs.microsoft.com/en-us/windows-server/storage/storage-migration-service/overview>

>   <https://www.vembu.com/blog/storage-migration-service-windows-server-2019/>

>   <https://plusontech.com/2018/10/13/step-by-step-windows-server-2019-storage-migration-service/>

>   <https://github.com/MicrosoftDocs/windowsserverdocs/blob/master/WindowsServerDocs/storage/storage-migration-service/migrate-data.md>
