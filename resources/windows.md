# Windows Help & Notes

## CRLF Warning 

This is GitBash telling you that git is helping.  Windows uses two characters for a new line `CR` (cariage return) and `LF` (line feed).
Classic Mac Operating system used the `CR` character.  Unix-like systems (including MacOS X) use only the `LF` character. 
If you try to open a file on Windows that has only `LF` characters, Windows will think it's all one line. To help you, 
since git knows people collaborate across file systems, when you check out files from the git database (`.git/` directory)
git replaces `LF` characters with `CRLF` before updating your working directory. 

When working on Windows, when you make a file locally, each new line will have `CRLF` in it. If your collaborator
(or server, eg GitHub) runs not a unix or linux based operating system (it almost certainly does) these extra 
characters will make a mess and make the system interpret your code wrong. To help you out, 
git will automatically, for Windows users, convert `CRLF` to `LF` when it adds
your work to the index (staging area). Then when you push, it's the compatible version. 

[git documentation of the feature](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration#Formatting-and-Whitespace) 


## Jupyter Book - Command Not Found After Installation

1. **Check Python Installation**:  
   Run `python --version`. If it shows a version, continue. If not, install Python.

2. **Install Jupyter Book**:  
   Ensure Jupyter Book is installed using `pip install -U jupyter-book`. If `jupyter-book --version` returns "command not found," proceed.

3. **Check Installation Errors**:  
   If there were no errors during installation, skip to Step 4.  
   If there were errors with a path (e.g., missing "Scripts" folder), do the following:
   - Press `Windows + R`, type `sysdm.cpl`, and press Enter.
   - Go to the **Advanced** tab → **Environment Variables**.
   - Add the path containing the "Scripts" folder to the `Path` variable. Save and exit.
   - Reopen Git Bash and try `jupyter-book --version`. If it works, you're done!  
   - If "Access denied" occurs, try `sudo jupyter-book --version`. Windows Defender may prompt you to unlock the file. After unlocking, try the command again.

4. **Check Path**:  
   Ensure the following path exists:
   ```
   C:\Users\[YOUR USERNAME]\AppData\Roaming\Python\Python312\Scripts
   ```
   If it does:
   - Repeat the steps for adding this path to the `Path` variable in **Environment Variables**.
   - Reopen Git Bash and check `jupyter-book --version` again.  

5. **Final Troubleshooting**:  
   If issues persist, contact your Professor or TA for help! :)
