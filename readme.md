1. git submodule add (url) (destination directory)
2. git pull (if submodule was added from another machine)
3. git submodule init (pull submodule code)
(OR if cloning the repo for the first time, use
git clone --recursive-submodules
git pull --recursive-submodules
Since each git submodule is essentially another git repository, you should 
4. git submodule update (--init)(--recursive)
Alias to make pulling everything easier
git config --global alias.clone-all 'clone --recursive-submodules'
git config --global alias.pull-all 'pull --recursive-submodules'

From gitsubmodules man page:

           WORKFLOW FOR AN ARTIFICIALLY SPLIT REPO

           # Enable recursion for relevant commands, such that
           # regular commands recurse into submodules by default
           git config --global submodule.recurse true

           # Unlike most other commands below, clone still needs
           # its own recurse flag:
           git clone --recurse <URL> <directory>
           cd <directory>

           # Get to know the code:
           git grep foo
           git ls-files --recurse-submodules

           Note
           git ls-files also requires its own --recurse-submodules flag.

           # Get new code
           git fetch
           git pull --rebase

           # Change worktree
           git checkout
           git reset
           
           #God tier commands, don't tell the admin you know these
           git submodule update --remote --rebase --recursive
           

