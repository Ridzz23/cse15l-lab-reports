# Lab Report 1

---

# `cd`

The `cd` command allows us to change the current working directory to a specific folder or path. This command is followed by the name of the folder which we would like to move into. 
<br>

![Image](cd_blank.png)
 > Since I have not provided any argument after `cd`, the current working directory does not change. The current working directory remains `/home`.
<br>

![Image](cd_folder.png)
> Here the `cd` command is followed by the path of the folder `lecture1/`. This is an acceptable argument. Therefore, the current working directory changes from `/home/` to `/home/lecture1/`.
<br>

![Image](cd_file.png)
> The `cd` command does not accept a file as an argument. Here I have provided `Hello.java` as the argument and therefore it has caused an error. Hence the current working directory does not change. The current working directory remains `/home/`.
<br>

---
# `ls`

The `ls` command is used to list out all the files and folders in the current working directory or given path. This command may or may not be followed by a path. 
<br>

![Image](ls_blank.png)
> Here the `ls` command is not followed by a path. So, the files and folders in the current working directory is printed. Here the current working directory is `/home/` which contains the `/lecture1/` folder. Therefore, `/lecture1/` is printed out.
<br>

![Image](ls_folder.png)
> Here the `ls` command is used with a path to the directory `lecture1/`. This is a valid argument. So, the files and folders which are within `lecture1/` are printed out.
<br>

![Image](ls_file.png)
> Since the `ls` command is used with a path to a file, it can not "list" the files or folders which are in the given path (as the file does not contain any files or folders). So, instead it just prints the path of the file as we have provided in the argument.
<br>

---

# `cat`

The `cat` command prints the contents of one or more files whose paths are provided. This command must be followed by one or more paths of specific files.
<br>

![Image](cat_blank.png)
> The `cat` command requires an argument. Since I did not provide an argument above, the `cat` command did not execute anything. Instead, it was waiting for an argument. This is because it can not read the contents of a file if there is no file path provided. I used Ctrl + C to forcefully terminate the running process.
<br>

![Image](cat_folder.png)
> The `cat` command does not work if we provide the path of a directory. This is because it can not read the contents of a folder. Instead, it errors out by stating that `lecture1/` is a directory.
<br>

![Image](cat_file.png)
> Here the `cat` command reads the contents of the file provided and prints it out.
<br>

![Image](cat_file2.png)
> This command can be used to read the contents of one or more files. In this case, I provided 2 file paths and the `cat` command read the contents of both files and printed them out in the same as I provided the paths.
<br>

