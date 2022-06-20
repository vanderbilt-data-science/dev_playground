# dev_playground
This repo provides an area for exploring merge conflict resolution, branching, and merging with Jupyter notebooks.

# Installation
To prepare the correct environment with nbdev and other relevant notebooks for data science in Jupyter, you'll need to first create the and activate the relevant conda virtual environment.  The steps are outlined below:

## 1. Clone this notebook locally
To clone this notebook locally, scroll up to the green button which says `Use this template`.  Click on this.  In the window that opens, under `Owner`, make sure to choose your own username.  Title the repo as you like, but probably go ahead and use `dev_playground_[name]` (e.g., `dev_playground_bell`) for this investigation.  Complete other fields as desired.

Now that you've created this remote repo on your own username, you'll need to clone it to your local filesystem (computer).  Click the green `Clone\Download` button in your repo, and click the clipboard to copy the git repo path.

On your local filesystem, go to a terminal (OSX) or open Git Bash (Windows), and `cd` if necessary to the directory in which you'd like to clone this repo.  Type `git clone` and then paste the remote git repo path (for Git Bash use `shift`+`insert` to paste).  For example, `git clone https://github.com/csbell-vu/dev_playground_bell.git`.  You may be asked for some authentication parameters about your GitHub account and user access token, and fill them in accordingly.  Now, you have the repo locally.

## 2. Create conda virtual environment using supplied yml file
Now, you're going to create a virtual environment based on the yml file in the repo.  OSX users can continue to use the same terminal, but Windows users will likely have to switch to the Anaconda Prompt.  To do this, click the Windows button and then under search (magnifying class), type "Anaconda Prompt".  Click the program when it is generated.  Use `cd` to navigate to the parent directory of your cloned repo.

Now that you're in your parent directory, use `cd` to enter the repo.  Type `conda env create -f environment.yml`.  Conda will now create an environment based on the supplied packages.  This may take some time.  After this is finished, type: `conda activate nbdev_env`.  This will activate your environment.

All done!

# During Workshop
In this workshop, you'll see and try, hands-on, resolving merge conflicts. You'll watch first, and then try it on your own in breakout rooms. Once in breakout rooms, you can take the next set of steps to try out and resolve merge conflicts. FIRST, decide who is **Person 1** and **Person 2** in your group.

## Add Collaborator to Repo
Here, we will be using **Person 1's** repo. Thus:
1. Person 1 - add Person 2 to your repo using their name, username, or email address.

## Open Jupyter, create branch, make changes, and push to your branch on GitHub
Now, we'll begin doing our work.
1. **Person 1** and **Person 2**: clone Person 1's repo to your local computer
2. Make sure you (both) have activated your virtual environment (`conda activate nbdev_env` if you followed the Installation instructions above) using the terminal (on OSX) or the Anaconda Prompt (on Windows).
3. `cd` into your repository. Type `jupyter lab` to start an instance of Jupyter. Wonderful.
4. Create a branch using the terminal (you can create a new terminal within Jupyter lab by clicking the `+` button):
  * **Person 1:** your branch will be called `mult3_person1`. To create your branch, type `git checkout -b mult3_person1` and click enter.
  * **Person 2:** your branch will be called `mult4_person2`. To create your branch, type `git checkout -b mult4_person2` and click enter.
5. Follow the instructions in the `dev_nb` notebook.

## Resolve merge conflict
1. First, we'll go ahead and merge in Person 1's pull request. Person 2 should review it and merge it in.
2. Person 1 should now review Person 2's pull request. Note that the PR cannot be merged as is. You'll remedy this.

### Person 1 merge resolution steps:
1. Note the name of the branch. It should be `mult4_person2`.
2. Come back to your local computer Jupyter. Open the terminal. Switch to the main branch `git checkout main`. You'll do a new pull by typing `git pull` to update the main branch to its new current state (because a new PR has been merged in).
3. Now, switch to Person 2's branch by typing `git checkout mult4_person2`.
4. You'll now merge main into this branch. To do this, type `git merge main`.
5. Oh no! A merge conflict! Type `git status`. Notice that you're still merging, you just need to fix the conflicting files.
6. To fix conflicting files, type `nbdev_fix_merge`.
7. It prompts us to fix certain files ourselves. Let's take a look. Normally, you'd resolve this by choosing one or the other. However, in this case, we can have both. Remove all `>>>>>`, `======`, and `<<<<<<<` annotations noting merge conflicts.
8. Save your file.
9. Now, at the command line, type `nbdev_clean_nbs`. Also, `nbdev_build_lib`. Wonderful.
10. Type `git status`. Add and commit all the updated/new files (see the instructions in the `dev_nb` notebook for more details on syntax.
11. Push this fixed branch using `git push origin mult4_person2`.
12. Return to GitHub and review the PR. Should be able to merge - approve and merge it on in!

Wonderful!

## Switch
Repeat the steps above, except this time, you'll add a new cell at the end of the notebook. Person 1 will add any function they like, and Person 2 will add any function they like. Make sure to create new branches. Repeat the steps above, except this time, **Person 1** should review and merge Person 2's PR first. Then, Person 2 should review Person 1's pull request and resolve the merge conflict.