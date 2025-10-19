TL;DR: the first line of `.gitignore` should be:

```
.ignore/
```

## Problem

Imagine the following situation: You are working on a publish script for your repo. You're about to hard-code the password in the script (just temporarily, for testing purposes) but then you remember how bad it would be if that password was committed in Git and pushed where everyone can see it. You smartly put the password in `password.txt` and diligently add that file to .gitignore. Later you realize you need the user name as well, so you switch it to `secrets.json`.... now you have to add that to `.gitignore as well. Do you remove the .gitignore entry for secrets.txt? What if someone already has that file sitting on their machine and now you create the situation where it might get leaked. Better leave both the old name and the new name in .gitignore. This is just clutter.

## Solution

- Put `.ignore/` in every .gitignore file. This means that any directory with this name (anywhere in the repo) will be ignored by Git.
- Put temporary files, secrets, log files, etc. in `.ignore/`.


## Not Just Git

This recommendation applies regardless of your choice of source control.

