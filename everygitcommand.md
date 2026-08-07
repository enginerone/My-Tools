## Setup & Starting a Repo
git init – Initializes a new Git repository in the current directory (creates .git).

git clone <url> – Makes a local copy of a remote repository (e.g., from GitHub).

git config --global user.name "Your Name" – Sets your name for commits.

git config --global user.email "you@example.com" – Sets your email for commits.

git config --global core.editor "code --wait" – Sets default editor (e.g., VS Code).

# Inspecting & Status
git status – Shows changed, staged, and untracked files; also current branch.

git log – Lists commit history (author, date, message).

git log --oneline – Compact one-line per commit.

git log -p – Shows commit history with diffs.

git log -S "text" – Finds commits that added/removed a specific string.

git diff – Shows unstaged changes in working directory.

git diff --staged – Shows staged changes (ready to commit).

git diff HEAD – Shows all changes vs last commit (staged + unstaged).

git show <commit> – Displays details of a specific commit.

# Staging & Committing
git add <file> – Stages a specific file.

git add . – Stages all changes in current directory (new + modified).

git add -p – Interactively stages parts of a file (patch mode).

git commit – Commits staged changes; opens editor for message.

git commit -m "message" – Commits with a short message inline.

git commit --amend – Edits the last commit (message or content).

# Branching & Switching
git branch – Lists local branches; * marks current branch.

git branch <name> – Creates a new branch at current commit.

git branch -d <name> – Deletes a merged branch.

git branch -D <name> – Force-deletes an unmerged branch.

git switch <name> – Switches to an existing branch.

git switch -c <name> – Creates and switches to a new branch.

git checkout <name> – Legacy way to switch branches (still works).

git checkout -b <name> – Legacy create+switch branch.

git switch -d <commit> – Checks out a past commit (detached HEAD).

# Merging & Integrating Changes
git merge <branch> – Merges specified branch into current branch.

git merge --no-ff <branch> – Merge without fast-forward (keeps merge commit).

git rebase <branch> – Reapplies current branch commits on top of another (linear history).

git rebase -i <base> – Interactive rebase to edit/squash/reorder commits.

git cherry-pick <commit> – Applies a single commit from another branch.

# Remotes & Syncing
git remote -v – Lists remote URLs (origin, etc.).

git remote add origin <url> – Adds a remote named “origin”.

git remote set-url origin <url> – Changes remote URL.

git push origin <branch> – Pushes local branch to remote.

git push -u origin <branch> – Pushes and sets upstream tracking.

git pull origin <branch> – Fetches + merges remote branch into current branch.

git fetch origin – Downloads remote changes without merging.

git fetch --all --prune – Fetches all remotes and removes stale refs.

# Undoing & Fixing
git reset <file> – Unstages a file but keeps changes in working directory.

git reset – Unstages all staged changes.

git reset --soft <commit> – Moves HEAD to commit, keeps changes staged.

git reset --mixed <commit> – Moves HEAD, keeps changes unstaged (default).

git reset --hard <commit> – Moves HEAD and discards working changes (dangerous).

git checkout -- <file> – Discards unstaged changes in a file (legacy; prefer git restore).

git restore <file> – Restores file in working directory (safer, modern).

git restore --staged <file> – Unstages a file (modern alternative to git reset <file>).

git revert <commit> – Creates a new commit that undoes a previous commit (safe for shared history).

git reflog – Shows history of HEAD moves; used to recover “lost” commits.

git clean -n – Shows untracked files that would be deleted.

git clean -f – Deletes untracked files (use with care).

git clean -fd – Deletes untracked files and directories.

# Stashing (Temporary Save)
git stash – Saves current changes and reverts working directory.

git stash -u – Stashes including untracked files.

git stash list – Lists saved stashes.

git stash pop – Applies latest stash and removes it from list.

git stash apply – Applies latest stash but keeps it in list.

git stash drop – Deletes a stash.

# History, Search & Debugging
git blame <file> – Shows who last edited each line and when.

git grep "pattern" – Fast search for a string in tracked files.

git bisect start – Starts binary search to find the commit that introduced a bug.

git bisect good / git bisect bad – Marks commits during bisect.

git bisect reset – Ends bisect session.

# Tags & Releases
git tag – Lists tags.

git tag v1.0.0 – Creates a lightweight tag.

git tag -a v1.0.0 -m "Release" – Creates an annotated tag.

git push origin --tags – Pushes all tags to remote.

# Working with Files
git mv <old> <new> – Moves/renames a file and stages the change.

git rm <file> – Removes a file and stages the deletion.

git rm --cached <file> – Stops tracking a file but keeps it locally.

# Advanced / Power-User Commands
git archive --format=zip --output=app.zip main – Exports a zip of a branch/commit.

git format-patch <base>..<tip> – Creates patch files for email/code review.

git apply --check <patch> – Checks if a patch applies cleanly.

git am <patch> – Applies patches from email/mailbox.

git replace <old> <new> – Replaces one commit with another (rewrite history helper).

git filter-branch / git filter-repo – Rewrites history (e.g., remove large files).

# Common Workflows (React/Vite Projects)
Start: git init → git add . → git commit -m "init" → git remote add origin <url> → git push -u origin main.

New feature: git switch -c feature/login → code → git add . → git commit -m "add login" → git push -u origin feature/login.

Sync before work: git switch main → git pull origin main → git switch feature/login → git rebase main or git merge main.

If you tell me which commands you use most (or which confuse you), I can tailor a minimal “daily driver” cheat sheet for your React/Vite ecommerce workflow.
