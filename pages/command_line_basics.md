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

### Push

### Bringing It All Together

Below is the most common sequence of commands for pushing your changes:

```
git add .
git commit -m "my commit message"
git push
```

[Next - Best Practices](./best_practices.md)
