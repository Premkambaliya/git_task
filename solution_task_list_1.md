## Part 1: Introduction to Version Control and Git

#### Task 1: Install and Configure Git
1. Configure Git with your username and email:
```
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```
ans:- git config globel using for configrution settings set and manage.

2. View your Git configuration:
```
git config --list
```
ans:- git config --list using for show a list in list our name ,email , path etc.

#### Task 2: Initialize a Repository

1. Create a new project folder and navigate to it:
```
mkdir MyProject
cd MyProject
```
ans:- mkdir using for make new folder and cd using for you go inside any folder

2. Initialize it as a Git repository:
```
git init
```
ans:- git init use for initilaizetion repo 

#### Task 3: Create a File and Make Multiple Commits

1. Create a new file and add content:  
   ```bash
   echo "My First Project" > README.md
   ```

   ans:- echo using for make a new file and in file write a message

2. Stage the file:  
   ```bash
   git add README.md
   ```

   ans:- git add use for you add a file in repo but first you initilaizetion repo 

3. Commit the file:  
   ```bash
   git commit -m "Initial commit: Added README.md"
   ```

   ans:- after git add you use git commit that useing for any message write in file in your repo

4. Make changes to the file:  
   ```bash
   echo "Added a description" >> README.md
   ```

   ans:- echo using for make a new file and in file write a message

5. Stage and commit the changes:  
   ```bash
   git add README.md
   git commit -m "Updated README with a description"
   ```

   ans:- git add use for you add a file in repo but first you initilaizetion repo 
   
   ans:- after git add you use git commit that useing for any message write in file in your repo

#### **Task 4: Check Status and Log**
1. Check the repository’s current status:  
   ```bash
   git status
   ```

   ans:- git status useing for cheak a status of your files

2. View commit history in detail:  
   ```bash
   git log --oneline --graph --decorate
   ```
   Example Output:  
   ```
   * 2f8d6a2 (HEAD -> main) Updated README with a description
   * d3c4b21 Initial commit: Added README.md
   ```

   ans:- git log using for show a history of git commit in your files

   #### **Task 5: Create and Clone a Repository**

1. Create a repository on GitHub named `example-repo`.  
2. Clone it locally:  
   ```bash
   git clone http://codinggita.com/example-repo
   ```
   ans:- git clone use for a clone any repo

#### **Task 6: Understanding the Git Workflow**
- Example Workflow:  
   1. Make changes to a file in the **working directory**:  
      ```bash
      echo "Workflow example" > workflow.md
      ```

ans:- echo using for make a new file and in file write a message

   2. Stage the file:  
      ```bash
      git add workflow.md
      ```

         ans:- git add use for you add a file in repo but first you initilaizetion repo 

   3. Commit the file to the **repository**:  
      ```bash
      git commit -m "Added workflow example"
      ```

         ans:- after git add you use git commit that useing for any message write in file in your repo

---

### **Part 2: Working with Repositories**

#### **Task 7: Branching and Merging**
1. Create a new branch for a feature:  
   ```bash
   git branch feature-login
   git checkout feature-login
   ```
   Or use:  
   ```bash
   git checkout -b feature-login
   ```

ans:- git branch use for goto first brach to second branch

ans:- git cheakout use for create new branch, deleate branch and swetch branch

2. Add a new file and commit changes:  
   ```bash
   echo "Login Page" > login.html
   git add login.html
   git commit -m "Added login page"
   ```

    ans:- echo using for make a new file and in file write a message

    ans:- git add use for you add a file in repo but first you initilaizetion repo 
    
    ans:- after git add you use git commit that useing for any message write in file in your repo

3. Merge the feature branch into `main`:  
   ```bash
   git checkout main
   git merge feature-login
   ```
   ans:- git cheakout use for create new branch, deleate branch and swetch branch


#### **Task 8: Handling Merge Conflicts**
1. Create two branches:  
   ```bash
   git branch branch-A
   git branch branch-B
   ```
   ans:- git branch use for goto first brach to second branch

