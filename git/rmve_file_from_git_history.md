# How to erase files in commit history that contain sensitive information

	git filter-branch --force \
	--index-filter 'git rm --cached --ignore-unmatch path/to/file.txt' \
	--prune-empty \
	--tag-name-filter cat -- \
	--all

**git filter-branch is a Git command that lets you modify the commit history of a repository.**


	--force 
is used to ensure that Git runs the command even if it detects potential issues.



	--index-filter 
is a flag that specifies the filter to apply to the index of the repository. In this case, it is used to remove the file path/to/file.txt from the index.



	'git rm --cached --ignore-unmatch path/to/file'
removes the specified file from the Git index, but keeps it in the file system.


	--prune-empty 
removes any empty commits that might be left after the filter operation.



	--tag-name-filter cat 
updates any tags that might point to filtered commits.



	-- --all 
specifies that the filter should be applied to all branches and tags in the repository.



Ultimately this command removes the file functional/creds.txt from the Git index, which will also remove it from the repository's 
commit history. It then cleans up any empty commits and updates any tags that might point to filtered commits.


**After this run:** 

	git push --force origin main
	
to push the changes that were made.
