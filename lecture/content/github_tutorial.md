
# Git, GitHub and your machine

## Motivation

Neuroscience/Experimental psychology necessarily generates code and data that ideally is traceable from acquisition to publication (I’m certain you all can name a few reasons for this).

A distributed version-control system (Git) hosted on a collaboration platform (GitHub) provides a rigorous provenance backbone. It allows us to maintain a history of our projects, collaborate with others, make our work transparent and share it with the world. 

### Why Git and GitHub?


**Git as a version control system:**
- tracks exactly what was changed, when, and by whom.
- creates a complete lineage of changes across branches, forks and collaborators, i.e the “commit history”
- gives the ability to revert/review the state of a project to any past point in time
- command line based or integration with tools like GitKraken for visual workflows.


**GitHub builds on Git to support:**
- Secure cloud-based backup and access
- Collaboration through branching, pull requests, code reviews.
- Issue tracking and project management.


Relevance for the lab:
- **Collaboration**
    - Transparent collaborative development
- **Standardization**
    - Reproducible analysis pipelines: preprocessing, analysis, generating plots 
    - Archiving of computational steps: compliance with data sharing policies, open science initiatives, etc.


```{dropdown} Key Git and GitHub Terms
:icon: info
:open:

**Commit**  
A snapshot of your changes. Each commit records what was changed and includes a message describing why.

**Push**  
Sends your commits from your local machine to a remote repository on GitHub.

**Pull**  
Fetches the latest changes from a remote repository and merges them into your local copy.

**Fork**  
Creates a personal copy of someone else's repository on your GitHub account. Used when you don't have write access to the original.

**Branch**  
A parallel version of the project where you can develop features or fixes without affecting the main code. Useful for working on isolated changes.

```


### Practice: Workflow — Version control using GitKraken

Let's jump into practice. We'll learn the relevant functions and terms along the way. 

**Goal:**
In this section, you’ll learn how to create a Git repository using GitKraken, make your first commit, and push it to GitHub. 


#### Step 1: Initialize a Local Repository
- Open GitKraken.
- In the left sidebar, click + → Init Repo
- Create or select a folder on your machine for tracking, e.g. your Desktop 
- Name the repo 'my-icecream_project' and confirm
  
This creates a local Git repository. GitKraken automatically tracks changes in that initialized folder. You’ll now see the main branch and an empty commit history.

screenshot - init_repo

#### Step 2: Add a File to Your Project
- Open the folder in file explorer/terminal.
- Create new file, e.g., ice_cream.md (Using a text editor or the command line, e.g. Nano/touch)
- add the names of your 3 favorite Ice cream flavors in descending order and save the changes
- Go back to the GitKraken Window. The file should appear under Unstaged Files

#### Step 3: Stage the File
Staging gives you control over what file/change to include in each commit-snapshot.

In GitKraken:
- Click the checkbox next to README.md to stage it

screenshot - staging
#### Step 4: Commit the Change
A commit is a saved version of the project and it's contents. You’ll now see it in the commit graph (visual log of a repository’s history)

- In the Commit Message box, choose an informative title and description:
    e.g.: Title: add ice_cream.md
         Description: Added a ranking of my favorite icecream flavors

- Click Commit Changes
- Rinse and repeat for every new, meaningful change

screenshot - comitting

### Local to Remote:

Now this is where we would stop if we would just like work on our own system. For collaboration and transperency we’ll need to push our local repository to GitHub. We'll show you how to do this the proper way, but Gitkraken will allow you to shortcut Steps 5 to 7, as it allows us to simply create a remote from a local repository via it's push function. GitKraken will then detect that there’s no remote set up yet and will ask if you want to create a new remote repository.

#### Step 5: Create a Remote Repository on GitHub
We'll first create a "remote" version of the repository to push our changes to.

- Go to https://github.com
- click + → "New Repository"
- Give it the same name as your local repository
- Leave it empty (no README or license)
- Click Create Repository
- Copy the URL (e.g., https://github.com/yourusername/repo_name.git)

screenshot - create_repo

#### Step 6: Connect GitKraken to the Remote Repository
Back in GitKraken:
- In the left panel, click Remote → Add Remote
- Name it origin (conventional default)
- Paste the GitHub URL, confir


screenshot - add_remote

#### Step 7: Push to GitHub
- Click the Push button (top toolbar).
- If prompted, log into GitHub via GitKraken’s authentication flow.
- Push your main branch to the origin remote.

The push sends your local commits to GitHub. You now have a fully synchronized local–remote setup.

--------------------------------------------------------------------------


### Version Control and conflicts

Now that we have to separate instances of our project, we can simply work locally and push to GitHub whenever sensible. For collaboration and project work we might have multiple people contributing to the same remote repository. In the next steo we'll illustrate the possible problems arising here and how to manage them. 

Some files, e.g. Markdown files can be directly edited using the GitHub web interface, so we'll do a quick simulation. 

#### Step 8: Edit Files on GitHub
- Navigate to your repository on GitHub.com
- Click on the ice_crean.md to open it.
- Click the ✏️ Edit button (top right)
- Make your changes, scroll down, and enter a commit message. Commit changes.

This edits the file directly on GitHub and creates a new commit in your remote repository. Let’s pull these changes to your local repo.

#### Step 9: Pull Changes from GitHub remote to local
- In GitKraken, simply click the Pull button (top toolbar)
- your commit history will be updated with the new changes + information where these changes stem from (i.e. the remote repository)
- profit??


#### Step 10: Creating Conflicts

Now let's see what happens if the changes to a certain file do not match between the local and remote repositories.

**Online Edit**
- Go to your repository on GitHub.com and open ice_cream.md
- Click the ✏️ Edit button, make a small change (e.g., add a new ice cream flavor), and commit directly to the main branch

screenshot - edit_online

**Local Edit**
- Without pulling the remote change, open ice_cream.md locally and make a different change to the same section of the file
- Save and commit your change using GitKraken


**Pull the Conflict**
- In GitKraken, click the Pull button.
- GitKraken will detect the conflicting changes and show a merge conflict notification

 
 screenshot conflict_warning

#### Step 11: Resolve a Merge Conflict in GitKraken

Resolving conflicts ensures both sets of changes are merged without losing data. GitKraken’s visual tools make this process easier to understand and control.

- In the right panel, click the conflicted file ice_cream.md.
- GitKraken will open a 3-way merge editor:
    - The left side shows your local changes.
    - The right side shows the incoming changes from GitHub.
    - The middle area is where you choose how to resolve the conflict.

- Use the interface to:
    - Accept one side,
    - Combine both,
    - Or manually edit the result.

- Once resolved, click Mark as Resolved.
- Finally, commit the merge using the Commit panel, and click Push to update GitHub

- screenshot merge_conflict
--------------------------------------------------------------------------

```{dropdown} ### Git for terminal wizards
:icon: info
:open:

Git is foremost a command line tool, therefore it is quite easy to setup and manage projects directly.
If you are already are confident in working with the command-line interface, using pure git might be faster and more reproducible. Here are the steps above as you'd implement them. 

##### 1. Create your project folder
mkdir my-icecream_project
cd my-icecream_project

##### 2. Initialize a git repo
git init

##### 3. Add your files to staging (or use '.' to add everything)
git add .
touch ice_cream.md

##### 4. Commit the files
git commit -m "Initial commit"

##### 5. Add the remote repository (replace with your GitHub repo URL)
git remote add origin https://github.com/your-username/my-icecream_project.git

##### 6. Push to the remote (assumes your local branch is named 'main')
git push -u origin main

```
