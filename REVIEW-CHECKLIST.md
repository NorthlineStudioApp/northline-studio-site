# Post-Review Checklist

## Status: ALL ITEMS RESEARCHED

---

## Decisions Made
- [x] Governing Law: Keep New Mexico
- [ ] Arbitration clause: User reviewing draft (optional addition)

---

## Tasks

### 1. Arbitration Clause (OPTIONAL)
**Status:** Draft below for review

**Does it reveal your name?** No. The clause is between "Northline Studio LLC" and "you" (the user). Your personal name never appears.

**Sample clause (if you want to add it to terms.html):**

```html
<h2>13. Dispute Resolution and Arbitration</h2>
<p>
  <strong>Informal Resolution First:</strong> Before initiating any formal dispute
  process, you agree to contact us at support@northlinestudio.app to attempt to
  resolve the dispute informally. We will try to resolve any claim within 30 days.
</p>
<p>
  <strong>Binding Arbitration:</strong> If we cannot resolve a dispute informally,
  you and Northline Studio LLC agree to resolve any claims through final and binding
  arbitration administered by the American Arbitration Association ("AAA") under its
  Consumer Arbitration Rules. Arbitration may be conducted remotely (by phone, video,
  or written submission) so neither party needs to travel.
</p>
<p>
  <strong>No Class Actions:</strong> All claims must be brought individually. You waive
  any right to participate in a class action, class arbitration, or representative action.
</p>
<p>
  <strong>Small Claims Exception:</strong> Either party may bring an individual action
  in small claims court if the claim qualifies.
</p>
<p>
  <strong>Opt-Out:</strong> You may opt out of this arbitration agreement by emailing
  support@northlinestudio.app within 30 days of first using the app, with subject line
  "Arbitration Opt-Out" and your anonymous app identifier (found in Settings).
</p>
```

**Pros:** Avoids courtroom litigation, can be done remotely, class action waiver
**Cons:** More complex language, some users dislike arbitration clauses
**Your call:** This is optional. Your current Terms are already solid.

---

### 2. Privacy Policy - User Communications
**Status:** ✅ COMPLETE (see updated section below)

Add this to "Information You Provide" section of privacy-policy.html:

```html
<li><strong>Support Communications:</strong> If you contact us for support, you provide
  your email address and any information included in your message. We use this only
  to respond to your inquiry.</li>
```

**Deployment note added:** Ensure emails are set up before launch.

---

### 3. In-App Terms Agreement
**Status:** ✅ RESEARCHED

**Current state:**
- Age Gate shows DOB picker + "This app is intended for adults 18+ only"
- Privacy Policy link exists in Settings screen
- NO explicit "By continuing, you agree to Terms" language at first launch

**Reviewer's suggestion:** Add Terms/Privacy agreement to age gate

**Is this blocking?** No. The current setup is common for many apps. Apple doesn't strictly require a clickthrough agreement - having Terms accessible is sufficient for most apps.

**Optional enhancement:** Could add below the Continue button:
"By continuing, you agree to our Terms of Service and Privacy Policy"
(with links)

**Recommendation:** Nice-to-have, not required. Your call if you want to add it.

---

### 4. In-App Safety Disclaimers
**Status:** ✅ VERIFIED - ALREADY COVERED

**Found in app:**
- **ActSelectionScreen:** "💕 Only do what you're both comfortable with" (always visible when picking acts)
- **StoreScreen:** "A consent-first relationship game for couples. All activities emphasize communication, mutual comfort, and connection."
- **Power Play acts:** Multiple acts include "Agree on a safe word first" and consent check-ins
- **Pack descriptions:** "Consent-first power exchange"

**Conclusion:** The reviewer's suggestion ("Always respect boundaries and obtain consent") is already implemented throughout the app. No changes needed.

---

### 5. App Store Privacy Questionnaire
**Status:** ✅ EXPLAINED

**What is it?**
When you submit to App Store Connect, Apple requires you to fill out an "App Privacy" section that generates the privacy "nutrition label" users see on your App Store listing.

**You'll answer questions like:**
- Do you collect Contact Info? → No
- Do you collect Identifiers? → Yes (anonymous ID)
- Do you collect Usage Data? → Yes (game analytics)
- Do you collect Sensitive Info? → Yes (anatomy preferences - select "Health" or "Sensitive Info")
- Is data linked to identity? → No (anonymous)
- Is data used for tracking? → No

**Where:** App Store Connect → Your App → App Privacy

**When:** During app submission, before review

**Your answers based on code audit:**
| Category | Collected? | Linked to Identity? | Used for Tracking? |
|----------|------------|---------------------|-------------------|
| Contact Info | No | - | - |
| Health (anatomy prefs) | Yes | No | No |
| Identifiers | Yes (anonymous) | No | No |
| Usage Data | Yes | No | No |
| Purchases | Yes | No | No |

---

### 6. Missouri Foreign LLC Registration
**Status:** ✅ RESEARCHED

**Do you need to register your NM LLC in Missouri?**

**Triggers for registration (if ANY apply, you likely need to register):**
- Physical office, store, or warehouse in Missouri
- Employees working in Missouri
- Regularly sell products/services to Missouri customers

**Exemption:** Business conducted for less than 30 days doesn't require registration.

**Your situation (app developer working from home in MO):**
- No physical business location (just home)
- No employees
- Customers are worldwide (not specifically Missouri)
- Revenue comes from Apple (based in California), not direct MO sales

**Gray area:** Working from home running an online business is a common scenario. Many solo app developers with out-of-state LLCs don't register in their home state if they have no physical presence, employees, or Missouri-specific customers. However, Missouri *could* argue you're "transacting business" from there.

**Risk of not registering:**
- Minimum $1,000 fine if caught
- Cannot sue in Missouri courts to enforce contracts (can still be sued though)

**If you decide to register:**
1. Get Certificate of Good Standing from New Mexico (within 60 days)
2. Appoint Missouri registered agent ($50-150/year)
3. File Application for Registration: $105 + 2.15% credit card fee
4. Processing: ~2 weeks online

**Recommendation:** Consult a business attorney or CPA familiar with Missouri. Many solo developers operate without registering, but it's technically a gray area. The safe path is to register; the common path is to not register until you have real MO presence.

**Sources:**
- [Missouri Secretary of State LLC-4 Form](https://www.sos.mo.gov/CMSImages/Business/llc4.pdf?v=2)
- [ZenBusiness: Missouri Foreign LLC Registration](https://www.zenbusiness.com/missouri-llc-foreign-qualification/)
- [Missouri Statute 347.153](https://law.justia.com/codes/missouri/title-xxiii/chapter-347/section-347-153/)

---

## Deployment Checklist (When Domain Ready)
- [ ] Buy domain: northlinestudio.app
- [ ] Set up email: support@northlinestudio.app
- [ ] Set up email: privacy@northlinestudio.app
- [ ] Push site to GitHub
- [ ] Enable GitHub Pages
- [ ] Point DNS to GitHub
- [ ] Update app config.ts: privacyPolicyUrl → https://northlinestudio.app/privacy-policy
- [ ] Update app SettingsScreen if needed
- [ ] Fill out App Store Connect privacy questionnaire
