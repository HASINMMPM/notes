
- Understanding Git workflows and commands is essential for efficient collaboration and version control in software development.
- In Git, a **Branch** represents an independent line of development, allowing multiple developers to work on different features or fixes simultaneously without interfering with the main codebase.
- Branches enable developers to isolate their work, experiment safely, and merge changes back into the main project when ready.
- **Feature branching** is a workflow where a developer creates a new branch specifically for developing a new feature or enhancement. This approach keeps the main branch stable while new features are being developed and tested.
- Once the feature is complete and tested, the feature branch is merged back into the main branch, often through a pull request.

**Steps in Feature Branching:**

1. **Create a new branch** from the main branch.
2. **Develop** the new feature on this branch.
3. **Commit** changes regularly to this branch.
4. **Push** the branch to the remote repository.
5. **Open a pull request** to merge the feature branch into the main branch.
6. **Review and merge** the pull request after approval.

- A **hotfix** is an urgent correction applied to the production codebase to address a critical issue. Unlike regular feature development, hotfixes require immediate attention and are often released outside the normal development cycle.
**Hotfix Workflow:**
1. **Create a new branch** from the main branch, often named with a `hotfix/` prefix (e.g., `hotfix/critical-bug-fix`).
2. **Implement** the necessary fix on this branch.
3. **Commit and push** the changes to the remote repository.
4. **Open a pull request** to merge the hotfix branch into the main branch.
5. **After merging**, create another pull request to merge the hotfix into the development branch to ensure the fix is included in future releases.

- A **pull request** is a mechanism for proposing changes to a repository.
- It allows developers to notify team members that a feature or fix is ready for review and integration.
**Pull Request Workflow:**

1. **Push** the feature or hotfix branch to the remote repository.
2. **Open a pull request** from the branch to the target branch (e.g., from `feature/new-feature` to `main`).
3. **Review** the proposed changes with team members.
4. **Address feedback** by making additional commits to the branch.
5. **Merge** the pull request once it has been approved.

### Basic Git Commands


- `git init`: Initialize a new Git repository.​
    
- `git clone [repository_url]`: Clone an existing repository from a remote URL.​
    
- `git branch`: List all local branches in the repository.​
    
- `git branch [branch_name]`: Create a new branch with the specified name.​
    
- `git checkout [branch_name]`: Switch to the specified branch.​
    
- `git checkout -b [branch_name]`: Create and switch to a new branch in one command.​
    
- `git status`: Display the state of the working directory and staging area.​
    
- `git add [file_name]`: Stage changes for the next commit.​
    
- `git commit -m "[commit_message]"`: Commit staged changes with a descriptive message.​
    
- `git pull`: Fetch and merge changes from the remote repository into the current branch.​[GitHub Docs](https://docs.github.com/en/desktop/making-changes-in-a-branch/managing-branches-in-github-desktop?utm_source=chatgpt.com)
    
- `git push`: Upload local branch commits to the remote repository.​
    
- `git merge [branch_name]`: Merge the specified branch into the current branch.​
    
- `git rebase [branch_name]`: Reapply commits on top of another base branch.​[Stack Overflow+1GitHub Docs+1](https://stackoverflow.com/questions/42229487/how-to-do-hotfixes-with-github-pull-requests?utm_source=chatgpt.com)
    
- `git log`: Show the commit history for the current branch.​
    
- `git diff`: Display differences between commits, branches, or the working directory.​
    
- `git reset [commit]`: Reset the current branch to a specified commit.​
    
- `git stash`: Temporarily save changes that are not ready to be committed.​
    
- `git tag [tag_name]`: Create a new tag at the current commit.