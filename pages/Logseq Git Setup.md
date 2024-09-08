### Setting Up Git Hooks for Logseq

Follow these steps to set up Git hooks for your Logseq repository. These hooks will ensure your repository is up-to-date before committing and push changes automatically after committing.

1. **Clone Your Git Repository:**
	- Go to your local drive and right-click on it.
	- Select `New Terminal at Folder`. If this option isn’t available, follow [this link](https://support.apple.com/en-us/HT201236) to enable it.
	- In the terminal, type:
	  ```bash
	  git clone git@github.com:{your-username}/{your-reponame}.git
	  ```
	  Replace `{your-username}` with your GitHub username and `{your-reponame}` with your repository name. Press Enter.
	- If prompted to authorize the connection, type `yes` and hit Enter.
	  
	  2. **Navigate to the Hooks Directory:**
	- After cloning, navigate into your repository folder:
	  ```bash
	  cd /path/to/your/repository
	  ```
	- Change into the `.git/hooks` directory:
	  ```bash
	  cd .git/hooks
	  ```
	  
	  3. **Create and Edit the `pre-commit` File:**
	- Open the `pre-commit` file with `nvim`:
	  ```bash
	  nvim pre-commit
	  ```
	- Paste the following code into `pre-commit`:
	  ```sh
	  #!/bin/sh
	  #
	  #
	  # Pull before committing
	  # Credential handling options:
	  #  - hardcode credentials in URL
	  #  - use ssh with key auth
	  #  - https://git-scm.com/docs/git-credential-store
	  #  - git credential helper on windows
	  
	  # Redirect output to stderr, uncomment for more output for debugging
	  # exec 1>&2
	  
	  output=$(git pull --no-rebase)
	  
	  # Handle non error output as otherwise it gets shown with any exit code by logseq
	  if [ "$output" = "Already up to date." ]; then
	      # no output
	      :
	  else
	      # probably error print it to screen
	      echo "${output}"
	  fi
	  
	  git add -A
	  ```
	- Save and exit `nvim` (press `Esc`, then type `:wq` and hit Enter).
	  
	  4. **Create and Edit the `post-commit` File:**
	- Open the `post-commit` file with `nvim`:
	  ```bash
	  nvim post-commit
	  ```
	- Paste the following code into `post-commit`:
	  ```sh
	  #!/bin/sh
	  
	  git push origin main
	  ```
	- Save and exit `nvim` (press `Esc`, then type `:wq` and hit Enter).
	  
	  5. **Make the Hook Scripts Executable:**
	- Ensure the scripts are executable by running:
	  ```bash
	  chmod +x ./pre-commit && chmod +x ./post-commit
	  ```
	  
	  6. **Configure Logseq for Git Integration:**
	- Open Logseq and add the folder containing the `.git` directory as your new graph.
	- Navigate to `Logseq > Settings > Version control`.
	- Toggle on `Enable Git auto commit`. If you prefer manual commits, consider using the Git plugin by haydenull for manual control.
	  
	  7. **Verify Your Setup:**
	- Make some changes in Logseq and wait a few minutes to see if the changes appear on GitHub.