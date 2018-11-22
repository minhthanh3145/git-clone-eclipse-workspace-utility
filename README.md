# Git clone & Eclipse Workspace utility
A utility to clone from Git into a new branch, creating a new Eclipse workspace and importing existing projects into this workspace

## Motivation
I find the work of cloning a repo into a new branch, then creating an Eclipse workspace and launch Eclipse with the workspace extremely repetitive, therefore in my spare time I wrote this batch file.

## Prerequisites
Windows 10 + Eclipse + a github repo.
Follow [this StakOverflow answer](https://stackoverflow.com/questions/44446216/eclipse-jdt-import-project-from-command-line) to use headless import Eclipse.

## What does this program do 
It takes 3 arguments:
- **@arg1** Name of the folder containing the new branch
- **@arg2** Name of the new branch
- **@arg3** Base branch to checkout the new branch from

It creates folder **@arg1** if not exists. Then it clones the repository into folder **@arg1**, fetching and pulling **@arg3**. It checkout or creates and checkout **@arg2** if not exists from **@arg3**. It also creates a new Eclipse workspace folder **@arg1** and imports existing projects into this workspace. Finally it launches Eclipse with this workspace. 

Here I separate between Eclipse workspace and the branch folder, since you won't want to commit Eclipse configuration files, but even that can be configured. Here I take care of some tricky processes like checking if a branch exists, and importing existing projects into Eclipse from command line. You should visit [this StackOverflow answer](https://stackoverflow.com/questions/44446216/eclipse-jdt-import-project-from-command-line) in order to do headless import easily. 

I also have a referenced folder of the repository I am working on. Basically I cloned the repository once and use it as a reference. This is because cloning from a folder is somewhat faster than cloning from git, especially if the project is big. However, you can still choose to clone directly if you so wish. There are many things you can twitch to suit your purpose.

## How to use 
Opening command line in the folder containing utility.bat, type: 
```
start utility @arg1 @arg2 @arg3
```
