!SLIDE

# The Basics #

!SLIDE

# Cloning an existing repository #

!SLIDE commandline incremental

    $ git clone git@github.com:jivesoftware/jiverscripts.git
    Cloning into jiverscripts...
    remote: Counting objects: 399, done.
    remote: Compressing objects: 100% (351/351), done.
    remote: Total 399 (delta 163), reused 162 (delta 26)
    Receiving objects: 100% (399/399), 968.16 KiB | 154 KiB/s, done.
    Resolving deltas: 100% (163/163), done.

!SLIDE

# Creating a new repository #

!SLIDE commandline incremental

    $ mkdir gitpreso

    $ cd gitpreso

    $ git init
    Initialized empty Git repository in ~/gitpreso/.git/

    $ git status
    # On branch master
    #
    # Initial commit
    #
    nothing to commit (create/copy files & use "git add" to track)
