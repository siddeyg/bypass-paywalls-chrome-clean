# Bypass Paywalls Clean - Documentation

## Overview

This repository serves as the **documentation and release repository** for the Bypass Paywalls Clean (BPC) Chrome extension. The actual extension code is hosted on [GitFlic](https://gitflic.ru/project/magnolia1234/bpc_uploads) for distribution.

**Important Note**: This is NOT a code repository. This repository contains:
- User-facing documentation
- Installation instructions
- Changelog/version history
- Allowlist configuration guides
- License and legal information

## What is Bypass Paywalls Clean?

Bypass Paywalls Clean is a browser extension for Chromium-based browsers (Chrome, Edge, Brave, Opera, Vivaldi, Yandex, Kiwi Browser) that allows users to read articles from websites that implement paywalls. The extension:

- Bypasses paywalls on 600+ supported news, magazine, and business websites
- Supports custom site configuration for unlisted sites
- Uses various techniques: cookie clearing, JavaScript blocking, user-agent spoofing, etc.
- Receives weekly updates with fixes and new sites
- Is provided for educational purposes only

## Repository Structure

```
bypass-paywalls-chrome-clean/
├── README.md              # Main user documentation (installation, usage, supported sites)
├── changelog.txt          # Version history and release notes
├── LICENSE                # MIT License
├── release-hashes.txt     # SHA checksums for release verification
├── not-for-install.txt    # Note directing to actual installation location
├── allowlist/             # Browser allowlist configuration guides
│   └── README.md          # OS-specific instructions for allowlisting the extension
└── .github/               # GitHub repository configuration
```

## Key Files Explained

### README.md
The main documentation file containing:
- **Installation instructions** - How to install via "load unpacked" or CRX file
- **Supported websites** - Comprehensive list of 600+ supported news sites organized by:
  - Geography (USA, Canada, Europe, Asia, Latin America, etc.)
  - Category (Business, Tech, Sports, Magazines, etc.)
  - Publisher groups (Media conglomerates with multiple properties)
- **Troubleshooting guide** - Common issues and solutions
- **Custom site configuration** - How to add unlisted sites
- **Update instructions** - How to keep the extension current

### changelog.txt
Version history showing:
- Release versions with dates
- New sites added
- Bug fixes for existing sites
- Feature updates and improvements
- Post-release patches

The changelog follows semantic versioning (v3.x.x.x) and includes detailed descriptions of changes.

### allowlist/README.md
Platform-specific instructions for adding the extension to browser allowlists:
- **Windows**: Registry modifications via .reg files or PowerShell scripts
- **macOS**: Mobile config profiles for policy management
- **Linux**: Notes on local extension installation (allowlist not needed)

Important warning about browser management messages when using allowlists.

### LICENSE
MIT License - permissive open source license allowing:
- Commercial and private use
- Modification and distribution
- Limited liability and no warranty

### release-hashes.txt
SHA-256 checksums for verifying the integrity of downloaded extension files.

## Extension Features

Based on the README documentation, the extension provides:

### Core Functionality
1. **Paywall Bypass** - Multiple techniques to access paywalled content
2. **Cookie Management** - Clear cookies to reset article limits
3. **Custom Sites** - User-configurable site support
4. **Automatic Updates** - Weekly releases with new sites and fixes

### Bypass Techniques
The extension employs various methods:
- Cookie blocking/removal (defeats metered paywalls)
- User-agent spoofing (Googlebot, Bingbot, Facebookbot)
- Referer modification (Facebook, Google, Twitter)
- Random IP addresses (X-Forwarded-For header)
- JavaScript blocking (selective by domain/inline)
- Regular expression blocking (scripts/XHR)
- AMP page redirects
- JSON content extraction
- Archive.is integration
- DOM element manipulation

### Permission Model
- **Limited host permissions by default** - Privacy-focused design
- **Opt-in for custom sites** - Users grant permissions as needed
- **Site-specific permissions** - Can request access per domain

## Supported Website Categories

The extension supports sites across:

### News & Media
- **National/International News**: NY Times, Washington Post, Reuters, The Economist, Financial Times
- **Business**: WSJ, Bloomberg, Forbes, Fortune, Harvard Business Review
- **Tech/Science**: Wired, MIT Tech Review, Scientific American, Nature, Science
- **Sports**: The Athletic, ESPN, Sports Illustrated
- **Magazines**: The Atlantic, New Yorker, Vanity Fair, Vogue, Time

### Geographic Coverage
- **North America**: 200+ US newspapers, Canadian nationals and regionals
- **Europe**: UK, Germany, France, Italy, Spain, Netherlands, Nordic countries
- **Asia**: India, Japan, Singapore, Hong Kong, Taiwan
- **Oceania**: Australia, New Zealand
- **Latin America**: Brazil, Argentina, Chile, Mexico

### Publisher Groups
Many sites are organized by media conglomerate:
- Gannett (USA Today network)
- Advance Local
- McClatchy Group
- Tribune Publishing
- Condé Nast
- Hearst Communications
- News Corp
- And 50+ other media groups

## Installation Methods

### Method 1: Load Unpacked (Developer Mode)
Best for: Testing, development, users comfortable with manual updates
- Download master ZIP from GitFlic
- Enable Developer Mode in browser
- Load unpacked extension folder
- No automatic updates

### Method 2: CRX File
Best for: Automatic updates, production use
- Download CRX from GitFlic
- May require allowlist configuration (see allowlist/README.md)
- Automatic updates
- Some browsers need extension added to policy allowlist

### Method 3: Mobile (Kiwi Browser)
Android users can install via Kiwi Browser with CRX or ZIP methods

## Update Strategy

The project follows a rapid release cycle:
- **Weekly releases** for new sites and bug fixes
- **Post-release updates** available via opt-in (10 days after release)
- **Manifest v3** migration completed (as of v3.8.8.0)
- Version history maintained in changelog.txt

## Custom Site Configuration

Users can extend the extension by adding custom sites with options:
- Cookie policies (allow/block)
- User-agent strings
- Referer headers
- IP spoofing
- JavaScript controls
- Content blocking rules
- AMP redirects
- JSON extraction
- Archive.is integration
- DOM manipulation

Example custom site configurations available for download.

## Troubleshooting Guidelines

The README provides a systematic troubleshooting approach:
1. Disable other extensions (especially ad blockers)
2. Verify site is enabled in options
3. Clear cookies via extension popup
4. Grant host permissions
5. Check for latest version
6. Handle AMP redirects properly
7. Report issues on GitHub with details

Recommended companion extension: uBlock Origin

## Browser Compatibility

### Supported Browsers
- **Desktop**: Chrome, Edge, Brave, Opera, Vivaldi, Yandex
- **Mobile**: Kiwi Browser (Android)
- **Limited**: Orion Browser (iOS/iPadOS - incomplete WebExtensions API)

### Firefox Users
Separate Firefox version available at:
https://github.com/bpc-clone/bypass-paywalls-firefox-clean

### iOS/iPadOS Users
Use ad blocker with custom filters and userscripts:
https://gitflic.ru/project/magnolia1234/bypass-paywalls-clean-filters

## Legal & Ethical Considerations

### License
MIT License - Educational purposes only

### Disclaimer
From the LICENSE:
> This software is provided for educational purposes only and is provided "AS IS", without warranty of any kind...

Users should:
- Respect copyright and publisher rights
- Support journalism through subscriptions when possible
- Use responsibly and ethically
- Understand local laws regarding paywall circumvention

### Not on Official Stores
The extension is NOT available on Chrome Web Store, requiring:
- Developer mode installation, OR
- Allowlist policy configuration

This is intentional due to store policies on paywall circumvention tools.

## Community & Support

### Issue Reporting
Submit new site requests or bug reports on GitHub with:
- Extension version
- Paywalled article URL
- Detailed issue description
- Results of troubleshooting steps

### Alternative Contact
If GitHub is offline: X/Twitter @Magnolia1234B (DM)

### Update Source
Primary distribution: GitFlic (Russian-based Git hosting)
- Mirrors resilience against takedowns
- Provides automatic updates for CRX installations

## Development Notes

### Recent Changes
- **Manifest v3 migration** (October 2024) - Updated to latest Chrome extension API
- **Performance improvements** - Optimized for faster page loads
- **New bypass techniques** - External fetch improvements, DOM manipulation

### Active Maintenance
- Regular weekly updates
- Responsive to site changes
- Community-driven site additions
- Bug fixes within days of reports

## Technical Architecture

While this repository doesn't contain the code, based on documentation we can infer:

### Extension Components
1. **Background Service** - Intercepts requests, modifies headers
2. **Content Scripts** - DOM manipulation, paywall removal
3. **Popup Interface** - User controls, cookie clearing
4. **Options Page** - Site configuration, custom sites
5. **Storage** - User preferences, site rules

### Bypass Strategy
- **Detection** - Identify paywall presence
- **Intervention** - Apply appropriate bypass technique(s)
- **Monitoring** - Track success/failure
- **Update** - Adapt to site changes

## Conclusion

This repository serves as the documentation hub for a widely-used browser extension that provides access to paywalled content across 600+ news and media websites. While the actual code is hosted elsewhere for distribution purposes, this repository provides:

- Comprehensive installation guides
- Detailed site support lists
- Version history and updates
- Configuration instructions
- Community support information

The project demonstrates:
- Active maintenance and rapid updates
- Broad website compatibility
- Flexible configuration options
- Privacy-conscious permission model
- Cross-platform support

Users should use this tool responsibly and support quality journalism through legitimate subscriptions when possible.
