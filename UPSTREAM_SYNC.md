# Quick Reference: Syncing Upstream Changes

## Standard Sync Workflow

```bash
# 1. Fetch latest from upstream (safe, doesn't change your code)
git fetch upstream

# 2. Check what's new
git log HEAD..upstream/main --oneline

# 3. Switch to main branch
git checkout main

# 4. Merge upstream changes
git merge upstream/main

# 5. Resolve any conflicts (if needed)
# Edit conflicted files, then:
git add <resolved-files>
git commit

# 6. Push to your fork
git push origin main
```

## Before You Sync

1. **Commit or stash your current work**
   ```bash
   git status  # Check for uncommitted changes
   git add . && git commit -m "WIP: my current changes"
   # OR
   git stash
   ```

2. **Create a backup branch** (optional but recommended)
   ```bash
   git branch backup-$(date +%Y%m%d)
   ```

## After Syncing

1. **Test your site**
   ```bash
   npm install  # In case dependencies changed
   npm run dev  # Test locally
   ```

2. **Check for broken personalizations**
   - Review `src/config.ts` - your settings should still be there
   - Check if any components you customized were updated
   - Verify your content files are intact

## Handling Conflicts

When conflicts occur, you'll see markers like:
```
<<<<<<< HEAD
Your version
=======
Upstream version
>>>>>>> upstream/main
```

**For `src/config.ts` conflicts:**
- Keep YOUR values (name, email, social links, etc.)
- Consider adopting new upstream features if useful

**For component conflicts:**
- Review what upstream changed
- Decide if you want their improvements or your customizations
- You can keep both by manually merging the best parts

## Selective Updates

Don't want everything? Update specific files:

```bash
# Get just one file from upstream
git checkout upstream/main -- <path/to/file>

# Or cherry-pick specific commits
git cherry-pick <commit-hash>
```

## Emergency: Undo a Bad Merge

```bash
# If you haven't pushed yet
git reset --hard HEAD~1

# If you already pushed
git revert -m 1 <merge-commit-hash>
git push origin main
```

