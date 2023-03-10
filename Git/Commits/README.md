# Commit Messages Conventions

### Basic Structure of Commit Messages

* The commit messages should be in structure of:

```
  | Commit Type |: | Subject |
  | Body |
  | Footer |
```

* Each part should be devided with **empty lines**

### Commit Type

* **๐ฅ FEAT**
  * New features added
* **๐ ๏ธ FIX**
  * Fixture on bugs
* **๐ DOCS**
  * Documentation update
* **๐จ STYLE**
  * Code formatting
  * Adding missing symbols
  * No actual fixtures on codes
* **โ๏ธ REFACTOR**
  * Refactoring on codes
* **๐งช TEST**
  * Adding unit test codes
* **๐ฆ CHORE**
  * Fixture on DevOps codes (builds, package managers, testings)

### ๐ฉ Subject

* Do not write **special characters** for puctuation including periods.
* Do not use **past tenses** when using verbs.
  ```
  Fixed --> Fix
  Modified --> Modify
  Added --> Add
  ```
* Write in a **compact form**, do not finish the sentence, only write **main points.**
* Write first letter in **capital letter**.
* **Do not** write too long, in general, not over **50 letters**.

### ๐ฆพ Body

* Write as **detailed as possible**, do not worry that commit messages are too long.
* Write **72 letters** per line at most, if you write more than 72 letters, **go on to the next line**.
* Write in focus on **'What you did'**, and **'Why you did it'**.
* **Do not** write to much on **'How you did'**. However, feel free to write a bit about the methodologies.

### ๐ฆถ Footer

* Writing footers are optional. You do not have to write footers when the commit situation is not applicable.
* Write issue tracker ID on footers. Comm@ team uses GitHub Issue pages on each repositories.
* Write in form of ' | Issue Type |: | #Issue Number |.
* When referencing multiple issue tracker IDs, divide them with commas (,).
* These are examples of issue types.
  * Fixes: On issue fixture process, not resolved yet.
  * Resolves: Issues resolved.
  * Ref: Issues to reference for the commit.
  * Releated to: Issues that are relevent to the commit, and is not resolved.

### Example of commit messages

```
FEAT: "Add account registeration feature"

Added account registeration feature to fully deploy service. Added new REST API route 
for registeration.

Resolves: #12
Ref: #34
Related to: #56, #78

```

### + Commit message Emojis (Gitmojis)

* You may add emojis in front of commit type.
* Use emojis that are equivalent to the commit type.
* In GitHub, typing ":" will bring up a list of suggested emojis.
* 'Gitmoji' extension in Visual Studio Code will help you with using Gitmojis.
* 'Gitmoji Plus: Commit Button' plugin in JetBrain products will help you with using Gitmojis.
* Comm@ Team uses gitmojis as the following:

| Emoji | Description                                                     |
| ----- | --------------------------------------------------------------- |
| ๐จ    | Changingย format / structure of the code                        |
| ๐ฐ    | Making a new file                                               |
| ๐    | Minor change on codes                                           |
| ๐    | Enhancing performance                                           |
| ๐    | Writing documentations                                          |
| ๐    | Reporting bugs; use @FIXME tag also                             |
| ๐    | Fixing bugs                                                     |
| ๐ฅ    | Removing codes or files; use @CHANGED tag also                  |
| ๐    | Changing directory structures                                   |
| ๐จ    | Refactoring codes                                               |
| ๐    | Enhancing UI/UX, style                                          |
| โฟ๏ธ  | Enhancingย accessibility                                        |
| ๐ง    | Commiting on Work-in-Progress codes; use @REVIEW tag also       |
| ๐    | New deployment or release                                       |
| ๐    | Version tag                                                     |
| โจ    | Introducing new features                                        |
| ๐    | DevOps works, buiilds, release, deployments, etc.               |
| ๐ฝ    | Code update following external API updates                      |
| ๐    | .gitignore adds, or fixes                                       |
| ๐    | Database related fixes                                          |
| ๐ก    | Comment addition or update in source code                       |
| ๐    | Merge Branches                                                  |
| โช    | Revert Changes                                                  |
| ๐ฉ    | Bad codes that were wrote just for now, andย needs to be fixed. |
| ๐    | Fixing security issues                                          |
