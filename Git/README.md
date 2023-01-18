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

* **FEAT**
  * New features added
* **FIX**
  * Fixture on bugs
* **DOCS**
  * Documentation update
* **STYLE**
  * Code formatting
  * Adding missing symbols
  * No actual fixtures on codes
* **REFACTOR**
  * Refactoring on codes
* **TEST**
  * Adding unit test codes
* **CHORE**
  * Fixture on DevOps codes (builds, package managers, testings)

### Subject

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

### Body

* Write as **detailed as possible**, do not worry that commit messages are too long.
* Write **72 letters** per line at most, if you write more than 72 letters, **go on to the next line**.
* Write in focus on **'What you did'**, and **'Why you did it'**.
* **Do not** write to much on **'How you did'**. However, feel free to write a bit about the methodologies.

### Footer

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
| 🎨    | Changing format / structure of the code                        |
| 📰    | Making a new file                                               |
| 📝    | Minor change on codes                                           |
| 🐎    | Enhancing performance                                           |
| 📚    | Writing documentations                                          |
| 🐛    | Reporting bugs; use @FIXME tag also                             |
| 🚑    | Fixing bugs                                                     |
| 🔥    | Removing codes or files; use @CHANGED tag also                  |
| 🚜    | Changing directory structures                                   |
| 🔨    | Refactoring codes                                               |
| 💄    | Enhancing UI/UX, style                                          |
| ♿️  | Enhancing accessibility                                        |
| 🚧    | Commiting on Work-in-Progress codes; use @REVIEW tag also       |
| 💎    | New deployment or release                                       |
| 🔖    | Version tag                                                     |
| ✨    | Introducing new features                                        |
| 🚀    | DevOps works, buiilds, release, deployments, etc.               |
| 👽    | Code update following external API updates                      |
| 🙈    | .gitignore adds, or fixes                                       |
| 🗃    | Database related fixes                                          |
| 💡    | Comment addition or update in source code                       |
| 🔀    | Merge Branches                                                  |
| ⏪    | Revert Changes                                                  |
| 💩    | Bad codes that were wrote just for now, and needs to be fixed. |
| 🔒    | Fixing security issues                                          |
