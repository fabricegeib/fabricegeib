# Git

```
git config --global user.name "Fabrice Geib WSL1 Debian"
git config --global user.email "fabricegeib@gmail.com"

git init

git status

git add .

git commit -m "Message"

# remove file
git rm --cached <file>

# remove tracked folder recursovely
git rm -r --cached <folder>
```

## GitHub CLI

```
gh

gh repo create iamfabriceg.xyz --private --source=. --remote=upstream --push

gh repo clone user/repo .

gh repo sync
```
