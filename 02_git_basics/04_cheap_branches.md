!SLIDE

# Cheap branches #
## Local, fast, disposable ##

!SLIDE

# Create a branch #

!SLIDE commandline incremental

    $ git checkout -b crazy_idea
    Switched to a new branch 'crazy_idea'

    $ echo "puts 'super fast code'" > super_fast.rb
    
    $ git add super_fast.rb
    
    $ git commit -m 'super fast refactor'
    [crazy_idea 95e5afc] super fast refactor
     1 files changed, 1 insertions(+), 0 deletions(-)
     create mode 100644 super_fast.rb

!SLIDE

# OMG! Urgent fix needed to production! #

!SLIDE commandline incremental

    $ git checkout master -b hotfix
    Switched to a new branch 'hotfix'
    
    $ echo "Fix issue." >> README.txt # pretend!
    
    $ git commit -m 'fix issue'
    [hotfix 0e1a30a] fix issue
     1 files changed, 1 insertions(+), 0 deletions(-)

    $ git checkout master
    Switched to branch 'master'

    $ git merge hotfix
    Updating 7b443d8..0e1a30a
    Fast-forward
     README.txt |    1 +
     1 files changed, 1 insertions(+), 0 deletions(-)
    
    $ git branch -d hotfix
    Deleted branch hotfix (was 0e1a30a).
    
    $ git push
    ...

!SLIDE

# Continue with that crazy idea... #

!SLIDE commandline incremental

    $ git checkout crazy_idea
    Switched to branch 'crazy_idea'
    
    $ # lets merge in that hotfix

    $ git rebase master
    First, rewinding head to replay your work on top of it...
    Applying: super fast refactor
    
    $ # we decide it works, passes tests, etc.. lets merge it in

    $ git checkout master
    
    $ git merge crazy_idea
    Updating 0e1a30a..9a81c6c
    Fast-forward
     super_fast.rb |    1 +
     1 files changed, 1 insertions(+), 0 deletions(-)
     create mode 100644 super_fast.rb
    
    $ git branch -d crazy_idea
    Deleted branch crazy_idea (was 9a81c6c).

!SLIDE bullets incremental

# Just a sample... #

* since they're fast and local, you use them more
* good practice - a branch per feature and/or JIRA issue
* easy multitasking and context switching

