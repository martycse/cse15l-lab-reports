# Lab Report 1 - Remote Access and FileSystem (Week 1)
So that's 9 total examples (3 for each command). For each of the 9 examples, include:

A screenshot or Markdown code block showing the command and its output.
What the absolute path to the working directory was right before the command was run.
A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
Indicate explicitly whether the output is an error or not, and if it's an error, explain why it's an error in one or two sentences. Note: Make sure to use backticks ` around keywords such as commands, file names, paths, etc. to make them show up as code like cd.
## CD - no arguments

**Result**

<img width="498" alt="Screenshot 2024-04-03 at 3 08 37 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/99317668-5110-462f-bac7-da391d5abc0a">


*Running the command `cd` on it's own with no argument caused a switch to the `home` directory which goes by the alias, `~`.*

## CD - Directory

**Result**

<img width="498" alt="Screenshot 2024-04-03 at 3 08 57 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/33c8c066-7bd8-42b0-9134-02b96461180a">

*Running the command `cd` with a directory argument resulted in a switch to the directory given which in this case was `/workspaces`*

## CD - File

**Result**

<img width="505" alt="Screenshot 2024-04-03 at 3 10 17 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/57b5935d-5789-479e-b94b-952ee8646eb1">

*Running the command `cd` with a file argument resuled in an error stating `bash: cd: Hello.java: not a directory`. The error happened because the cd command is used for switching to a designated directory and Hello.java is a file.*

## LS - No Arguments

**Result**

<img width="505" alt="Screenshot 2024-04-03 at 3 10 36 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/db6bb4cd-292f-41a0-80ed-54ba4803de19">


## LS - Directory

**Result**

<img width="505" alt="Screenshot 2024-04-03 at 3 11 16 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/96485e30-c4cd-4c13-aa02-42192012e4a5">


## LS - File

**Result**

<img width="505" alt="Screenshot 2024-04-03 at 3 11 47 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/1e063b84-3bbc-4cef-8116-129106c602ce">

## Cat - No arguments

**Result**

<img width="505" alt="Screenshot 2024-04-03 at 3 12 12 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/a636b315-dc84-41ff-8757-a944814255cb">


## Cat - Directoy

**Result**

<img width="505" alt="Screenshot 2024-04-03 at 3 13 07 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/326d7583-53ef-4afd-bd2d-5daa95360418">

## Cat - File

**Result**

<img width="600" alt="Screenshot 2024-04-03 at 3 13 28 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/cc0c9401-a545-4dce-9472-ad01564e069c">



