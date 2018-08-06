---
layout: post
title:      "May the --force be with you"
date:       2018-08-06 02:07:04 +0000
permalink:  may_the_--force_be_with_you
---


I'm taking a break for the NodeJS series I had planned this week for a quick post about Github. I've been switching between working on different projects and this week I had a minor scare. I went to check on my repository to find out that all my commits were gone. In what used to be one project's repository sat another project. To my memory, I remember force pushing at a some point. What do I do now?

After a thirty second panic session, I remembered that Github always tracks all commits so there should be an easy fix to that. Enter reflog -

> Reflog is a mechanism to record when the tip of branches are updated. This command is to manage the information recorded in it. Basically every action you perform inside of Git where data is stored, you can find it inside of the reflog.

git reflog // find the commit ID that I wanted to revert the status back to
git reset --hard ID // enter the ID here
git push -f origin master // force push it back to master on github

Just like that I got all my past 40+ commits back. That'll teach me to jump between projects and to use force carelessly.  

I figured this week would be a good time to review some Git commands. 

1. git init // Initialize a local Git repository
2. git clone [insert source link here] // Create a local copy of a remote repository
3. git add . // Add all files changes in your working directory to your index
4. git rm [insert filename] // Remove files from your index and your working directory so they will not be tracked
5. git status // Show the status of files in the index versus the working directory
6. git branch -a // List all branches
7. git branch [insert name here] // Create new branch with name
8. git commit -m "enter message here" // Create a new commit object pointing changes made
9. git push origin --delete [insert branch name here] //	Delete a remote branch
10. git checkout -b [insert branch name]	// Create a new branch and switch to it
11. git merge [insert source branch name] [insert target branch name] // Merge a branch into a target branch
12. git push -u origin [branch name] //	Push changes to remote repository 
13. git pull origin [insert branch name] //	Pull changes from remote repository
14. git log	// View changes

These are the commands that I use more regularly but of course there are a bunch more commands out there that are used. [Here's](https://www.youtube.com/watch?v=Y2Msq90ZknI) a video for a better understanding of what goes on in Git. 
