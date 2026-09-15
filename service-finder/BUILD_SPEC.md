# Kidmans Partners — Service Finder Functional Build Specification

**Purpose:** Developer-ready reference for the Business and Personal Service Finder forms, dynamic outcome pages, and unstyled Gravity Forms notifications.

> **Source hierarchy:** This specification consolidates the refreshed client brief, the Business landing-page and outcome-page PDFs, and the retained form-logic documentation. It resolves the previous Personal Step 3 inconsistency by using a pathway-specific qualifier for each Personal path.

---

## 1. Build Scope

| Item | Requirement |
|---|---|
| Landing pages | Two: Business Advisory Service Finder and Personal Advisory Service Finder |
| Form engine | Gravity Forms multi-page / conditional-logic forms |
| Image-choice interface | Jetsloth Gravity Forms Image Choices add-on |
| Answer steps | Three answer steps plus a lead-capture step |
| Full outcome combinations | 30 Business + 45 Personal = **75** answer combinations |
| Visual outcome templates | One Business outcome template and one Personal outcome template; data changes dynamically |
| User confirmation emails | Seven conditional, plain-text notifications — one for each top-level pathway |
| Admin notifications | Two plain-text notifications — one Business and one Personal |
| Total Gravity Forms notifications | **Nine**: 7 user confirmations + 2 admin notifications |
| Styling of notifications | None. Use Gravity Forms plain-text notification content only. |

---

## 2. Global Form Behaviour

1. Step 1 displays image-choice cards; it has no progress bar.
2. Selecting an answer on steps 1–3 automatically advances to the next relevant step.
3. Step 2 and Step 3 include a Back control.
4. Step 2 is conditionally shown based on the Step 1 pathway.
5. Step 3 is conditionally shown based on the Step 1 pathway.
6. Step 4 is a lead-capture gate: first name, last name, email, and optional phone. Personal may additionally collect optional suburb if approved.
7. Required first name, last name, and email fields must show an inline error state when a user attempts to submit without completing them.
8. On submit, create the entry, send the relevant plain-text user and admin notifications, then redirect to the selected outcome URL with approved query parameters.
9. The outcome page displays the selected pathway and all three answers. Its service-tier modules remain fixed within the relevant audience template; only the headline, intro, answer summary, breadcrumb, notification copy, and route change.

---

## 3. Business Service Finder — Field Map

### Step 1 — Business Stage

| Field label | Field key | Option value | Outcome key |
|---|---|---|---|
| Which best describes your business right now? | `business_stage` | Start-up / New Business | `startup` |
|  |  | Established Business | `established` |
|  |  | Exit / Succession Planning | `exit` |

### Step 2 — Conditional Priority / Challenge / Exit Type

| Condition: `business_stage` | Question | Field key | Options |
|---|---|---|---|
| `startup` | What is your biggest priority right now? | `startup_priority` | Getting Set Up Correctly; Managing Cash Flow; Minimising Tax |
| `established` | What is your biggest challenge right now? | `established_challenge` | Improving Profitability; Reducing Tax; Planning for Growth |
| `exit` | What type of exit are you planning? | `exit_type` | Selling to a Third Party; Family / Management Succession; Winding Down |

### Step 3 — Conditional Qualifier

| Condition: `business_stage` | Question | Field key | Options |
|---|---|---|---|
| `startup` | How long have you been trading? | `startup_trading_age` | Pre-Revenue / Just Starting; Under 12 Months; 1–3 Years |
| `established` | How many people are in your team? | `established_team_size` | Just Me / Sole Trader; 2–5 People; 6–20 People; 20+ People |
| `exit` | What is your intended timeline? | `exit_timeline` | Within 12 Months; 1–3 Years; 3–5 Years |

### Step 4 — Lead Capture

| Field | Key | Required |
|---|---|---:|
| First Name | `first_name` | Yes |
| Last Name | `last_name` | Yes |
| Email Address | `email` | Yes |
| Phone | `phone` | No |
| Privacy acknowledgement | `privacy_acknowledgement` | Yes |

