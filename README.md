# README
This is a blog about My Coding Life.

## How to init this project
```bash
git checkout --orphan gh-pages
git commit --allow-empty -m "Init empty branch"
git push origin gh-pages
git checkout main
echo "dist/" >> .gitignore
git worktree add dist gh-pages
```
