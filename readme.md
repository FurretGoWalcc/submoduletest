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
 
