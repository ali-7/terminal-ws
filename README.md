# Terminal Workshop

<!-- ## What is Terminal? -->
<h2 style="color: #b33939">
What is Terminal?
</h2>

The terminal is an application provides a command-line-interface<span style='color: #c7254e'> (CLI)</span> which you can type commands and lets you interact with the computer, Everything you can do in the <span style='color: #c7254e'> File Explorer (GUI) for an exapmle</span> you can do in <span style='color: #c7254e'> CLI</span>.
It takes commands and shows the output.

Sometimes you will need to use the terminal to accomplish your tasks by entering text commands into the computer directly which helps you to work faster, easier and give you more flexibility

**_Hint:_** The Terminal interface can seem daunting at first, with a bit of practice, you'll be up to speed in no time!

![](https://i.imgur.com/gay1Gvl.png)

<!-- ## what is shell? -->
<h2 style="color: #b33939">
what is shell?
</h2>

The shell is the program which actually processes commands and returns output. Most shells also manage foreground and background processes, command history and command line editing. These features (and many more) are standard in <span style='color: #c7254e'> bash</span>, the most common shell in modern <span style='color: #c7254e'> linux</span> systems.

And the **terminal** refers to a **wrapper** program which runs a **shell**.

---

<!-- ## How Terminal is Structured? -->
<h2 style="color: #b33939">
How Terminal is Structured?
</h2>

In Terminal, all files and folders begin at the root directory. The root directory is noted by a <span style='color: #c7254e'>/</span>.

Inside the root directory are essential files/folders that your machine needs, but we do not modify the files and folders in the root directory often. Inside of the root directory, we have a folder called <span style='color: #c7254e'>home</span> which contains all of the user accounts on your computer.
If you move into the directory for your user account, you will be in the <span style='color: #c7254e'>home</span> directory, which is denoted by <span style='color: #c7254e'>~</span>.
For example, if my user name on the computer is <span style='color: #c7254e'>ali</span>, then your home directory would be <span style='color: #c7254e'>/home/ali</span>. A synonym for the <span style='color: #c7254e'>/home/ali</span> path is <span style='color: #c7254e'>~</span> when you are logged in as <span style='color: #c7254e'>ali</span>.

---

## Common Commands:

<!-- ### 1- Move to a specific folder: -->
<h3 style="color: #b33939">
1- Move To A Specific Folder:
</h3>

The first thing you want to start to understand when using Terminal is how to navigate from folder to folder.

![directory-structure](https://user-images.githubusercontent.com/36124895/95195443-34cec680-07df-11eb-980c-640d91b71076.jpg)

One of the most common commands you will be using in Terminal is <span style='color: #c7254e'>cd</span> which is short for **_"change directory"_**.

The <span style='color: #c7254e'>cd</span> command is used to change the current directory.

In order to change a directory, type <span style='color: #c7254e'>cd</span> followed by the directory or a path to the directory:

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

**_Absolute Paths <span style='color: #c7254e'>VS</span> Relative Paths_**

A path is simply the way to reach a file or folder, it's like an address for the file or folder you're trying to reach.

When we specify a path starting from the **root directory** <span style='color: #c7254e'> / </span>, we call that an absolute path.

For example, if I am **currently** in the <span style='color: #c7254e'> ~ </span> home directory and I would like to change directories into my **Desktop** folder, I can do that in two of the following ways:

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

<!-- ### 2- Creating Files And Folders: -->
<h3 style="color: #b33939">
2- Creating Files And Folders: 
</h3>

Now that we know how to use the <span style='color: #c7254e'>cd</span> command and navigate in Terminal, let's see how we can create folders and files.

To create a folder we use the <span style='color: #c7254e'>mkdir</span> command which is short for
**_"make directory"_**.

In order to create a folder, type <span style='color: #c7254e'>mkdir</span> followed by the name of the folder that you would like to create:

```bash
mkdir folder_name
```

this folder will be created in your current directory.

**_Notes:_**

- This command can create multiple directories at once (space-separated names).

```bash
mkdir first_folder second_folder
```

- If you want to put a space in your folder name, use a <span style='color: #c7254e'> \ </span> before the space, This tells the terminal to include the space as part of the name instead of a separator.

- Preferred to use one-word names or underscores or dash instead of spaces, it keeps things kinda simple.

**_Now,_** after we created our first folder, let's create a new file inside it.

To create a file we use the <span style='color: #c7254e'>touch</span> command.

In order to create a file, type <span style='color: #c7254e'>touch</span> followed by the name of the file that you would like to create, but don't forget: before you create your file you need to change your directory to your folder that you want to create inside it:

```bash
cd FOLDER_NAME
touch FILE_NAME
```

<!-- ### 2- Moving Files And Folders: -->
<h3 style="color: #b33939">
3- Moving Files And Folders: 
</h3>

Now that you understand how to create files <span style='color: #c7254e'>touch</span> and folders <span style='color: #c7254e'>mkdir</span>, let's move onto another essential operation: moving and copying folders.

To move files and folders we use the <span style='color: #c7254e'>mv</span> command which is short for **_"move"_**.

Let's move the file we created in the previous lesson into the second folder
make sure you are inside the folder that has the file you created.

```bash
cd PATH_TO_ORIGINAL_FOLDER
mv FILE_NAME PATH_TO_NEW_FOLDER
```

Did it work? You shouldn't see any kind of success message or confirmation from Terminal, but you also should not see an error. This is very common when working with Terminal: you will see error messages if a command is incorrect, but very rarely see a success message. In other words, no news is good news. In this case, to make sure we did the correct thing, let's cd into NEW_FOLDER path and type in `ls`. We should see the file we moved.

<!-- ### 4- Listing Files and Flags: -->
<h3 style="color: #b33939">
4- Listing Files and Flags: 
</h3>

Sometimes when you be inside a directory you ask your self, **_What’s around me?_**
You may have forgotten the folders or you don't know what are the folders and files inside your directory, so, you need to use the <span style='color: #c7254e'> ls </span> command.

To show list the contents of a directory or directories we use the <span style='color: #c7254e'> ls </span> command which is short for **_"list"_**.

```bash
ls
```

**_Note:_** To show the contents of a directory pass the directory name to the ls command.

```bash
ls first_folder/second_folder
```

**_Flags:_**
Sometimes the default ls command does not give us all the information we want. In such cases, we'll need to add some **flags** (options) to get more details.

- To show list all contents (that includes the hidden files) of a directory we use the<span style='color: #c7254e'> -a </span> flag after the <span style='color: #c7254e'> ls </span> command which is short for **_"all"_**.

```bash
ls -a
```

- To show list the contents with information about the contents of a directory we use the<span style='color: #c7254e'> -l </span> flag after the <span style='color: #c7254e'> ls </span> command which is short for **_"long list"_**.

```bash
ls -l
```

- To show list the contents with information about the contents of a directory (that includes the hidden files)we use the<span style='color: #c7254e'> -la </span> flag after the <span style='color: #c7254e'> ls </span> command.

```bash
ls -la
```

<h3 style="color: #b33939">
5- Copying Files And Folders: 
</h3>

Sometimes you may want to make a copy of a file or a folder.
To copy a <span style="border-bottom: 2px solid black;">file</span>, we use the <span style='color: #c7254e'>cp</span> command which is short for **_"copy"_**.

```bash
cp PATH_TO_ORIGINAL_FILE PATH_TO_COPIED_FILE
```

In order to copy a <span style="border-bottom: 2px solid black;">folder</span>, you need to add <span style='color: #c7254e'>-r</span> flag as follows:

```bash
cp -r PATH_TO_ORIGINAL_FOLDER PATH_TO_COPIED_FOLDER
```

To learn more about the **flags** that you can pass to <span style='color: #c7254e'>cp</span>, you can type <span style='color: #c7254e'>man cp</span> (<span style='color: #c7254e'>man</span> is short for manual, use the arrow keys to move up and down. When you're finished, press <span style='color: #c7254e'>q</span> to quit.

<h3 style="color: #b33939">
6- Open files: 
</h3>

If you would like to open up a file, you can use the <span style='color: #c7254e'>xdg-open</span> command.

```bash
xdg-open PATH_TO_FILE_TO_OPEN
```
