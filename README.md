# Project description
The focus of this project is to analyse existing file system permissions and ensure they align with the required authorizations. If they do not, the permissions should be adjusted to grant access to authorized users and remove any unauthorized access.

## Check file and directory details
You can use the “ls” command to display names of files and directories in the current working directory. Adding the “-la” option will show detailed permissions and include hidden files.
![image](https://github.com/L0rdB43lish/Changing-file-permissions-on-Linux/blob/784297f0a147229c5eb23ba39b31eb827802aa64/Captura%20de%20tela%202024-12-19%20003227.png)

## Describe the permissions string
Let’s take the “project_k.txt” (-rw-rw-rw-) file and analyse its permissions.
- The first character is a “-”, which means it’s a file. 
- The next three characters (rw-) show that the owner of the file, reseacher2, has permission to read (r) and write (w) the file but not execute it. 
- The following three characters (rw-) indicate that members of the group “research_team” can also read and write the file but cannot execute it.
- The final three characters (r--) reveal that other users on the system can only read the file and cannot write to or execute it. 
- The presence of a (-) in the executable position across all three groups confirms that the file is not executable.

## Change file permissions
The organization does not allow others to have write (w) access to any files. Identify which file needs to have its permissions modified. 
The only file that requires modification is “project_k.txt” because its permissions include write (w) access for others, as indicated by the last three characters (rw-).
![image](https://github.com/L0rdB43lish/Changing-file-permissions-on-Linux/blob/784297f0a147229c5eb23ba39b31eb827802aa64/Captura%20de%20tela%202024-12-19%20010657.png)

I used the “chmod” command to remove write (w) permission for the other group on the “project_k.txt” file.

## Change file permissions on a hidden file
The hidden file “.project_x.txt” should not have write permissions for anyone, but the user and group should be able to read the file. 
![image](https://github.com/L0rdB43lish/Changing-file-permissions-on-Linux/blob/784297f0a147229c5eb23ba39b31eb827802aa64/Captura%20de%20tela%202024-12-19%20011614.png)

I used the “chmod” command to remove write (w) permissions from the user and other groups, and to add read (r) permission for the other group.

## Change directory permissions
The files and directories in the projects directory belong to the researcher2 user. Only researcher2 should be allowed to access the drafts directory and its contents. Use a Linux command to modify the permissions accordingly. 
![image](https://github.com/L0rdB43lish/Changing-file-permissions-on-Linux/blob/784297f0a147229c5eb23ba39b31eb827802aa64/Captura%20de%20tela%202024-12-19%20152707.png)

By running the “ls -la” command, we can observe that the group has execute (x) permission on the drafts directory. I used the “chmod” command to remove the execute (x) permission from the group for the drafts directory, leaving the other permissions intact for the owner of the directory.

## Summary
The file and directory permissions presented in this project were analysed and modified to align with the required adjustments, ensuring that authorized users have the necessary access while removing access for the unauthorized users.
