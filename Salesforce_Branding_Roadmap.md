# 🎨 Salesforce Branding Roadmap
### A Configuration-Only Guide to Making Your Org Feel Like Home

> **Powered by Intentional Design** · Beyond the Blue Cloud · Nonprofit Dreamin'
> *Pete Schweiss & Aly Marin*

---

## What This Is

This is a living, forkable roadmap for nonprofit (and any mission-driven) Salesforce admins who want to transform a generic Salesforce org into a branded, mission-aligned workspace — **using only clicks, not code.**

Every item in this guide is achievable through Salesforce configuration. No Apex. No LWC development. No Scratch Orgs. Just intentional design decisions made by people who care about the experience of the humans using the system every day.

**Fork it. Adapt it. Add to it. Share it.**

---

## Before You Start: Branding Intentions

Before touching a single setting, answer these questions with your brand manager or communications lead. Configuration decisions should follow brand decisions — not the other way around.

### The Brand Alignment Checklist

- [ ] **What are our primary and secondary brand colors?** (Get exact hex codes — not "kind of blue")
- [ ] **Do we have an approved logo file in PNG format with a transparent background?**
- [ ] **What do we call the people we serve?** (Contacts? Community Members? Participants? Students?)
- [ ] **What do we call our partner organizations?** (Accounts? Partners? Affiliates? Chapters?)
- [ ] **What is the emotional tone we want staff to feel when they open the system?** (Energized? Grounded? Supported?)
- [ ] **What is one sentence that describes why this system exists for our team?**
- [ ] **Are there images or photography that represent our mission?** (These can be used in homepage components and the login page)
- [ ] **Who on the team owns brand decisions?** (This person should be a collaborator on every customization decision)

> 💡 **Why this matters:** The fastest way to produce a "branded" org that still feels off is to apply colors without intent. Brand alignment starts with clarity, not configuration.

---

## ADA & Accessibility Guidelines

Branding should never come at the cost of accessibility. Every customization decision should be evaluated against WCAG 2.1 AA standards at minimum.

### Color Contrast Requirements

| Element | Minimum Contrast Ratio | Recommended |
|---|---|---|
| Normal text on background | 4.5:1 | 7:1 |
| Large text (18pt+ or 14pt bold) | 3:1 | 4.5:1 |
| UI components (buttons, icons) | 3:1 | 4.5:1 |
| Decorative elements only | No requirement | — |

