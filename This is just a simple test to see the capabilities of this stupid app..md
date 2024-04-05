### Setting Up Obsidian with Obsidian Git Plugin

1. **Download Obsidian:**
   - Install Obsidian using the following command:
    ```
     flatpak install flathub md.obsidian.Obsidian
    ```
   - Find Obsidian on [Flathub](https://flathub.org/apps/md.obsidian.Obsidian).

2. **Download Obsidian Git:**
   - Get the Obsidian Git from [GitHub](https://github.com/denolehov/obsidian-git).
   - Extract the downloaded zip file and copy the `obsidian-git` file.

3. **Integration with Obsidian:**
   - Open Obsidian and create a new folder.
   - Navigate to the chosen directory and access the `.obsidian` folder.
   - Inside, create a `plugins` folder and paste the `obsidian-git` file into it.
   - Enable community plugins in Obsidian and scan for new ones. You should see Obsidian Git appear; enable it.

### Integrating with GitHub

1. **Install Git:**
   - Download Git from [here](https://git-scm.com/downloads).

2. **Create a Personal Access Token (PAT):**
   - Follow the instructions to create a [Personal Access Token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token#creating-a-personal-access-token-classic).
   - ![[Pasted image 20240406003238.png]]

3. **Install Obsidian Git Plugin:**
   - Install the [Obsidian Git](https://github.com/denolehov/obsidian-git/wiki/Installation) community plugin.

4. **Set Up Repository:**
   - Create a folder to store the repository (e.g., `remote-blog/`).
   - Set scopes to `repo` & expiration to no expiration.

5. **Clone Remote Repository:**
   - Run the command (CMD/Ctrl + P): `Clone an existing remote repo`.
   - ![[Pasted image 20240406003254.png]]
   - Paste the URL of the forked repository with your Personal Access Token.

   ```
   https://<PERSONAL_ACCESS_TOKEN>@github.com/<USERNAME>/<REPO>.git
   ```

   For example:

   ```
   https://ghp_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX@github.com/deathraymind/obsidian.git
   ```

6. **Restart Obsidian** after setting up the repository.

### Making Edits and Backing Up

1. Make edits to your notes within Obsidian.

2. To publish your notes:
   - Run the command “Obsidian Git: Create backup” by opening the command palette (CMD/Ctrl + P).

### Additional Notes

- Ensure the file is created in the vault when selecting the directory.
- If encountering email errors on Linux, set up Git email globally:
  ```
  git config --global user.email "your_email@example.com"
  ```
  Replace `"your_email@example.com"` with your actual email address.

Remember to follow security practices and keep your Personal Access Token and email confidential.
