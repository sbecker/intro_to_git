!SLIDE

# Local Commands #

!SLIDE

# Tracking new files #

!SLIDE commandline incremental

    $ echo "This is a demo." > README
    $ echo "puts 'Hi Jivers'" > say_hi.rb

    $ git status
    # On branch master
    #
    # Initial commit
    #
    # Untracked files:
    #   (use "git add <file>..." to include in commit)
    #
    #       README
    #       say_hi.rb
    nothing added to commit but untracked files present 
    (use "git add" to track)

!SLIDE commandline incremental

    $ git add README

    $ git status
    # On branch master
    #
    # Initial commit
    #
    # Changes to be committed:
    #   (use "git rm --cached <file>..." to unstage)
    #
    #       new file:   README
    #
    # Untracked files:
    #   (use "git add <file>..." to include in commit)
    #
    #       say_hi.rb
    

!SLIDE commandline incremental

    $ git add say_hi.rb

    $ git status
    # On branch master
    #
    # Initial commit
    #
    # Changes to be committed:
    #   (use "git rm --cached <file>..." to unstage)
    #
    #       new file:   README
    #       new file:   say_hi.rb
    #

!SLIDE commandline incremental

    $ git commit -m 'initial commit'
    [master (root-commit) 3c85a9a] initial commit
     2 files changed, 2 insertions(+), 0 deletions(-)
     create mode 100644 README
     create mode 100644 say_hi.rb

    $ git status
    # On branch master
    nothing to commit (working directory clean)

!SLIDE

# Stage modified files #

!SLIDE commandline incremental

    $ echo "Another line." >> README

    $ git status
    # On branch master
    # Changes not staged for commit:
    #   (use "git add <file>..." to update what will be committed)
    #   (use "git checkout -- <file>..." to discard changes in working directory)
    #
    #       modified:   README
    #
    no changes added to commit (use "git add" and/or "git commit -a")

!SLIDE commandline incremental

    $ git add README
    $ git status
    # On branch master
    # Changes to be committed:
    #   (use "git reset HEAD <file>..." to unstage)
    #
    #       modified:   README
    #

    $ echo "Yet another line." >> README
    $ git status
    # On branch master
    # Changes to be committed:
    #   (use "git reset HEAD <file>..." to unstage)
    #
    #       modified:   README
    #
    # Changes not staged for commit:
    #   (use "git add <file>..." to update what will be committed)
    #   (use "git checkout -- <file>..." to discard changes in working directory)
    #
    #       modified:   README
    #

!SLIDE bullets incremental

# What the heck?! #

* 1: Modified README
* 2: Staged README for commit
* 3: Modified README again, before commit
* Git tracks changes, not files. "git add" took a snapshot of README as it was at the time.

!SLIDE

# Skipping the Staging Area #

!SLIDE commandline incremental

    $ echo "And another new line." >> README

    $ git commit -am 'add and commit in one'
    [master af695bc] add and commit in one
     1 files changed, 3 insertions(+), 0 deletions(-)

!SLIDE

# Ignoring files #

!SLIDE commandline incremental

    $ touch tmp.txt
    $ git status
    # On branch master
    # Untracked files:
    #   (use "git add <file>..." to include in commit)
    #
    #       tmp.txt
    nothing added to commit but untracked files present
    
    $ echo "tmp.txt" > .gitignore
    $ git status
    # On branch master
    # Untracked files:
    #   (use "git add <file>..." to include in commit)
    #
    #       .gitignore
    nothing added to commit but untracked files present

    $ git add .gitignore
    $ git commit -m 'ignore tmp.txt'

!SLIDE

# Viewing Logs #

!SLIDE commandline incremental

    $ git log
    commit be4a5769174d9b085c804a3695c486dd5931f43a
    Author: Scott Becker <scott.becker@jivesoftware.com>
    Date:   Thu Feb 24 22:03:38 2011 -0800

        ignore tmp.txt

    commit af695bce42aa0791190cee6e5524d97cd78a6f8f
    Author: Scott Becker <scott.becker@jivesoftware.com>
    Date:   Thu Feb 24 21:54:18 2011 -0800

        add and commit in one

    commit 3c85a9a386de5aec0593367c9a461fc2c933cf7f
    Author: Scott Becker <scott.becker@jivesoftware.com>
    Date:   Thu Feb 24 16:56:24 2011 -0800

        initial commit

!SLIDE

# Moving/Renaming Files #

!SLIDE commandline incremental

    $ git mv README README.txt

    $ git status
    # On branch master
    # Changes to be committed:
    #   (use "git reset HEAD <file>..." to unstage)
    #
    #       renamed:    README -> README.txt
    #

    $ git commit -m 'renamed README to README.txt'
    [master ca2e364] renamed README to README.txt
     1 files changed, 0 insertions(+), 0 deletions(-)
     rename README => README.txt (100%)

!SLIDE

# Removing files #

!SLIDE commandline incremental

    $ git rm say_hi.rb
    rm 'say_hi.rb'
    
    $ git status
    # On branch master
    # Changes to be committed:
    #   (use "git reset HEAD <file>..." to unstage)
    #
    #       deleted:    say_hi.rb
    #
    
    $ git commit -m 'removed say_hi.rb'
    [master d5f291b] removed say_hi.rb
     1 files changed, 0 insertions(+), 1 deletions(-)
     delete mode 100644 say_hi.rb
