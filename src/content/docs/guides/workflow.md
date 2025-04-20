---
title: Workflow for development
description: A comprehensive guide for development workflow
---
# General Development Workflow

1. **Clone the repository**  
   Use the following command to clone the repo:  
   ```bash
   git clone <repository-url>
   ```

2. **Create a new branch**  
   Switch to a new branch. Use a clear and descriptive naming convention like:  
   ```
   <your-name>/<feature-name>
   ```

3. **Write your code** ✨  
   Make your changes and implement the feature or fix.

4. **Commit your changes**  
   Follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification for commit messages.  
   You can install the VSCode extension to help with this:  
   [Conventional Commits Plugin](https://marketplace.visualstudio.com/items/?itemName=vivaxy.vscode-conventional-commits)

5. **Rebase before pushing**  
   Always rebase your branch onto the latest `main` to keep history clean:  
   ```bash
   git fetch origin
   git rebase origin/main
   ```  
   Resolve any conflicts manually.

6. **Push your branch**  
   Push your changes to the remote:  
   ```bash
   git push
   ```

7. **Open a Pull Request**  
   Create a Pull Request on GitHub. Make sure to include a clear title and description. Link related issues if applicable.

8. **Code Review Process**  
   - Request reviews from at least two team members
   - Respond to all comments and make necessary changes
   - Make sure all discussions are resolved before merging
   - Use GitHub's suggestion feature for small changes

9. **Testing Your Code**  
   - Run all tests locally before submitting PR:
   - Make sure your code includes unit tests for new functionality
   - Check that code coverage remains high (aim for >80%)
   - Test edge cases thoroughly

10. **Continuous Integration**  
    - All PRs must pass CI checks before merging
    - Fix any failing tests or linting errors immediately
    - Look for performance regressions in benchmark tests

---

🚫 **Never use `git push -f` unless absolutely necessary and approved.**  
Force pushing can disrupt team collaboration—use with extreme caution.

---

## Troubleshooting & Tips

1. **Resolving Merge Conflicts**  
   When encountering merge conflicts, carefully examine the conflicted files and resolve them manually:
   ```bash
   git status  # Check conflicted files
   # Edit conflict files to resolve conflicts
   git add <conflict-file>
   git rebase --continue
   ```

2. **Discarding Local Changes**  
   If you need to discard uncommitted changes:
   ```bash
   git checkout -- <file>  # Discard changes in a single file
   git restore <file>
   git reset --hard        # Discard all changes (use with caution)
   ```

3. **Managing Branches**  
   Commands to keep your workspace clean:
   ```bash
   git branch -d <branch-name>  # Delete local branches that have been merged
   git fetch --prune            # Clean up references to deleted remote branches
   ```
