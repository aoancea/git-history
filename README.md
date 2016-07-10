# git-history

## Introduction and purpose
This repository tries to explain and show at the same time how you can **move** and/or **split** a *file* under **GIT** and still keep all the **history**.

These actions are very common in projects where following certain guidelines requires to move things arround but at the same time keep all the history.

Examples are presented using Visual Studio 2015 IDE and Git CLI

## Abstract
 * [Move a file](#move-a-file)
 * Move a file and edit it at the same time
 * Split a file

## Move a file
Moving a file is quite easy and there are two methods to accomplish it:

#### Copy-Paste the file from *Source* to *Destination*(works also with drag-and-drop)
Pre drag-and-drop

![Pre drag-and-drop](https://raw.githubusercontent.com/aoancea/git-history/master/assets/move-a-file-pre-drag-and-drop.PNG)

Post drag-and-drop

![Pre drag-and-drop](https://raw.githubusercontent.com/aoancea/git-history/master/assets/move-a-file-post-drag-and-drop.PNG)
   
   
   
#### Run the following command
>git mv *source_file* *destination_file*
