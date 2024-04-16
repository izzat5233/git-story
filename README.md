## Getting Started

1. **Initialize a Git Repository:** Create a new directory called **`git-story`**. Navigate into this directory and initialize a Git repository using **`git init`**.

### Basics

1. **Create `chapter1.txt`:** Write the following paragraph in a new file named **`chapter1.txt`**:
    
    ```
    Once upon a time, in a village named "Init", lived a brave adventurer named Git.
    ```
    
    Add the file to the staging area with **`git add chapter1.txt`**.
    
2. **Commit Your Changes:** Commit the changes with the message "Chapter 1: Introduce Git from Init village" using **`git commit -m "Chapter 1: Introduce Git from Init village"`**.
3. **Check the Status:** Use **`git status`** to check the status of your working directory and staging area.
4. **Show the Last Commit:** Use **`git show`** to display the changes made in the last commit.
5. **Check the Commit History:** Use **`git log`** to view the commit history. Try using **`git log --oneline`** to see a simplified one-line-per-commit version of the log.

### Extend the Story

1. **Modify `chapter1.txt`:** Add more to the story in **`chapter1.txt`**. For example, add the following lines:
    
    ```
    Git was well-known for his curiosity and eagerness to learn.
    He had one dream - to explore the mysterious world of Version Control.
    ```
    
    Stage the changes with **`git add chapter1.txt`**.
    
2. **Commit the Changes:** Commit the changes with the message "Chapter 1: Extended story" using **`git commit -m "Chapter 1: Extended story"`**.
3. **Show and Log:** Use **`git show`** again to display the most recent commit. Then, use **`git log`** to see the new commit history.

By this point, you've used **`git init`**, **`git add`**, **`git commit`**, **`git status`**, **`git show`**, and **`git log`** in a realistic workflow.

## **Branching and Merging**

1. **Create a New Branch:** Create a new branch called **`chapter2`** using **`git branch chapter2`**, and switch to it using **`git checkout chapter2`**.
2. **Create `chapter2.txt`:** Write a short paragraph about Git's decision to leave Init to explore the world of Version Control in **`chapter2.txt`**. For instance:
    
    ```
    Chapter 2: Git's Decision
    Git, after much contemplation, decided to leave his home in Init to explore the vast world of Version Control.
    ```
    
    Stage and commit the changes with the message "Chapter 2: Git's decision".
    
3. **Switch and Merge:** Switch back to the **`master`** branch using **`git checkout master`**. Merge the **`chapter2`** branch into **`master`** using **`git merge chapter2`**. This should be a fast-forward merge as there are no new commits on **`master`** that **`chapter2`** doesn't have.
4. **Non-Fast-Forward Merge:** Let's introduce a scenario where a fast-forward merge isn't possible. First, create and switch to a new branch **`chapter3`** and create **`chapter3.txt`** with content:
    
    ```
    Chapter 3: Git's First Step into the World of Version Control
    With a heavy heart and a bag full of hopes, Git took his first step into the world unknown.
    
    ```
    
    Commit this change. Now, switch back to **`master`**, modify **`chapter1.txt`** or **`chapter2.txt`**, and commit this change. Try merging **`chapter3`** into **`master`**. This will be a non-fast-forward merge as there have been new commits on both **`master`** and **`chapter3`**.
    
5. **Simulate Merge Conflicts:** To create a merge conflict scenario, let's create a new branch from **`master`** called **`conflict_branch`**. In this branch, change the first line of **`chapter1.txt`** to:
    
    ```
    Once upon a time, in a town named "Init", lived an enthusiastic explorer named Git.
    ```
    
    Commit the changes. Now switch back to **`master`** and change the same line to:
    
    ```
    Once upon a time, in a town named "Init", lived a brave adventurer named Git.
    ```
    
    Commit the changes here too. Now, try to merge **`conflict_branch`** into **`master`**. This should result in a merge conflict. Solve this conflict, decide which version to keep, stage, and commit the merge.
    

By the end of this part, you would have practiced creating branches (**`git branch`**), switching branches (**`git checkout`**), merging branches (**`git merge`**), resolving conflicts, and experienced both fast-forward and non-fast-forward merges.

## More on Git Log, Diff , Stash and Rebase

1. **Log and Diff:** First, add more details to **`chapter2.txt`**, such as:
    
    ```
    His family and friends gathered to bid him farewell. It was an emotional moment, but Git was determined.
    ```
    
    But don't stage or commit them yet. Run **`git diff`** to see the un-staged changes in your working directory.
    
