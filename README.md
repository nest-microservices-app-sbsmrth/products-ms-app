### Steps to Create Git Submodules

1. **Create a new repository on GitHub, which will work as the host repository**

2. **Clone the repository to your local machine**

3. **Add the submodule**, where `repository_url` is the URL of the repository and `directory_name` is the name of the folder where you want the submodule to be saved (the folder **must not already exist** in the project):

   ```bash
   git submodule add <repository_url> <directory_name>
   ```

4. **Add the changes to the repository** (run `git add`, `git commit`, and `git push`):

   Example:

   ```bash
   git add .
   git commit -m "Add submodule"
   git push
   ```

5. **Initialize and update submodules**  
   When someone clones the repository for the first time, they need to run the following command to initialize and update the submodules:

   ```bash
   git submodule update --init --recursive
   ```

6. **To update submodule references**  
   Run the following command to fetch the latest commits from the submodule's default branch:

   ```bash
   git submodule update --remote
   ```

---

### Important

When working with a repository that contains submodules, **you must first update and push changes in the submodule**, and **only afterward** push changes to the main repository.

If you do it the other way around, the submodule references in the main repository may be lost, and you'll have to resolve conflicts manually.
