Syncing your Obsidian notes to a GitHub repository is a popular way to back up your notes and access them across multiple devices. Obsidian itself doesn't have built-in Git or GitHub integration, but the community has developed plugins and workflows to achieve this. Here's a step-by-step guide to sync your notes with a GitHub repository:

---

## **1. Set Up a GitHub Repository**
1. **Create a new repository on GitHub**:
   - Go to [GitHub](https://github.com/) and log in.
   - Click the **`+`** icon in the top-right corner and select **New repository**.
   - Name your repository (e.g., `obsidian-notes`) and set it to **private** or **public**, depending on your preference.
   - Click **Create repository**.

2. **Copy the repository URL**:
   - You’ll need this URL later to connect your local Obsidian vault to GitHub.

---

## **2. Install Git on Your System**
If you don’t already have Git installed, download and install it:
- **Windows**: [Git for Windows](https://git-scm.com/download/win)
- **macOS**: Use Homebrew: `brew install git`
- **Linux**: Install via your package manager: `sudo apt install git` (Debian/Ubuntu) or `sudo dnf install git` (Fedora).

---

## **3. Initialize Git in Your Obsidian Vault**
1. **Open your Obsidian Vault**:
   - Locate your Obsidian vault folder on your system.

2. **Initialize a Git repository in your vault**:
   - Open a terminal and navigate to your vault folder using the `cd` command:
     ```bash
     cd path/to/your/obsidian-vault
     ```
   - Initialize the Git repository:
     ```bash
     git init
     ```

3. **Add the GitHub repository as a remote**:
   - Use the URL you copied earlier:
     ```bash
     git remote add origin https://github.com/USERNAME/REPOSITORY.git
     ```

---

## **4. Install the Obsidian Git Plugin**
Obsidian has a community plugin called **Obsidian Git** that automates the syncing process.

1. **Enable Community Plugins**:
   - Open Obsidian.
   - Go to **Settings > Community Plugins** and enable **Safe Mode** if it’s off.

2. **Install the Obsidian Git Plugin**:
   - Go to **Community Plugins** and search for **Obsidian Git**.
   - Click **Install** and then **Enable**.

3. **Configure the Plugin**:
   - Go to **Settings > Obsidian Git** and configure the plugin:
     - **Commit Message**: Set a default commit message, e.g., `Update notes`.
     - **Auto Save Interval**: Set how frequently the plugin auto-commits and pushes your changes (e.g., every 10 minutes).
     - **Auto Pull**: Enable this to automatically pull changes from the GitHub repository when you open Obsidian.

4. **Authenticate with Git**:
   - Ensure that your local Git installation is authenticated with GitHub. You can authenticate using:
     - **HTTPS**: Use a Personal Access Token (PAT) instead of your password. Follow [GitHub's guide](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token).
     - **SSH**: Set up an SSH key. Follow [GitHub's guide](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh).

---

## **5. Commit and Push Your Notes**
1. **Make Your First Commit**:
   - Open the terminal in your vault folder.
   - Stage all files:
     ```bash
     git add .
     ```
   - Commit the changes:
     ```bash
     git commit -m "Initial commit"
     ```

2. **Push to GitHub**:
   - Push your changes to the remote repository:
     ```bash
     git push -u origin main
     ```
   - If `main` does not exist, create it:
     ```bash
     git branch -M main
     git push -u origin main
     ```

---

## **6. Automate Syncing with the Plugin**
The **Obsidian Git** plugin will handle syncing for you:
- It will **automatically commit and push** changes to your GitHub repository at the interval you’ve configured.
- Whenever you open Obsidian, it will **pull the latest changes** from your GitHub repository.

---

## **7. (Optional) Sync Across Devices**
To access your notes on another device:
1. Install Obsidian and set up the **Obsidian Git** plugin.
2. Clone your GitHub repository to a local folder:
   ```bash
   git clone https://github.com/USERNAME/REPOSITORY.git
   ```
3. Open the cloned folder as an Obsidian vault.

---

## **8. Common Issues and Tips**
- **Permission Denied (publickey)**: If you’re using SSH and encounter this error, ensure your SSH key is added to your GitHub account.
- **Merge Conflicts**: If you edit notes on multiple devices simultaneously, you may need to resolve conflicts manually.
- **Ignore Certain Files**: Use a `.gitignore` file in your vault folder to exclude files (e.g., `.obsidian/`).

Example `.gitignore` for Obsidian:
```
.obsidian/
*.DS_Store
Thumbs.db
```

---

By following these steps, you’ll have a fully automated workflow to sync your Obsidian notes to a GitHub repository. Let me know if you run into any issues! 🚀