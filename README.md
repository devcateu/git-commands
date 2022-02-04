# git-commands

### Show 20 the most changed files in git
git log --pretty=format: --name-only | sort | uniq -c | sort -rg | head -20
We should skip conf files and other noise

### It is removing local branches, which does not have remote conterpartners
git fetch -p && for branch in $(git branch -vv | grep ': gone]' | awk '{print $1}'); do git branch -D $branch; done
