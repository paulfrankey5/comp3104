#### COMP3104 - Developer Operations


# GitHub Action Status Badge

[![CI](https://github.com/paulfrankey5/comp3104/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/paulfrankey5/comp3104/actions/workflows/ci.yml)

# Commit Msg Hook (Enforce Commit Message Format)

Ensures commit messages follow a specific pattern.

**File:** `.git/hooks/commit-msg`

```bash
#!/bin/sh
COMMIT_MSG_FILE=$1
COMMIT_MSG=$(cat $COMMIT_MSG_FILE)

if ! echo "$COMMIT_MSG" | grep -Eq "^(feat|fix|docs|style|refactor|test|chore): .+"; then
  echo " Commit message must follow the format: <type>: <description>"
  echo " Example: feat: add user authentication"
  exit 1

```
# Pre-Commit Hook(Lint Code Before Commit)

Ensures that the code is linted before committing.

**File:** `.git/hooks/pre-commit`

```bash
#!/bin/sh
echo "Running pre-commit hook: Linting code..."
# npm run lint
if [ $? -ne 0 ]; then
  echo "Linting failed. Fix errors before committing."
  exit 1
fi
  ```

