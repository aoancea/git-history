# git-history

## Introduction and purpose
This repository tries to explain and show at the same time how you can **move** and/or **split** a *file* under **GIT** and still keep all the **history**.

These actions are very common in projects where following certain guidelines requires to move things arround but at the same time keep all the history.

Examples are presented using Visual Studio 2015 IDE and Git CLI

## Abstract
 * [Move a file](#move-a-file)
 * [Edit and move a file](#edit-and-move-a-file)
 * [Split a file](#split-a-file)

## Move a file
These steps are advised to be taken when you do not have to change anything in a file, just move it, but as you would see in the second part, [Edit and move a file](#edit-and-move-a-file) the outcome is identical.

Moving a file is quite easy and there are two methods to accomplish it:

#### Copy-Paste the file from *Source* to *Destination*(works also with drag-and-drop)
*Pre drag-and-drop*

![Pre drag-and-drop](https://raw.githubusercontent.com/aoancea/git-history/master/assets/move-a-file-pre-drag-and-drop.PNG)

*Post drag-and-drop*

![Pre drag-and-drop](https://raw.githubusercontent.com/aoancea/git-history/master/assets/move-a-file-post-drag-and-drop.PNG)

*Staged changes*

![Staged changes](https://raw.githubusercontent.com/aoancea/git-history/master/assets/move-a-file-staged-changes.PNG)

*History after check in*

![History after check in](https://raw.githubusercontent.com/aoancea/git-history/master/assets/move-a-file-history.PNG)  
   
#### Run git cli command
>git mv *source_file* *destination_file*

A good example  would be the following command that moves the file from ***Helpers*** to ***Filters*** folder as we did with drag-and-drop:
>git mv *Git.History.Web\****Helpers****\MovableSecurityHelperV5.cs* *Git.History.Web\****Filters****\MovableSecurityHelperV5.cs*

Running the following command will inform you of the movement changes
> git status

![Git status](https://raw.githubusercontent.com/aoancea/git-history/master/assets/move-a-file-git-status.PNG)

From this point, we can just commit and check the history of the moved file as described above

## Edit and move a file
All the steps described above apply here as well. The only addition to this part is the fact that editing the moved file will have the same result.

If you only have to move and edit a file, perform the steps described [above](#move-a-file) and also the additional edits you require.

## Split a file
Preserving the history of a file while moving/editing it is pretty easy as we already saw.
Splitting a file into two while preserving the history on the both ends it's a whole different adventure which I'll describe bellow.
