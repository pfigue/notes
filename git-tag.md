# Git Tagging

Tags: git, tags, code, signing, release
Description: How to use the git-tags command.

# Creating a signed tag

    git tag -u <signing-key-fpr-small> -m <tag-content> <tag-name> <commit-hash>

Use `GNUPGHOME='...'` if needed.

# Pushing all tags to a remote

    git push origin --tags

The usual `git push origin master` does not push tags.

Alternatively, to push just one tag:

    git push origin <tag-name>

# Deleting a tag

    git tag -d <tag-name>

# Verifying a signed tag

    git tag -v <tag-name>

Use `GNUPGHOME='...'` if needed.

# Listing all tags

    git tag

Or alternatively, matching a glob pattern:

    git tag -l <glob-pattern>

# References
1. [2.6 Git Basics - Tagging](https://git-scm.com/book/en/v2/Git-Basics-Tagging)