2. **Explore Git Log Options:** Now, commit the changes with the message "Chapter 2: Extended story". After committing, check the log with **`git log --stat`** to see statistics for files modified in each commit. You can also use **`git log -p`** to see the patch output, i.e., the actual changes in detail.

### Stashing Changes

1. **Stashing Changes:** Now, make some changes to **`chapter3.txt`**. For example:
    
    ```
    Git was ready for his journey, prepared to face the trials ahead.
    
    ```
    
    But don't stage or commit these changes. Suppose you need to switch to another task, and you want to save these changes without committing them. Use **`git stash save "WIP on chapter3"`** to stash these changes.
    
2. **List the Stashes:** You can list all the stashes using **`git stash list`**.
3. **Apply a Stash:** Finish your other task and come back to this one. Apply the changes you stashed earlier using **`git stash apply stash@{0}`**. This applies the stash and keeps it in the stash list for later use.
4. **Pop a Stash:** You can also use **`git stash pop stash@{0}`** to apply the stash and remove it from the stash list.
5. **Drop a Stash:** If you want to delete a stash without applying it, you can use **`git stash drop stash@{0}`**.

### **Pushing to a Remote Repository**

1. **Create a New Repository on GitHub:** First, go to GitHub and create a new repository. Name it, for example, "git-story".
2. **Connect your Local Repository to the Remote Repository:** Navigate to your local Git project (in this case, the "git-story" directory). Run the following command to connect your local repository to the remote repository you just created on GitHub:
    
    ```bash
    git remote add origin <YOUR_REMOTE_REPOSITORY_URL>
    ```
    
    Replace **`<YOUR_REMOTE_REPOSITORY_URL>`** with the URL of the repository you created on GitHub. You can find this URL on your GitHub repository page.
    
3. **Verify the Remote Repository:** Confirm that the remote repository has been set up with the following command:
    
    ```bash
    git remote -v
    ```
    
    This will list the URLs of the remote repositories associated with your local repository.
    
4. **Push Local Commits to the Remote Repository:** Now push the commits from your local repository to your remote repository on GitHub with this command:
    
    ```bash
    git push -u origin master
    ```
    
    This command pushes your **`master`** branch to the remote repository named **`origin`**. The **`-u`** option remembers the settings, so next time, you can simply run **`git push`**.
    
5. **View Your Project on GitHub:** Open your browser and go to your repository on GitHub. You should see all the files you've worked on along with the commit messages.

By the end of this section, you've learned how to push your local Git repository to a remote repository on GitHub, making it accessible from any computer and allowing you to collaborate with others.

### Interactive Rebase

1. **Interactive Rebase:** Let's say you made a series of minor commits to **`chapter3.txt`** and now realize that they should've been one single commit. The following lines were added in separate commits: Now, use **`git rebase -i HEAD~3`** to squash these commits into one.
    
    ```
    Git took a deep breath as he stepped into the world of Version Control.
    He knew the journey wouldn't be easy, but he was ready.
    He was doing this for his village, for Init.
    ```
    

By the end of this part, you would have learned how to use **`git diff`** to view changes, **`git stash`** to save work in progress, **`git log`** with different options to view detailed commit history, and **`git rebase -i`** for interactive rebasing.

### More into Interactive rebase

1. **Editing Commit Messages with Interactive Rebase:** Let's say the commit message of the third commit from the top is not informative enough. You can change it using interactive rebase. Run **`git rebase -i HEAD~3`** and replace **`pick`** with **`reword`** for the third commit. Save and exit the text editor. You will be prompted to enter a new commit message.
2. **Reordering Commits with Interactive Rebase:** Imagine that you committed some changes to **`chapter2.txt`** after making several commits to **`chapter3.txt`**. The story would make more sense if all commits for **`chapter2.txt`** were together. You can use interactive rebase to reorder commits. Run **`git rebase -i HEAD~5`** (or however many commits you need to go back) and reorder the lines to change the order of commits.
3. **Dropping Commits with Interactive Rebase:** Suppose you made a commit that is no longer necessary. You can remove it using interactive rebase. Run **`git rebase -i HEAD~4`**, replace **`pick`** with **`drop`** (or simply delete the line), and then save and exit.
4. **Squashing Commits with Interactive Rebase:** If you have multiple commits that should be one commit (similar to the example given before), you can squash them using interactive rebase. Suppose you made three commits to **`chapter3.txt`** where each commit added one line. You can squash these into one commit. Run **`git rebase -i HEAD~3`**, replace **`pick`** with **`squash`** or **`s`** for the last two commits, save and exit. You will then be prompted to create a new commit message for the squashed commits.

