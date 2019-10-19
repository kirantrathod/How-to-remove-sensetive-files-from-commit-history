# How-to-remove-sensetive-files-from-commit-history<br>
This repo is about removing sensetive files from commit history even if you have delted that from your current commit.<br>
This sensetive files might contain passwords or api keys etc.<br>
To secure ourself from exposing our private data to others we can use bfg tool instead of git-filter.  <br>
<br>
Note: For detailed information about how this works and why... please refer this : https://rtyley.github.io/bfg-repo-cleaner/ <br>


Steps to follow:<br>
1)First of all clone your git repo and keep it as backup for safety reason.<br>
2)For cloning current repo type command:<br>
	git clone --mirror your-repo-link.git<br>
3)Download bfg-any-version.jar file from https://rtyley.github.io/bfg-repo-cleaner/ .<br>
4)navigate to your local repository through terminal.<br>
5)rename file bfg-any-version.jar to bfg.jar(Optional).<br>
6)Type command:<br>
	java -jar bfg.jar --delete-files filename-to-be deleted  .git<br>
	Note: If you want to modify also the head, use parameter #--no-blob-protection<br>
7)Now navigate back to your cloned repo <br>
8)And type command :<br>
	git reflog expire --expire=now --all && git gc --prune=now --aggressive<br>
9)Now finally push:<br>
	git push or git push --all --force.<br>

	
	
