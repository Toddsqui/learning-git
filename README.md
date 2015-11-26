# Learning Git

Learning the Git commands in the command line.

##  GitHub !== Git
Git is a program which tracks every change you make in a git repository locally
(on your machine) saving it into the git internal database (the `.git` directory).
To use *git* you don't need GitHub:  it's not mandatory.

GitHub is a website hosting git repos providing you nice user interface and
workflows.

##  Creating a repo
The following command initializes a new repository in the current directory.

```sh
git init
```

This will create the `.git` directory in the current folder.

##  Getting the state of the repo

```sh
git status
```

##  Initial commit

Commits are like sending packages from a place to another place: for that you need to:

 1. Something to put in the package
 2. You need to put the things in the packgage
 3. Add the label (write what is in the package)
 4. Send the package.

This is the first commit in a repo.

```sh
# After doing `git init` and creating the README.md file
$ git status
On branch master

Initial commit

Untracked files:
	README.md

nothing added to commit but untracked files present
```

### Adding files (adding things in package)

So, you have something to put in the package (files!!!). To put them in the package, write `git add <filename1> <filname2> .. <filaname-n>`.

```sh
git add README.md
# to add all files
git add .
```

Let's check again the state of the repo:

```sh
$ git status
On branch master

Initial commit

Changes to be committed:
	new file:   README.md

```

###  Writing the commit message (adding the package label)
...so others can understand what it is in the package, without opening it.

```sh
git commit -m "Initial commit."
[master (root-commit) 4c06704] Initial commit.
 1 file changed, 31 insertions(+)
 create mode 100644 README.md
Macs-MacBook-2:learning-markdown macuser$ git status
On branch master
nothing to commit, working directory clean
```

### Add the remote url (destination address)
You need a destination. The destination is a remote url (e.g. a repo from GitHub). To create one, [click here](https://github.com/new)

```sh
git remote add origin git@github.com:Toddsqui/learning-markdown.git
```

###  Send the commit (send the package)
After having the package ready, we can send it!  :tada:

```sh
$ git push --all
Saving password to keychain failed
Identity added: /Users/macuser/.ssh/id_rsa (/Users/macuser/.ssh/id_rsa)
Counting objects: 3, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 569 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To git@github.com:Toddsqui/learning-markdown.git
 * [new branch]      master -> master
```

## Visualizing the git Commits

```sh
git log
```

##  Visualizing the file changes

Use `git diff`:

```sh
#  Use this before adding the files to be committed
git diff
# This will show the differences for added files
git diff --cached
```

Example:

```patch
diff --git i/README.md w/README.md
index b8d5eee..10acd94 100644
--- i/README.md
+++ w/README.md
@@ -59,28 +59,28 @@ Not modified line
 another not modified line

-deleted line
+added line
```
##  Using git branches and GitHub pull requests
Did you watch *Back to the future* movies? They explain perfectly how git
branches and GitHub  pull requests work. [Watch this!](https://www.youtube.com/watch?v=uHiLxKwaug0) :tv:

They are like parallel timelines where collaborators commit without being affected
by the other collaborators. When the feature branch is ready for merge, it is
merged in the main branch (usually master).

```
Main branch (master):  --*-- some stuff is committed here (by others) *----
                          \                                          /
Your feature branch:       *--- you start committing here ----------*
```

Follow the steps:

```sh
# create and switch on the new branch
git checkout -b my-branch

# edit something
# and commit
git add .
git commit -m '...'
git push

# Merge
# Switch on master
git checkout master

# Merge the feature branch into master
git merge my-branch

# Push the merge commit on GitHub
git push origin master

# Delete the branch
## ...locally (this will not delete the branch on GitHub)
git branch -d my-branch

# List branches -- This will show you all of the branches and which one you are on
git branch
```

### GitHub pull requests

It's a nice workflow on the top of the git merging by allowing collaborators to
visualize, review and merge the changes easily.

[Here](https://guides.github.com/introduction/flow/) you can find a nice visualization
of how GitHub PRs are working.

 1. After pushing the branch on GitHub, create a pull request.
 2. Let others review what you changed.
 3. You can use the GitHub UI or the command line to merge the pull request.

  /// TODO  Add git merge steps here