Interactive rebasing can be a powerful tool when used correctly, as it allows you to change your commit history in many ways. However, be careful when using it, as it can also easily lead to confusion or data loss if not used correctly. It's especially important to be cautious when rebasing commits that have been pushed to a shared repository.

## Rebase vs Merge

1. **Merge Workflow:** You've been working on the **`master`** branch, adding more to the adventures of Git. Now, you've learned about a new place called "The Hub" and decide to create a new chapter about it. You start working on this new chapter by creating a new branch **`chapter_hub`** from **`master`** and add **`chapter_hub.txt`** with a few lines:
    
    ```
    Chapter Hub: The Adventure in the Hub
    
    Git had heard tales of a mystical place called "The Hub", where many adventurers gathered and shared their journeys.
    ```
    
    Commit this change.
    
2. **Changes on Master:** Meanwhile, there are some changes made on **`master`**. Go back to **`master`** and add some more lines to **`chapter1.txt`**. Commit these changes.
3. **Merge Master:** Now, you want to include the changes made in **`master`** in your **`chapter_hub`** branch. One way to do this is using **`git merge`**. Switch to **`chapter_hub`** and merge **`master`** into it (**`git merge master`**). Notice the merge commit created and how it brings together the two branches.
4. **Rebase Workflow:** Let's introduce a similar scenario, but this time, use **`git rebase`** instead. Create a new branch **`chapter_fork`** from **`master`** and add **`chapter_fork.txt`** with a few lines. Commit this change.
5. **Changes on Master (Again):** Again, make some changes on **`master`** - perhaps more additions to **`chapter1.txt`**. Commit these changes.
6. **Rebase Master:** Now, you want these changes from **`master`** in your **`chapter_fork`** branch. This time, use **`git rebase master`** while on **`chapter_fork`**. This moves the entire **`chapter_fork`** branch to begin on the tip of the **`master`** branch.

In both workflows, you have accomplished the same end result: bringing changes from **`master`** into your feature branch. But the way history is recorded is different.

With **`git merge`**, your feature branch will retain its commit history, and a new merge commit is created. This preserves the context of the branch and its independence from the **`master`**'s timeline, but can make the history look complex.

On the other hand, **`git rebase`** moves your feature branch's changes onto the tip of **`master`**, making it appear as if you've created your feature branch from the latest **`master`** commit. This makes a linear and clean history, but it rewrites the commit history and removes the context of when the feature branch was originally created.

It's also worth mentioning that **`git merge`** is safe to use on public branches, while **`git rebase`** should be used with care as it rewrites history. It's better to use **`git rebase`** on local branches that haven't been shared with others.

## Amend, Revert, Reset, and Cherry-Pick

1. **Amend Commit:** Add a line to **`chapter1.txt`**:
    
    ```
    Git was eager to explore new places.
    
    ```
    
    Commit this change with the message "Chpater 1: Git's eagerness". Now, notice that "Chapter" has been misspelled in the commit message. Correct it using **`git commit --amend`**. This command will open the text editor allowing you to modify the last commit message. Change "Chpater" to "Chapter" and save the file.
    
2. **Revert Commit:** Add another line to **`chapter2.txt`**:
    
    ```
    Little did Git know, the adventures ahead were tougher than expected.
    
    ```
    
    Commit this change with the message "Chapter 2: The tough journey ahead". After committing, you decide these changes are not suitable for the chapter. Use **`git log`** to find the SHA-1 hash of the commit you want to revert, and then use **`git revert <commit-hash>`**. This will create a new commit that undoes the changes made in the commit you're reverting.
    
3. **Reset Commit:** Now add a line in **`chapter3.txt`**:
    
    ```
    Git, however, was confident in his abilities.
    
    ```
    
    Commit this change with the message "Chapter 3: Git's confidence". Soon after, you realize this change contradicts Git's character development. You decide you want to completely remove this commit from your history. Use **`git reset --hard HEAD~1`** to delete the last commit. Be careful, as this will permanently delete the commit and its changes.
    
4. **Cherry-Pick Commit:** On **`master`**, add this line to **`chapter2.txt`**:
    
    ```
    Back home, Git's family and friends were hoping for his safe return.
    
    ```
    
    Commit this change with the message "Chapter 2: Thoughts from home". You realize this information is also relevant to the new branch **`chapter_fork`** you're working on. Switch to **`chapter_fork`** branch, and use **`git cherry-pick <commit-hash>`** to apply this commit from **`master`** to **`chapter_fork`**.
    

By the end of this part, you will have learned how to modify the last commit using **`git commit --amend`**, how to undo changes using **`git revert`**, how to permanently delete commits using **`git reset`**, and how to apply changes from another branch using **`git cherry-pick`**.

## Git Reflog

