# dev_playground
This repo provides an area for exploring merge conflict resolution, branching, and merging with Jupyter notebooks
I have made changes on the remote server.
# Installation
To prepare the correct environment with nbdev and other relevant notebooks for data science in Jupyter, you'll need to first create the and activate the relevant conda virtual environment.  The steps are outlined below:

## 1. Clone this notebook locally
To clone this notebook locally, scroll up to the green button which says `Use this template`.  Click on this.  In the window that opens, under `Owner`, make sure to choose your own username.  Title the repo as you like, but probably go ahead and use `dev_playground` for this investigation.  Complete other fields as desired.

Now that you've created this remote repo on your own username, you'll need to clone it to your local filesystem (computer).  Click the green `Clone\Download` button in your repo, and click the clipboard to copy the git repo path.

On your local filesystem, go to a terminal (OSX) or open Git Bash (Windows), and `cd` if necessary to the directory in which you'd like to clone this repo.  Type `git clone` and then paste the remote git repo path (for Git Bash use `shift`+`insert` to paste).  For example, `git clone https://github.com/vanderbilt-data-science/dev_playground.git`.  You may be asked for some authentication parameters about your GitHub account and password, and fill them in accordingly.  Now, you have the repo locally.

## 2. Create conda virtual environment using supplied yml file
Now, you're going to create a virtual environment based on the yml file in the repo.  OSX users can continue to use the same terminal, but Windows users will likely have to switch to the Anaconda Prompt.  To do this, click the Windows button and then under search (magnifying class), type "Anaconda Prompt".  Click the program when it is generated.  Use `cd` to navigate to the parent directory of your cloned repo.

Now that you're in your parent directory, use `cd` to enter the repo.  Type `conda create -f environment.yml`.  Conda will now create an environment based on the supplied packages.  This may take some time.  After this is finished, type: `conda activate nbdev_env`.  This will activate your environment.

All done!
