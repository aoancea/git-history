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

#### The trick
 * The trick into preserving the history on both files is to create a new **branch**
 * We will have to move/edit the file in the newly created branch then merge it with the current one
 * This will create a conflict, but we will ***keep*** the new file from the new branch

*Create* ***'split-helper-v5'*** *branch*

![Create a new branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-create-new-branch.PNG)

*Rename and Move file on* ***'master'*** *branch*

![Rename and Move file on master branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-rename-and-move-file-on-master-branch.PNG)

*Switch to* ***'split-helper-v5'*** *branch*

![Switch to new branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-switch-to-new-branch.PNG)

*Rename and Move file on* ***'split-helper-v5'*** *branch*

![Rename and Move file on new branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-rename-and-move-file-on-new-branch.PNG)

*Switch to* ***'master'*** *branch*

![Switch to master branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-switch-to-master-branch.PNG)

*Open command prompt on* ***'master'*** *branch*

![Open command prompt on master branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-open-command-prompt.PNG)

*Run the merge command* - be aware that mergeing directly from Visual Studio 2015 does not give the same results
>git merge --no-ff split-helper-v5

![Switch to master branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-run-merge-in-git-cli.PNG)

*Merge conflicts*

![Merge conflicts](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-merge-conflicts.PNG)

*Merge conflicts detailed*

![Merge conflicts detailed](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-merge-conflicts-detailed.PNG)

*Keep file from* ***'master'*** *branch* - this will ensure history for the file on the 'master' branch

![Keep file from master branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-keep-file-from-master-branch.PNG)

*Keep file from* ***'split-helper-v5'*** *branch* - this will ensure history for the file on the new branch and thus accomplish the split

![Keep file from new branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-keep-file-from-new-branch.PNG)

*Leave deleted file from both branches* - we do not need the file from the place it was moved in neither of the two branches

![Keep file from new branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-leave-deleted-file-from-both-branches.PNG)

*Commit merge changes* - don't bother the ***[add]*** status of the file

![Keep file from new branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-commit-conflict-changes.PNG)

***'master'*** *branch file history*

![Keep file from new branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-master-branch-file-history.PNG)


***'split-helper-v5'*** *branch file history*

![Keep file from new branch](https://raw.githubusercontent.com/aoancea/git-history/master/assets/split-a-file-new-branch-file-history.PNG)

Completing these steps will make you end up with two files which have the same history

You will still have to move them in their right place, if you haven't in the above steps. For that, follow the instruction presented in [Move a file](#move-a-file)
