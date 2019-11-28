# Git compact

## Archive branch local and remote
  
	git tag archive/%BRANCHNAME% %BRANCHNAME%
	git branch -D %BRANCHNAME%
	git branch -d -r origin/%BRANCHNAME%
	git push --tags
	git push origin :%BRANCHNAME%

## Rename branch local and remote

	git branch %NEW_BRANCHNAME% origin/%OLD_BRANCHNAME%
	git push origin --set-upstream %NEW_BRANCHNAME%
	git branch -D %OLD_BRANCHNAME%
	git branch -d -r origin/%OLD_BRANCHNAME%
	git push origin :%OLD_BRANCHNAME%

	
## CSV of all remote branches with last commit date

	git branch -r --format="%%(refname:short);%%(authordate:short)" > "lastcommits.csv"