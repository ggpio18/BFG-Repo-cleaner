# BFG-Repo-cleaner
Removes large or troublesome blobs like git-filter-branch does, but faster. And written in Scala

# Clean Your Git Repository with BFG Repo Cleaner

## Introduction

If your Git repository has become bloated with large or sensitive files, BFG Repo Cleaner is a great tool to help you clean it up. This guide will walk you through the steps to use BFG Repo Cleaner effectively.

## Prerequisites

- Java installed on your machine
- Basic knowledge of Git commands

## Installation

1. **Download BFG Repo Cleaner**:
   Download the latest version of BFG Repo Cleaner from the [official website](https://rtyley.github.io/bfg-repo-cleaner/).

2. **Verify Java Installation**:
   Make sure Java is installed on your system. You can verify this by running:
   ```sh
   java -version

## Usage
## Step 1: Clone Your Repository
Clone your repository as a bare repository:
```sh
git clone --mirror git://example.com/some-big-repo.git
cd some-big-repo.git
```

## Step 2: Prepare for Cleaning
Identify the files you want to remove. Create a file (e.g., delete.txt) listing the names or patterns of the files you want to delete. For example:

```sh
*.log
*.bak
secret.txt
```

## Step 3: Run BFG Repo Cleaner
Use BFG Repo Cleaner to delete the specified files:
```sh
java -jar bfg.jar --delete-files delete.txt
```
You can also use other options, such as --strip-blobs-bigger-than to remove large files:
```sh
java -jar bfg.jar --strip-blobs-bigger-than 100M
```

## Step 4: Clean Your Repository
Run the following Git commands to finalize the cleaning process:
```sh
git reflog expire --expire=now --all
git gc --prune=now --aggressive
```

## Step 5: Push Changes
Push the cleaned repository back to your remote:
```sh
git push --force
```

# Conclusion
Congratulations! You have successfully cleaned your Git repository using BFG Repo Cleaner. Always ensure you have backups of your repository before performing such operations, as they can be irreversible.

References
- BFG Repo Cleaner Documentation
- Git Documentation



