# 4- Exploring History (`git diff & show`)

## Difference between current file and N commit ago (`git diff HEAD`)

Let's add another line to `foo.txt`

```
echo world >> foo.txt
```

Check what is different from your current version of `foo.txt` compared to the last commit

```
git diff HEAD foo.txt
```

> You see that "world" is preceded by a plus sign, indicating it is an insertion.

Check difference compared to two commits ago

```
git diff HEAD~1 foo.txt
```

You can check difference between the current file against a specific commit based on its identifier (the unique identifier is different for you, use `git log` to check!)

```
git diff <unique identifier> foo.txt
```


## What was done in ____ commit? (`git show`)

Sometimes we want to check what was done during a certain commit (instead of comparing differences)

```
git show HEAD~1 foo.txt
```

***
**You have now compared different versions of a file using `git diff` and check its changes during a specific commit using `git show`.**