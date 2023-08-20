<p align="center">
<img src="https://i.imgur.com/PazBqAN.png" alt="Linux file permissions"/>
</p>

<h1>Use Linux commands to manage file permissions</h1>

<h2>Project description</h2>

The research team at my organization needs to update the file permissions for certain files and
directories within the projects directory. The permissions do not currently reflect the level of
authorization that should be given. Checking and updating these permissions will help keep
their system secure. To complete this task, I performed the following tasks:


<h3>Check file and directory details</h3>

To check permissions set for files and subdirectories in the projects directory including hidden files, the command I would use inside that directory is: **ls -la** 
<br/><br/>
“ls” to list files and subdirectories with added option “-l” to check permissions and “-a” to include hidden files. 
<br/><br/>
<img src="https://i.imgur.com/TUSNKPp.png" alt="linux1"/>


<h3>Describe the permissions string</h3>

Each file or folder will have a 10-character string that conveys different information about these permissions. 1st character (d for directory – for a regular file). <br/>
The 2nd character is for read permissions for the user (r if user had read permissions, - if user lacks read permissions). <br/>
The 3rd character is for write permissions for the user (w if user had write permissions, - if user lacks write permissions).<br/>
The 4th character is for execute permissions for the user (x if user had execute permissions, - if user lacks execute permissions).<br/>
The 5th,6th,7th same as above three (read, write, execute) but this set pertains to permissions for the group.<br/>
The 8th, 9th, 10th characters also same as above (read, write, execute) but permissions for other. <br/>

For example take file name .project_x.txt. The preceding “.” Before project_x.txt denotes that this is a hidden file. Looking at the 10-character permission string (-rw--w----) we can see that since the 1st character is “-“ it is a regular file and not a directory. 
2nd,3rd,4th character indicates the USER has read and write permissions. 
5th,6th,7th character indicates the GROUP has only write permissions.
8th,9th,10th character indicates that OTHER has no permissions for this file.


<h3>Change file permissions</h3>

The organization does not allow other to have write access to any files. Based on the permissions established, identify which file needs to have its permissions modified. 
There are 3 files that need to modify permissions for other.
1.	Project_k.txt remove read and write for other.
2.	Project_r.txt remove read for other.
3.	Project_t.txt remove read for other
   
Commands to make this change is as follows: 

<img src="" alt="linux2"/>


<h3>Change file permissions on a hidden file</h3>

The research team has archived .project_x.txt, which is why it’s a hidden file. This file should not have write permissions for anyone, but the user and group should be able to read the file. Use a Linux command to assign .project_x.txt the appropriate authorization.

<img src="" alt="linux3"/>


<h3>Change directory permissions</h3>

The files and directories in the projects directory belong to the researcher2 user. Only researcher2 should be allowed to access the drafts directory and its contents. Use a Linux command to modify the permissions accordingly.

<img src="" alt="linux4"/>
