### That thing where you get asked about username and pwd all the time
git remote set-url origin git@github.com:username/repo.git

### Pull changes from a forked repo
git remote add upstream https://github.com/xxx/yyy.git
git fetch upstream
git merge upstream/master 
