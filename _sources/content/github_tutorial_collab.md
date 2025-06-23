## Collaboration using GitHub

In the previous lesson, we set up a repository, used Git for version control, and learned how to push and pull changes between our local and remote repositories on GitHub.

The next step: using GitHub to collaborate on a shared project.

### Goal:

We’ll learn how multiple people can contribute to the same project, either by creating branches within a single repository or by forking and working across separate repositories. We’ll explore how to propose and manage changes through pull requests, and how to track tasks and ideas using issues and project boards.

To practice, we’ll each contribute to a shared project using forks, pull requests, and issues, simulating real-world collaboration workflows.

--------------------------------------------------------------------------


## Practice - Collaboration

Pair up with the person next to you. Decide who will be the host and who will be the contributor. We’ll find out who has the best taste in ice cream?

Each participant should already have a file ice_cream.md in their repo, containing something like:
1.Pistachio
2.Vanilla
3.Chocolate


### Step 1: Host shares repo
- On GitHub:
- Go to https://github.com/your-username
- Open your repo (e.g., ice-cream-prefs)
- Copy the URL and send it to your partner (Contributor)

### Step 2: Contributor Forks and Clones
- Open the Host’s GitHub repo in your browser.
- In the top-right, click the “Fork” button.
    - GitHub will create a copy of the repo under your own username.

<figure>
  <img src="https://github.com/M-earnest/GitHub_practice/blob/main/lecture/static/fork_repo.png?raw=true" alt="Init a repo" width="600" height="400">
  <figcaption>Figure: Forking a repository </figcaption>
</figure>

You’re redirected to your new fork:
 https://github.com/your-username/ice-cream-prefs

- In GitKraken:
- Click + (top left) → Clone Repo
- Choose GitHub.com → Your Repositories
- Select your forked repo (E.g. ice-cream-prefs)
- Choose a folder to save it locally
- Click Clone the repo


<figure>
  <img src="https://github.com/M-earnest/GitHub_practice/blob/main/lecture/static/clone_repo.png?raw=true" alt="Init a repo" width="600" height="400">
  <figcaption>Figure: Cloning a repository </figcaption>
</figure>

You now have a local copy of the forked repo, ready to work on.

```{dropdown} Branching vs Forking
:icon: git-branch

**Branching: internal collaboration**  
Use when you’re working within a shared repository, e.g., in a lab where all members have write access.  
Each person creates a branch (e.g., `alice-new-stats`) and pushes it to the shared GitHub repo.  
Changes are proposed via pull requests.

**Forking: external collaboration**  
Use when you don’t have write access to the original repo — e.g., contributing to another lab’s codebase or to public tools.  
You click **Fork** on GitHub, which creates a copy of the repo under your own account.  
You clone your fork, work on it, push changes, and create a pull request back to the original repo.
```

### Step 3: Contributor makes and commits changes

Now we want to to contribute to this cool project we've found. As we are naturally unbiased in our assesments, we will improve the rankings of the original author. 

There are two ways to do this, either the proper way as described below or, as we are working with Markdown files, by editing the file directly in the browser. Either way, we will first be creating a fork of the repo in question.

A fork is your own indepenent copy of another repository on GitHub, letting you experiment and make changes without affecting the original project.

- Open the local folder of the cloned fork
- Edit the ice_cream.md file. Replace the three flavors with your own favorites, change the ranking, leave a comment
- Save the file
- In GitKraken, stage and commit with an informative message, e,g. updated rankings, added actually good flavors
- Push your changes to GitHub.

### Step 4: Contributor opens a pull request

A pull request lets you propose changes from your fork back to the original repository so they can be reviewed, discussed, and merged.

- Go to your forked repository on GitHub
- GitHub should show how many commits your repo is behind/ahead. Next to this you'll find the `contribute` button. Click it
- Click `Open pull request`
- Fill in the pull request form: Add a meaningful title + desription

<figure>
  <img src="https://github.com/M-earnest/GitHub_practice/blob/main/lecture/static/open_pr.png?raw=true" alt="Init a repo" width="600" height="300">
</figure>


<figure>
  <img src="https://github.com/M-earnest/GitHub_practice/blob/main/lecture/static/pull_request.png?raw=true" alt="Init a repo" width="600" height="300">
  <figcaption>Figure: Opening a pull request </figcaption>
</figure>



```{dropdown} Pull Request Template
:icon: checklist
:open:

**Summary**  
Short description of the change.

**Details**  
- What you did  
- Why you did it  
- Any notes on edge cases, testing, or unresolved questions

**Next steps** (optional)  
- What needs to happen after this PR (e.g., testing, further improvements)

```


