# N7 Shortlinks

![WordPress](https://img.shields.io/badge/WordPress-5.0%2B-blue)
![PHP](https://img.shields.io/badge/PHP-7.4%2B-purple)
![License](https://img.shields.io/badge/License-GPL--2.0-green)
![Version](https://img.shields.io/badge/Version-0.1.0-orange)

**Secure shortlink management plugin with tracking, statistics, and splash page support for WordPress.**

<p align="center">
  <strong>⭐ If you find this plugin useful, give it a star on GitHub! ⭐</strong>
</p>

---

## 📋 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Requirements](#-requirements)
- [Installation](#-installation)
- [Usage Guide](#-usage-guide)
  - [Creating a New Shortlink](#creating-a-new-shortlink)
  - [Redirect Modes](#redirect-modes)
  - [Splash Page](#splash-page)
  - [Statistics & Tracking](#statistics--tracking)
  - [Global Settings](#global-settings)
- [FAQ](#-faq)
- [Troubleshooting](#-troubleshooting)
- [Changelog](#-changelog)
- [Support](#-support)
- [License](#-license)

---

## 🎯 About

**N7 Shortlinks** is a WordPress plugin that allows you to create and manage shortlinks with ease. This plugin is perfect for:

- **Bloggers** who want to shorten affiliate URLs
- **Website owners** who want to track link clicks
- **Publishers** who want to display ads on splash pages before redirecting
- **Marketers** who need comprehensive visitor statistics

---

## ✨ Features

### 🔗 Shortlink Management
- **Custom Slugs**: Create memorable shortlinks with your own slugs
- **Auto-Generated Slugs**: 6-character random slugs for quick creation
- **Slug Validation**: Real-time availability checking
- **SEO-Friendly Redirects**: Automatic 301 redirects when changing slugs
- **Main Slug Configuration**: Customize the base path (default: `/go/`)
- **Bulk Operations**: Edit, delete, or toggle multiple links
- **Search & Filter**: Find links by slug, title, or destination URL
- **Active/Inactive Toggle**: Disable links without deletion

### 🚀 Redirect Modes
- **Direct Mode**: Instant 302 redirect to destination URL
- **Splash Mode**: Countdown page with monetization opportunities
  - Display WordPress pages/posts as splash content
  - Random content selection from configured pools
  - Overlay injection on existing WordPress content

### 📊 Statistics & Tracking
- **Click Metrics**: Total clicks, unique visitors (IP-based)
- **Geographic Data**: Country, country code, city, ISP via IPInfo.io API
- **Device Analytics**: Browser, OS, device type detection
- **Time-Based Analysis**: Daily, weekly, monthly click trends
- **Referrer Tracking**: See where visitors come from
- **Dashboard Insights**: Top links, recent clicks, visual charts
- **Privacy-Focused**: IP addresses hashed for unique visitor counting

### 🎨 Splash Page
- **Dual Countdown Modes**:
  - **Single**: Top-right countdown only
  - **Dual**: Top-right + footer countdown with scroll animation
- **Customizable Timer**: 0-60 seconds countdown duration
- **Theme Support**: Auto (system preference), Light, or Dark mode
- **Ad Monetization**: Header, sidebar, and footer ad slots
- **AdBlock Detection**: Notify users with ad blockers enabled
- **Content Integration**: Display any WordPress page/post content
- **Token-Based Security**: Time-limited tokens prevent bypass
- **Responsive Design**: Mobile-optimized splash pages

### 🛡️ Security
- **URL Validation**: Prevent malicious destination URLs
- **Input Sanitization**: All inputs cleaned with WordPress functions
- **Output Escaping**: XSS protection on all rendered data
- **Nonce Verification**: CSRF protection on state-changing operations
- **Token Validation**: HMAC-signed tokens for splash page redirects
- **Capability Checks**: Role-based access control (`manage_options`)
- **SQL Injection Prevention**: Prepared statements for all queries
- **IP Privacy**: SHA-256 hashing for visitor IP addresses

### 🌐 Internationalization
- **Multi-Language Ready**: Full translation support
- **Included Translations**: English, Indonesian (Bahasa Indonesia)
- **Text Domain**: `n7-shortlinks`
- **RTL Support**: Right-to-left language compatibility
- **Admin & Frontend**: Both dashboard and splash pages translatable

---

## 💻 Requirements

| Component | Minimum Version |
|-----------|-----------------|
| WordPress | 5.0 or higher |
| PHP | 7.4 or higher |
| MySQL | 5.6 or higher |

---

## 📥 Installation

### Method 1: Upload via WordPress Dashboard (Recommended)

1. Download the `n7-shortlinks-x.x.x.zip` file from the [Releases page](https://github.com/nandung-id/n7-shortlinks/releases)
2. Log in to your WordPress dashboard
3. Go to **Plugins → Add New → Upload Plugin**
4. Click **Choose File** and select the downloaded ZIP file
5. Click **Install Now**
6. After installation completes, click **Activate Plugin**

### Method 2: Manual Upload via FTP

1. Download the `n7-shortlinks-x.x.x.zip` file from the [Releases page](https://github.com/nandung-id/n7-shortlinks/releases)
2. Extract the ZIP file on your computer
3. Upload the `n7-shortlinks` folder to `/wp-content/plugins/` using FTP
4. Log in to your WordPress dashboard
5. Go to **Plugins** and activate **N7 Shortlinks**

---

## 📖 Usage Guide

### Creating a New Shortlink

1. Go to the **N7 Shortlinks** menu in your WordPress dashboard
2. Click the **Add New** button
3. Fill in the form with the following information:

| Field | Description | Example |
|-------|-------------|---------|
| **Title** | Title for identification (optional) | "Tokopedia Affiliate Link" |
| **Destination URL** | The target URL to redirect to | `https://tokopedia.com/product/123` |
| **Slug** | Short code for the URL (auto-generated if empty) | `shop123` |
| **Mode** | Choose Direct or Splash | Direct |
| **Status** | Active or Inactive | Active |

4. Click **Save**
5. Your shortlink is ready to use: `https://your-website.com/shop123`

### Redirect Modes

#### Direct Mode
Visitors will be immediately redirected to the destination URL without any intermediate page.

**When to use:**
- Links that don't require monetization
- Internal website links
- Links that need fast redirection

#### Splash Mode
Visitors will see a splash page with a countdown before being redirected to the destination URL.

**When to use:**
- Affiliate links you want to monetize with ads
- Download links that require confirmation
- Links where you want to display additional information

### Splash Page

When using **Splash Mode**, you can customize:

#### Countdown Timer
- Set the countdown duration (0-60 seconds)
- A value of 0 means immediate redirect (same as direct mode)
- Recommendation: 5-10 seconds for a balance between UX and monetization

#### Splash Content
Choose the content source to display:

| Type | Description |
|------|-------------|
| **Page** | Display content from a WordPress page |
| **Post** | Display content from a WordPress post |
| **Random** | Display random content from a selected list |

#### Ad Slots
You can place ad code in three locations:
- **Header**: At the top of the page
- **Sidebar**: Next to the content
- **Footer**: At the bottom of the page

### Statistics & Tracking

This plugin automatically tracks every click on your shortlinks.

#### Information Tracked:
- Total click count
- Click timestamp
- User agent (browser & device)
- IP address (for location analysis)
- Referrer (where the visitor came from)

#### Viewing Statistics:
1. Go to the **N7 Shortlinks** menu
2. Click on the shortlink you want to view statistics for
3. The **Statistics** tab will display complete data

### Global Settings

Access global settings via **N7 Shortlinks → Settings**:

#### Main Slug
- Customize the base path for all shortlinks (default: `go`)
- Example: Change from `/go/abc123` to `/link/abc123`
- **Important**: After changing, flush permalinks (Settings → Permalinks → Save)
- **SEO Protection**: Option to create 301 redirects for all existing links

#### Default Countdown
Set the default countdown duration (0-60 seconds) for new shortlinks in splash mode.

#### Countdown Mode
Choose how countdown buttons appear:
- **Single**: One countdown at top-right corner
- **Dual**: Top-right countdown + footer countdown with scroll animation

#### Theme
Choose the theme for splash pages:
- **Auto**: Follow visitor's system preference (light/dark)
- **Light**: Always display light theme
- **Dark**: Always display dark theme

#### Ad Codes
Enter ad codes (Google AdSense, Media.net, etc.) for monetization:
- **Header Ad**: Banner placement above content
- **Sidebar Ad**: Vertical ad alongside content
- **Footer Ad**: Banner placement below content
- Supports HTML/JavaScript injection

#### AdBlock Settings
- **Warning Message**: Custom message for ad blocker users
- **Whitelisted Domains**: Domains exempt from ad blocker detection

#### Tracking Settings
- **IPInfo.io API Token**: Enable server-side geolocation
  - Get free token at [ipinfo.io](https://ipinfo.io)
  - Provides country, city, ISP data
  - Results cached for 24 hours to save API quota

---

## ❓ FAQ

### Is this plugin free?
Yes, N7 Shortlinks is a free plugin.

### Is this plugin compatible with my theme?
Yes, this plugin works with all WordPress themes that follow WordPress standards.

### How many shortlinks can I create?
There is no limit to the number of shortlinks you can create.

### Will statistics data be lost if the plugin is deactivated?
No, data is stored in the WordPress database and will remain even if the plugin is deactivated. Data will only be deleted if you delete (uninstall) the plugin.

### How do I change a shortlink's slug?
1. Go to the shortlinks list
2. Click **Edit** on the shortlink you want to modify
3. Change the **Slug** field
4. Choose SEO redirect option:
   - **Create 301 Redirect** (Recommended): Old slug automatically redirects to new slug
   - **Delete Old Slug**: Old slug returns 404 error
5. Click **Save**

> 💡 **Tip**: Using 301 redirects preserves SEO value and prevents broken links!

### Does this plugin support 301 redirects?
Yes! The plugin supports both:
- **302 Redirects**: Used for actual shortlink redirects (temporary, suitable for changing destinations)
- **301 Redirects**: Used for SEO when changing slugs (permanent, preserves link juice)

When you change a shortlink's slug, you can create a 301 redirect from the old slug to the new one.

### How do I add ads to the splash page?
1. Go to **N7 Shortlinks → Settings**
2. Scroll to the **Ad Codes** section
3. Paste your ad code (Google AdSense, etc.) in the desired slot
4. Click **Save**

### Does this plugin affect SEO?
No, shortlinks use 302 redirects which do not affect your website's SEO.

---

## 🔧 Troubleshooting

### Shortlink not working (404 Error)

**Common causes:**
1. WordPress permalinks are not configured correctly
2. The `.htaccess` file cannot be written

**Solution:**
1. Go to **Settings → Permalinks**
2. Click **Save Changes** (without changing anything)
3. Try accessing the shortlink again

### Splash page not displaying ads

**Common causes:**
1. Invalid ad code
2. Ad blocker is active in the browser

**Solution:**
1. Make sure the ad code is correct
2. Disable ad blocker for testing
3. Check the browser console for JavaScript errors

### Statistics not being recorded

**Common causes:**
1. Caching plugin is too aggressive
2. CDN is caching the redirect page

**Solution:**
1. Exclude shortlink URLs from cache
2. Add a CDN rule to bypass shortlinks

### Plugin conflicts with other plugins

**Solution:**
1. Deactivate other plugins one by one to find the conflict
2. Contact support with information about the conflicting plugin

---

## 📝 Changelog

### Version 0.1.0 (Initial Release)
- ✅ Shortlink management with CRUD operations
- ✅ Direct (302) and Splash redirect modes
- ✅ Dual countdown modes (single/dual with scroll animation)
- ✅ Comprehensive click statistics and analytics
- ✅ Geographic tracking with IPInfo.io API integration
- ✅ Device, browser, and OS detection
- ✅ SEO-friendly 301 redirects for slug changes
- ✅ Main slug configuration with bulk redirect support
- ✅ Ad monetization slots (header, sidebar, footer)
- ✅ AdBlock detection and whitelisting
- ✅ Auto/light/dark theme support
- ✅ WordPress content integration for splash pages
- ✅ Overlay injection system for existing content
- ✅ Token-based security for splash redirects
- ✅ REST API with full CRUD endpoints
- ✅ React + TypeScript admin dashboard
- ✅ React + TypeScript splash page app
- ✅ Multi-language support (English, Indonesian)
- ✅ Database upgrade system for schema migrations

---

## 💬 Support

If you experience issues or have questions:

1. **GitHub Issues**: [Create a new issue](https://github.com/nandung-id/n7-shortlinks/issues)
2. **Email**: Contact the developer via [nandung.id](https://nandung.id)

### Before Contacting Support

Please include the following information:
- WordPress version
- PHP version
- N7 Shortlinks plugin version
- Clear description of the issue
- Screenshots if available

---

## 📄 License

N7 Shortlinks is licensed under the [GPL-2.0 License](https://www.gnu.org/licenses/gpl-2.0.html).

```
Copyright (C) 2024 Nandung Prasetyo

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.
```

---

## 👨‍💻 Credits

**Developed by:** [Nandung Prasetyo](https://nandung.id)

**Repository:** [github.com/nandung-id/n7-shortlinks](https://github.com/nandung-id/n7-shortlinks)

---

