# Command Line Basics

[Previous - Creating Repositories](./creating_repo.md)

The purpose of this page is to demonstrate some of the core git commands.

Here is a quick list of the commands discussed below.
| Command | Description |
| ------- | ----------- |
| Add | Prepares your code changes to be committed. |
| Commit | Packages your added code changes as a commit to be pushed. |
| Push | Pushes your committed code changes to your current branch in GitHub. |
| Checkout | Allows you to create or change branches. |
| Stash | Store your code changes and revert to the last commit. |
| Merge | Merge code from two branches together. |

## Pushing Code Changes

Pushing your code changes up to GitHub is a three-step process, and involves running three separate commands in sequence:

### Add

The **add** command prepares your code changes for committing, and is the first step necessary to push your code to GitHub.

You can add files individually by running:

`git add path/to/file`

More commonly, you will want to add all of your code changes at once, which can be done by running:

`git add .`

### Commit

The **commit** command packages your code together with a message to be pushed.

`git commit -m "your commit message"`

### Push

The **push** command takes all of your un-pushed commits and pushed them to GitHub.

`git push`

For newly created branches, the first push must have an additional argument:

`git push --set-upstream origin branch_name`

### Bringing It All Together

Below is the most common sequence of commands for pushing your changes:

```
git add .
git commit -m "my commit message"
git push
```

## Working With Branches

To keep different subtasks within the project organized, we can utilize git branches.
Every time you begin working on a new piece of the project, it is a good idea to
create a new branch.

### Checkout

To create a new branch, we use the **checkout** command:

`git checkout -b new_branch_name`

The *-b* flag indicates that this is a new branch. To switch to an existing branch,
simply use the checkout command without this flag:

`git checkout existing_branch_name`

### Stash

When working with branches, you will quickly notice that when checking out from
one branch to another, any un-committed code changes will move with you to the new
branch. Most of the time when changing branches, you will not want to take your changes
with you. You could just commit and push your changes, however you may not be far enough
with you current changes to want to push them. To get around this issue, we can
**stash** our changes.

`git stash`

You'll notice after stashing your changes, that your changes will be undone.
Don't worry, as your changes are still saved on your computer, and can be restored
using the **pop** command:

`git stash pop`

One important this to understand about stashed changes, is that they are not
specific to your branch. So, if you stash your changes on one branch, and then
run the **pop** command on another branch, your stashed changes from the other branch
will be applied. Furthermore, the **pop** command only restores the most recent stash.

With these restrictions in mind, there are a few additional commands we can use
to make **stash** easier to work. The first of which is the **save** command:

`git stash save "message describing what is stashed here"`

This command allows you to add a message to your stashed changes, which is especially
handy when used with the **list** command:

`git stash list`

This command will show you a list of all your stashes. If you used the **save**
command to give your stash a message, the message will be displayed alongside each
stash. Each stash will also have an id associated with it, in the form of
*stash@{number_of_stashed_back}*. When using the **pop** command by itself, it implicitly
chooses the most recent stash, which has an id of *stash@{0}*. You can however
define which stash is specifically restored with the **pop** command:

`git stash pop stash_id`

<u>Note:</u> If you have added any new
files, before stashing your changes, you will need to either stage the new file
(using the **add** command) or use the *-u* flag (meaning *unstaged*):

`git stash -u`

### Merge

Once you have finished working on a Git branch, you will likely want to merge
your changes into the master/main branch. To accomplish this you can use
the **merge** branch.

`git merge branch_to_merge_in`

When running the **merge** command, your current branch is the branch which
will have your changes applied, and the branch to merge in is provided with
the command.

<u>Note:</u> Sometime merging to branches which conflicting changes will
result in a *merge conflict*. To resolve this, you will need to go into the
files which have conflicting changes and manually edit the files. To prevent this,
it is good practice to merge the master/main branch into your branch (so that
any conflicts can bee resolved on your branch) before merging your branch up.

[Next - Best Practices](./best_practices.md)
