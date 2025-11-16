# Claude.md - Project Context for AI Assistants

## Project Identity

**Name**: Bypass Paywalls Clean - Chrome
**Type**: Documentation Repository for Browser Extension
**Purpose**: Provide installation guides, site lists, and version history for the BPC Chrome extension
**Code Location**: NOT in this repo - hosted on GitFlic at https://gitflic.ru/project/magnolia1234/bpc_uploads
**License**: MIT License
**Status**: Actively maintained with weekly updates

## Critical Context

### This is NOT a Code Repository
This repository contains **documentation only**. The actual extension code is distributed via GitFlic. When working with this repository:

- DO NOT expect to find `.js` files, `manifest.json`, or extension source code
- DO NOT attempt to build or compile anything
- DO expect documentation files, changelogs, and installation guides
- DO treat this as a user-facing documentation project

### Security & Legal Considerations

**This extension is designed to bypass paywalls on news websites.**

When working with this project:

#### What You CAN Do:
- Analyze existing documentation
- Improve installation instructions
- Update supported site lists from changelog
- Fix typos and formatting
- Reorganize documentation for clarity
- Create additional documentation (like this file!)
- Answer questions about how the extension works
- Explain bypass techniques used

#### What You MUST NOT Do:
- Create new bypass techniques or code
- Improve existing paywall bypass code (if you encounter it)
- Help circumvent new paywall implementations
- Provide guidance on defeating specific publisher protections
- Contribute to functionality that could be considered malware

#### Analysis vs. Enhancement
- **Allowed**: "This extension uses cookie clearing to bypass metered paywalls"
- **Allowed**: "The documentation shows it supports 600+ sites"
- **Allowed**: "The changelog indicates they updated to Manifest v3"
- **NOT Allowed**: "Here's how to bypass [specific site]'s new paywall"
- **NOT Allowed**: "You should add this script to defeat their protection"

### Ethical Considerations

This project exists in a legal/ethical gray area:
- Serves educational purposes (MIT License disclaimer)
- Helps users access content they may have partial rights to
- Potentially harms journalism business models
- Removed from Chrome Web Store (policy violation)

**Recommended User Guidance**: When discussing this project, remind users to:
- Support quality journalism through paid subscriptions when possible
- Use the tool responsibly and ethically
- Understand their local laws regarding paywall circumvention
- Respect copyright and publisher rights

## Repository Structure

```
/
├── README.md              # Primary user documentation (56KB) - comprehensive guide
├── changelog.txt          # Version history (77KB) - detailed release notes
├── LICENSE                # MIT License (1KB)
├── release-hashes.txt     # SHA-256 checksums for downloads (3KB)
├── not-for-install.txt    # Redirect notice (84 bytes)
├── allowlist/             # Browser allowlist configuration
│   └── README.md          # OS-specific allowlist instructions
├── .github/               # GitHub metadata
└── .git/                  # Git repository data
```

## Key Files Deep Dive

### README.md (Primary Documentation)
**Size**: ~1200 lines
**Purpose**: End-user installation and usage guide

**Sections**:
1. **Installation** - Platform-specific install instructions (Chrome, Edge, Brave, Opera, Vivaldi, Kiwi)
2. **Updates** - How to update CRX vs. unpacked installations
3. **Android** - Kiwi Browser installation
4. **Firefox** - Link to separate Firefox repo
5. **iOS/iPadOS** - Alternative solutions (adblocker + filters)
6. **Troubleshooting** - Systematic debugging steps
7. **Supported Websites** - Comprehensive list organized by:
   - Geographic region (USA, Canada, Europe, Asia, etc.)
   - Content category (News, Business, Tech, Sports, Magazines)
   - Publisher groups (Media conglomerates)
8. **Sites with Limited Free Articles** - Cookie clearing instructions
9. **New Site Requests** - How to request support for new sites
10. **Add Custom Site** - User configuration guide
11. **Add Excluded Site** - Subscription exemptions
12. **Changelog** - Links to changelog.txt
13. **License** - MIT License reference
14. **Disclaimer** - Legal/educational use notice

**Important Notes**:
- Contains 600+ supported websites with active links
- Organized hierarchically (region > category > publisher group)
- Updated weekly with new sites
- Includes detailed custom configuration options

### changelog.txt (Version History)
**Size**: ~2000 lines
**Purpose**: Track all releases and changes

**Format**:
```
Post-release
[Changes made after latest release]

* v3.x.x.x (YYYY-MM-DD)
Add [new sites]
Remove [deprecated sites]
Fix [bug fixes]
Update [improvements]
```

**Content Insights**:
- Weekly release cadence
- Rapid response to site changes (often same day)
- Manifest v3 migration completed October 2024
- Tracks 3+ years of history
- Shows evolution of bypass techniques

