# Useful Git Commands

## View git history for greping

`git log --format="%h (%an, %cs): %s"`

## Git delete local branch that is not "online" anymore

```
git branch -d <branch-name>
git fetch origin --prune
```

## Git show only files that changed on previous commit

```
git show --pretty="" --name-only
```

## Git remove tag (local+remote)                                                                                                                    
```                                                                             
# create                                                                        
git tag -a v1.0.2 -m "My new version!"                                          
                                                                                
# delete everywhere                                                             
git tag -d v1.0.2                                                               
git push origin :refs/tags/v1.0.2                                               
```

## Git no pass or username

First, [add an ssh-key to your github account](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account).

Then, open the file `.git/config` in your repo and change the `[remote "origin"]` url to:
```
url = git+ssh://git@github.com/<USERNAME>/<REPONAME>.git
```

Otherwise, if you want to just **not type the username** change the line:

`url = https://github.com/<USERNAME>/<REPONAME>.git`, to:  
`url = https://<USERNAME>@github.com/<USERNAME>/<REPONAME>.git`

