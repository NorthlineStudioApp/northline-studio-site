# Northline Studio Website - Planning Document

## Status: READY FOR DEPLOYMENT (one placeholder to fill)

---

## Remaining Action Item

**Fill in [STATE] placeholder in terms.html:119**
- Replace `[STATE]` with your LLC's registered state (e.g., "Delaware", "Wyoming", "California")
- This appears twice in the governing law section

---

## Completed Tasks

- [x] Audit app code for actual data practices
- [x] Update privacy policy with accurate information
- [x] Add GDPR section with proper legal bases (Contract, Legitimate Interests, Legal Obligations, Consent)
- [x] Add CCPA section with required categories (Identifiers, Customer records, Commercial info, Network activity)
- [x] Update all dates to 2026
- [x] Update all domain references to northlinestudio.app
- [x] Update all email references to @northlinestudio.app
- [x] Tighten language per Codex review
- [x] Verify Firebase SDK usage (only auth + database, NO analytics/crashlytics)
- [ ] Fill in [STATE] placeholder in terms.html

---

## Decisions Made

| Item | Decision |
|------|----------|
| Domain | `northlinestudio.app` |
| Geographic scope | Worldwide (GDPR + CCPA included) |
| Theme | Dark |
| Scope | Generic LLC site (multiple apps planned) |
| IAP type | One-time, non-consumable (no subscriptions) |

---

## App Data Practices (Verified from Code)

### Firebase Packages Installed
- `@react-native-firebase/app` - Core
- `@react-native-firebase/auth` - Anonymous auth only
- `@react-native-firebase/database` - Realtime Database

### NOT Installed (verified)
- ❌ `@react-native-firebase/analytics`
- ❌ `@react-native-firebase/crashlytics`

### Data Collected
- Anonymous Firebase UID (no email/password)
- Player nicknames (user-entered)
- Game preferences and settings
- Operational app events (9 types, stored in RTDB)
- Purchase confirmations

### NOT Collected
- Email addresses or passwords
- Real names or identity
- Location data
- Device identifiers
- IP addresses (Firebase RTDB doesn't log these by default)
- Photos/camera/contacts

---

## Codex Review Issues - RESOLVED

| Issue | Status |
|-------|--------|
| Dates said 2025 | ✅ Fixed to 2026 |
| GDPR legal basis weak | ✅ Rewritten with Contract/Legitimate Interests/Legal/Consent |
| CCPA categories missing | ✅ Added full categories, sources, purposes, disclosure |
| Governing law vague | ✅ Added [STATE] placeholder + venue |
| "subscriptions" mentioned | ✅ Changed to "non-consumable purchases" |
| Firebase may collect more | ✅ Verified - only RTDB, no Analytics/Crashlytics |

---

## Deployment Steps (When Domain Ready)

1. **Fill [STATE] placeholder:**
   - Edit terms.html line 119
   - Replace both instances of `[STATE]` with your LLC state

2. **Create email accounts:**
   - `support@northlinestudio.app` (general)
   - `privacy@northlinestudio.app` (GDPR/CCPA requests)

3. **Push to GitHub:**
   ```bash
   cd /Users/brentbolinger/Documents/northline-studio-site
   git init
   git add .
   git commit -m "Initial site"
   git remote add origin https://github.com/[username]/northlinestudio-site.git
   git push -u origin main
   ```

4. **Enable GitHub Pages:**
   - Settings > Pages > Source: main branch

5. **Configure custom domain:**
   - GitHub: Settings > Pages > Custom domain: northlinestudio.app
   - DNS: Add CNAME record pointing to [username].github.io
   - Enable "Enforce HTTPS"

6. **Update app:**
   - Update privacy policy URL in SettingsScreen.tsx
   - Update support email references

---

## Files

| File | Purpose | Status |
|------|---------|--------|
| index.html | Landing page | ✅ Ready |
| privacy-policy.html | GDPR/CCPA compliant | ✅ Ready |
| terms.html | Terms of service | ⏳ Needs [STATE] filled |
| support.html | FAQ + contact | ✅ Ready |
| styles.css | Dark theme | ✅ Ready |
| favicon.svg | Site icon | ✅ Ready |
| .nojekyll | GitHub Pages config | ✅ Ready |