### Step 5: Host makes changes to the original repo
While the pull request is still open:
- The host edits their own ice_cream.md file and changes one or more flavors.
- Save the file, commit the change, and push it to GitHub.

### Step 6: Review the pull request (before merging)
- Go to the pull request page on the host’s repository
- Notice that GitHub now shows "This branch has conflicts that must be resolved"
- This means the same file was changed in both the fork and the main repo

We'll use this as an opportunity to review the conflict and prepare to resolve it.


<figure>
  <img src="https://github.com/M-earnest/GitHub_practice/blob/main/lecture/static/merge_conflict.png?raw=true" alt="Init a repo">
  <figcaption>Figure: Merge conflict warning </figcaption>
</figure>


### Step 7: Resolving conflicts
- Click "Resolve conflicts".

GitHub will show the file with conflict markers like:

```
<<<<<<< HEAD
host's version
=======
contributor's version
>>>>>>> fork-branch
```



<figure>
  <img src="https://github.com/M-earnest/GitHub_practice/blob/main/lecture/static/resolve_merge.png?raw=true" alt="Init a repo">
  <figcaption>Figure: Resolving a merge conflict </figcaption>
</figure>


We'll edit the file to combine both changes into a clean, final version, remove the conflict markers (<<<<<<<, =======, >>>>>>>) and make sure the file looks correct.

Once you're done:
- Click "Mark as resolved"
- Click "Commit merge"
- Finally, click "Merge pull request" and confirm the merge



<figure>
  <img src="https://github.com/M-earnest/GitHub_practice/blob/main/lecture/static/resolve_pr.png?raw=true" alt="Init a repo">
</figure>

--------------------------------------------------------------------------

## Additional content - Managing projects via GitHub

GitHub Projects is a built-in tool for planning and tracking work. It helps you organize tasks, features, and bugs directly alongside your code. You can think of it as GitHub’s alternative to tools like Trello or Jira.

GitHub Projects allow you to:
    - Break your work into tasks or issues
    - Visualize progress using boards, tables, or timelines
    - Assign tasks to collaborators
    - Track pull requests and issues in one place
    - Set priorities and due dates

Projects are usually organized as boards with columns. The default setup looks like the following, but can be freely changed:
- To Do – upcoming tasks
- In Progress – work currently being done
- In Review – code under review or waiting for feedback
- Done – completed tasks

<figure>
  <img src="https://github.com/M-earnest/GitHub_practice/blob/main/lecture/static/project_card.png?raw=true" alt="Init a repo" >
  <figcaption>Figure: Project View </figcaption>
</figure>


Each item on the board can be:
- GitHub issue (bug, feature, task)
- pull request
- notes, i.e. ideas or reminders

### Practice - Project managment

Creating a new project:

- Go to your repository on GitHub or click on the three bars indicating a dropdown menu at the top-left
    - Click Projects
    - Click New Project
    - Choose a layout: Board, Table, or Roadmap
    - Name your project and set up columns or views as needed
 
#### Adding Collaborators to a Project

1. Open the project page
2. Click **Settings** → **Collaborators**

<figure>
  <img src="https://github.com/M-earnest/GitHub_practice/blob/main/lecture/static/project_settings.png?raw=true" alt="Init a repo" >
  <figcaption>Figure: Project settings </figcaption>
</figure>


3. Add members of your organization by typing their GitHub username
4. Assign permissions:
   - **Read** – View project but no edits
   - **Write** – Add/edit items, change statuses, assign fields
   - **Admin** – Full control including managing views, workflows, and settings


#### Adding Items to a Project:
- **From the project interface**:
  - Click **+ Add item** to create a new draft issue or task
  - Or click **+ Add cards** to search for and link existing issues or pull requests from any repository in the organization

- **From an issue or pull request**:
  - Open the issue or PR from any repo in the organization
  - In the right-hand sidebar, under **Projects**, click the dropdown and select your organization-level project
 
#### Assigning Tasks and Roles

- **Assign project items**:
  - Within the project view, click any item (issue, draft, or PR)
  - Use the **Assignee** field to assign a person.
  - Optionally, define a custom field like “Role” or “Lab Responsibility” to clarify who is doing what

- **Organize with views**:
  - Use filters to create views like:
    - “Assigned to me”
    - “Blocked tasks”
    - “Manuscript-related items”
  - Group by status, assignee, or priority

- **Track progress**:
  - Move cards through columns (e.g., To Do → In Progress → Review → Done)
  - Add status automation via workflows if enabled
