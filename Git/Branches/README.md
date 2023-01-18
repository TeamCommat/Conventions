# Git Branch Conventions

## Types of branches

### **👑 'master'** branch

* Use master branch for the main branch.
* master branch should always be eligible to deploy right away.
* Do not touch master branch directly in any circumstances.
* To update master branch, the process should be done by merging from develop, or hotfix branch.

### **🏗️ 'develop'** branch

* **Develop branch** is for developing the next version of the service.
* When all features for the next version is fully added, and all bugs and errors are resolved, merge develop branch to master branch.
* Developing process should be managed mainly with develop branch.
* Do not touch develop branch directly in any circumstances.
* To update develop branch, the process should be done by merging supporting branches.

### **🛟 Supporting** branches

* Supporting branches help developers to track up-to-date features and development processes.
* Use suitable supporting branches for your development.

#### 1) 🪄 **'feature'** branch

* **Feature branch** is for developing new features.
* When new features are needed, bifurcate from the develop branch.
* After development processes are done, merge to develop branch.
* Delete feature branch that are not needed anymore.

#### 2) 🛠️ **'fixture'** branch

* **Fixture branch** is for fixing bugs that occured from develop branch.
* Manage fixture branch like a feature branch.

#### 3) 🚀 **'release'** branch

* **Release branch** is for preparing deployment of newest version
* By using release branch, the development teams can work on the next version while some are preparing for release.
* Conduct final bug fixes, final examination, fixing documentation, and DevOps setups on release branch.

#### 4) 🚨 **'hotfix'** branch

* **Hotfix branch** is for fixing urgent bugs that occured to the master branch.
* When a bug is reported, bifurcate from the master branch.
* After fixing process is done, merge to the master branch.
* Merge to the develop branch also for update.


## How to name branches

### master branch, develop branch

* **Do not** use other names than 'master' and 'develop'

### feature branch

* Name the branch **'feature/{short explanation}**
* For example, in login feature addition process, name the branch **'feature/login'**

### fixture branch

* Name the branch **'fixture/{issue tracker ID}/{short explanation}**
* For example, if a bug is reported in a login process, name the branch **'fixture/123/login'**

### release branch

* Name the branch **'release/{version number}**
* For example, for version 1.1.1 release, name the branch **'release/1.1.1'**

### hotfix branch

* Name the branch **'hotfix/{version number}**
* For example, for version 1.1.2 hotfix, which is the master branch version, name the hotfix branch **'hotfix/1.1.2'**
