# Git notes
*********************************
1. To know difference between 2 commit  : git diff commit1..commit2
                       or 
	git diff HEAD..HEAD~1   [diff b/w current and on2 before]
                       or 
	git diff HEAD~1..
	git diff HEAD~1 HEAD~2
	
	git diff - to find difference between working area and index(Staging)
	git diff --cached  - to find difference between index area(Staging) and repository	

Comparing two branches 
	git diff branch1 branch2 


2. To un-stage a file from staged area
	git rm —cached filename
	git reset HEAD filename
		

3. Reset
    git reset HEAD filename    -> unstage file , it basically move file from  repo to staging area.
	git reset —-hard commitId  -> Reset HEAD to commitId.Working area and staging area also points to this HEAD 
	                              i.e. working area and stagin area files will get reset with repository file.
	git reset --soft commitId  -> Reset HEAD to commitId but it will keep changes in staging and working area.
	git reset --mixed commitId -> Reset HEAD to commitId but staging area also points to repository, ie unstaging data.
                                      and workarea will have data   
4. Stash  - When you dont want to stage and commit changes but still want save the changes then use it 
			git stash   --> will stash changes so that it won't be part of any commit.
			git stash list --> to see all stashed changes 
			git stash apply --> apply stashed data to working area.
			git stash clear --> clear stash.

5. Git checkout HEAD filename -> to hard reset a single file to work area and staging from repository.

6. History
     git log --graph --decorate --oneline    -> Command to see git commit as tree.
	 git show commitId  -> to see changes in the commit
	 git show HEAD~1  -> see changes of one commit before HEAD
	 git show HEAD~2  -> to see second last commit details.

	 git blame filename to see all changes in the file since it is crated.

7. Amend a commit 
	git commit --amend  -> If you want to add changes to last commit.

8. Interactive rebase 
	If you want to change commit history of an older commit then intereactive rebase 
	step 1 : Fix the issue , stage it and commit it
	Step 2 : run this command git rebase -i origin/master
	Step 3 : It will open a text editor 
	Step 5 : Re arrange pick , if you want to change existing commit message use reword command 
	         Use squash command to merge two commits 
	Step 6 : exit and save 
	Step 7 : Done.

8. git reflog -> to see all user actions in the repo.

9. git revert commitId  -> to revert a commit.

10. git cherry-pick to get a commit from another branch, it will basially rebase project 
     instead of this you can create a  new branch and merge it to release branch and develop branch 


 Useful links
 http://nvie.com/posts/a-successful-git-branching-model/
 

	