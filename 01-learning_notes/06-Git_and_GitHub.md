<h1 align="center">
    <strong>Version Control (Git & Github)</strong>
</h1>
<h3 align="center">
    <i>____by Maung Pauk</i>
</h3>

As a data engineer, you will create pipelines, write code, and work with files that change over time, and for doing this you will be using version controlling system like git. So this reading material will help you to give a fair idea of what git is, why do you need it and explore some basic commands of git.

## Let’s start with what is Git, and why is it needed? 

Git is a version control system (VCS), which is essentially a tool for tracking file changes over time. Consider it a timeline or history log for your work. Imagine you're working on a long document or a project; Git allows you to preserve different versions of your files at different points in time. This way, you can always return to an older version if something fails or if you want to see what changed. 

Git is very useful for teams. When numerous individuals work on the same codebase, it makes it easier to track who modified what, when, and how to combine those changes without losing anything. 

## Now that we know what git is let’s understand **what is a Git repository**?

A repository, commonly known as "repo," is a folder or project that Git tracks. Git keeps track of all file changes in this repository, as well as logs, branches, and commits. Consider it a snapshot diary for your project: every save or checkpoint (known as a "commit" in Git) is noted. 

Now let's get into the actual Git commands. We'll divide them into logical groupings, beginning with initial setup and local workflow commands, progressing to branching, and finally working with remote repositories. 

## Getting started with Git: Initial setup and local workflow
Let's imagine you're launching a new project. The first command you will probably use is: 
```git
git init
```

This command converts the current folder into a Git repository. It creates a hidden .git folder to keep track of anything you do from here. 

## Setting name and email
Next, it's a good idea to tell Git who you are by setting your name and email. This matters because Git uses this info to label your commits.

Here's how you do it:

```git
git config --global user.name "YourName"
git config --global user.email "you@example.com"
```

Once you set this, Git will remember it for all your projects going forward.

If you're working on an existing project hosted elsewhere—for example, on GitHub—you can bring it into your system using: 

```git
git clone https://github.com/username/project.git
```

Here the “**https://github.com/username/project.git**” is your git repository URL or in simple words, this is where your project work is on github.

This git clone command downloads the entire project, including the commit history, to a folder on your machine. 

Let’s assume you've made changes to certain files. You will want to verify the current status of your project using: 

```git
git status 
```

This displays which files have been updated, which are staged (ready to be committed), and which remain untracked. 

To add modifications to the staging area and prepare them for commit, use: 

```git
git add filename
```


You may also add everything with git add., which will stage all updated files. 

Once your changes have been staged, you can generate a commit using: 

```git
git commit -m "added new feature" 
```

This commit works as a snapshot. Git saves your modifications with a message that explains what you did. 

To view the history of commits made thus far, use: 

```git
git log 
```

You'll see a list of commits, each with a unique ID, timestamp, author, and message. This is your project's timeline. 

### Working With Branches 

Branches allow you to work on different features or fixes separately without affecting your main code. You can create a new branch using: 

```git
git branch:new-feature
```

This creates a new branch but does not switch to it immediately. To actually get to that branch, use: 

```git
git checkout new-feature
```

You will be then working in the new-feature branch. Changes made here will not affect your main branch (commonly referred to as main or master) or any other branch unless you explicitly merge them. 

Merge your feature branch back into main: 
In order to merge your branches together first you will switch to that branch where you want to merge your other branch and then perform the follwing

```git
git checkout main     --- this will switch you to your main branch
git merge new-feature --- this will merge the feature branch with the main branch
```

If everything goes smoothly, Git will integrate the changes automatically. If there are conflicting modifications, you must reconcile them manually. This scenario where conflicts occur is known as merge conflict. 

Once the branch has been merged and you no longer require it, you can delete it using: 

```git
git branch -d new-feature   ---- here new-feature is our branch name
```

This helps to keep your branch list tidy. 

Working with remote repositories 
To interact with others or simply backup your project online, you must connect your local repository to a remote one. To accomplish this, use: 

```git
git remote add origin https://github.com/username/project.git
```

Now, your local Git knows where to submit and receive changes. To verify the remote, you can use the command: 

```git
git remote -v
```

To push your local commits to the remote repository: 

```git
git push origin main   ----- to push a branch other than main just replace your branch name with “main” present in this command
```

This updates the remote repo's main branch with your most recent changes. 

To download fresh changes from the remote repository onto your local system, use: 

```git
git pull
```

Other useful Git commands
Sometimes you want to temporarily save your modifications before committing them. Perhaps you're switching to or just looking into a different branch. This is where git stash comes in. 

```git
git stash 
```

This makes sure that your unfinished work does not appear in any branch and stays hidden.

Later, when you're ready to resume your work you can use the command: 

```git
git stash pop 
```

This reapplies the changes to your working directory brining your file back from the hiding. 

Now, to receive the most recent changes from the remote without merging automatically, use: 

```git
git fetch 
```

This updates your local knowledge of the distant repository but has no effect on your current files until you merge it. 

Finally, if you want to know what specifically changed between two versions or what has changed in your working directory, use: 

```git
git diff 
```

This displays a line-by-line comparison, showing additions and deletions. 

These essential commands are more than adequate for what you'll be expected to know, whether in an exam or in real-world situations. 

Each command we've covered has a specific function: from initializing your project to staging and committing changes, managing branches, and syncing with remote repositories, they all provide you complete control over your version history and collaboration workflow.

**[↑ Up](/README.md)** | **[← Previous](05-python_essentials_for_de.md)** | **[Next →](07-docker.md)**