!SLIDE

# Subversion Integration #

!SLIDE

# Use Git locally, Subversion upstream! #

!SLIDE commandline incremental

    $ git svn clone http://svn.jiveland.com/svn/repos/jaf/apps
    Initialized empty Git repository in /Users/scott.becker/Archive/Development/gitsvn/apps/.git/
    W: Ignoring error from SVN, path probably does not exist: (160013): Filesystem has no item: '/svn/repos/!svn/bc/100/jaf/apps' path not found
    W: Do not be alarmed at the above message git-svn is just searching aggressively for old history.
    This may take a while on large repositories
    W: Ignoring error from SVN, path probably does not exist: (160013): Filesystem has no item: '/svn/repos/!svn/bc/100/jaf/apps' path not found
    W: Do not be alarmed at the above message git-svn is just searching aggressively for old history.
    This may take a while on large repositories
    r115752 = e0f1fbfe772264fdba470170256a97ba0cda347b (refs/remotes/git-svn)
    	A	README
    W: +empty_dir: demo
    W: +empty_dir: example
    W: +empty_dir: test
    r115755 = c2af7679d48033febec49a9192830f78b7b2041b (refs/remotes/git-svn)
    	A	test/openclient-js/test_gadget_feature.xml
    	A	example/openclient-js/microblogs.xml
    ...

!SLIDE commandline incremental smaller

    $ cd apps/

    $ git log
    commit e056e56329f235d91d1305299b0fdd63d58ee6ac
    Author: author.name <author.name@c71dbd84-28fa-0310-abbe-db3d66cda40d>
    Date:   Tue Feb 22 22:49:24 2011 +0000

        Made a change to foo.

        git-svn-id: http://svn.jiveland.com/svn/repos/jaf/apps@139257 c71dbd84-28fa-0310-abbe-db3d66cda40d

    commit 19e95b883b532fb1ca1e77d54e0d47b6158cab91
    Author: author.name <author.name@c71dbd84-28fa-0310-abbe-db3d66cda40d>
    Date:   Tue Feb 22 01:43:14 2011 +0000

        Made a change to bar.

        git-svn-id: http://svn.jiveland.com/svn/repos/jaf/apps@139172 c71dbd84-28fa-0310-abbe-db3d66cda40d

!SLIDE

# Commit locally, push to SVN repo #

!SLIDE

    $ vi README
    ...updated README file...
    
    $ git commit -am 'updated README'
    [master 62e6ea0] updated README
     1 files changed, 1 insertions(+), 0 deletions(-)
    
    $ git svn dcommit
    Committing to http://svn.jiveland.com/svn/repos/jaf/apps ...
    	M	README
    Committed r139636
    	M	README
    r139636 = 6cbe2cfc5d1d38e78f735ee26e67b3ef51aff379 (refs/remotes/git-svn)
    No changes between current HEAD and refs/remotes/git-svn
    Resetting to the latest refs/remotes/git-svn

!SLIDE

# Pulling in changes from SVN #

!SLIDE commandline incremental

    $ ...made another change to README elsewhere
    
    $ ...switch back to git-svn repo and pull in changes

    $ git svn rebase
    	M	README
    r139638 = 11d9b1cbf27bb4807d743e93d13e987a3eefc79f (refs/remotes/git-svn)
    First, rewinding head to replay your work on top of it...
    Fast-forwarded master to refs/remotes/git-svn.

