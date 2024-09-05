# 5- Tell git to ignore files
Make a file named `.gitignore` (you can also use nano/any-text-editor to do it)

Make a file that we would want `git` to ignore
```
touch ignore_this.txt
```

Add this file to `.gitignore`
```
echo ignore_this.txt >> .gitignore
```

Try `git add` a file we told `.gitignore` to not track

```
git add ignore_this.txt
```

```bash
## The following paths are ignored by one of your .gitignore files:
## ignore_this.txt
## Use -f if you really want to add them.
```

If you want to `add` a supposedly ignored file, use the `-f` flag

```bash
git add -f ignore_this.txt

# Then commit it too!
git commit -m "Add ignore_this.txt"
```

## BONUS - Use wildcard
You can use wildcard expressions in this file as well. Some common things in a `.gitignore` file are `.*`, `*~`, `~*`, which are often temporary or backup files.

***
**There should now be a `.gitignore` file in your directory.**