**Version Scheme**: v3.9.1.0 format
- Major.Minor.Patch.Build

### allowlist/README.md (Allowlist Guide)
**Size**: ~50 lines
**Purpose**: Help users configure browser policies to allow CRX installation

**Platforms Covered**:
1. **Windows** - Registry modifications, PowerShell scripts
2. **macOS** - Mobile config profiles
3. **Linux** - Local installation (no allowlist needed)

**Key Warning**: Adds "managed by organization" message to browser - explain to users this is expected.

## Supported Sites Analysis

From README.md, the extension supports:

### Geographic Distribution
- **USA**: ~200 sites (national + local news, business, magazines)
- **Canada**: ~15 sites (national + provincial)
- **Europe**: ~300 sites across 15+ countries
- **Asia**: ~30 sites (India, Japan, Singapore, Hong Kong)
- **Oceania**: ~40 sites (Australia, New Zealand)
- **Latin America**: ~15 sites (Brazil, Argentina, Chile, Mexico)

### Category Distribution
- **National/International News**: ~50 major outlets
- **Business/Finance**: ~100 publications
- **Tech/Science**: ~30 publications
- **Sports**: ~15 sites
- **Magazines**: ~100 general interest
- **Local News**: ~300 regional/city newspapers

### Publisher Groups
Supports major media conglomerates with multiple properties:
- Gannett (USA Today network)
- Advance Local
- Lee Enterprises
- McClatchy
- Tribune Publishing
- Hearst Communications
- Condé Nast
- News Corp Australia
- And 50+ others

Users can opt-in to entire publisher groups at once.

## Extension Features (Documented)

Based on README documentation, the extension provides:

### Bypass Techniques
1. **Cookie Management** - Clear/block cookies to reset article limits
2. **User-Agent Spoofing** - Impersonate Googlebot, Bingbot, Facebookbot
3. **Referer Modification** - Spoof referrals from Facebook, Google, Twitter
4. **IP Spoofing** - Random X-Forwarded-For headers
5. **JavaScript Blocking** - Selective by domain/inline
6. **Regex Blocking** - Block specific scripts/XHR requests
7. **AMP Redirects** - Redirect to AMP versions of articles
8. **JSON Extraction** - Extract article content from JSON-LD
9. **Archive Integration** - Fetch from archive.is
10. **DOM Manipulation** - Remove/unhide paywalled elements

### User Configuration
- Custom site addition
- Site exclusion (for subscriptions)
- Opt-in custom sites (privacy-focused permissions)
- Per-site permission requests
- Rule updates via online fetch

## Common Tasks & Guidance

### Updating the Supported Sites List
When new sites are added in changelog.txt:
1. Check changelog for "Add [site]" entries
2. Update README.md in appropriate section (geography/category)
3. Maintain alphabetical order
4. Use consistent formatting: `[Site Name](URL)`
5. Add to publisher group if applicable

### Fixing Documentation Typos
Safe and encouraged:
- Fix spelling/grammar in README.md
- Improve installation instructions clarity
- Update broken links
- Improve formatting/readability
- Add missing information from changelog

### Answering User Questions
When users ask about:
- **"Does it support [site]?"** → Check README.md supported sites list
- **"How do I install?"** → Direct to README.md installation section
- **"It's not working"** → Follow troubleshooting section
- **"How to add custom site?"** → Explain custom site configuration
- **"Is it safe?"** → Explain MIT License, educational purposes, security considerations
- **"Why not on Chrome Store?"** → Policy violation (paywall circumvention)

### Version Information
- Current version scheme: v3.x.x.x
- Latest documented: Check changelog.txt first entry
- Weekly updates expected
- Post-release patches common

## Development Activity Insights

From changelog analysis:

### Update Frequency
- **Weekly releases** - New version every 7-10 days
- **Post-release fixes** - Often 2-3 days after release
- **Rapid response** - Site breaks fixed within 24-48 hours

### Common Change Types
1. **Add**: New sites supported (~5-10 per release)
2. **Remove**: Deprecated sites (~2-5 per release)
3. **Fix**: Site-specific bugs (~10-15 per release)
4. **Update**: General improvements (~2-5 per release)

### Recent Major Changes (2024)
- **Manifest v3 migration** (October 2024)
- **Performance improvements**
- **External fetch enhancements**
- **New publisher group additions**

### Active Maintenance Indicators
- Consistent release dates
- Responsive to site changes
- Community-driven additions
- Modern web standards compliance (MV3)

## Browser Compatibility

### Fully Supported
- Chrome (desktop)
- Microsoft Edge (desktop)
- Brave (desktop)
- Opera (desktop)
- Vivaldi (desktop)
- Yandex (desktop)
- Kiwi Browser (Android)

