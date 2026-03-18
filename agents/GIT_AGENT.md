# Git Workflow Agent Tasks

## Repository Management
- Branch naming: `feature/description`, `bugfix/description`
- Keep local repo in sync with remote

## Commit Practices
- Use present tense: "Add feature" not "Added feature"
- Write concise, descriptive commit messages
- Run `pio run` before committing to ensure build passes

## Push Operations
- Push changes: `git push -u origin main`
- Force push only when necessary: `git push --force`
- Resolve merge conflicts before pushing

## Collaboration
- Review changes before committing
- Ensure clean working tree
- Verify remote repository state