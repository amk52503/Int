# Int
cd Desktop

	Enter the outer Experiment4 folder
Open the folder created during Experiment 4.
cd Experiment4

	Enter the cloned repository
Open the repository cloned inside the outer folder.
cd Experiment4



	Verify the repository folder
Display the current path and hidden files.
pwd
ls -a

Expected result: You should see the .git directory and README.md.
PART 2 – CHECK THE CURRENT BRANCH AND REMOTE

	Check the current branch
git branch

	Check the repository status
Make sure there are no uncommitted changes before continuing.
git status
Expected result: Ideally, Git reports a clean working tree. If changes are present, save or commit them before proceeding.

	Check the remote URL
Confirm that origin points to the correct GitHub repository.
git remote -v
Expected result: The output should show origin URLs for fetch and push.

	Switch to main if necessary
If you are not already on main, switch to it. If your branch is master, use git switch master.
git switch main

	Update local main before the demonstration
Bring the local main branch up to date before creating the demonstration commit.
git pull origin main

PART 3 – CREATE A LOCAL COMMIT ON THE SAME MAIN BRANCH

	Create a sample file
		notepad local-notes.txt

	Stage the file
git add local-notes.txt

	Commit the local change
git commit -m "Add local notes for Experiment 5"

	View the local commit
Display the latest commits.
git log --oneline	
PART 4 – CREATE A NEW REMOTE COMMIT ON GITHUB
	Open GitHub
Open https://github.com/, sign in, and open the same Experiment4 repository.


	Edit README.md on GitHub
Use the edit option for README.md and add the following line:
Remote changes for Experiment 5
PART 5 – FETCH THE LATEST REMOTE CHANGES

	Fetch updates
Return to Git Bash and download the latest remote commits. Fetch updates remote-tracking references but does not merge them into the local branch.
git fetch origin

	Check repository status
Check the working-tree status after fetching.
git status
PART 6 – REBASE THE CURRENT MAIN BRANCH
	Confirm the current branch
git branch

	Rebase main onto the updated remote main
Replay local commits that are not on origin/main on top of the latest remote main commit.
git rebase origin/main
git log –oneline

Expected result: If there are no conflicts, Git reports that the rebase completed successfully. If using master, run git rebase origin/master.

	Push the updated main branch 
git push origin main


➢ Verify the repository
pwd
ls -a

Expected result: The .git directory and README.md should be visible.
PART 2 – CHECK STATUS, BRANCHES, AND REMOTE
➢ Check the repository status
git status

Expected result: Ideally, the working tree is clean. If you have changes you want to keep, commit or safely save them before continuing.
➢ List local branches
git branch

Expected result: The current branch is marked with an asterisk (*). Check whether the main branch is named main or master.
➢ Check the GitHub remote
git remote -v

Expected result: origin should show the GitHub repository URL for fetch and push.
PART 3 – UPDATE AND PREPARE THE MAIN BRANCH

➢ Pull the latest remote changes
git pull origin main

If using master, run git pull origin master. This helps ensure that the local main branch is up to date before creating the feature branch.
PART 4 – CREATE AND COMMIT A FEATURE
➢ Create feature-branch
git branch feature-branch
git switch feature-branch

This creates feature-branch from the current main branch and switches to it.
➢ Create a sample feature file
notepad book-search.txt

In Notepad, type a sample line such as: "Book search feature implementation". Save the file and close Notepad.
➢ Stage the file
git add book-search.txt

➢ Commit the feature
git commit -m "Add book search feature"

➢ Verify the feature commit
git log --oneline

Expected result: The new feature commit should appear in the recent commit list.
PART 5 – SWITCH BACK TO THE MAIN BRANCH
➢ Switch to main
git switch main

If the repository uses master, run git switch master instead.
➢ Confirm the current branch
git branch
PART 6 – MERGE WITH A CUSTOM COMMIT MESSAGE
➢ Merge feature-branch into main
git merge --no-ff feature-branch -m "Merge book search feature"
The --no-ff option requests a merge commit even if Git could fast-forward. The -m option supplies the custom merge commit message.
PART 7 – VERIFY THE MERGE
➢ Check repository status
git status

Expected result: The working tree should be clean.
➢ View the latest commit details
git show HEAD

Expected result: The latest commit details should include the custom message "Merge book search feature".
➢ List branches merged into the current branch
git branch --merged

Expected result: feature-branch should normally appear because it has been merged into the current branch.
PART 8 – PUSH THE MERGE TO GITHUB
➢ Push the updated main branch
git push origin main

