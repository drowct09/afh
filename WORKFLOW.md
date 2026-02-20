# Development and Production Workflow

This repository uses a two-branch workflow to separate development/testing from production.

## Branch Structure

- **`main`** - Production branch (published/live version)
- **`develop`** - Development branch (for testing and development)

## Initial Setup

Run these commands in your terminal from the `c:\VC\afh` directory:

```bash
# 1. Create develop branch from main
git checkout -b develop

# 2. Push develop branch to GitHub (optional, for backup)
git push -u origin develop
```

## Daily Development Workflow

### Working on Changes

1. **Switch to develop branch** (if not already there):
   ```bash
   git checkout develop
   ```

2. **Make your changes** to files (edit, test, etc.)

3. **Stage and commit changes**:
   ```bash
   git add .
   git commit -m "Description of your changes"
   ```

4. **Push to GitHub** (optional, for backup):
   ```bash
   git push origin develop
   ```

### Testing Your Changes

- Open `index.html` in your browser to test locally
- Make adjustments as needed
- Commit changes to `develop` branch

## Publishing to Production

When you're ready to publish your changes:

1. **Switch to main branch**:
   ```bash
   git checkout main
   ```

2. **Merge develop into main**:
   ```bash
   git merge develop
   ```

3. **Push to GitHub** (publishes to afh):
   ```bash
   git push origin main
   ```

## Using Cursor's Git UI

### Switching Branches
- Click the branch name in the bottom-left status bar
- Select `develop` or `main` from the list

### Committing Changes
- Open Source Control panel (Ctrl+Shift+G)
- Stage your changes (+ icon)
- Enter commit message
- Click Commit button
- Select which branch to commit to (develop for dev, main for production)

### Merging Branches
- Switch to `main` branch
- Open Command Palette (Ctrl+Shift+P)
- Type "Git: Merge Branch"
- Select `develop` branch

## Quick Reference

| Task | Command |
|------|---------|
| Switch to develop | `git checkout develop` |
| Switch to main | `git checkout main` |
| Create new branch | `git checkout -b branch-name` |
| See current branch | `git branch` |
| Merge develop → main | `git checkout main && git merge develop` |
| Push develop | `git push origin develop` |
| Push main (publish) | `git push origin main` |

## Best Practices

1. **Always work on `develop`** for new features and changes
2. **Test thoroughly** before merging to `main`
3. **Keep `main` stable** - only merge when ready to publish
4. **Commit often** with descriptive messages
5. **Push regularly** to backup your work
