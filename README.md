# How-to-remove-sensetive-files-from-commit-history
This repo is about removing sensetive files from commit history even if you have delted that from your current commit.
This sensetive files might contain passwords or api keys etc.
To secure ourself from exposing our private data to others we can use bfg tool instead of git-filter.   
Note: For detailed information about how this works and why... please refer this : https://rtyley.github.io/bfg-repo-cleaner/


Steps to follow:
1)First of all clone your git repo and keep it as backup for safety reason.
2)For cloning current repo type command:
	git clone --mirror your-repo-link.git
3)Download bfg-any-version.jar file from https://rtyley.github.io/bfg-repo-cleaner/ .
4)navigate to your local repository through terminal.
5)rename file bfg-any-version.jar to bfg.jar(Optional).
6)Type command:
	java -jar bfg.jar --delete-files filename-to-be deleted  .git
7)Now navigate back to your cloned repo 
<br>
8)And type command :<br>
	git reflog expire --expire=now --all && git gc --prune=now --aggressive<br>
9)Now finally push:<br>
	git push or git push --all --force.<br>

	
	
