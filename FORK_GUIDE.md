# Fork Maintenance Guide

This guide covers how to personalize your Bloomfolio fork and handle upstream changes from the original repository.

## 🎯 Standard Personalization Steps

### 1. Update Package Information

**File: `package.json`**
- Change `name` from `"bloomfolio"` to your project name (e.g., `"colinsmithio"`)
- Update `version` if needed
- Consider adding your own repository URL

### 2. Personalize Site Configuration

**File: `src/config.ts`**
- Update `name`, `title`, `description` with your information
- Replace `avatar` path with your own image
- Update `location` and `email`
- Replace all `socialLinks` with your profiles
- Customize `extraLinks` (FAB Flower menu) with your own links
- Adjust `sections` visibility based on what you want to show

### 3. Update README.md

**File: `README.md`**
- Replace template description with your portfolio description
- Update installation instructions if needed
- Remove or update template-specific documentation
- Add your own project-specific information

### 4. Replace Placeholder Content

**Content Files:**
- `src/content/about/about.md` - Your about page
- `src/content/blog/` - Remove example posts, add your own
- `src/content/projects/` - Replace with your projects
- `src/content/work/` - Add your work experience
- `src/content/education/` - Add your education
- `src/content/hackathons/` - Add your hackathons (or disable section)

**Assets:**
- Replace `src/assets/bloomfolio.png` with your avatar/logo
- Update `public/favicon.svg` with your favicon
- Replace placeholder images in `public/images/`

### 5. Update Metadata

**Files to check:**
- `LICENSE` - Update if you want a different license
- `astro.config.mjs` - Update site URL if needed
- Any hardcoded references to "Bloomfolio" or original author

### 6. Clean Up Template Files

Consider removing:
- Template documentation files (or move to a docs folder)
- Example blog posts that are guides
- Placeholder images

---

## 🔄 Handling Upstream Changes

Your git remotes are already set up correctly:
- `origin` → Your fork (`terminusagency/colinsmithio`)
- `upstream` → Original repo (`lauroguedes/bloomfolio`)

### Workflow for Syncing Upstream Changes

#### Step 1: Fetch Latest Changes from Upstream

```bash
# Fetch all changes from the original repository
git fetch upstream
```

#### Step 2: Check What's Changed

```bash
# See what commits are in upstream but not in your fork
git log HEAD..upstream/main --oneline

# Or see a summary of changes
git diff HEAD..upstream/main --stat
```

#### Step 3: Merge or Rebase Upstream Changes

**Option A: Merge (Recommended for beginners)**
```bash
# Make sure you're on your main branch
git checkout main

# Merge upstream changes into your branch
git merge upstream/main
```

**Option B: Rebase (Cleaner history, but more complex)**
```bash
# Make sure you're on your main branch
git checkout main

# Rebase your changes on top of upstream
git rebase upstream/main
```

#### Step 4: Resolve Conflicts (if any)

If there are conflicts:
1. Git will mark conflicted files
2. Open each file and look for conflict markers:
   ```
   <<<<<<< HEAD
   Your changes
   =======
   Upstream changes
   >>>>>>> upstream/main
   ```
3. Edit to keep what you want
4. Stage resolved files: `git add <file>`
5. Continue merge/rebase:
   - Merge: `git commit`
   - Rebase: `git rebase --continue`

#### Step 5: Push Your Updated Fork

```bash
# Push merged changes to your fork
git push origin main

# If you rebased, you may need to force push (be careful!)
git push origin main --force-with-lease
```

---

## 🛡️ Best Practices for Maintaining a Fork

### 1. Keep Personalizations Separate

**Strategy: Create a personalization branch**
```bash
# Create a branch for your customizations
git checkout -b personalization

# Make all your personal changes here
# Then merge into main when ready
```

**Or: Use a separate config file**
- Keep `src/config.ts` as your personal config
- If upstream changes `config.ts`, you'll need to manually merge your values

### 2. Track What You've Changed

Create a file to document your customizations:

**File: `MY_CUSTOMIZATIONS.md`**
```markdown
# My Customizations

## Files I've Modified
- `src/config.ts` - Personal info and settings
- `package.json` - Project name
- `README.md` - Personal description

## Files I've Added
- Custom components, content, etc.

## Upstream Changes to Watch
- If upstream changes `src/config.ts`, I need to manually merge
- If upstream changes component structure, check compatibility
```

### 3. Regular Sync Schedule

**Recommended:**
- Sync monthly or when you see useful updates
- Before major feature work, sync to get latest bug fixes
- After syncing, test your site to ensure nothing broke

### 4. Selective Merging

You don't have to merge everything. If upstream adds features you don't want:

```bash
# Merge specific commits
git cherry-pick <commit-hash>

# Or merge specific files
git checkout upstream/main -- <path/to/file>
```

### 5. Protect Your Personalizations

**Files you'll always need to manually merge:**
- `src/config.ts` - Your personal info
- `package.json` - Your project name
- `README.md` - Your description
- Content files in `src/content/` - Your content

**Files that can usually auto-merge:**
- Component files (if you haven't customized them)
- Layout files (if you haven't customized them)
- Build configuration (usually safe to update)

---

## 🔍 Quick Reference Commands

```bash
# Check current remotes
git remote -v

# Fetch upstream changes (doesn't modify your code)
git fetch upstream

# See what's different
git log HEAD..upstream/main
git diff HEAD..upstream/main

# Merge upstream into your main branch
git checkout main
git merge upstream/main

# Push to your fork
git push origin main

# Create a backup branch before syncing
git branch backup-before-sync
```

---

## ⚠️ Common Pitfalls

1. **Force pushing to main** - Only do this if you're sure, and use `--force-with-lease`
2. **Losing personalizations** - Always check conflicts carefully, don't blindly accept upstream
3. **Not testing after sync** - Always run `npm run dev` and check your site after merging
4. **Merging too frequently** - You don't need to sync for every tiny upstream change

---

## 🎨 Making It Your Own

Once personalized, consider:
- Adding your own components
- Customizing the theme colors
- Adding new sections
- Integrating with your own APIs/services
- Custom domain setup
- Analytics integration

Remember: This is YOUR portfolio now. Make it reflect you!

