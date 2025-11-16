# Command Reference - Bypass Paywalls Clean Repository

## Table of Contents

- [Overview](#overview)
- [Repository Analysis Commands](#repository-analysis-commands)
  - [Basic Repository Information](#basic-repository-information)
  - [File Statistics](#file-statistics)
  - [Repository Size](#repository-size)
- [Documentation Search Commands](#documentation-search-commands)
  - [Find Supported Sites](#find-supported-sites)
  - [Search Changelog](#search-changelog)
  - [Search All Documentation](#search-all-documentation)
- [Site Analysis Commands](#site-analysis-commands)
  - [Count Supported Sites](#count-supported-sites)
  - [List Sites by Region](#list-sites-by-region)
  - [Find Publisher Groups](#find-publisher-groups)
- [Version & Release Commands](#version--release-commands)
  - [Check Latest Version](#check-latest-version)
  - [List Recent Releases](#list-recent-releases)
  - [Find Changes for Specific Site](#find-changes-for-specific-site)
- [Git Workflow Commands](#git-workflow-commands)
  - [Clone Repository](#clone-repository)
  - [Update Local Copy](#update-local-copy)
  - [Check for Changes](#check-for-changes)
- [Documentation Maintenance](#documentation-maintenance)
  - [Validate Links](#validate-links)
  - [Check Documentation Format](#check-documentation-format)
  - [Generate Statistics](#generate-statistics)
- [Extension Installation Commands](#extension-installation-commands)
  - [Download Extension](#download-extension)
  - [Verify Download Integrity](#verify-download-integrity)
  - [Browser Installation](#browser-installation)
- [Advanced Analysis](#advanced-analysis)
  - [Extract All URLs](#extract-all-urls)
  - [Analyze Update Patterns](#analyze-update-patterns)
  - [Generate Site Reports](#generate-site-reports)

---

## Overview

This document provides a comprehensive command reference for working with the Bypass Paywalls Clean documentation repository. All commands assume you're in the repository root directory unless otherwise specified.

**Note**: This is a documentation-only repository. There is no code to build or compile.

---

## Repository Analysis Commands

### Basic Repository Information

**View repository structure:**
```bash
tree -L 2 -a
# Shows directory tree with hidden files, 2 levels deep

# Alternative without tree command:
find . -maxdepth 2 -type d | sort
```

**Count all files by type:**
```bash
find . -type f | sed 's/.*\.//' | sort | uniq -c | sort -rn
# Output: Count of each file extension
```

**List all files with sizes:**
```bash
ls -lhR
# Recursive listing with human-readable sizes

# Or sorted by size:
find . -type f -exec ls -lh {} \; | sort -k5 -rh
```

### File Statistics

**Count lines in all markdown files:**
```bash
find . -name "*.md" -exec wc -l {} \; | sort -rn
# Shows line count for each .md file

# Total lines across all markdown:
find . -name "*.md" -exec cat {} \; | wc -l
```

**Count words in documentation:**
```bash
wc -w README.md
# Word count in README

wc -w DOCUMENTATION.md claude.md README.md
# Word count across multiple files
```

**Find largest files:**
```bash
find . -type f -exec du -h {} \; | sort -rh | head -10
# Top 10 largest files
```

### Repository Size

**Total repository size:**
```bash
du -sh .
# Total size of repository

du -sh --exclude=.git .
# Size excluding git history
```

**Size breakdown by directory:**
```bash
du -h --max-depth=1 | sort -rh
# Shows size of each top-level directory
```

---

## Documentation Search Commands

### Find Supported Sites

**Search for a specific website:**
```bash
grep -i "new york times" README.md
# Case-insensitive search

# With line numbers:
grep -in "new york times" README.md
```

**Find all sites in a category:**
```bash
# Find all business sites:
sed -n '/##### Business/,/^#/p' README.md | grep -E "^\[.*\]"

# Find all tech sites:
sed -n '/##### Tech\/Science/,/^#/p' README.md | grep -E "^\[.*\]"
```

**Find sites by country:**
```bash
# Find all UK sites:
sed -n '/##### United Kingdom/,/^#/p' README.md | grep -E "^\[.*\]"

# Find all Canadian sites:
sed -n '/#### Canada/,/^#/p' README.md | grep -E "^\[.*\]"
```

### Search Changelog

**Find when a site was added:**
```bash
grep -n "Add.*Washington Post" changelog.txt
# Shows line number and match

# Case-insensitive with context:
grep -in -B2 -A2 "add.*forbes" changelog.txt
```

**Find all changes in a version:**
```bash
# Show specific version changes:
sed -n '/\* v3.9.1.0/,/\* v3.9.0.0/p' changelog.txt

# Or using grep with context:
grep -A 20 "v3.9.1.0" changelog.txt | head -25
```

**Find fixes for a specific site:**
```bash
grep -i "fix.*bloomberg" changelog.txt
# All Bloomberg fixes

# With dates:
grep -B5 -i "fix.*bloomberg" changelog.txt | grep -E "(^\* v|Fix.*bloomberg)"
```

### Search All Documentation

**Search across all markdown files:**
```bash
grep -r "custom site" *.md
# Recursive search in all .md files

# With line numbers and file names:
grep -rn "custom site" *.md
```

**Find all external links:**
```bash
grep -roh "https\?://[^)]*" *.md | sort | uniq
# Extracts all HTTP/HTTPS URLs

# Count unique domains:
grep -roh "https\?://[^/]*" *.md | sort | uniq -c | sort -rn
```

---

## Site Analysis Commands

### Count Supported Sites

**Count total sites in README:**
```bash
grep -o "https\?://www\." README.md | wc -l
# Approximate count of sites

# More accurate - count markdown links:
grep -o "\[.*\](https\?://.*)" README.md | wc -l
```

**Count sites by format:**
```bash
# Count individual sites (single line links):
grep -E "^\[.*\]\(https" README.md | wc -l

# Count grouped sites (in lists):
grep -E "^[*-] \[.*\]\(https" README.md | wc -l
```

**Count sites per category:**
```bash
# Count business sites:
sed -n '/##### Business/,/^#/p' README.md | grep -c "https\?://"

# Count tech sites:
sed -n '/##### Tech\/Science/,/^#/p' README.md | grep -c "https\?://"
```

### List Sites by Region

**Extract all USA sites:**
```bash
sed -n '/##### Local USA news/,/#### Canada/p' README.md | \
  grep -oE "\[.*\]\(https?://[^\)]*\)" | \
  sed 's/\[\(.*\)\](\(.*\))/\1: \2/'
```

**Extract all European sites:**
```bash
sed -n '/#### Europe/,/#### Africa/p' README.md | \
  grep -oE "\[.*\]\(https?://[^\)]*\)" | \
  head -20
```

**List sites alphabetically:**
```bash
grep -oE "\[.*\]\(https?://[^\)]*\)" README.md | \
  sed 's/\[\(.*\)\](\(.*\))/\1/' | \
  sort | \
  uniq
```

### Find Publisher Groups

**List all publisher groups:**
```bash
grep "Grouped in options:" README.md -A 3
# Shows grouped publishers

# Extract just publisher names:
grep -oE "\*[A-Z][^*]*\*" README.md | sort | uniq | head -20
```

**Find sites in a publisher group:**
```bash
# Example: Find Gannett sites
sed -n '/\*Gannett Group/,/^\*/p' README.md
```

---

## Version & Release Commands

### Check Latest Version

**Get current version:**
```bash
head -20 changelog.txt | grep -E "^\* v"
# Shows latest version entry

# Extract just version number:
head -20 changelog.txt | grep -oE "v[0-9]+\.[0-9]+\.[0-9]+\.[0-9]+" | head -1
```

**Check post-release changes:**
```bash
# Show unreleased changes:
sed -n '/^Post-release/,/^\* v/p' changelog.txt
```

### List Recent Releases

**Show last 10 versions:**
```bash
grep -E "^\* v[0-9]" changelog.txt | head -10
# Lists version lines only

# With dates:
grep -E "^\* v.*\([0-9]{4}-" changelog.txt | head -10
```

**Count releases by year:**
```bash
grep -oE "\([0-9]{4}-" changelog.txt | \
  sed 's/[()]//g; s/-//' | \
  sort | uniq -c
```

**Show release frequency:**
```bash
# Extract all release dates:
grep -oE "\([0-9]{4}-[0-9]{2}-[0-9]{2}\)" changelog.txt | \
  sed 's/[()]//g' | \
  sort -r | \
  head -20
```

### Find Changes for Specific Site

**Track all changes for a site:**
```bash
# Example: Track all NY Times changes
grep -i "new york times\|nytimes\|nyt " changelog.txt

# With version numbers:
grep -B2 -i "new york times" changelog.txt | \
  grep -E "(^\* v|[Nn]ew [Yy]ork)"
```

**Find when site was removed:**
```bash
grep -n "^Remove" changelog.txt | head -20
# Shows all removal entries

# Specific site:
grep -i "Remove.*Seeking Alpha" changelog.txt
```

---

## Git Workflow Commands

### Clone Repository

**Clone the repository:**
```bash
git clone https://github.com/bpc-clone/bypass-paywalls-chrome-clean.git
cd bypass-paywalls-chrome-clean
```

**Clone specific branch:**
```bash
git clone -b main https://github.com/bpc-clone/bypass-paywalls-chrome-clean.git
```

### Update Local Copy

**Pull latest changes:**
```bash
git pull origin main
# Updates main branch

# Or fetch and merge:
git fetch origin
git merge origin/main
```

**Check what changed:**
```bash
git log --oneline -10
# Last 10 commits

# Detailed view:
git log --stat -5
```

### Check for Changes

**See uncommitted changes:**
```bash
git status
# Shows modified files

git diff
# Shows actual changes
```

**Compare with remote:**
```bash
git fetch origin
git diff main origin/main
# Shows differences between local and remote
```

**View file history:**
```bash
git log --follow README.md
# Shows commit history for README

# With changes:
git log -p README.md
```

---

## Documentation Maintenance

### Validate Links

**Extract all links:**
```bash
grep -oh "https\?://[^)]*" README.md | sort | uniq > links.txt
# Saves all links to file
```

**Find broken link patterns:**
```bash
# Find incomplete links:
grep -n "\](http" README.md | grep -v ")"

# Find malformed markdown links:
grep -n "\[.*\](.*" README.md | grep -v "https\?://"
```

### Check Documentation Format

**Find long lines:**
```bash
awk 'length > 120 {print NR": "length" chars"}' README.md
# Shows lines over 120 characters
```

**Check heading hierarchy:**
```bash
grep -n "^#" README.md
# Shows all headings with line numbers

# Count heading levels:
grep "^#" README.md | sed 's/\(#*\).*/\1/' | sort | uniq -c
```

**Find TODO or FIXME markers:**
```bash
grep -rn "TODO\|FIXME\|XXX" *.md
# Finds documentation tasks
```

### Generate Statistics

**Documentation word count by file:**
```bash
for file in *.md; do
  echo "$file: $(wc -w < "$file") words"
done | sort -k2 -rn
```

**Count code blocks:**
```bash
grep -c "^\`\`\`" README.md
# Should be even number (opening/closing)
```

**Find most common words:**
```bash
cat README.md | \
  tr '[:upper:]' '[:lower:]' | \
  tr -s '[:space:]' '\n' | \
  grep -v "^$" | \
  sort | uniq -c | sort -rn | head -20
```

---

## Extension Installation Commands

### Download Extension

**Download from GitFlic (example):**
```bash
# Using wget:
wget https://gitflic.ru/project/magnolia1234/bpc_uploads/blob/raw?file=bypass-paywalls-chrome-clean-3.9.1.0.crx

# Using curl:
curl -L -O "https://gitflic.ru/project/magnolia1234/bpc_uploads/blob/raw?file=bypass-paywalls-chrome-clean-3.9.1.0.crx"
```

**Download master zip:**
```bash
wget https://gitflic.ru/project/magnolia1234/bpc_uploads/blob/raw?file=bypass-paywalls-chrome-clean-master.zip

# Extract:
unzip bypass-paywalls-chrome-clean-master.zip
```

### Verify Download Integrity

**Check SHA-256 hash:**
```bash
# Calculate hash of downloaded file:
sha256sum bypass-paywalls-chrome-clean-3.9.1.0.crx

# Compare with release-hashes.txt:
grep "3.9.1.0" release-hashes.txt
```

**Verify all checksums:**
```bash
# If release-hashes.txt contains checksums:
sha256sum -c release-hashes.txt
```

### Browser Installation

**Chrome - Load unpacked:**
```bash
# 1. Open Chrome and navigate to:
google-chrome chrome://extensions/

# 2. Enable Developer Mode (toggle in top-right)
# 3. Click "Load unpacked"
# 4. Select the extension folder
```

**Check extension location:**
```bash
# Linux Chrome extension directory:
ls -la ~/.config/google-chrome/Default/Extensions/

# Look for extension ID starting with 'lkbebcjgcmobigpeffafkodonchffocl'
```

---

## Advanced Analysis

### Extract All URLs

**Get all unique domains:**
```bash
grep -roh "https\?://[^/)]*" README.md | \
  sed 's/https\?:\/\///' | \
  sort | uniq | wc -l
# Count of unique domains

# List them:
grep -roh "https\?://[^/)]*" README.md | \
  sed 's/https\?:\/\///' | \
  sort | uniq > supported-domains.txt
```

**Extract site names and URLs:**
```bash
grep -oE "\[([^\]]+)\]\((https?://[^)]+)\)" README.md | \
  sed 's/\[\([^]]*\)\](\([^)]*\))/\1|\2/' | \
  sort > sites-list.csv
# Creates pipe-delimited list: Name|URL
```

### Analyze Update Patterns

**Count changes by type:**
```bash
# Count additions:
grep -c "^Add " changelog.txt

# Count fixes:
grep -c "^Fix " changelog.txt

# Count removals:
grep -c "^Remove " changelog.txt
```

**Monthly release frequency:**
```bash
grep -oE "[0-9]{4}-[0-9]{2}" changelog.txt | \
  sort | uniq -c | sort -k2
# Shows releases per month
```

**Find most frequently updated sites:**
```bash
# Extract site names from Fix lines:
grep "^Fix " changelog.txt | \
  sed 's/^Fix \([A-Za-z ]*\).*/\1/' | \
  sort | uniq -c | sort -rn | head -20
```

### Generate Site Reports

**Create geographic distribution report:**
```bash
#!/bin/bash
# Save as: generate-geo-report.sh

echo "Geographic Distribution of Supported Sites"
echo "=========================================="
echo ""

for region in "USA" "Canada" "Europe" "Asia" "Oceania" "Latin America"; do
  count=$(sed -n "/#### $region/,/^####/p" README.md | grep -c "https\?://")
  echo "$region: $count sites"
done
```

**Generate category breakdown:**
```bash
# Count sites by category:
categories=("Business" "Tech/Science" "Sports" "Magazines")

for cat in "${categories[@]}"; do
  count=$(sed -n "/##### $cat/,/^#/p" README.md | grep -c "https\?://")
  printf "%-20s: %3d sites\n" "$cat" "$count"
done
```

**Create changelog summary:**
```bash
#!/bin/bash
# Count changes in last N versions

versions=5
echo "Summary of last $versions releases:"
echo "==================================="

grep -E "^\* v" changelog.txt | head -$versions | while read version; do
  version_num=$(echo $version | grep -oE "v[0-9.]+")

  # Get changes for this version
  changes=$(sed -n "/$version/,/^\* v/p" changelog.txt)

  adds=$(echo "$changes" | grep -c "^Add ")
  fixes=$(echo "$changes" | grep -c "^Fix ")
  removes=$(echo "$changes" | grep -c "^Remove ")

  echo ""
  echo "$version_num:"
  echo "  Added: $adds | Fixed: $fixes | Removed: $removes"
done
```

---

## Quick Reference Cheat Sheet

### Most Common Commands

```bash
# Find a site
grep -i "site name" README.md

# Check latest version
head -20 changelog.txt | grep "^\* v"

# Count supported sites
grep -c "https\?://" README.md

# Search changelog for site
grep -i "site name" changelog.txt

# Update repository
git pull origin main

# Check for changes
git status

# View file
cat README.md | less

# Search all docs
grep -r "keyword" *.md

# Count words in doc
wc -w README.md

# Show recent commits
git log --oneline -10
```

### Useful Aliases

Add these to your `~/.bashrc` or `~/.zshrc`:

```bash
# BPC aliases
alias bpc-update='git pull origin main'
alias bpc-version='head -20 changelog.txt | grep "^\* v"'
alias bpc-sites='grep -c "https\?://" README.md'
alias bpc-search='grep -rn'
alias bpc-status='git status'
```

---

## Tips & Best Practices

### For Documentation Contributors

1. **Always check existing content first:**
   ```bash
   grep -i "topic" *.md
   ```

2. **Validate before committing:**
   ```bash
   # Check for syntax errors
   grep -n "\](http" README.md | grep -v ")"
   ```

3. **Keep changelog updated:**
   ```bash
   # Check if site already exists
   grep -i "site name" README.md changelog.txt
   ```

### For Users

1. **Check if site is supported:**
   ```bash
   grep -i "example.com" README.md
   ```

2. **Find installation instructions:**
   ```bash
   sed -n '/### Installation/,/### Update/p' README.md
   ```

3. **Check latest version:**
   ```bash
   head -30 changelog.txt
   ```

### For AI Assistants

1. **Analyze repository structure:**
   ```bash
   tree -L 2 -I '.git'
   ```

2. **Extract statistics:**
   ```bash
   wc -l *.md && grep -c "https\?://" README.md
   ```

3. **Search for context:**
   ```bash
   grep -rn "keyword" *.md allowlist/*.md
   ```

---

## Additional Resources

- **README.md** - User installation and usage guide
- **DOCUMENTATION.md** - Comprehensive project documentation
- **claude.md** - AI assistant context and guidelines
- **changelog.txt** - Complete version history
- **allowlist/README.md** - Browser allowlist configuration

For command-line help with any command, use:
```bash
man command_name
# or
command_name --help
```

---

## Contributing

When adding new commands to this reference:

1. Test the command thoroughly
2. Provide clear examples with expected output
3. Include explanatory comments
4. Organize by category
5. Update the table of contents

---

**Last Updated**: 2025-11-16
**Maintained By**: Community contributors
