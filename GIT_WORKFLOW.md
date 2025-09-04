# Git Workflow Guide

## Repository Remote Management

### Scenario: Existing Local Repository with Different Remote

If you already have this repository locally but it was pointing to a different remote URL, here's how to update it to pull from the correct repository:

### Step 1: Check Current Remote Configuration
```bash
git remote -v
```
This will show your current remote URLs.

### Step 2: Update Remote URL
If you need to change the remote URL to point to this repository:
```bash
git remote set-url origin https://github.com/Has-Law/Haslaw-user.git
```

### Step 3: Verify the Change
```bash
git remote -v
```
Confirm that the remote now points to the correct repository.

### Step 4: Fetch Latest Changes
```bash
git fetch origin
```

### Step 5: Pull Latest Changes
```bash
git pull origin main
```

### Alternative: Start Fresh
If you prefer to start with a clean copy of the repository:

1. **Backup your local changes** (if any):
   ```bash
   git stash
   # or
   git commit -am "Save local changes"
   ```

2. **Clone the repository in a new location**:
   ```bash
   git clone https://github.com/Has-Law/Haslaw-user.git haslaw-user-new
   cd haslaw-user-new
   ```

3. **Apply your changes** from the backup if needed.

### Handling Conflicts
If you encounter conflicts when pulling:

1. **Review conflicted files**:
   ```bash
   git status
   ```

2. **Resolve conflicts manually** by editing the files

3. **Mark conflicts as resolved**:
   ```bash
   git add .
   git commit -m "Resolve merge conflicts"
   ```

### Common Git Commands for This Project

```bash
# Check repository status
git status

# View commit history
git log --oneline

# Create new branch for features
git checkout -b feature/your-feature-name

# Switch between branches
git checkout main
git checkout feature/your-feature-name

# Push changes
git push origin your-branch-name
```

## Development Workflow

### Setting Up Development Environment
1. **Install dependencies**:
   ```bash
   npm install
   ```

2. **Run development server**:
   ```bash
   npm run dev
   ```

3. **Build project**:
   ```bash
   npm run build
   ```

4. **Run linting**:
   ```bash
   npm run lint
   ```

### Best Practices
- Always create feature branches for new work
- Keep commits small and focused
- Write clear commit messages
- Pull latest changes before starting new work
- Test your changes before pushing

## Troubleshooting

### Issue: "fatal: refusing to merge unrelated histories"
If you get this error when pulling:
```bash
git pull origin main --allow-unrelated-histories
```

### Issue: Permission denied (publickey)
Make sure your SSH keys are set up correctly, or use HTTPS instead:
```bash
git remote set-url origin https://github.com/Has-Law/Haslaw-user.git
```

### Issue: Local changes would be overwritten
Stash your changes before pulling:
```bash
git stash
git pull origin main
git stash pop  # To reapply your changes
```