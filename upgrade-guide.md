# AnythingLLM Fork Upgrade Guide

## Update Repository

1. Add original repository as remote:
```bash
git remote add upstream https://github.com/mintplex-labs/anything-llm.git
```

2. Verify remotes:
```bash
git remote -v
```

3. Save local changes:
```bash
git stash
```

4. Update local master:
```bash
git fetch upstream
git checkout master
git merge upstream/master
```

5. Handle conflicts:
```bash
# If conflicts exist
git status  # Check conflicting files
git diff    # Analyze differences
# Manually resolve conflicts
git add .
git commit -m "Merge upstream changes"
```

6. Restore changes:
```bash
git stash pop
```

## Testing

1. Verify functionality:
```bash
docker-compose up --build
```

2. Test custom features

## Rollback (if needed)

```bash
git reset --hard HEAD@{1}  # Return to previous commit
git push -f origin master  # Force push to remote
```