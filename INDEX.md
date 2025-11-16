# Documentation Index - Bypass Paywalls Clean

## Welcome

This is the **master index** for the Bypass Paywalls Clean Chrome extension documentation repository. Use this guide to quickly find the information you need.

> **Important**: This is a documentation-only repository. The actual extension code is hosted on [GitFlic](https://gitflic.ru/project/magnolia1234/bpc_uploads).

---

## Quick Navigation

### For End Users
- **[Installation Guide](#installation)** - How to install the extension
- **[Supported Sites](#supported-sites)** - List of 600+ supported websites
- **[Troubleshooting](#troubleshooting)** - Common issues and solutions
- **[Updates](#updates)** - How to update the extension

### For Contributors
- **[Contributing](#contributing)** - How to contribute
- **[Documentation](#documentation)** - Writing and maintaining docs
- **[Commands Reference](#commands)** - Command-line tools and scripts

### For AI Assistants
- **[Claude.md](#claudemd)** - Project context and guidelines
- **[Security Policy](#security)** - What AI can/cannot help with
- **[Common Tasks](#common-tasks)** - Frequent operations

---

## Documentation Files

### 📘 README.md
**Primary user-facing documentation**

- **Size**: ~1,200 lines, 56KB
- **Purpose**: End-user installation, usage, and site support reference
- **Audience**: Extension users, first-time installers

**Key Sections**:
- Installation instructions (Chrome, Edge, Brave, Opera, Vivaldi, Kiwi)
- 600+ supported websites organized by region and category
- Troubleshooting guide
- Custom site configuration
- Update instructions
- License and disclaimer

**When to read**:
- Installing the extension for the first time
- Looking for supported sites
- Troubleshooting issues
- Learning about custom configurations

**[📄 Read README.md](README.md)**

---

### 📗 DOCUMENTATION.md
**Comprehensive project documentation**

- **Size**: ~400 lines with table of contents
- **Purpose**: Deep dive into repository structure, features, and architecture
- **Audience**: Contributors, technical users, documentation maintainers

**Key Sections**:
- Repository structure explanation
- Detailed file descriptions
- Extension features and bypass techniques
- Installation methods comparison
- Browser compatibility matrix
- Legal and ethical considerations
- Development notes and recent changes
- Technical architecture insights

**When to read**:
- Understanding the project structure
- Contributing to documentation
- Learning about bypass techniques
- Researching browser compatibility
- Understanding legal/ethical context

**[📄 Read DOCUMENTATION.md](DOCUMENTATION.md)**

---

### 📕 claude.md
**AI assistant project context**

- **Size**: ~600 lines with comprehensive TOC
- **Purpose**: Provide context and guidelines for AI assistants
- **Audience**: AI assistants (Claude, GPT, etc.), automated tools

**Key Sections**:
- Project identity and critical context
- Security and legal considerations
- What AI can/cannot help with
- Detailed file analysis
- Supported sites breakdown
- Common tasks and guidance
- Development activity insights
- Testing and QA guidelines
- Project governance

**When to read**:
- Working with AI assistants on this project
- Understanding ethical boundaries
- Learning project maintenance patterns
- Analyzing development activity
- Preparing for automated tasks

**[📄 Read claude.md](claude.md)**

---

### 📙 COMMANDS.md
**Command-line reference guide**

- **Size**: ~700 lines with extensive examples
- **Purpose**: Provide ready-to-use commands for common tasks
- **Audience**: Developers, contributors, power users, AI assistants

**Key Sections**:
- Repository analysis commands
- Documentation search commands
- Site analysis commands
- Version and release tracking
- Git workflow commands
- Documentation maintenance
- Extension installation commands
- Advanced analysis scripts

**When to read**:
- Searching for specific sites
- Analyzing changelog entries
- Generating statistics
- Maintaining documentation
- Automating tasks
- Learning repository workflows

**[📄 Read COMMANDS.md](COMMANDS.md)**

---

### 📜 changelog.txt
**Complete version history**

- **Size**: ~2,000 lines, 77KB
- **Purpose**: Track all releases, changes, and updates
- **Audience**: Users tracking changes, developers, contributors

**Format**:
```
Post-release
[Unreleased changes]

* vX.X.X.X (YYYY-MM-DD)
Add [new sites]
Remove [deprecated sites]
Fix [bug fixes]
Update [improvements]
```

**When to read**:
- Checking latest version
- Finding when a site was added
- Tracking bug fixes
- Understanding update patterns
- Researching site support history

**[📄 Read changelog.txt](changelog.txt)**

---

### 📋 allowlist/README.md
**Browser allowlist configuration**

- **Size**: ~50 lines
- **Purpose**: Help users configure browser policies for CRX installation
- **Audience**: Windows/macOS users installing via CRX

**Platforms Covered**:
- Windows (Registry, PowerShell)
- macOS (Mobile config profiles)
- Linux (No allowlist needed)

**When to read**:
- Installing CRX file
- Seeing "blocked by policy" errors
- Configuring enterprise policies
- Understanding browser management

**[📄 Read allowlist/README.md](allowlist/README.md)**

---

## Topic-Based Navigation

### Installation

**First-time installation:**
1. Start with [README.md - Installation](README.md#installation)
2. Choose your method:
   - **Load Unpacked**: [README.md - Load unpacked](README.md#load-unpacked-chrome-ms-edge-or-brave-all-desktop)
   - **CRX File**: [README.md - CRX-file](README.md#crx-file-other-chromium-browsers-operavivaldiyandex)
3. If blocked: [allowlist/README.md](allowlist/README.md)
4. Mobile users: [README.md - Android](README.md#android)

**Installation comparison:**
- [DOCUMENTATION.md - Installation Methods](DOCUMENTATION.md#installation-methods)

**Installation commands:**
- [COMMANDS.md - Extension Installation](COMMANDS.md#extension-installation-commands)

---

### Supported Sites

**Find if a site is supported:**
1. Quick check: [README.md - List of supported websites](README.md#list-of-supported-websites)
2. Search: `grep -i "site name" README.md`
3. Full analysis: [DOCUMENTATION.md - Supported Website Categories](DOCUMENTATION.md#supported-website-categories)

**By region:**
- USA: [README.md - National USA news](README.md#national-usa-news) and [Local USA news](README.md#local-usa-news)
- Canada: [README.md - Canada](README.md#canada)
- Europe: [README.md - Europe](README.md#europe)
- Asia: [README.md - China/Japan/India/Singapore](README.md#china-hong-kong--taiwan)
- Latin America: [README.md - Latin America](README.md#latin-america)

**By category:**
- Business: [README.md - Business](README.md#business)
- Tech/Science: [README.md - Tech/Science](README.md#techscience)
- Sports: [README.md - Sports](README.md#sports)
- Magazines: [README.md - Magazines/Blogs](README.md#magazinesblogs)

**Analysis commands:**
- [COMMANDS.md - Site Analysis Commands](COMMANDS.md#site-analysis-commands)

---

### Troubleshooting

**Extension not working:**
1. Follow: [README.md - Troubleshooting](README.md#troubleshooting)
2. Check version: `head -20 changelog.txt | grep "^\* v"`
3. Look for known issues in recent changelog entries

**Site-specific issues:**
1. Check changelog: `grep -i "site name" changelog.txt`
2. Try custom site configuration: [README.md - Add custom site](README.md#add-custom-site)
3. Report issue: [README.md - New site requests](README.md#new-site-requests)

**Common issues:**
- Adblocker conflicts: [README.md - Troubleshooting](README.md#troubleshooting)
- Permission issues: [DOCUMENTATION.md - Permission Model](DOCUMENTATION.md#permission-model)
- AMP redirects: [README.md - Troubleshooting](README.md#troubleshooting)

---

### Updates

**How to update:**
- CRX installation: [README.md - Update](README.md#update)
- ZIP installation: [README.md - Update](README.md#update)
- Post-release updates: [README.md - Update](README.md#update)

**Check latest version:**
- Command: `head -20 changelog.txt | grep "^\* v"`
- Online: [changelog.txt](changelog.txt)

**Update strategy:**
- [DOCUMENTATION.md - Update Strategy](DOCUMENTATION.md#update-strategy)

**Version commands:**
- [COMMANDS.md - Version & Release Commands](COMMANDS.md#version--release-commands)

---

### Contributing

**Documentation contributions:**
1. Read: [DOCUMENTATION.md](DOCUMENTATION.md)
2. Review: [claude.md - Working with This Repository](claude.md#working-with-this-repository)
3. Safe changes: [claude.md - Safe Changes](claude.md#safe-changes)
4. Commands: [COMMANDS.md - Documentation Maintenance](COMMANDS.md#documentation-maintenance)

**Adding sites to list:**
1. Check if already supported: `grep -i "site" README.md`
2. Check changelog for recent additions
3. Update alphabetically in correct region/category
4. Submit via: [README.md - New site requests](README.md#new-site-requests)

**Git workflow:**
- [COMMANDS.md - Git Workflow Commands](COMMANDS.md#git-workflow-commands)

---

### Commands

**Most common commands:**
- Find a site: `grep -i "site name" README.md`
- Check version: `head -20 changelog.txt | grep "^\* v"`
- Count sites: `grep -c "https\?://" README.md`
- Search changelog: `grep -i "site name" changelog.txt`
- Update repo: `git pull origin main`

**Full reference:**
- [COMMANDS.md](COMMANDS.md) - Complete command reference

**Quick reference:**
- [COMMANDS.md - Quick Reference Cheat Sheet](COMMANDS.md#quick-reference-cheat-sheet)

---

## Information by Audience

### 👤 End Users (Extension Users)

**Start here:**
1. [README.md](README.md) - Installation and usage
2. [README.md - Troubleshooting](README.md#troubleshooting) - If issues arise
3. [changelog.txt](changelog.txt) - Check latest version

**Common questions:**
- "How do I install?" → [README.md - Installation](README.md#installation)
- "Is my site supported?" → [README.md - Supported websites](README.md#list-of-supported-websites)
- "It's not working!" → [README.md - Troubleshooting](README.md#troubleshooting)
- "How do I update?" → [README.md - Update](README.md#update)
- "Can I add a site?" → [README.md - Add custom site](README.md#add-custom-site)

---

### 👨‍💻 Contributors (Documentation Writers)

**Start here:**
1. [DOCUMENTATION.md](DOCUMENTATION.md) - Understand the project
2. [claude.md - Working with This Repository](claude.md#working-with-this-repository) - Contribution guidelines
3. [COMMANDS.md](COMMANDS.md) - Useful commands

**Common tasks:**
- Update site list: [COMMANDS.md - Updating the Supported Sites List](COMMANDS.md#updating-the-supported-sites-list)
- Fix typos: [claude.md - Fixing Documentation Typos](claude.md#fixing-documentation-typos)
- Validate links: [COMMANDS.md - Validate Links](COMMANDS.md#validate-links)
- Check format: [COMMANDS.md - Check Documentation Format](COMMANDS.md#check-documentation-format)

**Guidelines:**
- Safe changes: [claude.md - Safe Changes](claude.md#safe-changes)
- What to avoid: [claude.md - Changes to Avoid](claude.md#changes-to-avoid)

---

### 🤖 AI Assistants (Claude, GPT, etc.)

**Start here:**
1. **[claude.md](claude.md)** - MUST READ - Critical context and guidelines
2. [DOCUMENTATION.md](DOCUMENTATION.md) - Project details
3. [COMMANDS.md](COMMANDS.md) - Automation commands

**Critical sections:**
- Security policy: [claude.md - Security & Legal Considerations](claude.md#security--legal-considerations)
- What you CAN do: [claude.md - What You CAN Do](claude.md#what-you-can-do)
- What you MUST NOT do: [claude.md - What You MUST NOT Do](claude.md#what-you-must-not-do)
- Common tasks: [claude.md - Common Tasks & Guidance](claude.md#common-tasks--guidance)

**Key takeaways:**
- [claude.md - Key Takeaways for AI Assistants](claude.md#key-takeaways-for-ai-assistants)

**Questions to ask users:**
- [claude.md - Questions to Ask Users](claude.md#questions-to-ask-users)

---

### 🔬 Researchers (Technical Analysis)

**Start here:**
1. [DOCUMENTATION.md](DOCUMENTATION.md) - Technical architecture
2. [COMMANDS.md - Advanced Analysis](COMMANDS.md#advanced-analysis) - Analysis scripts
3. [changelog.txt](changelog.txt) - Historical data

**Analysis topics:**
- Bypass techniques: [DOCUMENTATION.md - Bypass Techniques](DOCUMENTATION.md#bypass-techniques)
- Site coverage: [DOCUMENTATION.md - Supported Website Categories](DOCUMENTATION.md#supported-website-categories)
- Update patterns: [COMMANDS.md - Analyze Update Patterns](COMMANDS.md#analyze-update-patterns)
- Browser compatibility: [DOCUMENTATION.md - Browser Compatibility](DOCUMENTATION.md#browser-compatibility)

**Data extraction:**
- [COMMANDS.md - Extract All URLs](COMMANDS.md#extract-all-urls)
- [COMMANDS.md - Generate Site Reports](COMMANDS.md#generate-site-reports)

---

## Project Statistics (As of 2025-11-16)

### Repository
- **Total files**: ~10 files
- **Documentation size**: ~150KB (excluding git history)
- **Languages**: Markdown (98%), Text (2%)

### Extension Support
- **Supported sites**: 600+ websites
- **Geographic coverage**: 50+ countries across 6 continents
- **Publisher groups**: 50+ media conglomerates
- **Update frequency**: Weekly releases

### Documentation
- **README.md**: 1,200 lines, 56KB
- **changelog.txt**: 2,000+ lines, 77KB
- **DOCUMENTATION.md**: 400+ lines
- **claude.md**: 600+ lines
- **COMMANDS.md**: 700+ lines

### Maintenance
- **Release cadence**: ~7-10 days
- **Active maintenance**: 3+ years
- **Latest version**: Check [changelog.txt](changelog.txt)
- **Manifest version**: v3 (as of October 2024)

---

## External Resources

### Extension Downloads
- **GitFlic Distribution**: https://gitflic.ru/project/magnolia1234/bpc_uploads
- **Master ZIP**: https://gitflic.ru/project/magnolia1234/bpc_uploads/blob/raw?file=bypass-paywalls-chrome-clean-master.zip

### Related Projects
- **Firefox Version**: https://github.com/bpc-clone/bypass-paywalls-firefox-clean
- **iOS/iPadOS Filters**: https://gitflic.ru/project/magnolia1234/bypass-paywalls-clean-filters

### Community
- **GitHub Issues**: https://github.com/bpc-clone/bypass-paywalls-chrome-clean/issues
- **Twitter/X**: @Magnolia1234B
- **Original Repo**: https://github.com/bpc-clone/bypass-paywalls-chrome-clean

---

## Document Relationships

```
INDEX.md (you are here)
│
├─→ README.md (end users)
│   └─→ allowlist/README.md (CRX installation)
│
├─→ DOCUMENTATION.md (contributors, technical users)
│   ├─→ References README.md
│   ├─→ References changelog.txt
│   └─→ References allowlist/README.md
│
├─→ claude.md (AI assistants)
│   ├─→ References all other docs
│   ├─→ Provides context for automation
│   └─→ Sets security boundaries
│
├─→ COMMANDS.md (developers, automation)
│   ├─→ Implements tasks from claude.md
│   ├─→ Analyzes content from README.md
│   └─→ Processes changelog.txt
│
└─→ changelog.txt (version history)
    └─→ Referenced by all other docs
```

---

## Search This Documentation

### By Keyword

Use your terminal to search across all documentation:

```bash
# Search all markdown files
grep -rn "keyword" *.md

# Search including allowlist docs
grep -rn "keyword" *.md allowlist/*.md

# Case-insensitive search
grep -rin "keyword" *.md
```

### By Topic

| Topic | Primary Document | Section |
|-------|------------------|---------|
| Installation | README.md | [Installation](README.md#installation) |
| Supported Sites | README.md | [List of supported websites](README.md#list-of-supported-websites) |
| Troubleshooting | README.md | [Troubleshooting](README.md#troubleshooting) |
| Custom Sites | README.md | [Add custom site](README.md#add-custom-site) |
| Updates | README.md | [Update](README.md#update) |
| Bypass Techniques | DOCUMENTATION.md | [Bypass Techniques](DOCUMENTATION.md#bypass-techniques) |
| Browser Compat | DOCUMENTATION.md | [Browser Compatibility](DOCUMENTATION.md#browser-compatibility) |
| Legal/Ethics | DOCUMENTATION.md | [Legal & Ethical](DOCUMENTATION.md#legal--ethical-considerations) |
| AI Guidelines | claude.md | [Security & Legal](claude.md#security--legal-considerations) |
| Commands | COMMANDS.md | All sections |
| Version History | changelog.txt | Entire file |

---

## Getting Help

### For Users
1. Check [README.md - Troubleshooting](README.md#troubleshooting)
2. Search [changelog.txt](changelog.txt) for your issue
3. Submit issue on GitHub (link in README.md)

### For Contributors
1. Read [DOCUMENTATION.md](DOCUMENTATION.md)
2. Review [claude.md - Working with This Repository](claude.md#working-with-this-repository)
3. Check [COMMANDS.md](COMMANDS.md) for helpful commands

### For AI Assistants
1. **Always read [claude.md](claude.md) first**
2. Check [COMMANDS.md](COMMANDS.md) for automation
3. Reference [DOCUMENTATION.md](DOCUMENTATION.md) for details

---

## Quick Links Reference

| Link | Description |
|------|-------------|
| [README.md](README.md) | User guide |
| [DOCUMENTATION.md](DOCUMENTATION.md) | Project docs |
| [claude.md](claude.md) | AI context |
| [COMMANDS.md](COMMANDS.md) | Command reference |
| [changelog.txt](changelog.txt) | Version history |
| [allowlist/README.md](allowlist/README.md) | Allowlist guide |
| [LICENSE](LICENSE) | MIT License |

---

## About This Index

**Purpose**: Provide centralized navigation for all documentation

**Audience**: All users - from end users to AI assistants

**Maintenance**: Update when new docs are added or structure changes

**Last Updated**: 2025-11-16

**Questions?** Check the documentation or submit an issue on GitHub.

---

**[Back to top](#documentation-index---bypass-paywalls-clean)**
