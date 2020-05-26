## Useful git commands 

#### Revert one file in the commit. 

First check the differences:

`git diff <commit_hash> <file_path>`

for example:

`git diff a1b2c3d45 src/java/MyClass.java`

then reset:

`git reset <commit_hash> <file_path>`

`git reset a1b2c3d45 src/java/MyClass.java`

This will add file being reset to git staging (from commit_hash), and old version (one being removed from commit) to working directory.