**Free tools to check contrast:**
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) — paste your hex codes
- [Coolors Contrast Checker](https://coolors.co/contrast-checker) — visual and detailed
- [Accessible Colors](https://accessible-colors.com) — suggests accessible alternatives

### Logo & Image Accessibility
- Always provide descriptive `alt` text for any image used in custom homepage components or Experience Builder pages
- Do not rely on color alone to convey meaning in dashboards or list views
- Avoid using thin or light fonts on colored backgrounds — Salesforce's default font stack handles this well when contrast ratios are met
- When in doubt: test your org with a screen reader (NVDA for Windows, VoiceOver on Mac)

### Salesforce's Own Accessibility Resources
- [Salesforce Accessibility Overview](https://www.salesforce.com/company/accessibility/)
- [Lightning Design System Accessibility Guidelines](https://www.lightningdesignsystem.com/accessibility/overview/)

---

## Logo Dimensions Reference

Different areas of Salesforce accept logos at different sizes. Use these as your guide before exporting from Canva, Adobe, or your design tool of choice.

| Location | Recommended Dimensions | Format | Notes |
|---|---|---|---|
| **Theme Builder (org logo)** | 200 × 40px | PNG (transparent bg) | Displayed in the top navigation bar next to the app name. Will be compressed — keep it clean and simple. |
| **App Launcher icon** | 128 × 128px | PNG (transparent bg) | Square format. Appears in the App Launcher grid. Use icon/mark, not full wordmark. |
| **Login page logo** | 250 × 125px max | PNG (transparent bg) | Displayed above the login form on the right panel. See Login Page section below. |
| **Community/Experience Cloud header** | 200 × 50px | PNG (transparent bg) | Varies by template — test at multiple breakpoints. |
| **Email letterhead (Classic)** | 600px wide max | PNG or JPG | Used in email templates. |
| **Favicon (browser tab)** | 16 × 16px or 32 × 32px | ICO or PNG | Not configurable natively in core Salesforce — applies to Experience Cloud sites. |
| **Custom homepage banner** | 1200 × 300px | PNG or JPG | Used in Lightning App Builder image components. |

> 💡 **Export tip:** Always export logos at 2x the target size (e.g. 400 × 80px for Theme Builder) to ensure crispness on high-DPI screens. Salesforce will scale down; scaling up creates blurriness.

---

## The Branding Roadmap

Organized by **impact level** — start at the top for the highest-visibility wins.

---

### 🔴 Tier 1 — Highest Impact (Do These First)

#### 1. Lightning Theme Builder
**Where:** Setup → Themes and Branding

The single most impactful change you can make. Controls the global color of the navigation bar and the org logo visible to every user on every page.

**What you can configure:**
- Navigation bar background color
- Navigation bar text and icon color
- Brand color (used for highlights, active states, and focused elements)
- Page background color
- Org logo (appears top-left in navigation)
- Default avatar color

**Steps:**
1. Go to Setup → search "Themes and Branding"
2. Click "New Theme" (do not modify the Salesforce default — always create a new one)
3. Upload your logo (see dimensions above)
4. Set Brand Color to your primary hex code
5. Set Navigation Bar Color to match your brand palette
6. Adjust Navigation Bar Text Color to ensure contrast (check ADA ratios above)
7. Preview before activating
8. Click "Activate"

> ⚠️ **ADA note:** The navigation bar text color must meet 4.5:1 contrast ratio against the navigation bar background. Use the WebAIM checker before finalizing.

---

#### 2. Login Page Customization
**Where:** Setup → My Domain → Login Page Branding (requires My Domain to be enabled)

> **Note:** This applies when users log in directly at your org's login URL — not when using SSO/SAML. If your org uses SSO, users typically never see this page.

The login page is the *first impression* your system makes on a new team member. Most orgs leave it completely generic. A few minutes here goes a long way.

**What you can configure:**

| Setting | Description |
|---|---|
| **Right-side background color** | Fills the right panel behind the login form |
| **Right-side logo** | Appears above the login fields (see dimensions above) |
| **Right-side footer text** | Small text below the login button — use your tagline or a mission-aligned message |
| **Left-side background** | Can be a solid color or left to the Salesforce default |
| **Login button color** | Match to your brand primary color |
| **Login button text color** | Ensure contrast with button color |

**Steps:**
1. Setup → search "My Domain"
2. Scroll to "Authentication Configuration" → click "Edit"
3. Scroll to "Login Page Branding"
4. Upload logo (PNG, transparent background, 250 × 125px max)
5. Set background color, button color, footer text
6. Click "Save"
7. Test by opening a private/incognito browser window and navigating to your org's login URL

> 💡 **Mission moment:** The footer text field is small but powerful. Try something like *"Logging in to do meaningful work."* or your organization's tagline. It sets the tone before anyone clicks anything.

> ⚠️ **ADA note:** The login button color must meet 3:1 contrast ratio against the button background and 4.5:1 for any button text.

---

#### 3. App & Navigation Renaming
**Where:** Setup → App Manager + Navigation in each Lightning App

Renaming is one of the highest-impact, lowest-effort things you can do. Generic Salesforce terminology creates psychological distance from the mission. Your language should reflect your work.

**What you can rename:**

**Apps (App Manager):**
- Rename standard apps to match your org's mental model
- Example: "Sales" → "Donor Relations" | "Service" → "Program Support"
- Set a custom color and icon per app

**Navigation items:**
- Reorder tabs to reflect how your team actually moves through their day
- Remove tabs that aren't relevant to each audience
- Create audience-specific apps (one for program staff, one for development, one for leadership)

**Steps:**
1. Setup → App Manager → find your app → click dropdown → Edit
2. Update App Label and Description
3. Choose a custom color and icon (Salesforce provides ~100 standard icons)
4. Go to "Navigation Items" tab → reorder and add/remove items
5. Save and test

---

### 🟡 Tier 2 — High Impact (Do These Next)

#### 4. Object & Field Label Renaming
**Where:** Setup → Object Manager → [Object] → Fields & Relationships / Edit Object

Your CRM was built for salespeople. Your org is built for mission. The language should reflect that.

**Common renaming patterns for nonprofits:**

| Salesforce Default | Nonprofit Alternative |
|---|---|
| Contact | Community Member / Participant / Student / Client |
| Account | Organization / Partner / Chapter / School |
| Opportunity | Gift / Donation / Grant / Award |
| Lead | Inquiry / Prospect / Referral |
| Case | Request / Application / Support Ticket |
| Activity | Interaction / Touchpoint / Engagement |

**Steps:**
1. Setup → Object Manager → select object (e.g. Contact)
2. Click "Edit" at the top
3. Update "Label" and "Plural Label"
4. Save — changes propagate across the UI immediately
5. Repeat for individual field labels via Fields & Relationships

> ⚠️ **Important:** Renaming labels does not change API names. Integrations, reports using API names, and data migrations are unaffected. This is purely a UI change.

---

#### 5. Custom Homepage via Lightning App Builder
**Where:** Setup → Lightning App Builder → New → Home Page

The default Salesforce homepage is a blank slate. A custom homepage is your org's front door — it should tell staff where they are, why it matters, and what to do next.

**What you can add (all drag-and-drop, no code):**

| Component | Use Case |
|---|---|
| **Rich Text** | Mission statement, welcome message, announcements |
| **Image** | Mission photography, campaign imagery, seasonal art |
| **Recent Items** | Quick access to recently viewed records |
| **Report Chart** | Live dashboard data (fundraising progress, case counts, etc.) |
| **Custom Links** | Deep links to key views, reports, or external resources |
| **Chatter Feed** | Team announcements and community updates |
| **Today's Tasks** | Personalized activity queue for each user |
| **Knowledge** | Link to your BookStack, Confluence, or internal wiki |

**Design tips:**
- Lead with your mission or a motivating message — not a data table
- Use an image component at the top with mission photography (1200 × 300px)
- Keep it to 3–4 components max — avoid information overload
- Create different homepage assignments per profile or app so program staff see different content than development staff

**Steps:**
1. Setup → Lightning App Builder → New → Home Page
2. Give it a name (e.g. "Program Staff Home")
3. Drag and drop components from the left panel
4. Click "Activation" → assign to specific apps and/or profiles
5. Save and activate

---

#### 6. List View Customization & Branding
**Where:** Any Object List View → Edit Columns + Filters

List views are where staff spend most of their time. A well-organized list view signals organizational care.

**What you can configure:**
- Custom columns relevant to the team's workflow
- Filters pre-set to the most relevant records
- Saved list views named in your org's language (e.g. "Active Participants This Quarter" not "My Contacts")
- List view charts for visual data at a glance

> 💡 **Naming matters:** Name list views the way your team talks, not the way Salesforce thinks. "My Open Cases" → "Requests Needing My Attention"

---

### 🟢 Tier 3 — Refinement Layer

#### 7. Page Layout & Record Page Customization
**Where:** Setup → Object Manager → [Object] → Page Layouts AND Lightning Record Pages

Control what fields appear, in what order, and in what sections on every record page.

**Configuration options:**
- Reorder fields to match workflow priority
- Rename sections (e.g. "Contact Information" → "How to Reach Them")
- Hide fields that create confusion for certain profiles
- Add custom components to the right-hand sidebar (rich text, related lists, images)
- Use Dynamic Forms (available on custom objects and select standard objects) to show/hide fields based on field values

---

#### 8. Utility Bar Customization
**Where:** App Manager → Edit App → Utility Items

The utility bar lives at the bottom of the screen and provides quick access to tools without navigating away from a record.

**Useful utility items:**
- Recent Items
- History
- Notes
- Macros (for support teams)
- Custom links to frequently used reports or external tools

> 💡 **Keep it minimal** — 2 to 3 utility items maximum. More than that and it becomes noise.

---

#### 9. Custom Compact Layouts
**Where:** Setup → Object Manager → [Object] → Compact Layouts

Compact layouts control what fields appear in the highlights panel at the top of a record and in mobile views. Put the most mission-relevant fields first.

**Example for a Contact/Community Member:**
- Name (always first)
- Program Enrollment Status
- Primary Staff Contact
- Last Interaction Date
- Key Identifier (student ID, case number, etc.)

---

#### 10. Email Letterhead & Templates
**Where:** Setup → Classic Letterheads AND Email Templates

If your team sends emails from Salesforce, branded letterheads ensure every outbound communication reflects your organization — not a generic CRM.

**Letterhead elements:**
- Header image (600px wide, your org's logo/banner)
- Header background color
- Body background color
- Body text color and font
- Footer text (address, unsubscribe language, mission tagline)

> ⚠️ **ADA note:** Ensure sufficient contrast between body text color and body background color. Avoid light gray text on white backgrounds.

---

#### 11. Report & Dashboard Folders
**Where:** Reports Tab → All Folders / Dashboards Tab → All Folders

Organize reports and dashboards into folders named for your team's mental model, not the default Salesforce structure.

**Naming convention suggestions:**
- "Leadership Reporting — Q-over-Q"
- "Program Outcomes — Active Participants"
- "Development Team — Pipeline & Pipeline"
- "Board-Ready Dashboards"

Dashboard components also support custom colors — match chart colors to your brand palette where possible.

---

#### 12. Path Configuration
**Where:** Setup → Path Settings

Paths provide a visual progress bar at the top of records, guiding staff through key stages of a process. Available on Opportunities, Cases, Leads, and custom objects.

**What you can add per stage:**
- Key Fields panel (show the 3–5 most important fields for that stage)
- Guidance for Success (a text block explaining what should happen at this stage)
- Celebratory confetti for closed/completed stages ✨

> 💡 **Use your language:** Rename stages to match your workflow. "Closed Won" → "Gift Received" | "Closed Lost" → "Not This Time"

---

## Sharing This Roadmap

This document is designed to be shared, adapted, and built upon.

**Suggested uses:**
- Fork this repo and customize for your org's specific context
- Share the GitHub URL via QR code at conferences or training sessions
- Use it as a scoping checklist when onboarding a new Salesforce admin
- Adapt it for client orgs if you're a consultant or implementation partner

**Please contribute back:** If you find a configuration option that belongs here, open a pull request. This is a community document.

---

## Quick Reference — Priority Checklist

```
TIER 1 (Do First)
[ ] Theme Builder — colors, logo, navigation
[ ] Login Page Branding — logo, colors, footer text, button
[ ] App & Navigation Renaming — rename, reorder, create audience-specific apps

TIER 2 (Do Next)
[ ] Object & Field Label Renaming — speak your mission's language
[ ] Custom Homepage — front door of your org
[ ] List View Naming & Configuration — organize for workflow, not defaults

TIER 3 (Refinement)
[ ] Page Layouts & Record Pages — field order, sections, components
[ ] Utility Bar — 2–3 items max
[ ] Compact Layouts — highlights panel priority
[ ] Email Letterhead & Templates — branded outbound comms
[ ] Report & Dashboard Folders — named for your team
[ ] Path Configuration — visual workflow with guidance
```

---

## Additional Resources

| Resource | URL |
|---|---|
| Salesforce Lightning Design System | lightningdesignsystem.com |
| Salesforce Accessibility Overview | salesforce.com/company/accessibility |
| Trailhead: Customize Your Org with Themes | trailhead.salesforce.com |
| Trailhead: Lightning App Builder | trailhead.salesforce.com |
| Trailhead: Nonprofit TCO Overview | trailhead.salesforce.com |
| WebAIM Contrast Checker | webaim.org/resources/contrastchecker |
| WCAG 2.1 Quick Reference | w3.org/WAI/WCAG21/quickref |
| Salesforce Nonprofit Pricing | salesforce.com/nonprofit/pricing |

---

## About This Series

**Powered by Intentional Design** is a content series exploring how intentional platform design drives mission alignment, user adoption, and belonging at work.

**Beyond the Blue Cloud** is the flagship session — a collaboration between a Technology Leader and a Brand Manager exploring how nonprofit Salesforce orgs can move from generic utility to mission-aligned community hub.

*Pete Schweiss — Director of Technology Services, Hope Ignites*
*Aly Marin — [Title, Organization]*

---

*Last updated: March 2026 · Contributions welcome via pull request*