1. **Exploring Reflog:** Run **`git reflog`** to see a list of operations that updated HEAD. This includes every commit, amendment, cherry-pick, checkout, rebase, etc. you've performed. It's a great tool to understand the movement of the HEAD pointer and can serve as a safety net if you need to recover lost commits.
2. **Recovering Lost Commit:** Now, let's create a scenario to recover a lost commit. Add another line to **`chapter3.txt`**:
    
    ```
    The first challenge Git faced was understanding the concepts of Version Control.
    
    ```
    
    Commit this change with the message "Chapter 3: Git's first challenge".
    
3. **Losing the Commit:** Now, assume that you accidentally hard reset the last two commits by running **`git reset --hard HEAD~2`**. Running **`git log`** won't show the last two commits now. But you realize you need the commit "Chapter 3: Git's first challenge" back.
4. **Recovering the Commit:** Here, **`git reflog`** comes to the rescue. Run **`git reflog`** and find the SHA-1 hash of the commit "Chapter 3: Git's first challenge". Then, use **`git cherry-pick <commit-hash>`** to apply that commit back to your current HEAD.

Remember, **`git reflog`** is a lifesaver when you've lost commits. It should be used with caution, but can save you in a pinch when you need to recover lost work.

## Git Hooks

1. **Introduction to Git Hooks:** Git hooks are scripts that Git executes before or after events such as commit, push, and receive. Git hooks are a built-in feature - no need to download anything. Git hooks are run locally.
2. **commit-msg Hook:** Let's create a simple pre-commit hook that checks if the commit message follows a certain format. First, navigate to the **`.git/hooks`** directory in your repository. Create a new file called **`commit-msg`** (no file extension).
3. **Writing the Hook:** In the **`commit-msg`** file, add the following code:
    
    ```
    #!/bin/sh
    COMMIT_MSG_FILE=$1
    COMMIT_MSG_CONTENT=$(cat "$COMMIT_MSG_FILE")
    
    if [[ ! "$COMMIT_MSG_CONTENT" =~ ^Chapter\ [1-9][0-9]*:.*$ ]]; then
        echo "ERROR: Commit message does not follow the standard - 'Chapter X: ...'"
        exit 1
    fi
    ```
    
    This code will prevent any commit that does not have a message starting with "Chapter X: ...". Save the file and make it executable using **`chmod +x commit-msg`**.
    
4. **Testing the Hook:** Try committing a change with a message that doesn't follow the correct format. The commit should be rejected. Now, commit with a message that does follow the format, like "Chapter 4: Git's Victory". The commit should be successful.

Remember, these hooks are not committed with the rest of your project and reside on your local machine only. If you want to share these hooks with your team or make them part of the project, you'll need to add them to the project's directory and then create a setup script or mention in your documentation that these scripts need to be copied to **`.git/hooks/`** to be activated.

These hooks can be powerful tools for enforcing certain rules, but be careful as they can also be disruptive to the workflow if used incorrectly.

## Git Bisect

1. **Introduction to Git Bisect:** **`git bisect`** is a powerful tool for finding the commit that introduced a bug in your project. Let's simulate a situation where you have to use it. Imagine you have been adding new features and making many changes to your story over the past weeks. Today, you've realized that a critical error (a typo) has crept into **`chapter1.txt`** at some point, but you're not sure when.
2. **Starting Bisect:** First, ensure that you are on the branch where the error exists (let's assume **`master`** for now). Start the bisect process using **`git bisect start`**.
3. **Bad Commit:** Next, mark the current commit as bad since the error exists in this commit. Use **`git bisect bad`**.
4. **Good Commit:** Now, you need to find a commit where you're sure the error didn't exist. For our case, let's assume it's the commit where **`chapter1.txt`** was first created. Use **`git log`** and find the commit hash where you added **`chapter1.txt`**. Mark that commit as good using **`git bisect good <commit-hash>`**.
5. **Bisect Process:** Git will now checkout a commit halfway between the good and bad commits. Check **`chapter1.txt`** and see if the typo exists. If it does, mark this commit as bad using **`git bisect bad`**. If the error does not exist in this commit, mark it as good using **`git bisect good`**.
6. **Repeat Process:** Repeat the process until Git pinpoints the exact commit that introduced the error. Once that happens, Git will display something like: **`xxxxxxx is the first bad commit`**.
7. **Exit Bisect:** Now that you've found the offending commit, end the bisect session using **`git bisect reset`**. This will take you back to where you were before starting the bisect process.

Remember, **`git bisect`** is a very powerful tool when you're trying to find the commit that introduced a bug in your project. It works on the principle of binary search, efficiently narrowing down the problematic commit