### Separate Version
- Firefox (separate repo: bypass-paywalls-firefox-clean)

### Limited Support
- Orion Browser (iOS/iPadOS) - incomplete WebExtensions API
- iOS/iPadOS users should use adblocker + custom filters

### Installation Methods by Browser
- **Chrome/Edge/Brave**: Load unpacked OR allowlist + CRX
- **Opera/Vivaldi/Yandex**: CRX (no allowlist needed)
- **Kiwi**: CRX or ZIP
- **Edge 116+**: May need Forcelist in addition to allowlist

## Distribution Strategy

### Why Not Chrome Web Store?
- Violates store policies on paywall circumvention
- Requires sideloading via developer mode or allowlist

### Why GitFlic?
- Russian-based Git hosting
- Resilient to Western takedowns
- Provides automatic updates for CRX
- Alternative to GitHub for controversial projects

### Update Mechanisms
1. **CRX Installation**: Automatic updates from GitFlic
2. **Unpacked Installation**: Manual updates (download new ZIP)
3. **Post-Release Updates**: Opt-in feature (10 days after release)

## Testing & Quality Assurance

Based on documentation, recommended testing approach:

### Before Reporting Bugs
1. Test in incognito/private mode
2. Disable other extensions (especially ad blockers)
3. Clear site cookies via extension popup
4. Grant host permissions
5. Update to latest version
6. Check for AMP redirect issues
7. Test with JavaScript disabled
8. Try archive.is for the URL

### Issue Reporting Requirements
- Extension version
- Browser and version
- Paywalled article URL
- Detailed description of issue
- Steps already attempted

## Working with This Repository

### Safe Changes
- Documentation improvements
- README.md clarifications
- Installation guide updates
- Supported site list updates (from changelog)
- Formatting improvements
- Link updates
- Translation additions

### Changes Requiring Caution
- Changelog modifications (should match releases)
- License changes (consult maintainer)
- Structural reorganization (may break links)

### Changes to Avoid
- Adding code files (wrong repo)
- Creating new bypass techniques (security policy)
- Removing legal disclaimers
- Changing license terms without permission

## Useful Commands for Analysis

```bash
# Count supported sites in README
grep -o "https\?://[^)]*" README.md | wc -l

# List recent changelog entries
head -50 changelog.txt

# Find specific site in README
grep -i "new york times" README.md

# Count lines in documentation
wc -l README.md changelog.txt

# Extract version numbers from changelog
grep -E "^\* v[0-9]" changelog.txt | head -20
```

## Project Governance

### Maintainer
- Primary: magnolia1234 (based on GitFlic URLs and GitHub references)
- Contact: GitHub issues or X/Twitter @Magnolia1234B

### Community
- GitHub: Issue tracking, feature requests
- Updates: GitFlic for distribution
- Social: X/Twitter for announcements

### Contribution Model
- Community site requests via GitHub issues
- Maintainer implements in extension code
- Documentation updated in this repo
- Weekly release cycle

## Key Takeaways for AI Assistants

1. **This is a documentation-only repository** - no code here
2. **Analyze but don't enhance bypass techniques** - security policy
3. **Support ethical use** - remind users to support journalism
4. **Weekly updates are normal** - active project
5. **600+ sites supported** - comprehensive coverage
6. **Installation requires sideloading** - not on Chrome Store
7. **MIT License with educational disclaimer** - legal gray area
8. **GitFlic distribution** - resilient hosting strategy
9. **Cross-platform** - desktop and mobile support
10. **Privacy-conscious** - limited permissions by default

## Questions to Ask Users

When helping users with this project:

1. **What browser are you using?** (Different install methods)
2. **What site isn't working?** (Check supported list)
3. **Did you try troubleshooting steps?** (Systematic debugging)
4. **Do you have a subscription?** (Add to exclusions)
5. **Are you seeing the extension icon?** (Installation verification)
6. **Have you granted host permissions?** (Permission model)
7. **Are you using the latest version?** (Check changelog)

## Related Projects

- **Firefox Version**: https://github.com/bpc-clone/bypass-paywalls-firefox-clean
- **iOS/iPadOS Filters**: https://gitflic.ru/project/magnolia1234/bypass-paywalls-clean-filters
- **Distribution**: https://gitflic.ru/project/magnolia1234/bpc_uploads

## Final Notes

This project provides a valuable service but exists in ethical/legal complexity. When working with it:

- **Be helpful** to users trying to access information
- **Be responsible** about not encouraging abuse
- **Be clear** about legal/ethical considerations
- **Be supportive** of journalism and paid subscriptions
- **Be cautious** about creating new circumvention methods
- **Be accurate** in describing functionality and limitations

This documentation repository serves thousands of users weekly who rely on it for accessing paywalled content. Treat it with the seriousness and ethical consideration it deserves.