### Business outcome routes

| Pathway | Route | Dynamic title |
|---|---|---|
| Start-up | `/your-plan/startup/` | Here’s Your Start-up Action Plan, `{first_name}`. |
| Established | `/your-plan/established/` | Here’s Your Growth & Profitability Plan, `{first_name}`. |
| Exit | `/your-plan/exit/` | Here’s Your Exit Preparation Plan, `{first_name}`. |

**Combination count:** `3×3 + 3×4 + 3×3 = 30`.

---

## 4. Personal Service Finder — Field Map

### Step 1 — Life Stage

| Field label | Field key | Option value | Outcome key |
|---|---|---|---|
| Which best describes your life stage right now? | `personal_stage` | Wealth Accumulator | `wealth` |
|  |  | Pre-Retiree | `pre_retirement` |
|  |  | Retiree | `retirement` |
|  |  | Sudden Change | `life_change` |

### Step 2 — Conditional Goal / Concern / Priority / Need

| Condition: `personal_stage` | Question | Field key | Options |
|---|---|---|---|
| `wealth` | What is your biggest financial goal right now? | `wealth_goal` | Growing My Investments; Maximising My Super; Reducing My Tax |
| `pre_retirement` | What concerns you most about retirement? | `pre_retirement_concern` | Running Out of Money; Tax in the Transition; Protecting My Estate |
| `retirement` | What is most important to you right now? | `retirement_priority` | Sustainable Income; Aged Care Planning; Estate and Legacy |
| `life_change` | What would help you most right now? | `life_change_need` | Understanding Where I Stand; Protecting What I Have; Planning What Comes Next |

### Step 3 — Conditional Qualifier

| Condition: `personal_stage` | Question | Field key | Options |
|---|---|---|---|
| `wealth` | What is your approximate household income? | `wealth_household_income` | Under $100k; $100k–$200k; $200k–$500k; $500k+ |
| `pre_retirement` | When do you plan to retire? | `pre_retirement_timeline` | Within 2 Years; 2–5 Years; 5–10 Years |
| `retirement` | What is your primary income source in retirement? | `retirement_income_source` | Account-Based Pension / Super; Age Pension; Investment Income; Combination of the Above |
| `life_change` | What best describes your situation? | `life_change_situation` | Separation or Divorce; Loss of a Partner or Family Member; Redundancy or Career Change; Inheritance or Windfall |

### Step 4 — Lead Capture

| Field | Key | Required |
|---|---|---:|
| First Name | `first_name` | Yes |
| Last Name | `last_name` | Yes |
| Email Address | `email` | Yes |
| Phone | `phone` | No |
| Suburb | `suburb` | No — include only if Kidmans approves its use |
| Privacy acknowledgement | `privacy_acknowledgement` | Yes |

### Personal outcome routes

| Pathway | Route | Dynamic title |
|---|---|---|
| Wealth Accumulator | `/your-plan/accumulator/` | Here’s Your Wealth Building Plan, `{first_name}`. |
| Pre-Retiree | `/your-plan/pre-retiree/` | Here’s Your Retirement Transition Plan, `{first_name}`. |
| Retiree | `/your-plan/retiree/` | Here’s Your Retirement Income Plan, `{first_name}`. |
| Sudden Change | `/your-plan/life-change/` | Here’s Your Financial Reset Plan, `{first_name}`. |

**Combination count:** `3×4 + 3×3 + 3×4 + 3×4 = 45`.

### Personal compliance requirements

- Use empathetic and neutral language for the Sudden Change path.
- Avoid imagery that depicts a specific sensitive event.
- Place the General Advice Warning directly below the Personal form and before the next content section.
- Confirm the final AFSL/CAR disclosure wording with Kidmans / compliance before launch.

---

## 5. Outcome-Page Data Contract

Every redirected outcome URL should receive, or retrieve from the form entry, the following values:

