# git-scripts

Just a couple of git aliases I made to make life easier.

## commit-claude

This is the main one. It looks at your staged changes and uses Claude to generate a commit message for you.

If your project has existing commits, it'll look at the last 20 messages and try to match your style. If it's a new project, it'll use a standard conventional commit format.

**Usage:**
```bash
# Stage your changes
git add .

# Let Claude write the commit message
git commit-claude
```

You'll need the `claude` CLI tool installed for this to work.

If you want to use a different model than the default, you can set an environment variable:

```bash
# Example alias for your .gitconfig if you want a different model
commit-claude = "!CLAUDE_MODEL=sonnet ~/path/to/your/git-scripts/commit-claude"
```

## newwt

Simple helper for creating new git worktrees. Creates a worktree in a directory next to your current project with the branch name.

**Usage:**
```bash
git newwt feature-branch-name
```

This creates `../project-feature-branch-name` with the new branch checked out.

## Installation

Just add these aliases to your git config:

```ini
[alias]
    commit-claude = "!~/path/to/git-scripts/commit-claude"
    newwt = "!~/path/to/git-scripts/newwt"
```

That's it.