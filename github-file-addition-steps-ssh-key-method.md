## Adding Files to a GitHub Repository using SSH Key Authentication

1. **Generate SSH key:**
   - Open your terminal or command prompt.
   - Run the following command to generate a new SSH key:
     ```shell
     ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
     ```
     Replace `"your_email@example.com"` with your GitHub email address.
   - You will be prompted to enter a file path to save the key. Press Enter to accept the default location (`~/.ssh/id_rsa`) or specify a custom path.
   - You will be prompted to enter a passphrase for the key. It's optional but recommended for added security. Press Enter to skip or enter a passphrase.

2. **Add SSH key to GitHub:**
   - Run the following command to copy the public key to your clipboard:
     ```shell
     cat ~/.ssh/id_rsa.pub | pbcopy
     ```
     If you're using Windows, replace `pbcopy` with `clip`.
   - Go to the GitHub website (https://github.com) and log in to your account.
   - Click on your profile picture in the top right corner and select "Settings".
   - In the left sidebar, click on "SSH and GPG keys".
   - Click on the green "New SSH key" button.
   - Give the key a descriptive title, such as "My Personal SSH Key".
   - Paste the copied public key into the "Key" field.
   - Click on the "Add SSH key" button to save the key.

3. **Clone the repository using SSH:**
   - On the repository page, click on the green "Code" button and copy the SSH URL.
   - Open your terminal or command prompt and navigate to the directory where you want to clone the repository.
   - Run the following command to clone the repository using SSH:
     ```shell
     git clone git@github.com:<username>/<repository>.git
     ```
     Replace `<username>` with your GitHub username and `<repository>` with the name of the repository.

4. **Add files to the repository:**
   - Place the files you want to add to the repository in the cloned directory.
   - Use the `git add` command to add the files. For example, to add all files, you can run:
     ```shell
     git add .
     ```
   - Use the `git commit` command to create a commit for the added files. Provide a meaningful commit message to describe the changes. For example:
     ```shell
     git commit -m "Add files to the repository"
     ```

5. **Push changes to GitHub:**
   - Use the `git push` command to push the changes to the GitHub repository:
     ```shell
     git push origin <branch_name>
     ```
     Replace `<branch_name>` with the name of the branch you want to push to. By default, the main branch is named "master" or "main".

6. **Verify the changes on GitHub:**
   - Go back to your GitHub repository page and refresh it.
   - You should see the newly added files listed in the repository.

---
