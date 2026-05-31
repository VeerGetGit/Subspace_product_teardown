# 🔍 Product Teardown — Subspace.money

> **Assignment:** Product Intern · Vocallabs.ai / Subspace.money  
> **Deadline:** 31 May 2026  
> **Author:** [Veer](https://github.com/VeerGetGit)

---

## 📌 About the Company

**[Subspace.money](https://subspace.money)** is a Bengaluru-based consumer fintech founded in 2021 by IIT Madras alumni **Ashok Kumar** and **Mritunjoy Dash**.

| Metric | Value |
|---|---|
| ARR (FY25) | ₹36.5 Cr |
| External Funding | Zero (Bootstrapped) |
| Founded | 2021 |
| Gift Card Brands | 200+ |
| AI-run Operations | 90%+ |

**Core offerings:** OTT account sharing · Bill splitting · Gadget rentals (10 min) · Discounted gift cards · Hyperlocal subscription discovery

---

## 🧭 Research Methodology

I approached this as a first-time user — installed the app, browsed as a new visitor, went through the subscription join flow, and read recent reviews before forming conclusions.

- Installed Subspace on Android and navigated the full flow from sign-up to subscription join
- Explored [subspace.money](https://subspace.money) across Home, Explore, Wallet, API, and Blog sections
- Read Play Store reviews (Jan–May 2026), filtering for 1–2 star reviews to identify real pain points
- Compared onboarding and trust flows against CRED, Splitwise, Airbnb, Netflix, and Spotify
- Captured 11 screenshots across all 5 feedback areas as supporting evidence
- Cross-referenced company data via Tracxn, Product Hunt, and the Subspace blog

---

## 🏗️ Strategic Framework — SWOT

> *I used SWOT here because Subspace's biggest risks are internal execution gaps (trust, messaging) as much as external competitive pressure.*

| | |
|---|---|
| **💪 Strengths** | Bootstrapped and profitable at ₹36.5 Cr ARR — rare in consumer fintech. Genuine PMF in India's OTT-heavy market. Negotiate API is technically unique. India's first subscription marketplace. Network effects grow with group stickiness. |
| **⚠️ Weaknesses** | Users report being kicked from shared subscriptions with no refund path. Home screen conflates 4 use cases — confusing for new users. No clear ICP in marketing. Refund friction visible in Play Store reviews. |
| **🚀 Opportunities** | India's subscription economy is growing fast. College students are a high-sharing, price-sensitive ICP not yet explicitly targeted. Negotiate API could become a B2B product for HR/finance teams. WhatsApp-native payment flows would reduce group collection friction. |
| **🚨 Threats** | Netflix India explicitly prohibits account sharing outside the household. OTT enforcement could disrupt the core sharing product. CRED and BharatPe active in adjacent reward/savings spaces. Regulatory attention on payment aggregation increasing. |

---

## 🗺️ User Journey Summary

| Step | Observation |
|---|---|
| Opened website | 4 equal-weight tiles: Add Subscriptions, Bill Payments, Events, Sell Products — no hierarchy or recommended first action for a new visitor |
| Opened app | Dark-themed home shows "No Active Subscriptions" with a single Explore Services CTA — clean but gives no context on what to do first |
| Explored Explore tab | Gift cards, shared subscriptions, and rentals shown together. Visually dense |
| Viewed a subscription listing | Netflix Premium Plan shows admin name, slot count (0/4), next billing date, ₹171.15 price, and Join Now button — no ToS or refund terms |
| Looked for dispute flow | After joining, there is no visible "Report Admin" or "Request Refund" option anywhere in the app |
| Compared competitors | Spotify has a dedicated student page (₹69/2 months). CRED uses one clear CTA per screen. Neither conflates multiple use cases on first open |

---

## ⚔️ Competitor Landscape

| Feature | Subspace | CRED | Splitwise | Walnut |
|---|---|---|---|---|
| Subscription Sharing | ✅ Core | ❌ | ❌ | ❌ |
| Bill Splitting | ✅ | ❌ | ✅ Core | ✅ |
| Negotiate API | ✅ Unique moat | ❌ | ❌ | ❌ |
| Sub Marketplace | ✅ India first | Partial | ❌ | ❌ |
| Gadget Rentals | ✅ 10-min | ❌ | ❌ | ❌ |
| Gift Card Discounts | ✅ 200+ brands | ✅ | ❌ | ❌ |
| Profitable / Bootstrapped | ✅ | ❌ | ❌ | N/A |
| In-app Dispute Flow | ❌ | ✅ | N/A | N/A |
| ICP Clarity | ❌ Unclear | CC users | Bill splitters | Trackers |

> **Key observation:** Subspace's differentiation is not communicated clearly on first open.

---

## 📋 The 5 Product Feedbacks

*Priority order based on User Impact × Execution Feasibility for a small team.*

---

### #1 · FEATURES — No Dispute Flow: Users Pay, Then Get Stuck

**🔴 Priority: Critical | Impact: High | Effort: Medium**

**Observed:** The Netflix Premium Plan join screen shows ₹171.15, admin name, slot count — but no refund policy, no info on what happens if the admin removes you, and no dispute mechanism anywhere. Play Store reviews (Jan–May 2026) show a recurring pattern: users pay → get kicked out → get no response.

**Problem:** The shared subscription model depends on members trusting their payment is protected. There is currently no in-app path to resolve admin removal or inactivity. The support route (a phone number found only in Play Store review replies) does not scale.

**Ship Instead:**
- Add a **"Report this Group"** button on the subscription management screen, visible after joining
- Hold member payments for **48 hours** before releasing to admins (escrow model)
- Trigger an **automatic refund** if a member is removed within 72 hours of payment
- Add an **Admin Trust Score** on group listings built from dispute history and completion rate

> *This mirrors how Airbnb handles host-guest conflicts and directly addresses the most common 1-star complaint.*

---

### #2 · UX — First Open Confusion: Four Products, No Starting Point

**🟡 Priority: High | Impact: High | Effort: Low**

**Observed:** Home screen shows 4 equal-weight tiles with no recommended first action. The Explore tab mixes gift cards, brand discounts, and shared subscriptions in one scroll. No onboarding tour, no intent question, no personalisation.

**Problem:** Showing all 4 use cases without hierarchy may reduce Day 1 activation — a user with one specific goal has to search rather than be guided. Products like CRED keep a single dominant CTA per screen.

**Ship Instead:**
> On first launch, show a short intent selector:  
> *"What do you want to do? → Save on OTT / Split a bill / Rent something / Discover deals"*

Route each user to a focused view and store the preference. This is a feature-flag level change — no backend infrastructure required, A/B testable in a week.

---

### #3 · GTM & ICP — Broad Messaging: Everyone Is Targeted, Nobody Feels Spoken To

**🟡 Priority: High | Impact: High | Effort: Low**

**Observed:** Homepage describes the app as "your one-stop destination to save money, rent anything, and enjoy discounted subscriptions and gift cards." No student-specific landing page, no professional tier messaging, no segment-targeted ad creative. Play Store listing leads with 10 emoji-heavy bullets covering unrelated categories.

**Problem:** Group sharing and Negotiate API are well-suited to college students and young professionals — price-sensitive users who already share passwords and split bills. Spotify targets Indian students with a dedicated page and single price (₹69/2 months). Subspace's equivalent offer is buried with no student-specific framing.

**Ship Instead:**
- **College students:** *"Watch Netflix for ₹99/month, split with your hostel group"*
- **Young professionals:** Auto-detected subscription audit — *"See what your team is overpaying for"*
- Two ICP-specific landing pages; ad creative matched to each segment

---

### #4 · COMPETITOR ANALYSIS — Platform ToS Risk: Netflix Says No, Subspace Says Nothing

**🟡 Priority: Medium | Impact: Medium | Effort: Low**

**Observed:** Netflix India Help Center explicitly states accounts may not be shared outside the household. The Subspace Netflix join screen shows ₹171.15 with no disclaimer, no mention of this household policy, and no distinction between an officially supported family plan and an informal share.

**Problem:** If Netflix enforces its policy on a Subspace-facilitated group, users lose access with no prior warning. There's also a nuance: the Premium plan allows 4 simultaneous streams, so within-plan device sharing could be technically within limits — but this nuance is invisible to buyers.

**Ship Instead:**
- Add a **platform safety label** to each listing: *"Family Plan (Platform Approved)"* vs *"Community Shared"*
- On Community Shared listings, add a **one-line risk note** + **auto-refund guarantee** if access is lost within 7 days
- Longer term: explore **official reseller agreements** with OTT platforms to convert grey-area sharing into white-label distribution

---

### #5 · POTENTIAL COLLABORATIONS — Negotiate API Has No Partner Surface or B2B Packaging

**🟢 Priority: High LTV | Impact: Medium | Effort: High**

**Observed:** The Negotiate API is mentioned once on the homepage in a single sentence under "Deals." No API docs, no developer page, no partner portal, no impact metrics. The Business API blog post is dated August 2024 with no follow-up.

**Problem:** The Negotiate API is Subspace's most technically distinctive feature — no Indian fintech competitor offers automated price negotiation at this level. But without a B2B surface, it only benefits individual app users. HR teams and SMB finance managers managing subscription budgets for employees would likely pay for this as a managed service.

**Ship Instead:**
- Package as **"Subspace for Business"** — a dashboard where HR/finance teams input their subscription list and receive negotiated rates
- First distribution targets: **Razorpay's startup ecosystem**, **Zoho's SMB base**, college ERP platforms
- Publish a public **savings calculator** and developer docs to drive inbound B2B interest

---

## 📊 Prioritisation Summary

| # | Feedback | User Impact | Feasibility | Reasoning |
|---|---|---|---|---|
| 1 | Admin Trust / Dispute Flow | 🔴 Critical | Medium | Users losing money with no in-app recourse affects every shared subscription purchase |
| 2 | Onboarding Intent Flow | 🟠 High | Fast | Feature flag change; directly improves D1 retention with no backend work |
| 3 | ICP-Focused GTM | 🟠 High | Fast | Landing page + ad creative changes; unlocks college referral loop |
| 4 | ToS Risk Disclosure | 🟡 Medium | Fast | UI badge change; reduces legal exposure and builds buyer confidence |
| 5 | Negotiate API B2B | 🟢 High LTV | Slow | Highest margin opportunity but needs biz dev pipeline; longer runway |

---

## 🤝 Potential Collaborations

| Partner | Use Case |
|---|---|
| **Razorpay / Cashfree** | Payment escrow for admin-member transactions, reducing in-house compliance burden |
| **Juspay** | 1-click checkout for frictionless group payment collection |
| **Zoho / Freshworks** | Distribution channel for the Negotiate API B2B product to SMB customers |
| **Samarth (College ERP)** | Campus-level student subscription negotiation and group sharing |
| **WhatsApp Business API** | Native group payment collection inside WhatsApp, where most target users coordinate |

---

## 🔖 Closing Note

Subspace is one of the very few bootstrapped Indian consumer fintechs generating ₹36.5 Cr ARR without external funding. The Negotiate API and group sharing moat are real.

The five issues above are **execution gaps** — not structural failures:
a missing dispute flow, a first-open UX that doesn't guide users, broad marketing that hasn't found its segment, a platform risk users don't know about, and a B2B product that hasn't been built yet.

**Fix these, and the moat gets wider.**

---

> 📎 Full teardown document with screenshots available in this repository.  
> 🔗 GitHub: [VeerGetGit](https://github.com/VeerGetGit)