2. Modify the same line in `README.md` in both branches.  
3. Merge `branch-A` into `main`:  
   ```bash
   git checkout main
   git merge branch-A
   ```
   ans:- git cheakout use for create new branch, deleate branch and swetch branch

4. Attempt to merge `branch-B` into `main` (this will cause a conflict):  
   ```bash
   git merge branch-B
   ```
5. Resolve the conflict manually in `README.md`, then:  
   ```bash
   git add README.md
   git commit -m "Resolved merge conflict between branch-A and branch-B"
   ```
    ans:- git add use for you add a file in repo but first you initilaizetion repo 
    
    ans:- after git add you use git commit that useing for any message write in file in your repo

#### **Task 9: Renaming and Deleting Branches**
1. Rename a branch:  
   ```bash
   git branch -m old-branch-name new-branch-name
   ```
2. Delete a branch:  
   ```bash
   git branch -d feature-login
   ```

---

### **Part 3: Advanced Git Operations**

#### **Task 10: Using Git Stash**
1. Make changes to a file but don’t commit:  
   ```bash
   echo "Temporary work" >> temp.md
   ```
   ans:- echo using for make a new file and in file write a message

2. Stash the changes:  
   ```bash
   git stash
   ```
3. View stashed changes:  
   ```bash
   git stash list
   ```
4. Apply the stashed changes:  
   ```bash
   git stash apply
   ```
5. Drop the stash after applying:  
   ```bash
   git stash drop
   ```

#### **Task 11: Rewriting History with Interactive Rebase**
1. Create multiple commits:  
   ```bash
   echo "Commit 1" > file1.txt && git add file1.txt && git commit -m "Commit 1"
   echo "Commit 2" > file2.txt && git add file2.txt && git commit -m "Commit 2"
   echo "Commit 3" > file3.txt && git add file3.txt && git commit -m "Commit 3"
   ```
2. Squash commits into one:  
   ```bash
   git rebase -i HEAD~3
   ```
   Example: Replace `pick` with `squash` for the second and third commits.

#### **Task 12: Cherry-Picking Commits**
1. Create a new branch:  
   ```bash
   git checkout -b cherry-pick-example
   ```

   ans:- make new branch and switch branch

2. Cherry-pick a specific commit from another branch:  
   ```bash
   git cherry-pick <commit-hash>
   ```

#### **Task 13: Tagging Commits**
1. Tag the current commit:  
   ```bash
   git tag -a v1.0 -m "Version 1.0 release"
   ```
2. Push the tag to the remote repository:  
   ```bash
   git push origin v1.0
   ```
ans:- git push use for push repo in github
#### **Task 14: Working with Remote Repositories**
1. Add a remote repository:  
   ```bash
   git remote add origin <repository-url>
   ```
2. Push your changes to the remote repository:  
   ```bash
   git push origin main
   ```
   ans:- git push use for push repo in github

#### **Task 15: Forking and Contributing**
1. Fork a repository on GitHub.  
2. Clone the fork locally:  
   ```bash
   git clone <forked-repo-url>
   ```
   ans:- git clone using for clone repo

3. Create a new branch, make changes, and push:  
   ```bash
   git checkout -b fix-typo
   echo "Typo fixed" >> README.md
   git add README.md
   git commit -m "Fixed a typo"
   git push origin fix-typo
   ```
    ans:- make new branch and switch branch

    ans:- echo using for make a new file and in file write a message

    ans:- git add use for you add a file in repo but first you initilaizetion repo 
    
    ans:- after git add you use git commit that useing for any message write in file in your repo

    ans:- git push use for push repo in github

4. Open a pull request on GitHub.  

---

### **Part 4: Additional Practice**

#### **Task 16: Simulate Team Collaboration**
1. Create a repository and share it with a friend.  
2. Both make changes to the same file simultaneously.  
3. Practice resolving merge conflicts and pushing changes.

#### **Task 17: Git Ignore**
1. Create a `.gitignore` file:  
   ```bash
   echo "node_modules/" > .gitignore
   ```
2. Add files and ensure ignored files are not staged:  
   ```bash
   git add .
   ```
ans:- git add. useing for all file add in repo