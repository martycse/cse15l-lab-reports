# Lab Report 1 - Remote Access and FileSystem (Week 1)

## `CD` - no arguments

**Result:**
*Running the command `cd` on it's own with `no argument` caused a switch to the `home` directory which goes by the alias, `~`. This is because running the command on its own without an explicit directory, automatically switches to the home directory `(~)`. The output given is not an error as it performs the command properly*

<img width="498" alt="Screenshot 2024-04-03 at 3 08 37 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/99317668-5110-462f-bac7-da391d5abc0a">

## `CD` - Directory

**Result:**
*Running the command `cd` with a `directory argument` resulted in a switch to the directory given which in this case was `/workspaces`. The reason for this output is because I gave the command `cd` an explicit directory. The output given is not an error as it performs the command properly and switches to the provided directory `/workspaces`*

<img width="498" alt="Screenshot 2024-04-03 at 3 08 57 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/33c8c066-7bd8-42b0-9134-02b96461180a">

## `CD` - File

**Result:**
*Running the command `cd` with a `file argument` resuled in an error stating `bash: cd: Hello.java: not a directory`. The error/output happened because the cd command is used for switching to a designated directory and `Hello.java` is a file.*

<img width="505" alt="Screenshot 2024-04-03 at 3 10 17 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/57b5935d-5789-479e-b94b-952ee8646eb1">

## `LS` - No Arguments

**Result:**
*Running the command `ls` with `no arguments` resulted in all the files and folders being diplayed. The reason for this output was because LS was ran with no speccific argument, therefore it displayed all the files and folders. There is no error because the terminal displays the correct files*

<img width="505" alt="Screenshot 2024-04-03 at 3 10 36 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/db6bb4cd-292f-41a0-80ed-54ba4803de19">


## `LS` - Directory

**Result:**
*Running the command `ls` with a `directory argument`, in this case `/workspaces` results in the folder within the directory to be displayed which is, `lecture1`. The command doesn't produce an error since it displays the contents of `/workspaces` in the terminal which is what `ls` is meant to do*

<img width="505" alt="Screenshot 2024-04-03 at 3 11 16 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/96485e30-c4cd-4c13-aa02-42192012e4a5">


## `LS` - File

**Result:**
*Running the command `ls` with a `file argument`, in this case `Hello.java` results in only `Hello.java` being displayed again in the `terminal`. This is because `Hello.java` does not hold any folders or files within it. This is not an error and the command does what its intended*

<img width="492" alt="Screenshot 2024-04-03 at 4 25 07 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/45e10a2d-c6e5-4a74-b251-4be7010940ca">

## `Cat` - No arguments

**Result:**
*Running the `cat` command with `no arguments` results in nothing and displays and empty terminal after the command. The `cat` command could not find an element to concatenate and display its elements therefore the `terminal` remains in the default state. This is not an error since nothing was given to `cat`*

<img width="505" alt="Screenshot 2024-04-03 at 3 12 12 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/a636b315-dc84-41ff-8757-a944814255cb">


## `Cat` - Directory

**Result:**
*Running the `cat` command with a `directory argument`, in this case `/workspaces/lecture1`, results in an error. The error states `cat: /workspaces/lecture1: Is a directory`. This is because the `cat` command is meant to receive a `path` and `print` it's contents.*

<img width="505" alt="Screenshot 2024-04-03 at 3 13 07 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/326d7583-53ef-4afd-bd2d-5daa95360418">

## `Cat` - File

**Result:**
*Running the `cat` command with a `file argument`, in this case `Hello.java`, results in it's contents being printed. This is not an error because cat is meant to do this and it succesfully diplays the contents of `Hello.java`.*

<img width="597" alt="Screenshot 2024-04-03 at 3 46 52 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/5c3ceaca-333f-45cb-ae89-f40b1cddfbe6">


