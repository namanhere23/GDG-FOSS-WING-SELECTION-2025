### Answer the following questions in you own words.

> It's not necessary that you havee to know and answer all the questions. Just answer the ones
> you know and write in your own words.

1. Give the difference between the remotes - upstream and origin - with an example.

We use origin when we want to push to our's forked repository, whereas upstream when we want to push to the original soure repository.

2. You have two branches A and B and you have currently made some changes in branch A.
You want to move into branch B but do not want to commit the current changes in branch A.
What will you do?

I would first stash the changes, then switch to branch B. git stash pop, this command helps to get the commits back

3. You were assigned a work to implement a feature and create a PR to your organization's remote repository.
For this you made a branch (say A) and made some changes and commited them. Now you moved to some other branch 
(say B) to do some other assigned work. But later you realisd that have to complete the task assigned earlier 
first and commited some changes in branch B which are meant for branch A. How will you use git to bring the 
changes from branch B to branch A?

I would stay in branch B only then I would checkout to branch A using git checkout B, then I would cherry-pick <hash>, then I can remove by git reset

3. What is the difference between fetching changes and pulling changes?

Fetches just fetches and does not merge, whereas pulling merges and if there is any issue it would show merge conflicts

4. What does -i flag stand for? What is it's significance in git?

The -i flag stands for interactive. I have used when I want to have to clean the commit history.

5. You are working in an organization that follows very strict guidelines for PRs and commits.
You made three commits in your PR and the maintainer says you were supposed to make a single commit.
What will you do in this case?

Using the git rebase HEAD~3 we can go the commit which is three commits before then I would do force push the commits

6. Explain `git merge` and `git rebase` with example(s).

Git merge is used to combine both branches, whereas the rebase moves one branch on the top of the other branch.
Merge gives us a tree like structure whereas in rebase it looks like the linear structure.

7. Write the flow how you create a repository and push changes to it. Also mention the commands used at each step.

I would make a github repository, after that I would open the terminal on the folder where we wants the changes.
The commits for this work are
    - git init (For initializing the repository)
    - git add . (For adding all the files that were changed)
    - git commit -m "first commit" (Commit with message "first commit")
    - git branch -M main (Create the branch main)
    - git remote add origin <github repo link> (Link local repo with remote GitHub repo)
    - git push -u origin main (Push code to github on main branch)


8. How would you prevent a file or folder from getting tracked by git?

I would simply create .gitignore file, then I would add the relative path there that would prevent the file or folder from getting tracked by git

9. You did not implement the step you mentioned in question 8 and now you have committed and pushed your database's
secret key to the github. How will you remove the key from your git's commit history to avoid any misuse?

git filter-repo --path <file> --invert-path. This filters the repo where <file> file has commit and also removes from each commit. But also change the API Key because, it could be possible that for that time being somebody have already stolen the key.