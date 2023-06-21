 Step-by-Step Guide to Add a File to GitHub

1. Open the command prompt or terminal on your computer.

2. Navigate to the local repository directory where your file is located using the `cd` command. For example:

```cmd
cd /path/to/repository
```

3. Use the `git add` command followed by the file name or path to add the file to the staging area. For example, to add a file named "example.txt":

```cmd
git add example.txt
```

If you want to add all files in the current directory and its subdirectories, you can use the following command instead:

```cmd
git add .
```

4. Confirm that the file has been added to the staging area by running `git status`:

```cmd
git status
```

The file should appear under the "Changes to be committed" section.

5. Finally, commit the changes using the `git commit` command:

```cmd
git commit -m "Add example.txt"
```

Replace "Add example.txt" with a descriptive commit message for your file

6. If you haven't set the upstream repository yet, you will need to set it using the `git remote add origin` command:

```cmd
git remote add origin <repository_url>
```

Replace `<repository_url>` with the URL of your GitHub repository.

7. Push the changes to GitHub using the `git push` command:

```cmd
git push origin <branch_name>
```

Replace `<branch_name>` with the name of the branch you want to push the changes to (e.g., "main" or "master").

After executing these steps, the file will be added to your GitHub repository. Make sure you have the necessary permissions to push changes to the repository.