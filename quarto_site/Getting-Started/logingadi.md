---
title: "Login to Gadi"
---

Access to Gadi is via SSH to gadi.nci.org.au. This provides a Unix shell on one of the Gadi login nodes.

For security reasons we ask that you avoid setting up passwordless ssh to Gadi. Entering your password every time you login is more secure, or using specialised ssh secure agents.

# Connecting from Linux/Mac/Unix

Open a Terminal application and use the following commands:
```bash
 ssh [your-6-character-username]@gadi.nci.org.au
```
The username is assigned when you created your NCI account and used for all HPC system accesses.  

Note: Do not use these login nodes to run long jobs or jobs with big computational requirements.   

# Connecting from Windows
The hostname for SSH connections to Gadi is gadi.nci.org.au. Your username is provided when you created your NCI account. You can check it via Mancini at https://my.nci.org.au/.

Windows does not provide an SSH client by default. We recommend:

MobaXterm from http://mobaxterm.mobatek.net
PuTTY from http://www.chiark.greenend.org.uk/~sgtatham/putty/
With MobaXterm on Windows system, create a new SSH session by clicking on `Session` tab or `Sessions` menu item on the top-left corner. Use `gadi.nci.org.au` as `Remote host` and NCI username as `Specify username`. Then log in with the new SSH session.  

Note: We advise that you make yourself familiar with the Linux operating system and the use of command line before continue using Gadi.  

# Recomended learning: [Introduction to the Unix Shell](https://swcarpentry.github.io/shell-novice/ )  