```text
first_name
email
journey_type                 # business | personal
pathway_key                  # e.g. established | pre_retirement
step1_answer
step2_answer
step3_answer
outcome_slug
entry_id                     # optional but recommended
```

Recommended query-string pattern:

```text
/your-plan/established/?first_name={First Name:1}&step1={Business Stage:1}&step2={Established Challenge:2}&step3={Established Team Size:3}&entry={entry_id}
```

The outcome-page hero, breadcrumb, answer-summary band, user-notification content, and developer preview should be populated from these values.

---

## 6. Fixed Service-Tier Modules

To keep the build maintainable, service tiers are fixed by audience rather than re-authored for all 75 combinations. Pathway answers personalise the hero, summary, and communication; they do not create separate card structures.

### Business fixed tier set

| Tier | Services |
|---|---|
| Start Here | Business Advisory & Mentoring; Bookkeeping & Management Reporting |
| Recommended | Taxation & Business Services; Finance & Lending; Audit, Compliance & Assurance |
| Also Consider | SMSF; Wealth Management |

### Personal fixed tier set

| Tier | Services |
|---|---|
| Start Here | Wealth Management; SMSF & Superannuation Planning |
| Recommended | Tax Planning & Structuring; Finance & Lending; Estate & Legacy Planning |
| Also Consider | Investment Strategy Review; Personal Cash-Flow & Asset-Protection Review |

> Any service-name or regulatory wording must be confirmed against Kidmans’ approved service catalogue before launch.

---

## 7. Gravity Forms Notifications — Plain Text Only

The client has specified that no additional email styling can be applied. Configure **plain-text** Gravity Forms notifications — no HTML layout, no logo, no CSS, no design workarounds.

### User confirmations — seven conditional notifications

Create one conditional notification for each pathway. The conditions are based on Step 1.

| # | Notification name | Condition | Subject |
|---:|---|---|---|
| 1 | Business — Start-up plan | `business_stage = Start-up / New Business` | Your Kidmans Start-up Action Plan |
| 2 | Business — Established plan | `business_stage = Established Business` | Your Kidmans Growth & Profitability Plan |
| 3 | Business — Exit plan | `business_stage = Exit / Succession Planning` | Your Kidmans Exit Preparation Plan |
| 4 | Personal — Wealth plan | `personal_stage = Wealth Accumulator` | Your Kidmans Wealth Building Plan |
| 5 | Personal — Pre-Retirement plan | `personal_stage = Pre-Retiree` | Your Kidmans Retirement Transition Plan |
| 6 | Personal — Retirement plan | `personal_stage = Retiree` | Your Kidmans Retirement Income Plan |
| 7 | Personal — Financial reset plan | `personal_stage = Sudden Change` | Your Kidmans Financial Reset Plan |

Every user notification must include the exact three chosen answers, the correct outcome-page link, the static relevant service tiers, the discovery-call CTA URL, Kidmans contact details, and the approved personal-advice disclosure where relevant.

### Admin notifications — two plain-text notifications

| Notification name | Trigger | Minimum required content |
|---|---|---|
| New Business Service Finder lead | Every Business submission | Full contact details; all three answers; selected outcome route; entry ID; link to Gravity Forms entry |
| New Personal Service Finder lead | Every Personal submission | Full contact details; all three answers; selected outcome route; entry ID; link to Gravity Forms entry; personal/compliance flag where relevant |

---

## 8. Definition of Done

1. Both forms are functional in the wireframe and in Gravity Forms.
2. All 75 valid answer combinations can be selected and previewed.
3. Every combination renders the correct audience, path title, all three answers, summary sentence, and route.
4. The outcome-page module is reusable; static tier cards are not duplicated 75 times.
5. Seven plain-text user notification configurations and two plain-text admin notifications are documented and ready to configure.
6. Personal disclosure and Sudden Change content have been approved by Kidmans/compliance.

---

*Prepared for the Kidmans developer handoff.*
