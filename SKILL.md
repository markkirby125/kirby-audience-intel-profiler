---
name: kirby-audience-intel-profiler
description: "Extracts, formats, and validates subniche audience intelligence (insider jargon, daily friction, emotional triggers, taboo generic words) to tune generic content to specific buyer avatars."
category: research
triggers: [audience-dataset, subniche-lexicon, buyer-persona-intel, avatar-profiler, audience-intel, subniche-profiler]
---

# SOP: Subniche Audience Intel Extraction & Profiling

> Standard Operating Procedure for constructing high-fidelity Subniche Audience Intel Profiles that transform generic educational text into resonant, domain-native content.

---

## 1. The Subniche Translation Problem

Raw PLR and general AI drafts fail because they use **lowest-common-denominator language**. They address "business owners" looking to "grow their business." 

No real human identifies as a "generic business owner":
* A freelance developer cares about scope creep, client invoice delays, Git merge conflicts, and unbillable maintenance.
* A Shopify brand owner cares about inventory reorder minimums, ad account bans on Meta, return rates, and shipping carrier surcharges.
* A real estate agent cares about expired listings, open-house tire kickers, split commissions, and MLS compliance.

The same underlying business concept (e.g., "follow up with leads promptly") requires completely different vocabulary, stakes, and metaphors for each audience. This skill extracts and organizes that domain intelligence.

```
┌─────────────────────────────────────────────────────────┐
│                    Generic Topic                        │
│          "How to manage customer cancellations"         │
└────────────────────────────┬────────────────────────────┘
                             │
            ┌────────────────┴────────────────┐
            ▼                                 ▼
┌───────────────────────────┐   ┌───────────────────────────┐
│     SaaS Founder Intel    │   │  High-Ticket Coach Intel  │
├───────────────────────────┤   ├───────────────────────────┤
│ Terms: Churn, MRR, exit   │   │ Terms: Retention, deposit,│
│ interview, Stripe billing │   │ scope dispute, onboarding │
│ Stake: LTV/CAC ratio      │   │ Stake: Referral pipeline  │
└───────────────────────────┘   └───────────────────────────┘
```

---

## 2. The 5 Core Intel Dimensions

Every Subniche Audience Profile must capture five distinct dimensions:

### 1. Insider Lexicon Whitelist
* The technical jargon, acronyms, and operational shorthand that signal *"I am one of you."*
* *Test:* If a word wouldn't be used naturally in a private Slack group of practitioners, don't include it.

### 2. Taboo Generic Words (The Blacklist)
* Overused, vague words that instantly brand the content as amateur or AI-generated.
* *Examples to ban:* "success", "journey", "unlock", "elevate", "game-changer", "scale your business", "wear many hats".

### 3. Concrete Daily Operational Frictions (The Scars)
* Not abstract fears ("fear of failure"), but **tangible daily annoyances**.
* *Examples:* 
  - *"Waiting 14 days for Stripe payouts during a cash flow crunch."*
  - *"Getting a chargeback notification on a $180 order after the customer already signed for delivery."*

### 4. Skepticism & Objection DNA
* Why does this audience mistrust generic advice?
* What courses or tools have burned them in the past?
* What do they believe *"never works in my specific industry"*?

### 5. Status & Identity Aspirations
* What does success look like to them in terms of lifestyle and peer recognition? (e.g., not just "$10k/month", but *"firing the micromanaging client and taking Friday afternoons off with zero Slack pings"*).

---

## 3. Extraction Protocol

To profile an audience with an operator or research an unfamiliar niche, execute this structured inquiry:

```markdown
Analyze the target micro-audience: [Insert Niche, e.g., Boutique Fitness Gym Owners]
1. List 15 insider technical terms, KPIs, or slang phrases they use daily.
2. List 10 generic business buzzwords they roll their eyes at.
3. Identify their #1 operational headache that steals their time before 10 AM.
4. Identify the biggest financial leak in their business model.
5. What is the most common bad advice handed out by generic marketing gurus that ruins their business?
6. Format the findings into a standard Audience Intel Profile.
```

---

## 4. Audience Intel Profile Schema

Save the profile as `audience_intel_[slug].json` or `.yaml`:

```yaml
---
audience_profile:
  avatar_name: "B2B Fractional CMO"
  target_market: "Solo consultants advising $2M-$10M ARR companies"
  experience_level: "Senior (Ex-VP of Marketing / Senior Agency Director)"
  
  lexicon_whitelist:
    - "pipeline velocity"
    - "attribution model"
    - "deal size / ACV"
    - "sales-marketing alignment"
    - "outbound sequence"
    - "ad spend efficiency"
    - "churn mitigation"
    - "board decks"

  taboo_generic_terms:
    - "make sales"
    - "get clients"
    - "social media marketing"
    - "grow your brand"
    - "passive income"

  daily_friction_points:
    - "Founders micromanaging channel tactics instead of letting strategy run"
    - "Sales teams blaming marketing for unqualified SQLs"
    - "Legacy CRM tracking broken and unmaintained by junior reps"
    - "Clients treating retainers like 24/7 on-call tech support"

  core_objections_to_training:
    - "I have 15 years of corporate experience; generic marketing courses are insulting."
    - "My clients are enterprise B2B; retail or e-commerce tactics don't apply."

  aspirational_victory: "Operating with 4 high-retainer accounts ($6k/mo each), zero tactical execution, and quarterly advisory calls only."
---
```

---

## 5. Integration with Personalization Engine

When running `kirby-plr-personalizer`:
1. Ingest `audience_profile.yaml`.
2. Automatically inject the `lexicon_whitelist` into the prompt's vocabulary requirement.
3. Pass `taboo_generic_terms` into the negative prompt constraints.
4. Ground all metaphors in the `daily_friction_points`.
