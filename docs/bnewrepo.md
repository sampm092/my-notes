# Github

## When you want to connect with git

Create a new repository on the command line

```
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin <your repo link>
git push -u origin main
```

…or push an existing repository from the command line

```
git remote add origin <your repo link>
git branch -M main
git push -u origin main
```

## Renaming Github

### Step 1: Rename the Repository on GitHub

<ol>1.	Go to GitHub and navigate to the repository you want to rename.</ol>
<ol>2.	Click on the "Settings" tab in the repository.</ol>
<ol>3.	Change the repository name in the "Repository name" field under the "General" section.</ol>
<ol>4.	Save your changes.</ol>

### Step 2: Update Local Repository in VSCode
After renaming the repository on GitHub, you need to update the remote URL in your local repository within VSCode. Follow these steps:
<ol>1.	Open VSCode and make sure you have the repository opened in your workspace.</ol>
<ol>2.	Open the terminal inside VSCode (Ctrl + ~ or View -> Terminal).</ol>
<ol>3.	Run the following command to check the current remote URL:
```
bash
```
Copy code
```
git remote -v
```
You will see something like this:
```
bash
```
Copy code
```
origin  https://github.com/username/old-repo-name.git (fetch)
origin  https://github.com/username/old-repo-name.git (push)
```
</ol>
<ol>4.	Update the remote URL to the new repository name:
```
bash
Copy code
git remote set-url origin https://github.com/username/new-repo-name.git
```
</ol>
<ol>5.	Verify the change by running:
```
bash
```
Copy code
```
git remote -v
```
You should see the updated URL:
```
bash
```
Copy code
```
origin  https://github.com/username/new-repo-name.git (fetch)
origin  https://github.com/username/new-repo-name.git (push)
```
</ol>
<ol>6.	After updating the remote URL, you can continue working with your repository in VSCode, and any future pushes or pulls will be directed to the renamed repository.</ol>
### Step 3: Test the Change
You can test if the change was successful by trying to push or pull any updates:
```
bash
```
Copy code
```
git push origin main
```
This ensures that the remote repository is correctly linked with your local repository in VSCode.</ol>

