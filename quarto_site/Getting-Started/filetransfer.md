# File Transfer

File transfer should be done using Gadi's data-mover nodes (domain name 'gadi-dm.nci.org.au'), which are dedicated for moving data to and from the system at a high speed.  

| Operating System | Program  | Description                                                                                          |
|------------------|----------|------------------------------------------------------------------------------------------------------|
| Mac and Linux    | `rsync`    | A powerful tool for transferring large files, with the ability to compare source and destination and only send changes. |
| Mac and Linux    | `scp`      | A simple file transfer tool (secure copy).                                                           |
| Windows          | WinSCP   | A graphical interface for transferring files.                                                        |  

> Note: Transferring Code  
> The best way to transfer code from one computer to another is to host the code in a source code repository using a > versioning system such as git and clone the repository to the supercomputer. Recommended learning: [Version Control with Git](https://swcarpentry.github.io/git-novice/ )  

# SCP
## From local system →  Gadi 

To start a scp transfer through Gadi's data-mover nodes, you can run the command,
```bash
$ scp <source> <destination>
```
Notice that the domain is `gadi-dm.nci.org.au`, as you are logging into a data-mover node instead of a login node. 

Replace the filename with the file you wish to transfer, including the file extension e.g. .sh, .pdf, and use your username as the login. The destination should be replaced with location that you want the file to be placed in, like the following for an example: 
```bash
$ scp testfile.sh <user>@gadi-dm.nci.org.au:/scratch/<project dir>/<somewhere>/
```  

You will then be prompted for your password, once entered, your file transfer will begin. 

## From Gadi → local system

If you want to do the opposite, move a file from Gadi to your local system, you simply need to reverse the prompt to reflect this, like so
```bash
$ scp <user>@gadi-dm.nci.org.au:/scratch/<project dir>/<somewhere>/ ./
```

To find a listing of all the options available to you with scp, e.g. which option to use to transfer a folder/directory, use the command
```bash
$ man scp
```

# rsync
If you are transferring a larger file and want to add a layer of protection to the transfer, using rsync will give you the ability to resume a transfer that has been interrupted. As with SCP, reversing your pathways will change which direction the transfer is happening, either uploading from your local device or downloading from Gadi.  

rsync also allows greater control over the transfer and exactly what happens with the file by placing options into the command line, such as 
```bash
$ rsync -vP  testfile.sh <user>@gadi-dm.nci.org.au:/home/900/<user>
```
the `-vP` in the command line means that the output file will be verbose and preserve all of its attributes such as timestamps. -P is a great way to get an exact copy of your file.

To find a listing of all the options available to you with rsync, e.g. which option to use to transfer a folder/directory, use the command
```bash
$ man rsync
```
to print a list of all of the variables that you can use.  

```bash
-a, --archive    archive mode; equals -rlptgoD (no -H,-A,-X)
-v, --verbose               increase verbosity
-P                          same as --partial --progress
-x, --one-file-system       don't cross filesystem boundaries
-H, --hard-links            preserve hard links
-g, --group                 preserve group
--chmod=CHMOD           affect file and/or directory permissions
```
If something happens and your transfer doesn't complete, simply run the exact command again and the transfer will pick up where it left off.  

# Large transfers over 500 GiB
For large transfer, over 500 GiB for instance, it is better to submit the transfer as a job to the copyq queue. To read the process of how to achieve this, follow this [link](https://opus.nci.org.au/spaces/Help/pages/236880320/Job+Submission...).  
