# Terminal Workshop

## What is Terminal?

The terminal is an application provides a command-line-interface`(CLI)` which you can type commands and lets you interact with the computer, Everything you can do in the `File Explorer (GUI) for an exapmle` you can do in `CLI`.
It takes commands and shows the output.

Sometimes you will need to use the terminal to accomplish your tasks by entering text commands into the computer directly which helps you to work faster, easier and give you more flexibility

**_Hint:_** The Terminal interface can seem daunting at first, with a bit of practice, you'll be up to speed in no time!

![](https://i.imgur.com/gay1Gvl.png)

## what is shell?

The shell is the program which actually processes commands and returns output. Most shells also manage foreground and background processes, command history and command line editing. These features (and many more) are standard in ` bash`, the most common shell in modern `linux` systems.

And the **terminal** refers to a **wrapper** program which runs a **shell**.

---

## How Terminal is Structured?

In Terminal, all files and folders begin at the root directory. The root directory is noted by a `/`.

Inside the root directory are essential files/folders that your machine needs, but we do not modify the files and folders in the root directory often. Inside of the root directory, we have a folder called `home` which contains all of the user accounts on your computer.
If you move into the directory for your user account, you will be in the `home` directory, which is denoted by `~`.
For example, if my user name on the computer is `ali`, then your home directory would be `/home/ali`. A synonym for the `/home/ali` path is `~` when you are logged in as `ali`.

---

## Common Commands:

### 1- Move To A Specific Folder:

The first thing you want to start to understand when using Terminal is how to navigate from folder to folder.

![directory-structure](https://user-images.githubusercontent.com/36124895/95195443-34cec680-07df-11eb-980c-640d91b71076.jpg)

One of the most common commands you will be using in Terminal is `cd` which is short for **_"change directory"_**.

The `cd` command is used to change the current directory.

In order to change a directory, type `cd` followed by the directory or a path to the directory:

1- if we want **to move into a directory** we specify the name of the directory we are moving into:

```bash
cd directory_name/
```

example:

```bash
cd Download/
```

in this example, your directory will move into the Download directory.

2- If you want **to move up a directory** you will use:

```bash
cd ..
```

3- If you want to go up to the home directory you will use:

```bash
cd
```

or

```bash
cd ~
```

**_Note:_** The path is relative to the current directory.
That means if you type `cd myfolder`, it will only work if the current directory you in has a folder called `myfolder`

**_Absolute Paths `VS` Relative Paths_**

A path is simply the way to reach a file or folder, it's like an address for the file or folder you're trying to reach.

When we specify a path starting from the **root directory** `/`, we call that an absolute path.

For example, if I am **currently** in the `~` home directory and I would like to change directories into my **Desktop** folder, I can do that in two of the following ways:

**1- Absolute Path:** starting from the root (first **/**, then **home**, then **ali**, then **Desktop**)

```bash
cd /home/ali/Desktop
```

**in your case**

```bash
cd /home/$USER/Desktop
```

**_Note:_** `$USER` is an environment variable in your shell that keeps track of the current user of the shell. You can know who is the current user by using the command `whoami`

**2- Relative path:** relative to where I am currently

```bash
cd Desktop
```

If you want to change your current directory to another directory, **not in the same folder** you will need to use the **absolute Path** for that folder or you need to go up levels to use the **relative paths**.

**How do you know which directory you are in if you forget or don't know?**
You can use a command called `pwd` (present working directory) which will display the **absolute path** and let you know what current directory you are working in. So if you are ever unsure, just type in `pwd`.

### 2- Creating Files And Folders:

Now that we know how to use the `cd` command and navigate in Terminal, let's see how we can create folders and files.

To create a folder we use the `mkdir` command which is short for
**_"make directory"_**.

In order to create a folder, type `mkdir` followed by the name of the folder that you would like to create:

```bash
mkdir FOLDER_NAME
```

this folder will be created in your current directory.

**_Notes:_**

- This command can create multiple directories at once (space-separated names).

```bash
mkdir FIRST_FOLDER SECOND_FOLDER
```

- If you want to put a space in your folder name, use a `\` before the space, This tells the terminal to include the space as part of the name instead of a separator.

- Preferred to use one-word names or underscores or dash instead of spaces, it keeps things kinda simple.

**_Now,_** after we created our first folder, let's create a new file inside it.

To create a file we use the `touch` command.

In order to create a file, type `touch` followed by the name of the file that you would like to create, but don't forget: before you create your file you need to change your directory to your folder that you want to create inside it:

```bash
cd FOLDER_NAME
touch FILE_NAME
```

### 3- Moving Files And Folders:

Now that you understand how to create files `touch` and folders `mkdir`, let's move onto another essential operation: moving and copying folders.

To move files and folders we use the `mv` command which is short for **_"move"_**.

Let's move the file we created in the previous lesson into the second folder
make sure you are inside the folder that has the file you created.

```bash
cd PATH_TO_ORIGINAL_FOLDER
mv FILE_NAME PATH_TO_NEW_FOLDER
```

Did it work? You shouldn't see any kind of success message or confirmation from Terminal, but you also should not see an error. This is very common when working with Terminal: you will see error messages if a command is incorrect, but very rarely see a success message. In other words, no news is good news. In this case, to make sure we did the correct thing, let's cd into NEW_FOLDER path and type in `ls`. We should see the file we moved.

<!-- ### 4- Listing Files and Flags: -->

### 4- Listing Files and Flags:

Sometimes when you be inside a directory you ask your self, **_What’s around me?_**
You may have forgotten the folders or you don't know what are the folders and files inside your directory, so, you need to use the `ls` command.

To show list the contents of a directory or directories we use the `ls` command which is short for **_"list"_**.

```bash
ls
```

**_Note:_** To show the contents of a directory pass the directory name to the ls command.

```bash
ls FIRST_FOLDER/SECOND_FOLDER
```

#### **_Flags:_**

Sometimes the default ls command does not give us all the information we want. In such cases, we'll need to add some **flags** (options) to get more details.

- To show list all contents (that includes the hidden files) of a directory we use the`-a` flag after the `ls` command which is short for **_"all"_**.

```bash
ls -a
```

- To show list the contents with information about the contents of a directory we use the`-l` flag after the `ls` command which is short for **_"long list"_**.

```bash
ls -l
```

- To show list the contents with information about the contents of a directory (that includes the hidden files)we use the`-la` flag after the `ls` command.

```bash
ls -la
```

### 5- Copying Files And Folders:

Sometimes you may want to make a copy of a file or a folder.
To copy a file, we use the `cp` command which is short for **_"copy"_**.

```bash
cp PATH_TO_ORIGINAL_FILE PATH_TO_COPIED_FILE
```

In order to copy a folder, you need to add `-r` flag as follows:

```bash
cp -r PATH_TO_ORIGINAL_FOLDER PATH_TO_COPIED_FOLDER
```

To learn more about the **flags** that you can pass to `cp`, you can type `man cp` (`man` is short for manual, use the arrow keys to move up and down. When you're finished, press `q` to quit.

### 6- Open files:

If you would like to open up a file, you can use the `xdg-open` command.

```bash
xdg-open PATH_TO_FILE_TO_OPEN
```

### 7- Displaying Contents Of A File:

`cat` command is used to print the contents of a file.

In order to see the content of a file, type `cat` followed by the name of the file that you would like to see the content for it:

```bash
cat FILE_NAME
```

**_Note:_** If your file was empty you will not get an output.

### 8- Removing/Deleting Files And Folders:

#### Before You Begin

**When removing a directory using a desktop file manager, the directory is actually moved to the Trash and can be easily recovered.**

**Be extra careful when removing files or directories from the command line because once the directory is deleted using the command it cannot be fully recovered.**

To remove or delete files and folders, we use the `rm` command which is short for **_"remove"_**.

**There is no confirmation or undo so be VERY careful when using the `rm` command.**

- To delete a single file

```bash
rm FILE_NAME
```

- To delete multiple files at once, use the `rm` command followed by the file names separated by space.

```bash
rm FILE_NAME1 FILE_NAME2 FILE_NAME3
```

- To remove directories and all the files within them, use the `rm` command with the `-r` (recursive) flag (option):

```bash
rm -r FOLDER_NAME
```

- If a directory or a file within the directory is write-protected, you will be prompted to confirm the deletion.

- To remove directories and all the files without being prompted, use `rm` with the `-r` (recursive) and `-f`:

```bash
rm -rf FOLDER_NAME
```

### 9- Moving Files to trash:

To move files or directories to the trash, use `gio trash` command.

```bash
gio trash FOLDER_NAME_OR_FILE_NAME
```

---

Now let's do some **exercises**
