# Github access via SSH

## Step 1: Generate an SSH Key (if you don’t have one
Open Terminal (or Git Bash on Windows).

Run the following command (replace <your_email@example.com> with your email):

```
ssh-keygen -t rsa -b 4096 -C "<your_email@example.com>"
```

When prompted, press Enter to accept the default file location.

Optionally, set a passphrase for added security.

## Step 2: Add Your SSH Key to the SSH Agent
Start the SSH agent in the background:

```
eval "$(ssh-agent -s)"
```
Add your SSH private key to the SSH agent:

```
ssh-add ~/.ssh/id_rsa
```
(Replace id_rsa with your key filename if you used a different name.)

## Step 3: Add Your SSH Key to Your GitHub Account
Copy the SSH Key to your clipboard:

```
cat ~/.ssh/id_rsa.pub
```
(Again, replace id_rsa.pub with your public key filename if different.)

Go to GitHub:

Log in to your GitHub account.
Navigate to Settings (click on your profile picture in the top right).
Select SSH and GPG keys from the sidebar.
Click on New SSH key.
Paste your SSH key into the "Key" field, give it a title, and click Add SSH key.

## Step 4: Clone the Private Repository via SSH
Go to the private repository on GitHub.

Click on the Code button and select SSH.

Copy the SSH URL (it will look like git@github.com:username/repo.git).

Open your terminal and run:

```
git clone git@github.com:username/repo.git
```

## Step 5: Verify the Setup
After cloning, navigate into the repository folder:

```
cd repo
```
You can now pull, push, and perform other Git operations on the private repository using SSH.

### Notes
Ensure your SSH key is added to your GitHub account before trying to clone the repository.
If you encounter any issues, check your SSH configuration or GitHub settings for troubleshooting.
By following these steps, you should be able to add an agent service for GitHub and download a private repository using your SSH key.
