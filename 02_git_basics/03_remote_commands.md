!SLIDE

# Remote Repositories #

!SLIDE smaller

# Jiverscripts on Github... #

    $ git clone git@github.com:jivesoftware/jiverscripts.git

!SLIDE

# Showing Your Remotes #


!SLIDE commandline incremental

    $ cd jiverscripts/
    
    $ git remote
    origin

    $ git remote -v
    origin	git@github.com:jivesoftware/jiverscripts.git (fetch)
    origin	git@github.com:jivesoftware/jiverscripts.git (push)

!SLIDE

# Adding a remote to existing repo #

!SLIDE commandline incremental

    $ cd gitpreso

    $ git remote add origin git@github.com:sbecker/gitpreso.git

    $ git push -u origin master
    Counting objects: 14, done.
    Delta compression using up to 2 threads.
    Compressing objects: 100% (11/11), done.
    Writing objects: 100% (14/14), 1.23 KiB, done.
    Total 14 (delta 2), reused 0 (delta 0)
    To git@github.com:sbecker/gitpreso.git
     * [new branch]      master -> master
    Branch master set up to track remote branch master 
     from origin.

!SLIDE

# Pushing to remotes #

!SLIDE commandline incremental

    $ echo "So very fine." >> README.txt 
    
    $ git commit -am 'Added another line to readme.'
    [master 7b443d8] Added another line to readme.
     1 files changed, 1 insertions(+), 0 deletions(-)

    $ git push origin master
    Counting objects: 5, done.
    Delta compression using up to 2 threads.
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 337 bytes, done.
    Total 3 (delta 1), reused 0 (delta 0)
    To git@github.com:sbecker/gitpreso.git
       d5f291b..7b443d8  master -> master

!SLIDE

# Pulling from remotes #

!SLIDE commandline incremental

    $ git pull
    remote: Counting objects: 5, done.
    remote: Compressing objects: 100% (3/3), done.
    remote: Total 3 (delta 1), reused 0 (delta 0)
    Unpacking objects: 100% (3/3), done.
    From github.com:sbecker/gitpreso
       d5f291b..7b443d8  master     -> origin/master
    Updating d5f291b..7b443d8
    Fast-forward
     README.txt |    1 +
     1 files changed, 1 insertions(+), 0 deletions(-)
