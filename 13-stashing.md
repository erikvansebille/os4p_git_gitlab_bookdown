# Stashing (`git stash`)

There are times when you may want to stash (set aside) your current work rather than commit.

Examples:

* Realized that you were working on the wrong branch
* Realized that you and your collaborator are working on the same lines and resolving conflicts may be difficult
* Need to immediately switch to another branch and do not want to commit the change
* Partial commit

```
git branch
touch temp_script.sh
git add temp_script.sh
git status
```

## Stash

```
git stash
git stash list
```

## Unstash

```
git stash apply
git stash list
```

```
git stash apply --index
git stash list
```

## Delete Stash

```
git stash drop
git stash list
```


Note: You can perform both `git stash apply` and `git stash drop` at the same time by entering `git stash pop`.

## Branch a Stash

Probably the best use of stash: `git stash branch <branch_name>`

```
git stash branch <branch_name>
```