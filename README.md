# Git-Practice
Repository to do a group practice of the git and github flow

## 🌿 Beginner Git & GitHub Activity: Branching Practice
🎯 Goal

 - Cloning a repository

 - Creating and switching branches

 - Making commits

 - Pushing branches to GitHub

 - Creating a pull request

 - Reviewing and merging changes

## Day 1 - Using Branches
### Instructions
<details>
<summary>Step 1 - Creating Dev</summary>

#### 1️⃣ Clone the repository...

    git clone <repo-url>
    cd Git-Practice

#### ...and check your connection to the remote repository:

    git remote -v

This should show the address of the repository in github:

![alt text](./assets/01_remote_address.png)

#### 2️⃣ Create the dev branch from main and switch to it

    git checkout -b dev

You will see something like this in your teminal:

![alt text](./assets/02_create_local_dev.png)

This means that you have created a new branch called dev and switched to it.

#### 3️⃣ Pull the origin/dev branch to your local branch

    git pull origin dev

This will pull all of the changes from the remote dev branch to your local dev branch. You will see something like this in your terminal:

![alt text](./assets/03_pull_origin_dev.png)

In this case, as I created the dev branch and pushed it with the content, there were no new changes to pull, so the output shows "Already up to date." In your case, you will see instead a list of files that were updated.
</details>
<details>
<summary>Step 2 - Exploring Branches</summary>

#### 1️⃣ Check your local branches

    git branch

You will see a list with your local branches:

![alt text](./assets/04_listing_local_branches.png)

The branch with the asterisk (*) is the one you are currently in.

#### 2️⃣ Check the remote branches

    git branch --remote

You will see a list with your remote branches:

![alt text](./assets/05_listing_remote_branches.png)

This shows the branches that are in the remote repository. The origin/ prefix indicates that these branches are in the remote repository named origin.

#### 3️⃣ Check both remote and local branches

    git branch --all

You will see a list with all the branches, local and remote ones:

![alt text](./assets/06_listing_all_branches.png)

</details>
<details>
<summary>Step 3 - Creating feature branches</summary>

#### 1️⃣ Create a feature branches from dev but don't switch to it

    git branch feature/<feature-to-implement>

This will create a new branch called feature/feature-to-implement from the current branch (dev), but you will remain in the dev branch.

<i style="color: orange">In the Contributors.md file, you will have a feature assigned to you for this project, so use that to create the name of your branch.</i>

If you have issues with naming branches, here you have an article about <a href="https://medium.com/@abhay.pixolo/naming-conventions-for-git-branches-a-cheatsheet-8549feca2534" target="_blank">naming branches conventions</a>.

#### 2️⃣ List your local branches to see the new feature branch

    git branch

#### 3️⃣ Switch to your new feature branch

    git checkout feature/<feature-to-implement>

#### 4️⃣ Make changes to the Contributors.md file
Open the Contributors.md file in your code editor and add your name and a link to your GitHub profile under the appropriate section.

#### 5️⃣ Stage your changes

    git add Contributors.md

#### 6️⃣ Commit your changes

    git commit -m "Add <your-name> to Contributors"

#### 7️⃣ Check the status of your branch

    git status

#### 8️⃣ Push your feature branch to the remote repository

    git push -u origin feature/<feature-to-implement>

This will push your feature branch to the remote repository and set the upstream branch, so the remote and local branches are connected.

#### 9️⃣ Write the html code for the feature you have been assigned

Open the index.html file in your code editor and add the html code for the feature you have been assigned.

#### 🔟 Stage, commit, and push your changes

    git add index.html
    git commit -m "Implement <feature-to-implement>"
    git push

Once you have pushed your changes, you can go to the GitHub repository and see your feature branch with the changes you made.
</details>


## Day 2 - Protecting Branches and PRs
### Instructions
<details>
<summary>Step 1 - Creating a Pull Request</summary>

#### 1️⃣ Go to the GitHub repository in your web browser

#### 2️⃣ You will see a notification about your recently pushed branch. Click on the "Compare & pull request" button.
- If you don't see the notification, you can go to the "Pull requests" tab and click on the "New pull request" button.

![alt text](./assets/07_compare_and_pr.png)

#### 3️⃣ Set the base to dev and the compare to your feature branch

![alt text](./assets/08_set_base_and_compare.png)

#### 4️⃣ Fill in the title and description for your pull request

![alt text](./assets/09_fill_pr_details.png)

#### 5️⃣ Click on the "Create pull request" button

![alt text](./assets/10_create_pr.png)

This will create a pull request from your feature branch to the dev branch.

#### 6️⃣ Notify your teammates to review the pull request
- you can send the link of the PR via slack or any other communication tool you use
</details>

<details>
<summary>Step 2 - Reviewing a Pull Request</summary>

#### 1️⃣ Go to the "Pull requests" tab in the GitHub repository

#### 2️⃣ Click on the pull request created by one of your teammates

![alt text](./assets/11_open_pr.png)

Alternatively, you can go to the PR through the link shared by your teammate.

#### 3️⃣ Review the changes made in the pull request:

- Create a local copy of the branch to review from the local dev.

        git checkout dev
        git pull origin dev
        git checkout -b review/<feature-to-review>

- Pull the feature branch to your local review branch.

        git pull origin feature/<feature-to-review>

- Resolve any merge conflicts if there are any.

- Review the code changes in your code editor (is everything working as expected? Are there any bugs? Is the code clean and well-structured?)

#### 4️⃣ After the review is done, go to the "Files changed" tab to see the changes made in the pull request
- Approve the changes by clicking on the "Review changes" button and selecting "Approve" if all looks good

![alt text](./assets/12_approve_pr.png)

- Request changes by clicking on the "Review changes" button and selecting "Request changes" if there are issues that need to be addressed

![alt text](./assets/13_request_changes_pr.png)

#### 5️⃣ Once the PR has all the approvals, let your teammate know they can merge the pull request
</details>

<details>
<summary>Merging a Pull Request</summary>

#### 1️⃣ If everything looks good and there are no merge conflicts:

- Click on the "Merge pull request" button

![alt text](./assets/14_merge_pr.png)

- Confirm the merge by clicking on the "Confirm merge" button

![alt text](./assets/15_confirm_merge.png)

- Delete the origin feature branch by clicking on the "Delete branch" button

- Delete the local feature branch:

        git branch -d feature/<feature-to-implement>

- Update your local dev branch:

        git checkout dev
        git pull origin dev

- Update any other local feature branches:

        git checkout feature/<feature-to-implement>
        git pull origin dev

#### 2️⃣ If there are merge conflicts:
- Resolve the merge conflicts locally in your code editor

- Stage, commit, and push the changes to the feature branch

- Go back to the pull request in GitHub and verify that the merge conflicts have been resolved

- Proceed with the merging steps as described above

#### 3️⃣ Let your teammate know that the feature branch has been merged and deleted so they can also delete their local feature branch and update their local dev branch

![alt text](./assets/16_delete_branch.png)

</details>

## Day 3 - Merging Branches Locally
### Instructions

