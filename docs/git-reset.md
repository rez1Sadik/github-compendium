# Executing the Git Reset in VS Code

Visual Studio Code's graphical interface does not support creating "orphan branches." Therefore, the most efficient method is to execute the exact same commands using VS Code's Integrated Terminal.

## Step 1: Open the Integrated Terminal
1. Open your repository in VS Code.
2. From the top menu, select **Terminal > New Terminal** (or press `⌃ + \`` on your keyboard).
3. Ensure the terminal dropdown menu on the right indicates `zsh` or `bash`.

## Step 2: Execute the Commands
Copy and paste the sequence directly into the VS Code terminal. Press Enter after each line.

```bash
git checkout --orphan temp_branch
git add -A
git commit -m "Initial commit"
git branch -D main
git branch -m main
git push -f origin main
```
Note: This will completely overwrite the remote repository history, resulting in a single, clean commit.

### Step 3: Deploy the Updates
Because we previously set up GitHub Actions, deploying these changes is fully automated. You only need to push your local files to GitHub.

Run these commands in your VS Code terminal:
```bash
git add .
git commit -m "Apply minimalist theme and add Git Reset guide"
git push
```