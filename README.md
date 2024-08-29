



## Dev
1. Clone the repository
2. Create a .env file based on the .env.template
3. Run the command `git submodule update --init --recursive` to rebuild the submodules
4. Run the command `docker compose up --build`

### Steps to create Git Submodules
1. Create a new repository on GitHub
2. Clone the repository to the local machine
3. Add the submodule, where `repository_url` is the URL of the repository and `directory_name` is the name of the folder where you want to store the submodule (it should not exist in the project)
```
git submodule add <repository_url> <directory_name>
```
4. Add the changes to the repository (git add, git commit, git push)
Example:
```
git add .
git commit -m "Add submodule"
git push
```
5. Initialize and update submodules. When someone clones the repository for the first time, they should run the following command to initialize and update the submodules:
```
git submodule update --init --recursive
```
6. To update the submodule references:
```
git submodule update --remote
```


## Important
When working in the repository that has submodules, **first update and push** in the submodule and **then** in the main repository.

If done in reverse order, the submodule references in the main repository will be lost, and we'll have to resolve conflicts.