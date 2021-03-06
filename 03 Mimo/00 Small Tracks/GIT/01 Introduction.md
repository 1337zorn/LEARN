# Git Introduction
Hey, in this course, we'll dive into Git, a system for tracking changes in files and coordinating work in teams.

    $ git init

        Initialized empty Git repository in ////.git/

While Git is very popular for software projects, we can use it to keep track of changes in any file.
But what exactly did we just do?

We've just created a repository, which is a special directory, that imports our work to Git.
Every project we want to track needs such a repository.

    $ mkdir project
    $ cd project
    $ git init
    
        Initialized empty Git repository in /Users/user/project/.git/

Psst: Repositories are also reffered to as repos.

Sweet! With git init, we can turn an ordinary directory into a repository and start tracking changes.
-
Up until now, we haven't made any changes to our repository, have we?
In order to confirm that, let's check it's status!

    $ git status

        on Branch master
        Initial commit
        nothing to commig (create/copy files and use "git add" to track)

Psst: when there arent any files with changes in the working directory, we say that the directory is clean.

Every Git starts withthe git command. Don't worry about branches for now. 
All we need to know is that we're working on the master branch!
-
It's time to make some changes. Let's create a text file an check the status of the repository again!

    $ touch cookie.txt
    $ git status

        On branch master
        Initial commit
        Untracked files:
            cookie.txt
        nothing added to commit but untracked files present
        (use "git add" to track)

Right there! The git status command reveals that cookie.txt is currently untracked.

Now, in order to keep track of cookie.txt we need to add it to the list of tracked files.

    $ git add cookie.txt
    $ git add status

        On branch master
        Initial commitChanges to be commited:
        new file: cookie.txt

Perfect! When we add a file to the list of tracked files using git add, we're said to stage it.

Lets add something to cookie.txt so we can see what happens to it's status!

    $ echo Hello world > cookie.txt
    $ git status

        On branch masterInitial commit
        Changes to be committed:
            new file: cookie.txt
        Changes not staged for commit:
            modified: cookie.txt
        Hello world!

Sweet! Cookie.txt is still tracked but now it's not staged anymore because its content has changed.
We need to use git add to stage it again.

Sometimes we want to stage multiple files. While it would take a while to do this file by file, there is a great shortcut.

    $ touch cookie.txt
    $ touch cake.txt
    $ git add .
    $ git status

        On branch master
        Changes to be commited:
            new file: cookie.txt
            new file: cake.txt

Nice! Using gitt add with . we can add all the unstaged files in the current directory(and deeper),
making this a great way to add multiple files.

When we run git add, Git captures a snapshot of the changes that we can make permanent by commiting them to the repos.

    $ git commit -m "Add cookie and cake"
        [master (root-commit) cf010b1] Add cookie and cake
        2 files changed, 1 insertion(+)
            create mode 100644 cookie.txt
            create mode 100655 cake.txt

Thats it! After the -m, we can provide a commit message, which is useful to keep note of our commits.

As we've seen, there's a workflow that we almost always follow when we work with Git.

    Make changes in the working directory
    Use git add to stage them
    Use git commit to save the changes to repository

Sweet! We make changes in the working directory, stage them files we want to commit in the stageing area, and make them permanent by committing them.

If you're on macOS, you can get Git along with the Xcode Command Line Tools.

You can run $ xcode-select --install or try to run git from the Terminal; if you don’t have it, you'll be prompted to install it.

Great! After installing the Xcode Command Line Tools, we're all set to run git from the Terminal.

Git is a version control system that tracks changes and helps us coordinate work in teams.

A repository, or repo, is a special type of directory that keeps track of the files within it.

Depending on the actual status of a repository, git status cann tell us:
    if our working directory is clean
    what files are tracked but not staged
    what files are untracked
    what files are staged and ready to be committed

We use git add with the file's name to stage it and git commit -m followed by a commit message to commit it.
