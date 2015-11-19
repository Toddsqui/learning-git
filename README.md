# Learning Git

Learning the Git commands in the command line.

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
