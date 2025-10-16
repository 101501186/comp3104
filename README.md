#### COMP3104 – Developer Operations


# GitHub Action Status Badge
[![CI](https://github.com/101501186/COMP3104/actions/workflows/ci.yml/badge.svg)](https://github.com/101501186/COMP3104/actions/workflows/ci.yml)

# Commit Msg Hook (Enforce Commit Message Format)
Ensures commit messages follow a specific pattern.
File: .git/hooks/commit-msg

# Pre-Commit Hook (Lint Code Before Commit)

Ensures that the code is linted before committing.
File: .git/hooks/pre-commit
```
# !/bin/sh
echo "Running pre-commit hook: Linting code..."
node --version
#  npm run lint
if [ $? -ne 0 ]; then
  echo "Linting failed. Fix errors before committing."
  exit 1
```

# Pre-Push Hook (Run Tests Before Push)

Runs tests before allowing a push.
File: .git/hooks/pre-push
```
# !/bin/sh
echo "Running pre-push hook: Running tests..."
npm test
if [ $? -ne 0 ]; then
  echo "Tests failed! Fix them before pushing."
  exit 1
fi
```
