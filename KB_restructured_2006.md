# BrightChamps Analytics Knowledge Base
*Restructured for LLM navigation — organized by user intent, not table structure.*

---

# 🗺️ ROUTING INDEX — Read This First

Match the user's question to the right section. Go directly to that section.

| If the user asks about... | Go to |
|---|---|
| what is BrightChamps / how does the business work / what does the company do | Section BC — BUSINESS CONTEXT |
| what is a Hunter / SM / Sales Rep / Scout / RM / Teacher / who owns what | Section BC — BUSINESS CONTEXT (Actor Directory) |
| what is Trial Completed / Trial Booked / Trial Confirmed / Trial Cancelled / Churned Lead / lead stage values | Section BC — BUSINESS CONTEXT (Lead Stages) |
| what is URI / renewal / instalment conceptually / what is T-6 | Section BC — BUSINESS CONTEXT (URI Journey) |
| what is fresh / crosssale / URI conceptually (not SQL) | Section BC — BUSINESS CONTEXT (Payment Buckets) |
| what is DC2C / demo-to-conversion / acquisition funnel conceptually | Section BC — BUSINESS CONTEXT (Acquisition Journey) |
| conversions / enrolments / how many enrolled yesterday / how many paid | Section 1 — CONVERSION METRICS |
| classes sold / classes booked / how many classes were sold / fresh classes / crosssale classes | Section 1 — CONVERSION METRICS |
| fresh collection / crosssale collection / revenue collected / INR collected / enrollment revenue | Section 2 — COLLECTION METRICS |
| overall collection / total revenue / all collections including addons kit demo | Section 2 — COLLECTION METRICS (overall_collection, broader than fresh_crosssale_collection) |
| net collection / after refunds / refund adjusted / net revenue | Section 2 — COLLECTION METRICS (net_collection) |
| ATS / average transaction size / average ticket size (payment-based, fixed per transaction_date) | Section 2 — COLLECTION METRICS (fresh_ats or fresh_crosssale_ats) |
| ATS / average transaction size / funnel ATS (in context of Conv % or demo cohort analysis) | Section 3 — FUNNEL METRICS (funnel_ats from booking_etl) |
| URI conversion / renewal count / instalment count / paid renewals / post-28day paid txns | Section 1 — CONVERSION METRICS (URI_conversion) |
| URI classes / renewal classes / instalment classes / post-enrollment classes | Section 1 — CONVERSION METRICS (URI_classes) |
| URI collection / renewal revenue / instalment revenue / post-enrollment revenue | Section 2 — COLLECTION METRICS (URI_collection) |
| URI ATS / renewal ATS / instalment ATS / post-enrollment ticket size — clarify context first (transaction-date vs cohort) | Section 2 (URI_ats) or Section 11 (uri_cohort_ats) — NEVER default to Section 2 without clarifying |
| URI RPC / renewal rate per class / instalment rate per class — clarify context first (transaction-date vs cohort) | Section 2 (URI_rpc) or Section 11 (uri_cohort_rpc) — NEVER default to Section 2 without clarifying |
| RPC / rate per class / revenue per class / price per class | Section 2 — COLLECTION METRICS |
| Conv % / DC2C / L2DJ / L2DC / DJ2DC / L2C / funnel rates / demo joined / demo completed / deals / deal count / deals done | Section 3 — FUNNEL METRICS |
| campaign performance / campaign report / campaign analysis / full funnel performance | Section 10 — MANDATORY REPORTING PAIRS |
| quality / LQS / DQS / SQS / lead quality / demo quality / sales pitch quality | Section 4 — QUALITY METRICS |
| why did Conv % drop / RCA / root cause / what drove the change | Section 5 — RCA FRAMEWORK |
| teacher wise / by teacher | Section 3 — FUNNEL METRICS + GROUP BY teacher_id |
| teacher_type / full-time teacher / part-time teacher / fixed teacher | Section 5 — RCA FRAMEWORK |
| hunter wise / SM wise / rep wise / sales rep / by lead owner / by sales person | Section 3 — FUNNEL METRICS + GROUP BY lead_owner_email |
| post demo hunter / by post demo owner / who closed the deal | Section 3 — FUNNEL METRICS + GROUP BY post_demo_lead_owner |
| scout wise / by scout | Section 3 — FUNNEL METRICS + GROUP BY scout_owner_email |
| team manager / by manager / manager wise | Section 3 — FUNNEL METRICS + GROUP BY team_manager (pre-demo) or post_demo_team_manager (post-demo) |
| business leader wise / by BL / business leader breakdown | Section 3 — FUNNEL METRICS + GROUP BY business_leader (pre-demo) or post_demo_business_leader (post-demo) |
| day on day / week on week / trend / last 10 days / over time | Section 3 or 1 + GROUP BY date |
| how many students enrolled (unique students, not conversions) | Section 6 — ENROLLED STUDENTS |
| OTO / OTM / one to one / one to many / demo mode / class type | Section 7C — OTO vs OTM (clarify: demo perspective or enrollment perspective first) |
| NRI / non-NRI / Indian parent / ethnicity / Indian leads / NRI conversion | Section 7D — NRI vs Non-NRI (ethnicity_flag in booking_etl) |
| grade / student grade / little champs / junior champs / senior champs / grade band / age group | Section 7E — Grade Band (grade in booking_etl) |
| new parent / repeat parent / new student / repeat student / new vs repeat / parent type / student type | Section 7F — Parent Type & Student Type (booking_etl) |
| lead source / UTM / channel / booking source / Google / Facebook / referral / attribution / where did leads come from | Section 7G — Lead Source / UTM Attribution (booking_etl) |
| geo filter / region filter / vertical filter / country | Section 7 — DIMENSIONS |
| what table to use / table schema / join keys | Section 8 — TABLE REFERENCE |
| a metric not found anywhere in this document | Section 9 — OUT OF KB |
| uri pool size / pool due / pool size / how many students entered the uri pool | Section 11 — URI FUNNEL METRICS |
| uri overall pool / total pool including direct payments | Section 11 — URI FUNNEL METRICS |
| uri team pool / rm team pool / pool excluding direct payments | Section 11 — URI FUNNEL METRICS |
| uri cohort conversion / what % of uri pool renewed / uri funnel conversion rate | Section 11 — URI FUNNEL METRICS |
| uri 7 day conversion / renewed within 7 days / uri % 7 day | Section 11 — URI FUNNEL METRICS |
| uri 30 day conversion / renewed within 30 days / uri % 30 day | Section 11 — URI FUNNEL METRICS |
| days to renew / renewal speed / how fast are renewals / payment efficiency / time to renewal | Section 11 — URI FUNNEL METRICS |
| uri cohort ATS / uri ATS cohort / uri RPC cohort / renewal ATS cohort / renewal RPC cohort | Section 11 — URI FUNNEL METRICS |
| uri funnel by RM / team lead wise uri / renewal performance by RM | Section 11 — URI FUNNEL METRICS |
| marketing spend / ad spend / total spend / FB spend / Google spend | Section 12 — MARKETING SPEND & EFFICIENCY |
| CPL / cost per lead / cost per demo scheduled | Section 12 — MARKETING SPEND & EFFICIENCY |
| CPD / cost per demo completed / cost per completed demo / cost per deal | Section 12 — MARKETING SPEND & EFFICIENCY |
| ROAS / return on ad spend / marketing ROI | Section 12 — MARKETING SPEND & EFFICIENCY |
| ROAS-6M / 6 month ROAS / extrapolated ROAS | Section 12 — MARKETING SPEND & EFFICIENCY |
| CAC / cost per acquisition / cost per new parent | Section 12 — MARKETING SPEND & EFFICIENCY |
| LTV / LTV per parent / first year LTV / second year LTV / 2-year LTV / LTV/CAC | Section 12 — MARKETING SPEND & EFFICIENCY |
| spend by campaign / campaign_origin FB or Google / campaign_source channel | Section 12 — MARKETING SPEND & EFFICIENCY |
| campaign country / campaign geo / campaign targeting country / campaign_country | Section 12 — MARKETING SPEND & EFFICIENCY (campaign_country) |
| campaign region group / campaign_region_group | Section 12 — MARKETING SPEND & EFFICIENCY (campaign_region_group) |
| campaign investor view / campaign spend by Vietnam / campaign spend by USA_Canada / campaign_region_investor | Section 12 — MARKETING SPEND & EFFICIENCY (campaign_region_investor) |
| classes scheduled / class volume / how many classes were put on calendar | Section 13 (classes_scheduled) |
| breakup of classes / status-wise classes / class status distribution / % of each status | Section 13 (classes_breakup) |
| cancelled by parent / parent cancellation / parent cancellation % | Section 13 (cancellations_by_parent, cancellation_pct_by_parent) |
| cancelled by teacher / teacher cancellation / teacher cancellation % | Section 13 (cancellations_by_teacher, cancellation_pct_by_teacher) |
| time between cancellation and class / cancellation lead time / how much notice before cancelling | Section 13 (avg_time_to_cancellation_by_parent / avg_time_to_cancellation_by_teacher) |
| incomplete classes / classes that didn't finish | Section 13 (incomplete_classes) |
| student no shows / student joined but teacher didn't / teacher no-show | Section 13 (student_joined_teacher_no_show) |
| teacher no shows / teacher joined but student didn't / student no-show | Section 13 (teacher_joined_student_no_show) |
| on time class start / punctuality / both joined on time | Section 13 (on_time_class_start) |
| on time teacher join / teacher punctuality / late teacher join / teacher late joining | Section 13 (on_time_teacher_join, late_teacher_join) |
| early drop off / dropped out early / left before class finished | Section 13 (early_dropoff) |
| perfect class / perfect class % | Section 13 (perfect_class_pct) |
| PQS / teacher PQS score / PQS buckets / PQS distribution | Section 13 (avg_pqs_score, pqs_bucket_pct) |
| PTM-QS / PTM quality score / PTM-QS buckets | Section 13 (avg_ptm_qs, ptm_qs_bucket_pct) |
| parent joined PTM / % parent attendance PTM / parent PTM join rate | Section 13 (parent_ptm_join_pct) |
| student feedback rating / star rating distribution / average rating | Section 13 (avg_student_feedback_rating, feedback_rating_bucket_pct) |
| time to submit feedback / feedback submission lag | Section 13 (feedback_submit_lag) |
| assignment completion / % assignment done | Section 13 (assignment_completion_pct) |
| assignment score / average assignment score % | Section 13 (assignment_avg_score_pct) |
| quiz completion / % quiz done | Section 13 (quiz_completion_pct) |
| quiz score / average quiz score % | Section 13 (quiz_avg_score_pct) |
| OTO vs OTM vs Master Class for paid classes | Section 13 — Business Context (Class Mode Classification) |

⛔ **URI ATS / URI RPC disambiguation:** When the user says "URI ATS" or "URI RPC" — with or without a time period or geo filter — NEVER default to Section 2. Always present both options (Section 2 transaction-date view vs Section 11 cohort view) and ask the user to clarify which analytical lens they need before writing any SQL. A time period like "Q1" or a geo filter like "USA Canada" does NOT resolve the ambiguity — both lenses support time and geo filters.

**Post-disambiguation routing (once the user has answered):**
- User selects **transaction date** → go directly to Section 2 URI RPC. Do NOT ask any follow-up questions. Apply Rule 4 (two cuts: Overall + Excl. SEA) automatically and run immediately.
- User selects **cohort / URI pool date** → go directly to Section 11 URI FUNNEL METRICS. Do NOT ask any follow-up questions. Apply Rule 4 automatically and run immediately.

---

# SECTION 0: UNIVERSAL RULES — Apply to EVERY Query

These rules have NO exceptions. Apply them before writing any SQL.

---

## Rule 1 — IST Timezone (MANDATORY)
All ETL timestamps are stored in UTC. All reporting is in IST (UTC+5:30).

**Always use IST conversion for date filtering:**
```sql
DATE(column_name + INTERVAL '5:30 hours')
```

**Common date patterns (copy these exactly — never hardcode a date string for a relative term):**

| User says | SQL pattern |
|---|---|
| "yesterday" | `DATE(col + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1` |
| "today" | `DATE(col + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours')` |
| "last 7 days" | `DATE(col + INTERVAL '5:30 hours') >= DATE(current_timestamp + INTERVAL '5:30 hours') - 7 AND DATE(col + INTERVAL '5:30 hours') <= DATE(current_timestamp + INTERVAL '5:30 hours') - 1` |
| "last N days" | `DATE(col + INTERVAL '5:30 hours') >= DATE(current_timestamp + INTERVAL '5:30 hours') - N AND DATE(col + INTERVAL '5:30 hours') <= DATE(current_timestamp + INTERVAL '5:30 hours') - 1` |
| "last month" (relative) | `DATE_TRUNC('month', col + INTERVAL '5:30 hours')::date = DATE_TRUNC('month', CURRENT_DATE - INTERVAL '1 month')::date` |
| "last 2 months" vs "previous month" | `DATE_TRUNC('month', col + INTERVAL '5:30 hours')::date >= DATE_TRUNC('month', CURRENT_DATE - INTERVAL '2 months')::date AND DATE_TRUNC('month', col + INTERVAL '5:30 hours')::date < DATE_TRUNC('month', CURRENT_DATE)::date` |
| "May-26" / "Mon-YY" (full month) | `DATE_TRUNC('month', col + INTERVAL '5:30 hours')::date = '2026-05-01'` — derive YYYY-MM-01 from Mon-YY |
| "day on day for last 10 days" | Use `GROUP BY DATE(col + INTERVAL '5:30 hours')` with the last-N-days filter above |

⛔ NEVER filter by raw UTC date. Never hardcode a specific date string for a relative term like "yesterday" or "last month".

---

## Rule 2 — Active Status Filter (MANDATORY)
```sql
booking_etl  → WHERE booking_status = 'active'
```
Forgetting this inflates ALL metrics with cancelled/invalid records. No exceptions.

---

## Rule 3 — Unique Lead Grain
```sql
student_id || vertical_name   -- for COUNT DISTINCT (funnel counts)
```
Use `SUM(...)` for collection/amount metrics — no deduplication needed there.

---

## Rule 4 — Two Cuts for Global Queries
Unless the user specifies a region, always present results twice:
1. **Overall** — no region filter
2. **Excl. SEA** — `AND booking_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')`

---

## Rule 5 — Banned Columns
| ❌ Never use | ✅ Use instead | Why |
|---|---|---|
| `demo_class_type` | `demo_class_type_attr` | Canonical OTO/OTM column for DEMO mode only |
| `paid_class_category = 'OTO'` or `= 'OTM'` | `paid_class_category ILIKE '%OTM%'` | Column stores long strings — exact match returns zero rows |
| `booking_source` | `attr_booking_source` | Pre-attribution; reflects only last landing page touchpoint |
| `utm_source` | `attr_utm_source` | Pre-attribution; use attributed version |
| `utm_medium` | `attr_utm_medium` | Pre-attribution; use attributed version |
| `utm_content` | `attr_utm_content` | Pre-attribution; use attributed version |
| `utm_campaign` | `attr_utm_campaign` | Pre-attribution; use attributed version |
| `indian_names` | — | Does NOT exist in warehouse |
| `business_region_name` (in booking_etl) | `booking_region_name` | `business_region_name` does not exist in booking_etl; it is valid only in brightchamps.student_etl (used for payment_etl geo joins) |
| `booking_region_group` in WHERE clause | — | Derived CASE column — SELECT layer only; filter by `booking_region_name` or `business_region_name` instead |
| `booking_region_investor` in WHERE clause | — | Derived CASE column — SELECT layer only; filter by `booking_region_name` or `business_region_name` instead |
| `attribution_channel` in WHERE clause | — | Derived CASE column built on `attr_booking_source` — SELECT layer only; filter by `attr_booking_source` instead |

---

## Rule 6 — Geo vs Vertical Filter Source (CRITICAL for payment_etl queries)

When filtering `payment_etl` based metrics (Sections 1 & 2) by both geo AND vertical:

| Filter type | Source table | Column | How to apply |
|---|---|---|---|
| Geo / Region / Country | `brightchamps.student_etl` (requires JOIN) | `b.business_region_name` | JOIN on `payment_etl.student_id = student_etl.student_id` |
| Vertical / Course / Product | `payment_etl` directly (NO JOIN needed) | `payment_etl.vertical_name` | Filter directly on the payment table alias |

**Why this matters:** For conversion and collection metrics you always want the purchased vertical, not the demo vertical. `payment_etl.vertical_name` is the purchased product. Geo is resolved via `brightchamps.student_etl.business_region_name`, joined on `student_id`.

**Template for geo + vertical filter on payment_etl:**
```sql
FROM stage_brightchamps.payment_etl pd
LEFT JOIN brightchamps.student_etl b ON pd.student_id = b.student_id
WHERE pd.flag != 'No Payment'
  AND b.business_region_name = 'USA_Canada'   -- geo from student_etl
  AND pd.vertical_name = 'Codechamps'        -- vertical from payment_etl ← NOT b.vertical_name
```

⛔ Never write `b.vertical_name` in a payment_etl query. That is the demo product, not the purchase product.

---

## Rule 7 — Marketing Date Exception (Section 12 only)

Section 0 Rule 1 applies to `booking_etl`, `payment_etl`, and `parent_etl`. **Marketing spend tables are different.**

| Table / column | Storage | Filter pattern |
|---|---|---|
| `stage_brightchamps.marketing_campaign_etl.campaign_date_ist` | **Already IST** (day-level) | `DATE(campaign_date_ist)` — **no** `+ INTERVAL '5:30 hours'` |
| tryouts spend sources (`date_of_day`, Google `date`) | **Already IST** | `DATE(date_of_day)` — **no** `+ INTERVAL '5:30 hours'` |
| `stage_brightchamps.booking_etl.booking_creation_date` | UTC | `(booking_creation_date + INTERVAL '330 minutes')::date` |

⛔ Applying `+5:30` on `campaign_date_ist` will shift dates incorrectly. `created_at` / `updated_at` on marketing tables are audit columns — not for business date filtering.

---

## Rule 8 — Marketing Spend Stitching (Section 12 only)

Spend (`marketing_campaign_etl`) and funnel (`booking_etl`) **cannot be row-joined directly**. For all efficiency metrics (CPL, ROAS, CAC, LTV):

1. Aggregate **spend** and **numerator/denominator** separately at the requested dimension grain
2. Divide at the end — **never** average row-level ratios

### Stitch conditions (when linking spend to bookings)

| # | Condition |
|---|---|
| 1 | `(booking_creation_date + INTERVAL '330 minutes')::date = campaign_date_ist::date` |
| 2 | `UPPER(attr_utm_campaign) = UPPER(campaign_name)` |
| 3 | `booking_status = 'active'` |

Additional booking filters — **Paid CPL only** (remove both for Overall CPL):
- `attr_booking_source_grouped = 'paid'`
- `attr_utm_campaign IS NOT NULL`

⛔ Do **not** require `campaign_country = booking_country` for the base stitch.

### Geo columns for marketing queries

| Use | Do NOT use |
|---|---|
| `booking_country` | `parent_country_name` |
| `booking_region_name` | `parent_region_name` |

### Dimensions on `marketing_campaign_etl` only

Slice spend on any combination of: `campaign_date_ist`, `campaign_source`, `campaign_name`, `campaign_origin`, `campaign_region`, `campaign_country`, `demo_flag`.

### Dimensions NOT on `marketing_campaign_etl` (e.g. vertical, course, rep)

1. From `booking_etl`: get `DISTINCT UPPER(attr_utm_campaign)` for the remaining filters where `booking_status = 'active'`
2. Filter `marketing_campaign_etl` with `UPPER(campaign_name) IN (...)` plus date (and any marketing-native dims)
3. `SUM(spends_inr)` for spend; count bookings separately with the full dimension on the funnel side

### User language → column mapping

| User says | Column |
|---|---|
| FB spend / Google spend / platform | `campaign_origin` (`'FB'` or `'Google'` only) |
| Channel / booking source | `campaign_source` (finer tagging) |
| Campaign type | `demo_flag` — filter only when user specifies |

### Always-on spend exclusions

```sql
AND demo_flag != 'Recruitment Campaign'
AND spends_inr > 0   -- exclude zero-spend rows
```

Vietnam/Thailand exclusion is **dashboard-only** — not mandatory in KB queries unless user requests.

---

# SECTION BC: BUSINESS CONTEXT

*This section is the company knowledge layer. Consult it when a question references business concepts (actors, journey stages, product terms) that must be resolved before writing SQL. All metric SQL definitions remain in Sections 1–6. All dimension SQL remains in Section 7.*

---

## BC-1 — Company Overview

**What BrightChamps does:** Online EdTech platform (founded 2019–20, COVID era) offering live classes to school-age children in extra-curricular, future-skills subjects — Coding, Robotics, Financial Literacy, Mathematics, Chess, and Languages. These are NOT school curriculum subjects.

**Geographies:** USA & Canada · EMEA · Vietnam · Thailand · UK · India

**Channel:** 100% website-based; no mobile app. Paid acquisition via Facebook and Google ads.

**Core funnel in one line:** Ad Click → Lead Submission → Free Demo Class → Paid Enrollment → Academy Classes → Renewal

---

## BC-2 — Actor Directory

Every business question involves at least one of these actors. Resolve the actor before writing SQL.

| Actor | Role | Active Stage |
|---|---|---|
| **Parent** | Primary decision-maker; submits lead, pays, schedules classes | All stages |
| **Student** | End learner; attends demo and paid classes | All stages |
| **Scout** | Outreach team; runs pre-demo confirmation campaigns (calls, SMS, WhatsApp, AI calling) to maximise demo attendance | Pre-demo only |
| **Teacher** | Delivers both demo and paid classes; assigned by vertical (e.g. Coding teacher for a Coding lead); may change during paid journey due to attrition or parent request | Demo + Academy |
| **Hunter** (also: SM, Sales Rep) | Primary lead owner post-demo; attends demo session, delivers the 15-min sales pitch, creates payment link, chases leads to Closed Won via Zoho follow-up tasks | Demo → Conversion |
| **RM (Relationship Manager)** | Academy phase owner; manages daily class operations, teacher changes, instalment follow-ups, and the URI/renewal pipeline from T-6 trigger onwards | Academy + URI |

**SQL field mapping — all in `stage_brightchamps.booking_etl`:**

| Field | Maps to | When to use |
|---|---|---|
| `lead_owner_email` | Current Hunter (SM / Sales Rep) assigned to the lead | Default for "by sales rep / by SM / by hunter" questions; reflects the live assignment |
| `scout_owner_email` | Current Scout assigned to the lead | Pre-demo phase analysis; confirmation campaigns, L2DJ attribution |
| `team_manager` | Manager of the current Hunter (`lead_owner_email`) | "By manager" questions scoped to pre-demo or general lead ownership |
| `business_leader` | Business leader above the current Hunter | "By BL" questions scoped to pre-demo or general lead ownership |
| `post_demo_lead_owner` | Hunter (SM / Sales Rep) assigned after Trial Completed; responsible for driving conversion | Use for post-demo conversion analysis — this is the person accountable for Closed Won |
| `post_demo_team_manager` | Manager of `post_demo_lead_owner` | "By manager" questions scoped to post-demo conversion accountability |
| `post_demo_business_leader` | Business leader of `post_demo_lead_owner` | "By BL" questions scoped to post-demo conversion accountability |
| `teacher_id` | Teacher who conducted the demo class | Teacher performance, DQS analysis |

⚠️ **Critical disambiguation:** `lead_owner_email` ≠ `post_demo_lead_owner`. A lead can be reassigned after the demo. If the question is about who drove the conversion, use `post_demo_lead_owner`. If the question is about current lead ownership or pre-demo activity, use `lead_owner_email`. When ambiguous, ask the user which they mean.

---

## BC-3 — Acquisition Journey & Lead Stages

**Standard form flow:**
- Step 1: Parent enters phone number, student name, student grade
- Step 2: Parent picks demo date/time → `booking_date` = submission date; `demo_date` = chosen slot

**Lead types:**
- **Valid Lead** — both steps completed (phone + demo date). Used in all funnel analysis.
- **Partial Lead** — only Step 1 completed; no demo date. Lower conversion; tracked separately.

**Pre-demo phase (booking_date → demo_date):** Scout team + automated campaigns (email/SMS/WhatsApp/AI calling) aim to confirm demo attendance. The 1-hour-before campaign is the highest-leverage touchpoint. When a parent confirms: Lead-to-Demo-Join rate = ~60–65%. Without confirmation: significantly lower.

**Demo class structure (60 min, on Zoom):**

| Phase | Duration | Owner |
|---|---|---|
| Rapport + Discovery | First 10 min | Teacher |
| Teaching (tailored to student interest/gap) | 30–45 min | Teacher |
| Sales pitch (course plans, pricing, objection handling) | Final 15 min | Hunter |

**Lead stage pipeline — column `lead_stage` in `stage_brightchamps.booking_etl`:**

| `lead_stage` value | Meaning |
|---|---|
| `Trial Booked` | Demo date exists; demo has not yet occurred |
| `Trial Confirmed` | Parent has confirmed attendance for the upcoming demo |
| `Trial Cancelled/ Missed/ Not Completed` | Demo did not complete — covers cancellations, no-shows, and incomplete sessions |
| `Trial Completed` | Demo ran to completion — entry point for all sales stages below |
| `Contacted by Sales` | Hunter has made first outreach contact post-demo |
| `Parent Appointment Scheduled` | Hunter has a confirmed follow-up call booked with the parent |
| `Interested` | Parent has expressed positive intent to enroll |
| `Negotiation/ Review` | Active pricing/package discussion or parent reviewing the proposal |
| `On Hold` | Interested but paused due to timing or budget constraint |
| `Closed Won` | Payment received; student is enrolled |
| `Closed Lost` | Parent declined; lead is permanently closed |
| `Churned Lead` | Lead re-entered from a previously closed/lost state or disengaged after showing interest |

⚠️ **Gotchas:**
- `Trial Cancelled/ Missed/ Not Completed` is a **single value** — use the exact string including slashes. Do NOT filter for "Not Completed" alone.
- `Negotiation/ Review` is also a **single value** — not two separate stages.
- `Trial Confirmed` sits between `Trial Booked` and the demo — it confirms pre-demo intent but does NOT mean the demo happened.
- For counting demos completed, filter `lead_stage = 'Trial Completed'` OR use `demo_completed = 1` (preferred for SQL, as `lead_stage` may update with lag).

**Cross-reference:** For DC2C, L2DJ, L2DC funnel rate SQL → Section 3. For LQS/DQS/SQS quality score SQL → Section 4.

---

## BC-4 — Payment Buckets: Fresh, Cross-sale, URI

These three buckets are **mutually exclusive** and cover every row in `payment_etl` where `flag != 'No Payment'`.

| Bucket | Business meaning | SQL guard in payment_etl |
|---|---|---|
| **Fresh** | Student's very first paid enrollment (any course) | `flag = 'Fresh payment'` OR (`flag IN ('Cross-sale-Fresh','Instalment','Renewal') AND within_28_days_student = 1`) |
| **Cross-sale** | Additional course purchased by an existing student, within 28 days of their first enrollment on a different course | `flag = 'Cross-sale-Fresh' AND within_28_days_student_course = 1 AND within_28_days_student = 0` |
| **URI** | Renewal or Instalment payment made after BOTH 28-day windows have closed — i.e., the student's ongoing subscription revenue | `flag IN ('Renewal','Instalment') AND within_28_days_student = 0 AND within_28_days_student_course = 0` |

**Business intuition:**
- Fresh = new student entering BrightChamps for the first time
- Cross-sale = same student buying a second product soon after joining
- URI = existing student renewing or paying an instalment on an ongoing course

**Cross-reference:** For exact SQL per metric → Section 1 (conversion counts) and Section 2 (collection amounts).

---

## BC-5 — Enrollment Options

When a parent converts, the Hunter configures:

| Decision | Options | Business note |
|---|---|---|
| **Class format** | OTO (one-to-one) or OTM (group) | OTM = lower per-class price; higher gross margin for BrightChamps |
| **Course selection** | Single course or multiple simultaneous courses | Each product = separate enrollment row in payment_etl |
| **Package size** | 30 / 45 / 60 / 90 / 120 classes | Curriculum-defined per vertical |
| **Cross-sale** | Parent who demoed Product X may purchase Product Y simultaneously | Demo vertical ≠ paid vertical in these cases |

**OTO vs OTM applies at two independent levels:**
- **Demo level:** determined by how many students join the Zoom session (≥2 = OTM). Column: `demo_class_type_attr` in booking_etl.
- **Paid level:** chosen by parent at enrollment. Column: `paid_class_category ILIKE '%OTM%'` in payment_etl.

**Cross-reference:** For OTO/OTM SQL → Section 7C.

---

## BC-6 — Academy Journey

After enrollment, the student enters the Academy phase, owned by the **RM**.

**Key facts:**
- Parent must schedule their full class calendar (e.g. 30 classes → choose preferred weekdays/times for all 30) before classes begin — mandatory step.
- Teacher assigned to paid classes may differ from the demo teacher.
- Classes run on Zoom; class completion requires both student and teacher present for ≥40 minutes.
- **Perfect class** criteria: both parties joined on time + quiz conducted during or after class.
- **Paid class quality score:** 0–10 per completed class; measures teacher engagement and content delivery.
- Teacher changes can occur due to teacher attrition or parent-initiated feedback request; RM coordinates.

**Quality scores active in academy:** Paid Class Quality Score (0–10). DQS and SQS are demo-stage only.

**Cross-reference:** For LQS/DQS/SQS SQL definitions → Section 4.

---

## BC-7 — URI / Renewal Journey

**Trigger:** When a student reaches T-6 (6 classes remaining in their purchased package), they enter the URI pool. Example: 30-class purchase → URI trigger at class 25.

**Process:** RM engages the parent — ideally during a live class — to gauge renewal interest. If the parent needs time, Zoho follow-up tasks are created at 15 or 30-day intervals.

**Timeline contrast:**

| Journey | Avg. days from trigger to payment |
|---|---|
| Acquisition (lead → first enrollment) | 3–4 days |
| URI (T-6 trigger → renewal payment) | 25–30 days |

**What a renewal payment looks like in payment_etl:** `flag IN ('Renewal','Instalment')` with both 28-day flags = 0. This is the URI bucket. One student with two renewals = two separate rows.

**Cross-reference:** For URI metric SQL (conversion, collection, ATS, RPC, classes) → Sections 1 and 2.

---

## BC-9 — Marketing Spend & Paid Acquisition

**What marketing spend represents:** INR spent on paid digital acquisition — Facebook (Meta) and Google ads.

**Spend source (KB default):** `stage_brightchamps.marketing_campaign_etl` → `SUM(spends_inr)` at campaign-day grain.

**Raw spend sources (drill-down below campaign level):**

| Platform | tryouts table | Cutoff |
|---|---|---|
| FB / Meta | `tryouts.performance_marketing_spends` | — |
| Google legacy | `tryouts.performance_marketing_google_spends` | `date_of_day < '2026-04-01'` |
| Google new | `tryouts.google_campaign_location_daily_metrics` + `tryouts.google_campaigns` | `date >= '2026-04-01'` |

**Funnel tables for marketing efficiency:**

| Table | Schema | Role |
|---|---|---|
| `booking_etl` | `stage_brightchamps` | **All** marketing funnel metrics — CPL denominator (`COUNT(DISTINCT student_id||vertical_name)`), ROAS, CAC, collection numerators |
| `parent_etl` | `brightchamps` | LTV numerator (`net_collection_amt_one_yr`) only |
| `marketing_campaign_etl` | `brightchamps` | Spend only — do **not** use `lead_count` column for CPL |

⛔ Do NOT use `lead_etl` for marketing metrics — use `booking_etl` with `COUNT(DISTINCT student_id||vertical_name)` for CPL denominator (student+vertical grain).

**Cross-reference:** All metric SQL → Section 12.

---

# SECTION 1: CONVERSION METRICS

**Primary table:** `stage_brightchamps.payment_etl`
**Date column:** `transaction_date`
**Mandatory filter:** `flag != 'No Payment'`
**Geo join (when region filter needed):** `LEFT JOIN brightchamps.student_etl b ON payment_etl.student_id = b.student_id`

⚠️ `conversion_flag` in `booking_etl` is a DIFFERENT thing — it's a funnel flag for DC2C rate calculation. For counting paid enrollments, ALWAYS use `payment_etl` with the flag values below.
ℹ️ For business meaning of Fresh / Cross-sale / URI buckets → Section BC-4.

**Metrics in this section:** `fresh_crosssale_conversion`, `fresh_conversion`, `crosssale_conversion`, `fresh_classes`, `fresh_crosssale_classes`, `URI_conversion`, `URI_classes`

---

### fresh_crosssale_conversion or fresh_crosssale enrolment or conversions or enrolment

**Definition:** Total paid enrollments (fresh + crosssale) in a time window

**SQL — no geo filter:**
```sql
SELECT
  SUM(CASE WHEN flag IN ('Fresh payment', 'Cross-sale-Fresh') THEN 1 ELSE 0 END) AS fresh_crosssale_conversion
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**SQL — with geo/vertical filter (requires JOIN):**
```sql
SELECT
  SUM(CASE WHEN a.flag IN ('Fresh payment', 'Cross-sale-Fresh') THEN 1 ELSE 0 END) AS fresh_crosssale_conversion
FROM stage_brightchamps.payment_etl AS a
LEFT JOIN brightchamps.student_etl AS b ON a.student_id = b.student_id
WHERE a.flag != 'No Payment'
  AND DATE(a.transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
  AND b.business_region_name = 'USA_Canada'   -- geo: from student_etl
  -- AND a.vertical_name = 'Codechamps'      -- vertical: from payment_etl (purchased product) ← NOT b.vertical_name
```

**Gotcha:** Do NOT use `booking_etl.conversion_flag` for this metric. That column only tells you funnel conversion status, not payment amounts or payment-level counts.

**Cross-validate (ECS):** Run fresh and crosssale counts separately (`flag = 'Fresh payment'` and `flag = 'Cross-sale-Fresh'`), verify they sum to the combined metric. Also verify Overall ≥ Excl. SEA count.

---

### fresh_conversion or fresh enrolment or fresh payment

**Definition:** New (first-time) enrollments only — excludes cross-sales

```sql
SELECT
  SUM(CASE WHEN flag = 'Fresh payment' THEN 1 ELSE 0 END) AS fresh_conversion
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** Counts ONLY `Fresh payment` rows — one per new student. `fresh_conversion` IS a reliable proxy for new student count. Do NOT use `fresh_crosssale_conversion` as a proxy for new students — a student who buys two courses on day 1 generates 1 `Fresh payment` + 1 `Cross-sale-Fresh`, appearing as 2 in `fresh_crosssale_conversion` but only 1 in `fresh_conversion`. Use `fresh_conversion` when the question is "how many new students enrolled"; use `fresh_crosssale_conversion` when the question is "how many total enrollment events occurred."

**Cross-validate (ECS):** `fresh_conversion + crosssale_conversion = fresh_crosssale_conversion` exactly. Verify this equality holds — any mismatch indicates a SQL error. Also verify `fresh_conversion` ≤ `fresh_crosssale_conversion` and Overall ≥ Excl. SEA.

---

### crosssale_conversion or crosssale enrolment or cross-sale

**Definition:** Cross-sale enrollments — existing students buying a new course (any time, no 28-day window restriction)

```sql
SELECT
  SUM(CASE WHEN flag = 'Cross-sale-Fresh' THEN 1 ELSE 0 END) AS crosssale_conversion
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** No 28-day guard. Counts ALL `Cross-sale-Fresh` rows regardless of when the student first enrolled. This means `fresh_conversion + crosssale_conversion = fresh_crosssale_conversion` exactly — the three metrics form a clean additive split: fresh_crosssale = fresh + crosssale with no overlap and no gap.

**Cross-validate (ECS):** `fresh_conversion + crosssale_conversion` must equal `fresh_crosssale_conversion` exactly. Any mismatch indicates a SQL error. Verify Overall ≥ Excl. SEA count.

---

### fresh_classes or classes sold or classes booked

**Definition:** Total classes sold in the first 28 days from the student's first enrolment — fresh payments only, using `within_28_days_student` guard for non-fresh flags.

```sql
SELECT
  SUM(CASE
    WHEN flag = 'Fresh payment'
      OR (flag IN ('Cross-sale-Fresh', 'Instalment', 'Renewal')
          AND within_28_days_student = 1)
    THEN classes_paid ELSE 0
  END) AS fresh_classes
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** Uses `within_28_days_student` ONLY — NOT `within_28_days_student_course`. Using the course-level guard here will overcount. This is different from `fresh_crosssale_classes` which uses both guards. Also: `classes_paid` is the number of classes in the **purchased package**, NOT classes actually attended or scheduled. RPC metrics based on this are "price per purchased class", not "price per attended class".

**Cross-validate (ECS):** Run `Fresh payment` classes and `(Cross-sale-Fresh/Instalment/Renewal AND within_28_days_student=1)` classes separately, verify they sum to `fresh_classes`. Sanity: `fresh_classes / fresh_conversion` = average package size per enrollment (should be a reasonable integer, e.g. 12–96 classes).

---

### fresh_crosssale_classes or crosssale classes or total classes sold or classes paid

**Definition:** Total classes paid from the first date of student enrolment till 28 days — includes both student-level and course-level 28-day guards.

```sql
SELECT
  SUM(CASE
    WHEN flag = 'Fresh payment'
      OR (flag IN ('Cross-sale-Fresh', 'Instalment', 'Renewal')
          AND (within_28_days_student = 1 OR within_28_days_student_course = 1))
    THEN classes_paid ELSE 0
  END) AS fresh_crosssale_classes
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** This uses BOTH `within_28_days_student` OR `within_28_days_student_course` — unlike `fresh_classes` which uses only `within_28_days_student`. `fresh_crosssale_classes` ≥ `fresh_classes` always. Like all `classes_*` metrics: `classes_paid` = **purchased package size**, not attended or scheduled classes.

**Cross-validate (ECS):** `fresh_crosssale_classes` ≥ `fresh_classes` always. The difference = classes from rows where `within_28_days_student=0 AND within_28_days_student_course=1` (course-level 28-day window only). Verify that difference is non-negative.

---

### URI_conversion or URI conversion or renewal count or instalment count or paid renewals or post-enrollment paid transactions

**Definition:** Count of paid Renewal/Instalment transactions where the student is OUTSIDE both the student-level and course-level 28-day windows. These are students who previously enrolled and are renewing or paying instalments after the initial 28-day period.

```sql
SELECT
  SUM(CASE
    WHEN flag IN ('Renewal', 'Instalment')
     AND within_28_days_student = 0
     AND within_28_days_student_course = 0
    THEN 1 ELSE 0
  END) AS URI_conversion
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** Both 28-day guards must be `= 0`. This is the third mutually exclusive bucket for `Renewal/Instalment` rows — rows where `within_28_days_student = 1` belong to `fresh_conversion` logic; rows where `within_28_days_student_course = 1 AND within_28_days_student = 0` belong to `crosssale_conversion` logic. URI captures the rest.

**Cross-validate (ECS):** Every `Renewal/Instalment` row has exactly one of three possible states for the two 28-day flags — verify the three bucket counts sum to the total:
```sql
-- Bucket 1: fresh (within_28_days_student = 1)
SELECT COUNT(*) FROM stage_brightchamps.payment_etl
WHERE flag IN ('Renewal','Instalment') AND flag != 'No Payment' AND within_28_days_student = 1
-- Bucket 2: crosssale (within_28_days_student = 0 AND within_28_days_student_course = 1)
SELECT COUNT(*) FROM stage_brightchamps.payment_etl
WHERE flag IN ('Renewal','Instalment') AND flag != 'No Payment' AND within_28_days_student = 0 AND within_28_days_student_course = 1
-- Bucket 3: URI (both = 0) → this should equal URI_conversion
SELECT COUNT(*) FROM stage_brightchamps.payment_etl
WHERE flag IN ('Renewal','Instalment') AND flag != 'No Payment' AND within_28_days_student = 0 AND within_28_days_student_course = 0
-- Total: Bucket 1 + Bucket 2 + Bucket 3 must equal this
SELECT COUNT(*) FROM stage_brightchamps.payment_etl
WHERE flag IN ('Renewal','Instalment') AND flag != 'No Payment'
```
Bucket 3 count = `URI_conversion`. Sum of all three buckets = total `Renewal/Instalment` rows. Any mismatch means a row was missed or double-counted.

---

### URI_classes or URI classes or renewal classes or instalment classes or post-enrollment classes

**Definition:** Classes purchased in Renewal/Instalment transactions outside both 28-day windows.

```sql
SELECT
  SUM(CASE
    WHEN flag IN ('Renewal', 'Instalment')
     AND within_28_days_student = 0
     AND within_28_days_student_course = 0
    THEN classes_paid ELSE 0
  END) AS URI_classes
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** `classes_paid` = classes in the **purchased renewal/instalment package**, not classes attended. One student can have multiple URI_classes rows in the same period (e.g., renewed twice). URI_classes is a volume metric per transaction, not per student.

**Cross-validate (ECS):** `URI_classes / URI_conversion` = average package size per renewal transaction — should be a reasonable integer. Run `URI_collection` (Section 2) separately and verify `URI_collection / URI_classes = URI_rpc`.

---

# SECTION 2: COLLECTION METRICS

ℹ️ For business meaning of Fresh / Cross-sale / URI buckets → Section BC-4. For URI journey context (T-6 trigger, renewal timeline) → Section BC-7.

**Primary table:** `stage_brightchamps.payment_etl`
**Amount column:** `collection_amount_inr`
**Mandatory filter:** `flag != 'No Payment'`
**Geo join:** `LEFT JOIN brightchamps.student_etl b ON pd.student_id = b.student_id`

**Metrics in this section:** `fresh_crosssale_collection`, `fresh_collection`, `crosssale_collection`, `overall_collection`, `net_collection`, `URI_collection`, `URI_ats`, `URI_rpc`, `fresh_ats`, `fresh_crosssale_ats`, `fresh_rpc`, `fresh_crosssale_rpc`

**ATS disambiguation:** Two different ATS metrics exist in this KB.
- `fresh_ats` / `fresh_crosssale_ats` (this section) — from `payment_etl`, measured on `transaction_date`. **Fixed once the day closes.** Use for revenue reporting.
- `funnel_ats` (Section 3) — from `booking_etl`, measured on `demo_date`. **Changes as new conversions arrive for the demo cohort.** Use for funnel/Conv % analysis.
When user asks for ATS in context of DC2C or conversion rate → Section 3. When user asks for ATS as a standalone revenue metric → this section.
- `uri_cohort_ats` (Section 11) — from `uri_performance_etl`, measured on cohort `pool_date_ist`. **Use for pool cohort analysis.** ⛔ When user says "URI ATS" without explicit context — DO NOT default to Section 2. Offer both Section 2 (URI_ats, transaction-date) and Section 11 (uri_cohort_ats, cohort view) and ask the user to clarify.

---

### fresh_crosssale_collection or fresh crosssale collection or total collection or revenue collected or collection

**Definition:** Total INR collected — fresh payments + cross-sale/instalment/renewal within 28 days of enrollment

**SQL — no geo filter:**
```sql
SELECT
  SUM(CASE
    WHEN flag = 'Fresh payment'
      OR (flag IN ('Cross-sale-Fresh', 'Instalment', 'Renewal')
          AND (within_28_days_student = 1 OR within_28_days_student_course = 1))
    THEN collection_amount_inr ELSE 0
  END) AS fresh_crosssale_collection
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**SQL — with geo/vertical filter:**
```sql
SELECT
  SUM(CASE
    WHEN pd.flag = 'Fresh payment'
      OR (pd.flag IN ('Cross-sale-Fresh', 'Instalment', 'Renewal')
          AND (within_28_days_student = 1 OR within_28_days_student_course = 1))
    THEN pd.collection_amount_inr ELSE 0
  END) AS fresh_crosssale_collection
FROM stage_brightchamps.payment_etl pd
LEFT JOIN brightchamps.student_etl b ON pd.student_id = b.student_id
WHERE pd.flag != 'No Payment'
  AND b.business_region_name = 'USA_Canada'   -- geo: from student_etl
  -- AND pd.vertical_name = 'Codechamps'     -- vertical: from payment_etl ← NOT b.vertical_name
  AND DATE(pd.transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** Must include ALL four flags — `Fresh payment`, `Cross-sale-Fresh`, `Instalment`, `Renewal`. The `within_28_days_student` and `within_28_days_student_course` guards are mandatory for non-fresh flags. Never simplify to just `Fresh payment`.

**Cross-validate (ECS):** Run fresh_collection and crosssale_collection separately (see entries below), verify they sum to the combined total. Also verify Overall ≥ Excl. SEA INR value.

---

### fresh_collection or fresh revenue

**Definition:** INR collected in the first 28 days from the student's first enrollment — includes fresh payments AND cross-sale/instalment/renewal within 28 days of the student's first enrollment

```sql
SELECT
  SUM(CASE
    WHEN flag = 'Fresh payment'
      OR (flag IN ('Cross-sale-Fresh', 'Instalment', 'Renewal')
          AND within_28_days_student = 1)
    THEN collection_amount_inr ELSE 0
  END) AS fresh_collection
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** This is NOT just `flag = 'Fresh payment'`. It includes `Cross-sale-Fresh`, `Instalment`, and `Renewal` rows where `within_28_days_student = 1`. Uses only the student-level 28-day guard — NOT `within_28_days_student_course`.

**Cross-validate (ECS):** `fresh_collection + crosssale_collection = fresh_crosssale_collection` — this equality holds because the two guards are mutually exclusive: fresh_collection captures `within_28_days_student=1`; crosssale_collection captures `within_28_days_student_course=1 AND within_28_days_student=0`. Together they cover all rows in fresh_crosssale_collection. Verify this sum equality holds. Also verify `fresh_collection` ≤ `fresh_crosssale_collection`.

---

### crosssale_collection or cross-sale revenue

**Definition:** INR collected against a second/third enrollment within 28 days of that course's enrollment — explicitly excludes rows where the student's first enrollment is also within 28 days (`within_28_days_student = 0`)

```sql
SELECT
  SUM(CASE
    WHEN flag IN ('Cross-sale-Fresh', 'Instalment', 'Renewal')
     AND within_28_days_student_course = 1
     AND within_28_days_student = 0
    THEN collection_amount_inr ELSE 0
  END) AS crosssale_collection
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** The `AND within_28_days_student = 0` condition is critical — it isolates rows that are within the course-level 28-day window but OUTSIDE the student-level window. Without it, this double-counts rows already captured in `fresh_collection`. Note: `fresh_collection + crosssale_collection = fresh_crosssale_collection` exactly — the two guards are mutually exclusive so together they cover the full fresh_crosssale scope.

**Cross-validate (ECS):** `fresh_collection + crosssale_collection` should equal `fresh_crosssale_collection`. Verify this sum. Also verify `crosssale_collection` ≤ `fresh_crosssale_collection` always.

---

### overall_collection or total revenue or all collections including addons

**Definition:** Total INR collected across ALL payment types — includes enrollment payments, addons, kit replacements, demo payments, and special packages. No 28-day guard. Use this when the user wants the complete revenue picture, not just enrollment-linked collection.

```sql
SELECT
  SUM(CASE
    WHEN flag IN ('Fresh payment', 'Renewal', 'Instalment', 'Cross-sale-Fresh',
                  'addons-paid', 'Kit Replacement Payment', 'Demo Payment',
                  'Zero Classes Package Payment', 'Anomaly Package Payment')
    THEN collection_amount_inr ELSE 0
  END) AS overall_collection
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** `overall_collection` ≥ `fresh_crosssale_collection` always — it includes 5 additional flag types (addons, kit, demo, zero classes, anomaly packages) with no 28-day guard. Never use `overall_collection` as a proxy for enrollment revenue — use `fresh_crosssale_collection` for that.

**Cross-validate (ECS):** `overall_collection` − `fresh_crosssale_collection` = non-enrollment revenue (addons + kit + demo + special packages). Verify this difference is non-negative.

---

### net_collection or net revenue or collection after refunds or refund adjusted collection

**Definition:** Overall collection minus refunds. Refund amounts are stored as negative values in `collection_amount_inr` — adding them reduces the total.

```sql
SELECT
  SUM(CASE
    WHEN flag IN ('Fresh payment', 'Renewal', 'Instalment', 'Cross-sale-Fresh',
                  'addons-paid', 'Kit Replacement Payment', 'Demo Payment',
                  'Zero Classes Package Payment', 'Anomaly Package Payment')
    THEN collection_amount_inr ELSE 0
  END)
  + SUM(CASE WHEN flag = 'Refund' THEN collection_amount_inr ELSE 0 END) AS net_collection
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** Refund `collection_amount_inr` values are stored as negative numbers — the formula uses addition (not subtraction) intentionally. Do NOT change to subtraction or the refunds will be double-counted. `net_collection` ≤ `overall_collection` always.

**Cross-validate (ECS):** Run `overall_collection` and `SUM refunds` separately. Verify `overall_collection` + refunds = `net_collection`. Sanity: refund SUM should be ≤ 0 (negative values).

---

### URI_collection or URI revenue or renewal revenue or instalment revenue or post-enrollment revenue

**Definition:** INR collected from Renewal/Instalment transactions outside both 28-day windows.

```sql
SELECT
  SUM(CASE
    WHEN flag IN ('Renewal', 'Instalment')
     AND within_28_days_student = 0
     AND within_28_days_student_course = 0
    THEN collection_amount_inr ELSE 0
  END) AS URI_collection
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**SQL — with geo/vertical filter:**
```sql
SELECT
  SUM(CASE
    WHEN pd.flag IN ('Renewal', 'Instalment')
     AND pd.within_28_days_student = 0
     AND pd.within_28_days_student_course = 0
    THEN pd.collection_amount_inr ELSE 0
  END) AS URI_collection
FROM stage_brightchamps.payment_etl pd
LEFT JOIN brightchamps.student_etl b ON pd.student_id = b.student_id
WHERE pd.flag != 'No Payment'
  AND b.business_region_name = 'USA_Canada'   -- geo: from student_etl
  -- AND pd.vertical_name = 'Codechamps'     -- vertical: from payment_etl ← NOT b.vertical_name
  AND DATE(pd.transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** No 28-day window bound — this captures ALL Renewal/Instalment rows outside both 28-day guards, which may include renewals months or years after the student's first enrollment. Do not compare URI_collection directly with fresh_collection as a "same-period cohort" — they represent fundamentally different lifecycle stages. Also: one student can have multiple URI rows in the same period (e.g., renewed twice in the same month), so URI_collection is a transaction-level total, not a per-student metric.

**Cross-validate (ECS):** Run `URI_conversion` count (from Section 1) separately. Verify `URI_collection / URI_conversion = URI_ats`. Sanity: URI_collection should be positive; `overall_collection` ≥ `fresh_crosssale_collection` + `URI_collection`.

---

### URI_ats or URI average transaction size or renewal ATS or instalment ATS or post-enrollment ticket size

**Definition:** Average INR per Renewal/Instalment transaction outside the 28-day window — `URI_collection` ÷ `URI_conversion`.

```sql
SELECT
  SUM(CASE
    WHEN flag IN ('Renewal', 'Instalment')
     AND within_28_days_student = 0
     AND within_28_days_student_course = 0
    THEN collection_amount_inr ELSE 0
  END)
  / NULLIF(SUM(CASE
    WHEN flag IN ('Renewal', 'Instalment')
     AND within_28_days_student = 0
     AND within_28_days_student_course = 0
    THEN 1 ELSE 0
  END), 0) AS URI_ats
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** Per-transaction average, not per-student. One student who renewed twice in the same month has 2 rows — both contribute to URI_ats denominator and numerator. URI_ats will be lower than the true per-student average if students tend to renew in smaller instalments multiple times.

**Cross-validate (ECS):** Run `URI_collection` and `URI_conversion` separately. Verify their ratio matches `URI_ats`. Sanity: positive INR value; compare to `fresh_ats` — URI_ats often higher as renewal packages tend to be larger; if URI_ats < fresh_ats investigate whether instalment splits are diluting the average.

---

### URI_rpc or URI rate per class or renewal rate per class or instalment rate per class

**Definition:** Average INR per class for Renewal/Instalment transactions outside the 28-day window — `URI_collection` ÷ `URI_classes`.

```sql
SELECT
  SUM(CASE
    WHEN flag IN ('Renewal', 'Instalment')
     AND within_28_days_student = 0
     AND within_28_days_student_course = 0
    THEN collection_amount_inr ELSE 0
  END)
  / NULLIF(SUM(CASE
    WHEN flag IN ('Renewal', 'Instalment')
     AND within_28_days_student = 0
     AND within_28_days_student_course = 0
    THEN classes_paid ELSE 0
  END), 0) AS URI_rpc
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** `classes_paid` = purchased package size, not attended classes. Per-transaction metric — a student who renewed twice has two rows, both contributing to N and D. URI_rpc = "average price per purchased class in renewal/instalment transactions outside 28 days."

**Cross-validate (ECS):** Run `URI_collection` and `URI_classes` separately. Verify their ratio matches `URI_rpc`. Sanity: positive INR value; compare to `fresh_rpc` — URI_rpc vs fresh_rpc divergence indicates whether renewal packages are priced differently per class than initial enrollments.

⚠️ **URI RPC disambiguation:** `URI_rpc` (this section) is a transaction-date metric from `payment_etl`. `uri_cohort_rpc` (Section 11) is a cohort metric from `uri_performance_etl`. When user says "URI RPC" without explicit cohort context — DO NOT default to Section 2. Offer both options and ask user to clarify.

---

### fresh_ats or fresh average transaction size or average fresh ticket size or fresh ATS

**Definition:** Average INR paid per fresh enrollment. Fixed once the transaction day closes — unlike `funnel_ats` which is measured on `demo_date` and changes as new conversions arrive for that demo cohort.

⚠️ Do NOT confuse with `funnel_ats` in Section 3. `funnel_ats` uses `booking_etl` + `demo_date` and is a cohort metric. `fresh_ats` uses `payment_etl` + `transaction_date` and is a point-in-time metric.

```sql
SELECT
  SUM(CASE
    WHEN flag = 'Fresh payment'
      OR (flag IN ('Cross-sale-Fresh', 'Instalment', 'Renewal')
          AND within_28_days_student = 1)
    THEN collection_amount_inr ELSE 0
  END)
  / NULLIF(SUM(CASE WHEN flag = 'Fresh payment' THEN 1 ELSE 0 END), 0) AS fresh_ats
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** The numerator (`fresh_collection`) spans 4 flag types across the full 28-day student window. The denominator (`fresh_conversion`) counts ONLY `Fresh payment` rows — not instalments or renewals within that window. This means `fresh_ats` represents "total 28-day spend per fresh enrollment event", NOT "average size of the first transaction." A student who paid ₹10K upfront and ₹5K instalment in week 3 contributes ₹15K to the numerator but only 1 to the denominator.

**Cross-validate (ECS):** Run `fresh_collection` (numerator) and `fresh_conversion` (denominator) separately. Verify their ratio matches `fresh_ats`. Sanity: `fresh_ats` ≥ average first-payment size (denominator is smaller than all 28-day payers). Compare to `fresh_crosssale_ats` — fresh_ats ≤ fresh_crosssale_ats is expected since crosssale adds more collection events.

---

### fresh_crosssale_ats or crosssale average transaction size or average crosssale ticket size or fresh crosssale ATS

**Definition:** Average INR paid per fresh + crosssale enrollment. Point-in-time metric measured on `transaction_date`.

⚠️ Same distinction as `fresh_ats` — do NOT confuse with `funnel_ats` in Section 3.

```sql
SELECT
  SUM(CASE
    WHEN flag = 'Fresh payment'
      OR (flag IN ('Cross-sale-Fresh', 'Instalment', 'Renewal')
          AND (within_28_days_student = 1 OR within_28_days_student_course = 1))
    THEN collection_amount_inr ELSE 0
  END)
  / NULLIF(SUM(CASE WHEN flag IN ('Fresh payment', 'Cross-sale-Fresh') THEN 1 ELSE 0 END), 0) AS fresh_crosssale_ats
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** Denominator (`fresh_crosssale_conversion`) counts `Fresh payment` AND `Cross-sale-Fresh` rows with NO 28-day guard. Numerator (`fresh_crosssale_collection`) captures collection within 28 days only. This means a Cross-sale-Fresh transaction outside 28 days adds 1 to the denominator but ₹0 to the numerator — slightly deflating the ATS. This is by design: the denominator counts enrollment events, the numerator captures the 28-day revenue those events generate.

**Cross-validate (ECS):** Run `fresh_crosssale_collection` (numerator) and `fresh_crosssale_conversion` (denominator) separately. Verify ratio matches `fresh_crosssale_ats`. Sanity: `fresh_crosssale_ats` ≥ `fresh_ats` expected (crosssale adds more collection per enrollment event).

---

### fresh_rpc or fresh rate per class or fresh revenue per class

**Definition:** Average INR per class for fresh enrollments — `fresh_collection` ÷ `fresh_classes`.

```sql
SELECT
  SUM(CASE
    WHEN flag = 'Fresh payment'
      OR (flag IN ('Cross-sale-Fresh', 'Instalment', 'Renewal')
          AND within_28_days_student = 1)
    THEN collection_amount_inr ELSE 0
  END)
  / NULLIF(SUM(CASE
    WHEN flag = 'Fresh payment'
      OR (flag IN ('Cross-sale-Fresh', 'Instalment', 'Renewal')
          AND within_28_days_student = 1)
    THEN classes_paid ELSE 0
  END), 0) AS fresh_rpc
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** `classes_paid` = classes in the **purchased package**, not classes attended or scheduled. `fresh_rpc` is "price per purchased class in the 28-day fresh window." Numerator and denominator use identical flag + guard logic so the ratio is internally consistent.

**Cross-validate (ECS):** Run `fresh_collection` and `fresh_classes` separately. Verify their ratio matches `fresh_rpc`. Sanity: positive INR value; `fresh_rpc` should be ≤ `fresh_ats` (dividing by more units lowers the per-unit rate).

---

### fresh_crosssale_rpc or crosssale rate per class or fresh crosssale revenue per class

**Definition:** Average INR per class for fresh + crosssale enrollments — `fresh_crosssale_collection` ÷ `fresh_crosssale_classes`. Both numerator and denominator use the same guard logic: `Fresh payment` + `(Cross-sale-Fresh, Instalment, Renewal)` with `within_28_days_student = 1 OR within_28_days_student_course = 1`.

```sql
SELECT
  SUM(CASE
    WHEN flag = 'Fresh payment'
      OR (flag IN ('Cross-sale-Fresh', 'Instalment', 'Renewal')
          AND (within_28_days_student = 1 OR within_28_days_student_course = 1))
    THEN collection_amount_inr ELSE 0
  END)
  / NULLIF(SUM(CASE
    WHEN flag = 'Fresh payment'
      OR (flag IN ('Cross-sale-Fresh', 'Instalment', 'Renewal')
          AND (within_28_days_student = 1 OR within_28_days_student_course = 1))
    THEN classes_paid ELSE 0
  END), 0) AS fresh_crosssale_rpc
FROM stage_brightchamps.payment_etl
WHERE flag != 'No Payment'
  AND DATE(transaction_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** `classes_paid` = purchased package size, not attended classes. Both numerator and denominator use the same flag + guard logic (both 28-day guards), so no asymmetry.

**Cross-validate (ECS):** Run `fresh_crosssale_collection` (numerator) and `fresh_crosssale_classes` (denominator) separately. Verify their ratio matches `fresh_crosssale_rpc`. Sanity: `fresh_crosssale_rpc` ≈ `fresh_rpc` — large divergence between the two is worth investigating (mix shift between fresh-only vs crosssale packages).

---

# SECTION 3: FUNNEL METRICS

ℹ️ For business context on the acquisition journey (lead stages, Scout/Hunter roles, pre-demo phase) → Section BC-3. For DC2C conceptual meaning → Section BC-3.

**Primary table:** `stage_brightchamps.booking_etl` aliased as `a`
**Mandatory filter:** `booking_status = 'active'`
**Default date column:** `demo_date` for rates, `booking_creation_date` for lead volume

**Date dimension clarification rule:** Before computing DC2C or DJ2DC, clarify whether the user wants results by `demo_date` (when the demo happened) or `booking_creation_date` (when the lead came in). Default to `demo_date` if unspecified. These give different numbers.

**Breakdown queries:** For teacher-wise, rep-wise, business-leader-wise, vertical-wise breakdowns — add `GROUP BY` on the relevant column. Examples below.

---

### leads or total leads

```sql
SELECT COUNT(DISTINCT a.booking_id) AS leads
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND DATE(booking_creation_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

---

### unique_leads or unique leads

```sql
SELECT COUNT(DISTINCT a.student_id || a.vertical_name) AS unique_leads
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND DATE(booking_creation_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

---

### demo_eligible_leads or demos scheduled

```sql
SELECT COUNT(DISTINCT CASE WHEN is_demo = 1 THEN a.student_id || a.vertical_name END) AS demo_eligible_leads
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND DATE(demo_date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

---

### L2DJ or lead to demo joined rate or demo join rate

**Definition:** % of demo-eligible leads (past demo date in IST) that joined the demo.
Denominator restricted to past demo dates — avoids inflating with future-scheduled demos.


```sql
SELECT
  COUNT(DISTINCT CASE WHEN demo_joined = 1 AND is_demo = 1
      AND DATE(demo_date + INTERVAL '5:30 hours') < DATE(current_timestamp + INTERVAL '5:30 hours')
    THEN a.student_id || a.vertical_name END) * 100.0
  / GREATEST(COUNT(DISTINCT CASE WHEN is_demo = 1
      AND DATE(demo_date + INTERVAL '5:30 hours') < DATE(current_timestamp + INTERVAL '5:30 hours')
    THEN a.student_id || a.vertical_name END), 1.0) AS L2DJ
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND DATE(demo_date + INTERVAL '5:30 hours') >= DATE(current_timestamp + INTERVAL '5:30 hours') - 10
  -- adjust date range as needed
```

**Cross-validate (ECS):** Count demo_joined and demo_eligible (past date) separately, verify ratio matches L2DJ. Numerator: `COUNT DISTINCT WHERE demo_joined=1 AND is_demo=1 AND demo_date (IST) < today`. Denominator: `COUNT DISTINCT WHERE is_demo=1 AND demo_date (IST) < today`.

**Day-on-day pattern:**
```sql
SELECT
  DATE(demo_date + INTERVAL '5:30 hours') AS demo_date_ist,
  booking_region_name,
  COUNT(DISTINCT CASE WHEN is_demo = 1 AND demo_joined = 1
      AND DATE(demo_date + INTERVAL '5:30 hours') < DATE(current_timestamp + INTERVAL '5:30 hours')
    THEN a.student_id || a.vertical_name END) * 100.0
  / GREATEST(COUNT(DISTINCT CASE WHEN is_demo = 1
      AND DATE(demo_date + INTERVAL '5:30 hours') < DATE(current_timestamp + INTERVAL '5:30 hours')
    THEN a.student_id || a.vertical_name END), 1.0) AS L2DJ
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND DATE(demo_date + INTERVAL '5:30 hours') >= DATE(current_timestamp + INTERVAL '5:30 hours') - 10
  AND DATE(demo_date + INTERVAL '5:30 hours') <= DATE(current_timestamp + INTERVAL '5:30 hours') - 1
GROUP BY 1, 2
ORDER BY 1
```

---

### DJ2DC or demo joined to demo completed or demo joined to deal

⚠️ **"Deals" = `demo_completed = 1`** — these terms are used interchangeably across dashboards and stakeholder communication.

```sql
SELECT
  COUNT(DISTINCT CASE WHEN demo_completed = 1 AND is_demo = 1
    THEN a.student_id || a.vertical_name END) * 100.0
  / GREATEST(COUNT(DISTINCT CASE WHEN demo_joined = 1 AND is_demo = 1
    THEN a.student_id || a.vertical_name END), 1.0) AS DJ2DC
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND DATE(demo_date + INTERVAL '5:30 hours') >= '2026-05-01'
  AND DATE(demo_date + INTERVAL '5:30 hours') < '2026-06-01'
  -- replace dates with appropriate range
```

**Cross-validate (ECS):** Count demo_completed leads (numerator) and demo_joined leads (denominator) separately, verify ratio matches DJ2DC. Sanity: DJ2DC should be ≤ 100% and demo_completed count should be ≤ demo_joined count.

---

### DC2C or Conv % or conversion rate or demo to conversion rate

**Definition:** % of demo-completed leads that converted.
⚠️ ALWAYS report alongside DC2C_3days and Funnel ATS in the same output.

```sql
SELECT
  COUNT(DISTINCT CASE WHEN demo_completed = 1 AND is_demo = 1 THEN a.student_id || a.vertical_name END) AS demo_completed,
  SUM(CASE WHEN is_demo = 1 AND demo_completed = 1 THEN conversion_flag END) AS conversions,
  ROUND(SUM(CASE WHEN is_demo = 1 AND demo_completed = 1 THEN conversion_flag END) * 100.0
    / GREATEST(COUNT(DISTINCT CASE WHEN demo_completed = 1 AND is_demo = 1 THEN a.student_id || a.vertical_name END), 1.0), 2) AS DC2C
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND is_demo = 1
  AND DATE(demo_date + INTERVAL '5:30 hours') >= '2026-05-01'
  AND DATE(demo_date + INTERVAL '5:30 hours') < '2026-06-01'
```

**Cross-validate (ECS):** Count demo_completed leads (denominator) and SUM conversion_flag where demo_completed=1 (numerator) in two separate SELECT statements. Verify numerator ÷ denominator × 100 = DC2C rate. A mismatch means a filter or grain error.

**Teacher-wise / rep-wise DC2C pattern:**
```sql
SELECT
  te.teacher_id,
  te.teacher_name,
  te.status        AS teacher_status,
  te.type          AS teacher_type,
  COUNT(DISTINCT CASE WHEN demo_completed = 1 AND is_demo = 1 THEN a.student_id || a.vertical_name END) AS demo_completed,
  SUM(CASE WHEN is_demo = 1 AND demo_completed = 1 THEN conversion_flag END) AS conversions,
  ROUND(SUM(CASE WHEN is_demo = 1 AND demo_completed = 1 THEN conversion_flag END) * 100.0
    / GREATEST(COUNT(DISTINCT CASE WHEN demo_completed = 1 AND is_demo = 1 THEN a.student_id || a.vertical_name END), 1.0), 2) AS DC2C
FROM stage_brightchamps.booking_etl a
LEFT JOIN brightchamps.teacher_etl te ON a.teacher_id = te.teacher_id
WHERE booking_status = 'active'
  AND is_demo = 1
  AND DATE(demo_date + INTERVAL '5:30 hours') >= '2026-05-01'
  AND DATE(demo_date + INTERVAL '5:30 hours') < '2026-06-01'
GROUP BY 1, 2, 3, 4
ORDER BY demo_completed DESC
```

---

### DC2C_3days or 3-day conversion or maturity-guarded conversion

**Definition:** % of demo-completed leads (demo >3 days ago in IST) that converted within 3 days.
Maturity guard `CURRENT_DATE - 4` excludes recent demos that haven't had a full 3-day window.

```sql
SELECT
  SUM(CASE
    WHEN DATEDIFF('day', DATE(demo_date + INTERVAL '5:30 hours'), DATE(conversion_date + INTERVAL '5:30 hours')) <= 3
      AND demo_completed = 1
      AND DATE(demo_date + INTERVAL '5:30 hours') <= CURRENT_DATE - 4
    THEN conversion_flag
  END) * 100.0
  / GREATEST(COUNT(DISTINCT CASE
    WHEN demo_completed = 1
      AND DATE(demo_date + INTERVAL '5:30 hours') <= CURRENT_DATE - 4
    THEN a.student_id || a.vertical_name
  END), 1.0) AS DC2C_3days
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND is_demo = 1
  AND DATE(demo_date + INTERVAL '5:30 hours') >= '2026-05-01'
  AND DATE(demo_date + INTERVAL '5:30 hours') < '2026-06-01'
```

**Cross-validate (ECS):** Run numerator (SUM conversion_flag where demo_date ≤ CURRENT_DATE-4 and demo_completed=1 and day diff ≤ 3) and denominator (COUNT DISTINCT where demo_date ≤ CURRENT_DATE-4 and demo_completed=1) separately. Verify ratio matches. Also verify DC2C_3days ≤ DC2C (3-day rate should be lower or equal to full DC2C).

---

### funnel_ats or ATS or average transaction size or average ticket size

⚠️ Always report alongside DC2C. Conv % and ATS move inversely — a Conv % rise with ATS drop means cheaper leads, not genuine improvement.

```sql
SELECT
  AVG(CASE WHEN conversion_flag = 1 THEN CAST(a.first_collection_amount_inr AS INTEGER) END) AS funnel_ats
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND is_demo = 1
  AND DATE(demo_date + INTERVAL '5:30 hours') >= '2026-05-01'
  AND DATE(demo_date + INTERVAL '5:30 hours') < '2026-06-01'
```

**Cross-validate (ECS):** Run `SUM(first_collection_amount_inr) WHERE conversion_flag=1` and `COUNT(*) WHERE conversion_flag=1` separately. Verify SUM ÷ COUNT = AVG (funnel_ats). Sanity: ATS should be a positive number and within a reasonable range (e.g. not ₹0 or ₹10,000,000+).

---

### L2C or lead to conversion rate

⚠️ ALWAYS report alongside L2C_7days.

```sql
SELECT
  SUM(conversion_flag) * 100.0
  / GREATEST(COUNT(DISTINCT a.student_id || a.vertical_name), 1.0) AS L2C
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND DATE(booking_creation_date + INTERVAL '5:30 hours') >= '2026-05-01'
  AND DATE(booking_creation_date + INTERVAL '5:30 hours') < '2026-06-01'
```

**Cross-validate (ECS):** Run `SUM(conversion_flag)` (numerator) and `COUNT DISTINCT student_id || vertical_name` (denominator) in separate SELECT statements. Verify ratio matches L2C. Also verify L2C ≥ L2C_7days (7-day window is more conservative).

---

### L2C_7days or 7-day lead to conversion

**Maturity guard:** `CURRENT_DATE - 8` ensures only leads with a full 7-day window are counted.

```sql
SELECT
  SUM(CASE
    WHEN DATEDIFF('day', DATE(booking_creation_date + INTERVAL '5:30 hours'), DATE(conversion_date + INTERVAL '5:30 hours')) <= 7
      AND DATE(booking_creation_date + INTERVAL '5:30 hours') <= CURRENT_DATE - 8
    THEN conversion_flag
  END) * 100.0
  / GREATEST(COUNT(DISTINCT CASE
    WHEN DATE(booking_creation_date + INTERVAL '5:30 hours') <= CURRENT_DATE - 8
    THEN a.student_id || a.vertical_name
  END), 1.0) AS L2C_7days
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND DATE(booking_creation_date + INTERVAL '5:30 hours') >= '2026-05-01'
  AND DATE(booking_creation_date + INTERVAL '5:30 hours') < '2026-06-01'
```

**Cross-validate (ECS):** Run the maturity-guarded numerator (conversions within 7 days) and denominator (leads created > 8 days ago) in separate SELECT statements. Verify ratio matches L2C_7days. Also verify L2C_7days ≤ L2C (7-day window is always more conservative than the unbounded rate).

---

# SECTION 4: QUALITY METRICS

ℹ️ For business context on when LQS/DQS/SQS apply and who owns them → Section BC-6 (Academy) and Section BC-3 (Acquisition). Key rule: DQS and SQS are only valid for Trial Completed leads; LQS applies at lead level regardless of demo outcome.

**Primary table:** `stage_brightchamps.booking_etl`
**Mandatory filter:** `booking_status = 'active'`

| Score | Column | Good Threshold | Scope |
|---|---|---|---|
| LQS | `booking_quality_score` | >= 43 | All bookings (~80–90% have a score) |
| DQS | `demo_class_score` | > 15 | demo_completed = 1 AND is_demo = 1 ONLY |
| SQS | `sales_pitch_audit_score` | > 7 | demo_completed = 1 AND is_demo = 1 ONLY |

⚠️ Never apply DQS or SQS to bookings where demo_completed = 0 — scores are NULL there.

---

### perc_good_lqs or LQS % or lead quality score

```sql
SELECT
  ROUND(COUNT(DISTINCT CASE WHEN booking_quality_score >= 43 THEN a.student_id || a.vertical_name END) * 100.0
    / GREATEST(COUNT(DISTINCT CASE WHEN booking_quality_score IS NOT NULL THEN a.student_id || a.vertical_name END), 1.0), 2) AS perc_good_lqs
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND DATE(booking_creation_date + INTERVAL '5:30 hours') >= '2026-05-01'
  AND DATE(booking_creation_date + INTERVAL '5:30 hours') < '2026-06-01'
```

**Cross-validate (ECS):** Count `booking_quality_score >= 43` (numerator) and `booking_quality_score IS NOT NULL` (denominator) separately. Verify ratio × 100 = LQS %. Sanity: result must be between 0 and 100.

---

### perc_good_dqs or DQS % or demo quality score

```sql
SELECT
  ROUND(SUM(CASE WHEN a.demo_class_score IS NOT NULL AND a.demo_class_score > 15 AND demo_completed = 1 AND is_demo = 1 THEN 1 ELSE 0 END) * 100.0
    / GREATEST(SUM(CASE WHEN a.demo_class_score IS NOT NULL AND a.demo_class_score > 0 AND demo_completed = 1 AND is_demo = 1 THEN 1 ELSE 0 END), 1.0), 2) AS perc_good_dqs
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND DATE(demo_date + INTERVAL '5:30 hours') >= '2026-05-01'
  AND DATE(demo_date + INTERVAL '5:30 hours') < '2026-06-01'
```

**Cross-validate (ECS):** Count rows where `demo_class_score > 15 AND demo_completed=1` (numerator) and `demo_class_score > 0 AND demo_completed=1` (denominator) separately. Verify ratio. Sanity: denominator must be ≤ total demo_completed count.

---

### perc_good_sqs or SQS % or sales pitch quality score

```sql
SELECT
  ROUND(SUM(CASE WHEN a.sales_pitch_audit_score IS NOT NULL AND a.sales_pitch_audit_score > 7 AND demo_completed = 1 AND is_demo = 1 THEN 1 ELSE 0 END) * 100.0
    / GREATEST(SUM(CASE WHEN a.sales_pitch_audit_score IS NOT NULL AND a.sales_pitch_audit_score > 0 AND demo_completed = 1 AND is_demo = 1 THEN 1 ELSE 0 END), 1.0), 2) AS perc_good_sqs
FROM stage_brightchamps.booking_etl a
WHERE booking_status = 'active'
  AND DATE(demo_date + INTERVAL '5:30 hours') >= '2026-05-01'
  AND DATE(demo_date + INTERVAL '5:30 hours') < '2026-06-01'
```

**Cross-validate (ECS):** Count rows where `sales_pitch_audit_score > 7 AND demo_completed=1` (numerator) and `sales_pitch_audit_score > 0 AND demo_completed=1` (denominator) separately. Verify ratio. Sanity: DQS and SQS denominators should be similar — both require demo_completed=1.

---

# SECTION 5: RCA FRAMEWORK

Use when the user asks WHY a metric changed. Always follow this sequence.

## Step 1 — Locate the Funnel Leak First
Before explaining why, show where:
```
L2DJ → DJ2DC → DC2C_3days
```
Whichever stage shows the largest drop — that's where to focus the RCA.

## Step 2 — Standard RCA Output (run in this order)

1. **Headline** — DC2C + DC2C_3days + Funnel ATS, current vs prior period
2. **Funnel stages** — L2DJ, DJ2DC, DC2C_3days side-by-side (where is the leak?)
3. **By vertical** — DC2C_3days + Funnel ATS per `vertical_name`
4. **Quality signals** — LQS%, DQS%, SQS%
5. **Channel mix** — DC2C_3days + Funnel ATS by `attr_booking_source`
6. **Demo format** — DC2C_3days + Funnel ATS by `demo_class_type_attr` (OTO vs OTM)
7. **Rep-level** — DC2C_3days + SQS + Funnel ATS per `post_demo_lead_owner` (conversion accountability) or `lead_owner_email` (current lead ownership). Use `team_manager` / `post_demo_team_manager` for manager rollups; `business_leader` / `post_demo_business_leader` for BL rollups.
8. **Synthesis** — interpret Conv % and ATS together at every dimension

## Step 3 — Rate + Distribution Decomposition

For any metric change across a dimension:

```
Total Change = Rate Effect + Distribution Effect + Interaction
```

**Rate Effect:** `Σ [ share_baseline × (rate_current − rate_baseline) ]` → Are individual segments converting better/worse?
**Distribution Effect:** `Σ [ (share_current − share_baseline) × rate_baseline ]` → Did volume shift to lower/higher-performing segments?

Both lenses always required. Rate dominated → fix quality within segments. Distribution dominated → fix top-of-funnel mix.

## RCA Dimension Reference

| Dimension | Column | Notes |
|---|---|---|
| Vertical | `vertical_name` | Mix shift to lower-converting verticals can explain an overall drop |
| Channel | `attr_booking_source` | Always use `attr_` — never raw `booking_source` |
| Demo format | `demo_class_type_attr` | OTO vs OTM — OTO typically converts higher |
| Lead quality | `booking_quality_score` | >= 43 = good |
| Demo quality | `demo_class_score` | > 15 = good |
| Sales pitch | `sales_pitch_audit_score` | > 7 = good |
| Booker type | `user_type` | 'Parent' / 'Student' |
| Grade | `grade` | Grades convert at different rates |
| Hot lead | `hot_lead_flag` | 1 = high intent |
| Sales rep / SM / Hunter (current) | `lead_owner_email` | Current Hunter (SM / Sales Rep) assigned to lead; pre-demo or general ownership questions |
| Sales rep / SM / Hunter (post-demo) | `post_demo_lead_owner` | Hunter (SM / Sales Rep) accountable for conversion after Trial Completed — prefer this for DC2C RCA |
| Scout | `scout_owner_email` | Pre-demo confirmation and L2DJ attribution |
| Team Manager | `team_manager` / `post_demo_team_manager` | Manager rollup — use pre/post variant to match the rep field being analysed |
| Business Leader | `business_leader` / `post_demo_business_leader` | BL rollup — use pre/post variant to match the rep field being analysed |
| Demo type | `demo_type` | 'first booking', 'reschedule', 'hubs' |
| Lost reason | `lost_reason` | Direct signal on why leads didn't convert |
| Teacher status | `te.status` (alias `teacher_status`) | Active / inactive flag — whether the teacher is currently engaged with BrightChamps. Join `brightchamps.teacher_etl te ON te.teacher_id = be.teacher_id`. |
| Teacher type | `te.type` (alias `teacher_type`) | `'full_time'` / `'part_time'` — full_time = first preference for demo assignment, higher payout per class; part_time = also demo-eligible, lower payout, second preference. Same join as above. |

⚠️ Both `teacher_status` and `teacher_type` require a join to `brightchamps.teacher_etl` — neither exists directly in `booking_etl`. **Always include all four teacher columns together:** `te.teacher_id, te.teacher_name, te.status AS teacher_status, te.type AS teacher_type`. Do not filter to `full_time` only when analysing demo performance; segment by teacher_type to compare both.

---

# SECTION 6: ENROLLED STUDENTS

Use this section ONLY when the user asks about unique enrolled students (not payments/conversions).

**Table:** `brightchamps.enrolled_student_etl`
**Grain:** One row per unique student
**Date column:** `First_Onboarding_Date` (stored in UTC — apply IST conversion)

---

### enrolled_students or unique enrolled students or how many students enrolled

**Definition:** Count of unique students whose first enrollment happened in the given time window

```sql
SELECT
  COUNT(DISTINCT Student_Id) AS enrolled_students
FROM brightchamps.enrolled_student_etl
WHERE DATE(First_Onboarding_Date + INTERVAL '5:30 hours') = DATE(current_timestamp + INTERVAL '5:30 hours') - 1
```

**Gotcha:** This table counts students, not courses. A student enrolling in 2 courses on the same day = 1 row here. For course-level enrollment counts, the student_course_etl table is needed (schema not yet documented — check Metabase).

---

# SECTION 7: DIMENSIONS

## 7A — Geo Resolution (4 levels, try in order)

**Level 1 — Group aliases → resolve to list of booking_region_name values**

| User says | Filter as |
|---|---|
| "Global" / "All" / "Overall" | No filter |
| "International" / "Intl" | `booking_region_name != 'India'` |
| "SEA" (as a group) | `booking_region_name IN ('SEA', 'Indonesia', 'Vietnam')` |
| "Americas" | `booking_region_name = 'USA_Canada'` |
| "EMEA" | `booking_region_name IN ('UK', 'MEA_Focus', 'Europe')` |

**Level 2 — Direct match (exact booking_region_name values in DB)**

`India` · `USA_Canada` · `UK` · `MEA_Focus` · `ANZ` · `Europe` · `SEA` · `Indonesia` · `Vietnam`

```sql
WHERE booking_region_name = 'UK'
```

**Level 3 — Country alias → booking_region_name**

| User says | booking_region_name |
|---|---|
| US / USA / United States / United States of America / America | USA_Canada |
| Canada | USA_Canada |
| Britain / England / Great Britain / United Kingdom | UK |
| Middle East / Gulf / UAE / Saudi / Dubai | MEA_Focus |
| Australia / New Zealand / Aus / NZ | ANZ |
| Europe / EU / Germany / France / Spain / Italy (any European country) | Europe |
| Singapore / Malaysia / Thailand / Philippines / SEA country | SEA |
| Indonesia / Jakarta | Indonesia |
| Vietnam / Ho Chi Minh | Vietnam |

**Level 4 — Fuzzy:** If no match at levels 1–3, search the `booking_country` column and confirm with user.

⚠️ `booking_region_group` and `booking_region_investor` are DERIVED columns (CASE expression results), NOT stored values. Never use them in a WHERE clause. Always filter by `booking_region_name` (booking_etl queries) or `business_region_name` (payment_etl queries via student_etl join).

### Derived Region Groups

Two standard grouping columns used for reporting rollups. Both go in the SELECT layer only.

---

**`booking_region_group`** — Standard operational grouping

| Result value | Condition |
|---|---|
| `SEA minus Vietnam` | `booking_region_name IN ('SEA', 'Indonesia')` |
| `ROW` | All regions not in `('SEA','Vietnam','Indonesia','USA_Canada','India')` |
| *(region name as-is)* | `India`, `USA_Canada`, `Vietnam` |

```sql
-- booking_etl queries:
CASE
  WHEN booking_region_name NOT IN ('SEA','Vietnam','Indonesia','USA_Canada','India') THEN 'ROW'
  WHEN booking_region_name IN ('SEA','Indonesia') THEN 'SEA minus Vietnam'
  ELSE booking_region_name
END AS booking_region_group

-- payment_etl queries (business_region_name from student_etl join):
CASE
  WHEN b.business_region_name NOT IN ('SEA','Vietnam','Indonesia','USA_Canada','India') THEN 'ROW'
  WHEN b.business_region_name IN ('SEA','Indonesia') THEN 'SEA minus Vietnam'
  ELSE b.business_region_name
END AS booking_region_group
```

---

**`booking_region_investor`** — Investor-view grouping (Vietnam and USA_Canada broken out; all others = ROW)

| Result value | Condition |
|---|---|
| `Vietnam` | `booking_region_name = 'Vietnam'` |
| `USA_Canada` | `booking_region_name = 'USA_Canada'` |
| `ROW` | All other regions |

```sql
-- booking_etl queries:
CASE
  WHEN booking_region_name NOT IN ('Vietnam','USA_Canada') THEN 'ROW'
  ELSE booking_region_name
END AS booking_region_investor

-- payment_etl queries (business_region_name from student_etl join):
CASE
  WHEN b.business_region_name NOT IN ('Vietnam','USA_Canada') THEN 'ROW'
  ELSE b.business_region_name
END AS booking_region_investor

-- uri_pool_etl / uri_performance_etl queries (business_region column):
CASE
  WHEN business_region NOT IN ('Vietnam','USA_Canada') THEN 'ROW'
  ELSE business_region
END AS booking_region_investor
```

---

## 7B — Vertical Resolution (3 levels)

⚠️ **Which table's `vertical_name` to use — depends on the primary table:**
- **`payment_etl` queries (Sections 1 & 2):** Filter `payment_etl.vertical_name` directly — this is the **purchased product**. Never use `booking_etl.vertical_name` here.
- **`booking_etl` queries (Section 3 funnel metrics):** Filter `booking_etl.vertical_name` — this is the **demo product**.
- **Why they differ:** A student may have booked a demo for Codechamps but purchased MathChamps. `booking_etl` records the demo vertical; `payment_etl` records the purchased vertical. Using the wrong table gives you the wrong product.

**Level 1 — Direct match (exact vertical_name values in DB)**

`Codechamps` · `MathChamps` · `Robochamps` · `Lingochamps` · `Finchamps` · `Entrepreneurship`

**Level 2 — Alias → vertical_name**

| User says | vertical_name |
|---|---|
| coding / code / codechamp | Codechamps |
| math / maths / mathematics / mathchamp | MathChamps |
| robotics / robot / robo / robochamp | Robochamps |
| language / lingo / lingochamp / english | Lingochamps |
| finance / financial literacy / finchamp | Finchamps |
| entrepreneurship / entrepreneur / startup | Entrepreneurship |

**Level 3 — Fuzzy:** Search `course_name` column.

---

## 7C — OTO vs OTM

⚠️ **Two completely independent OTO/OTM concepts exist. Always clarify which one the user means before writing any SQL.**

When user asks about OTO/OTM, ask ONE clarifying question: "Do you want OTO/OTM from the **demo perspective** (how was the demo conducted?) or from the **enrollment perspective** (what mode did the student pay for)?" These use different tables, different columns, and give different numbers. A student who attended an OTM demo can enroll OTO, and vice versa — the two are not linked.

---

### 7C-1 — Demo class OTO/OTM

**Question this answers:** Was the demo conducted 1-on-1 or in a group?
**Table:** `booking_etl`
**Column:** `demo_class_type_attr` (NOT `demo_class_type` — see banned columns)
**Use for:** Funnel metrics broken by demo mode — L2DJ, DJ2DC, DC2C, conversion % by demo type

| Value | Meaning |
|---|---|
| `'OTO'` | Single student in the demo (One-to-One) |
| `'OTM'` | Two or more students in the demo (One-to-Many) |

```sql
WHERE demo_class_type_attr = 'OTO'   -- or 'OTM'
```

---

### 7C-2 — Paid class OTO/OTM (enrollment mode)

**Question this answers:** Did the student enroll into an OTO or OTM paid course?
**Table:** `payment_etl`
**Column:** `paid_class_category`
**Use for:** Conversion counts, collection, ATS, RPC broken by enrolled class mode

⚠️ `paid_class_category` stores longer text strings — it does NOT contain clean `'OTO'`/`'OTM'` values. Always use `ILIKE '%OTM%'` to detect OTM. Anything that does NOT match is OTO.

```sql
-- Counting conversions by paid class mode
SUM(CASE WHEN paid_class_category ILIKE '%OTM%' THEN 1 ELSE 0 END) AS otm_conversion,
SUM(CASE WHEN paid_class_category NOT ILIKE '%OTM%' THEN 1 ELSE 0 END) AS oto_conversion

-- Filtering to OTM only
WHERE paid_class_category ILIKE '%OTM%'

-- Filtering to OTO only
WHERE paid_class_category NOT ILIKE '%OTM%'
```

⛔ Never write `paid_class_category = 'OTM'` or `paid_class_category = 'OTO'` — exact match returns zero rows.
⛔ Never use `demo_class_type_attr` to classify paid class mode, and never use `paid_class_category` for demo mode.

---

## 7D — NRI vs Non-NRI (Ethnicity Flag)

**Table:** `booking_etl`
**Column:** `ethnicity_flag`

| Value | Meaning |
|---|---|
| `'Indian'` | NRI parent — Indian-origin parent (living outside India) |
| `'Non-Indian'` | Non-NRI parent |
| blank / NULL | Unknown — ethnicity not captured |

**Use for:** Funnel metrics (L2DJ, DJ2DC, DC2C) and ATS analysis segmented by NRI status. NRI (Indian-origin) parents have higher conversion probability and higher ATS — this is a high-signal dimension for performance analysis.

```sql
-- Filter to NRI parents only
WHERE ethnicity_flag = 'Indian'

-- Filter to non-NRI parents only
WHERE ethnicity_flag = 'Non-Indian'

-- Group by NRI status (always handle blank)
GROUP BY CASE
  WHEN ethnicity_flag = 'Indian' THEN 'NRI'
  WHEN ethnicity_flag = 'Non-Indian' THEN 'Non-NRI'
  ELSE 'Unknown'
END
```

**Gotcha:** `ethnicity_flag = 'Indian'` does NOT mean the lead is from India geographically. It refers to the parent's ethnic origin — an Indian-origin parent living in USA/UK/UAE would have `ethnicity_flag = 'Indian'` but `booking_region_name = 'USA_Canada'` (or respective region). Never conflate this with the geo dimension. Always handle blank values explicitly — filtering `WHERE ethnicity_flag = 'Indian'` will silently drop blank rows from the denominator.

**Cross-validate (ECS):** When breaking a funnel metric by ethnicity, verify Indian + Non-Indian + Unknown = Overall total. The Unknown bucket (blank) should be called out separately — never silently drop it.

---

## 7E — Grade Band

**Table:** `booking_etl`
**Column:** `grade`
**Raw values:** 0–12 (numeric), NULL / blank

Never filter or group by raw grade values — always map to the standard bands below:

| Raw grade value | Band label |
|---|---|
| 0, 1, 2, 3 | `Little Champs` |
| 4, 5, 6 | `Junior Champs` |
| 7, 8, 9, 10, 11, 12 | `Senior Champs` |
| NULL / blank | `NA` |

**Standard SQL pattern (always use this CASE expression):**
```sql
CASE
  WHEN grade BETWEEN 0 AND 3 THEN 'Little Champs'
  WHEN grade BETWEEN 4 AND 6 THEN 'Junior Champs'
  WHEN grade >= 7            THEN 'Senior Champs'
  ELSE 'NA'
END AS grade_band
```

**Use for:** Funnel metrics (L2DJ, DJ2DC, DC2C), conversion rates, and ATS segmented by student age group. Grade band is a high-signal dimension — conversion behaviour differs significantly across bands.

**Gotcha:** Always use the CASE expression above — never filter `WHERE grade = 5` or group by raw `grade` values directly. The `ELSE 'NA'` clause handles both NULL and any unexpected non-numeric values in one shot. When presenting results, always include the NA bucket explicitly — never drop it silently, as it can be a sizeable portion of leads.

**Cross-validate (ECS):** Little Champs + Junior Champs + Senior Champs + NA must equal the Overall total. Any mismatch means the CASE expression has a gap or a raw grade value is outside 0–12.

---

## 7F — Parent Type & Student Type (New vs Repeat)

**Table:** `booking_etl`
**Columns:** `parent_type`, `student_type`

| Column | Value | Meaning |
|---|---|---|
| `parent_type` | `'new'` | Parent has never purchased any BrightChamps product for any of their children |
| `parent_type` | `'repeat'` | Parent has already converted in the past (any child, any course) |
| `student_type` | `'new'` | This specific student has never enrolled in any course before |
| `student_type` | `'repeat'` | This specific student is already enrolled in a course and has submitted a lead for another or the same course |

**Use for:** Funnel metrics (L2DJ, DJ2DC, DC2C) and conversion analysis segmented by acquisition type. Repeat parents and repeat students typically show higher conversion rates — important for separating organic re-engagement from new acquisition performance.

```sql
-- Filter to new parents only
WHERE parent_type = 'new'

-- Filter to repeat students only
WHERE student_type = 'repeat'

-- Group by both dimensions together
GROUP BY parent_type, student_type
```

**Gotcha:** `parent_type` and `student_type` are independent and can diverge. A parent with two children can be `parent_type = Repeat` (already purchased for child 1) while the lead is `student_type = New` (child 2 has never enrolled). Never assume the two always match — always clarify which dimension the user means. If the user asks about "new vs repeat" without specifying, ask: "Do you mean new/repeat at the **parent** level or the **student** level?"

Always handle NULL/blank values — include an `ELSE 'Unknown'` guard when grouping by these columns.

⛔ Values are stored in **lowercase** — never write `= 'New'` or `= 'Repeat'` (title-case). Always use `= 'new'` and `= 'repeat'`.

**Cross-validate (ECS):** New + Repeat (+ Unknown if any blanks) must equal Overall for whichever column is being used. Verify both columns separately when using both in the same query.

---

## 7G — Lead Source / UTM Attribution

**Table:** `booking_etl`

Two layers of UTM data exist. **Always use the `attr_` (attributed) columns** — never the raw UTM columns.

### Layer 1 — Raw UTMs (landing page level, pre-attribution)

These capture the exact UTM parameters from the landing page where the lead was submitted. They reflect only the last touchpoint and are NOT reliable for channel analysis.

| Column | Description |
|---|---|
| `utm_source` | Raw source from landing page |
| `utm_medium` | Raw medium from landing page |
| `utm_campaign` | Raw campaign from landing page |
| `utm_content` | Raw content from landing page |
| `booking_source` | Derived channel label from raw UTMs |

⛔ **Never use these columns for analysis.** They are pre-attribution and will misattribute leads with multiple touchpoints. These are already listed in Rule 5 (Banned Columns).

---

### Layer 2 — Attributed UTMs (parent-level attribution, use these always)

Attribution logic runs at the **parent level**, looking back at the first channel touchpoint within the last 30 days. These are the authoritative source-of-truth columns for channel analysis.

| Column | Description |
|---|---|
| `attr_utm_source` | Attributed UTM source |
| `attr_utm_medium` | Attributed UTM medium |
| `attr_utm_campaign` | Attributed UTM campaign |
| `attr_utm_content` | Attributed UTM content |
| `attr_booking_source` | **Primary channel dimension** — derived from attributed UTMs. Use this for all lead source analysis. |

**`attr_booking_source` known values (exhaustive):**

| Value | Notes |
|---|---|
| `Affiliate` | |
| `AI Retention` | |
| `App-Android` | |
| `App-IOS` | |
| `Bing` | |
| `Blank` | Unattributed — include in NULL/blank bucket for completeness |
| `Blog` | |
| `Community` | |
| `Criteo` | |
| `Direct+NULL` | Direct traffic or no UTM present |
| `DSA` | Dynamic Search Ads (Google) |
| `DSA_EGS, Sales Referral` | |
| `DSA_EGS, Teacher Referral` | |
| `DSA_EGS` | |
| `FB` | Facebook paid |
| `Google` | Google paid |
| `Google-app/project-X/fb-app` | App-based campaigns |
| `Google-Display` | |
| `MKT Affiliate` | |
| `MKT Partnership` | |
| `Organic` | |
| `Other-Referral` | |
| `Others` | |
| `Partial Leads` | |
| `pinterest` | |
| `Retention` | |
| `Retention - Calling` | |
| `Sales-Referral` | |
| `Social` | |
| `Student-Referral` | |
| `Summer Camp` | |
| `Taboola` | |
| `Teacher-Referral` | |
| `Tiktok` | |
| `twitter` | |
| `URI Cross-Sell` | |
| `Webinar` | |

⚠️ Values are case-sensitive and mixed-case (e.g. `Tiktok` not `TikTok`, `twitter` not `Twitter`, `FB` not `Facebook`). Always match exact casing when filtering.

```sql
-- Lead count by channel
GROUP BY attr_booking_source

-- Filter to a specific channel
WHERE attr_booking_source = 'Google'

-- Multi-column attribution breakdown
GROUP BY attr_booking_source, attr_utm_medium
```

**Gotcha:** Attribution is computed at the parent level over a 30-day lookback. Two leads from the same parent in the same window will share the same attributed source — this is by design. Do not expect `attr_booking_source` to always match `booking_source` for a given row.

**Cross-validate (ECS):** When breaking funnel metrics by `attr_booking_source`, verify all channel buckets sum to Overall. Check for a sizeable NULL/blank bucket — unattributed leads should be called out, not silently dropped.

---

### Attribution Channel (Derived Grouping Column)

`attribution_channel` is a cleaner, consolidated grouping of `attr_booking_source` values into reportable channel buckets. It is a DERIVED column (CASE expression result) — **SELECT layer only, never use in WHERE**. Filter by `attr_booking_source` instead.

| `attribution_channel` value | `attr_booking_source` values it covers |
|---|---|
| `AI Retention` | `AI Retention` |
| `Webinar` | `Webinar` |
| `Organic` | `Organic` |
| `Sales Retention` | `Sales Retention` |
| `Novachamps` | Any value containing `EGS` or `DSA` |
| `URI Cross-Sell` | `URI Cross-Sell` |
| `Student-Referral` | `Student-Referral` |
| `Teacher-Referral` | `Teacher-Referral` |
| `Sales-Referral` | `Sales-Referral` |
| `FB` | `FB` |
| `Marketing Retention` | `Retention - Calling`, `Retention` |
| `Social` | `Social` |
| `Google` | `Google`, `Google-Display`, `Google-app/project-X/fb-app` |
| `Direct + Others` | All remaining values (catch-all) |

```sql
CASE
  WHEN attr_booking_source = 'AI Retention'                                             THEN 'AI Retention'
  WHEN attr_booking_source = 'Webinar'                                                  THEN 'Webinar'
  WHEN attr_booking_source = 'Organic'                                                  THEN 'Organic'
  WHEN attr_booking_source = 'Sales Retention'                                          THEN 'Sales Retention'
  WHEN attr_booking_source LIKE '%EGS%' OR attr_booking_source LIKE '%DSA%'            THEN 'Novachamps'
  WHEN attr_booking_source = 'URI Cross-Sell'                                           THEN 'URI Cross-Sell'
  WHEN attr_booking_source = 'Student-Referral'                                         THEN 'Student-Referral'
  WHEN attr_booking_source = 'Teacher-Referral'                                         THEN 'Teacher-Referral'
  WHEN attr_booking_source = 'Sales-Referral'                                           THEN 'Sales-Referral'
  WHEN attr_booking_source = 'FB'                                                        THEN 'FB'
  WHEN attr_booking_source IN ('Retention - Calling', 'Retention')                     THEN 'Marketing Retention'
  WHEN attr_booking_source = 'Social'                                                    THEN 'Social'
  WHEN attr_booking_source IN ('Google', 'Google-Display', 'Google-app/project-X/fb-app') THEN 'Google'
  ELSE 'Direct + Others'
END AS attribution_channel
```

⚠️ Order of conditions matters — the `LIKE '%EGS%' OR LIKE '%DSA%'` check for Novachamps must come before the catch-all. Values like `DSA_EGS, Sales Referral` and `DSA_EGS, Teacher Referral` will correctly roll up to `Novachamps`.

---

# SECTION 8: TABLE REFERENCE

| Table | Full Name | Grain | Use For | Mandatory Filter |
|---|---|---|---|---|
| payment_etl | `stage_brightchamps.payment_etl` | Transaction | Conversion counts, collection INR | `flag != 'No Payment'` |
| booking_etl | `stage_brightchamps.booking_etl` | Booking (multiple rows per lead possible) | Funnel rates, quality, RCA dimensions, marketing metrics; use `COUNT(DISTINCT student_id\|\|vertical_name)` for CPL denominator | `booking_status = 'active'` |
| student_etl | `brightchamps.student_etl` | Student | Geo filter for payment_etl queries (`business_region_name`) | None |
| marketing_campaign_etl | `stage_brightchamps.marketing_campaign_etl` | Campaign-day | Ad spend (`spends_inr`) — campaign level only | `demo_flag != 'Recruitment Campaign'`, `spends_inr > 0` |
| parent_etl | `brightchamps.parent_etl` | One row per converted parent | LTV (`net_collection_amt_one_yr`) | `conversion_flag = 1` in ETL |
| teacher_etl | `brightchamps.teacher_etl` | Teacher | Default teacher dimension table. Always output four columns when any teacher breakdown is requested: `te.teacher_id`, `te.teacher_name`, `te.status AS teacher_status` (active/inactive), `te.type AS teacher_type` (`'full_time'` / `'part_time'`). Additional attributes available: `te.joined_at` (date teacher joined BrightChamps) and `te.terminated_at` (date teacher was deboarded/terminated — NULL if still active). | None |

## Join Keys
- `payment_etl → student_etl`: `payment_etl.student_id = student_etl.student_id`
- `booking_etl → student_etl`: `booking_etl.student_id = student_etl.student_id`
- `marketing_campaign_etl → booking_etl` (stitch): `(booking_creation_date + INTERVAL '330 minutes')::date = campaign_date_ist::date` AND `UPPER(attr_utm_campaign) = UPPER(campaign_name)`
- `parent_etl → booking_etl` (LTV): `parent_etl.parent_id = booking_etl.parent_id`
- `teacher_etl → booking_etl`: `teacher_etl.teacher_id = booking_etl.teacher_id`

## Conversion Question Decision Tree
```
User asks about COUNT of paid events       → payment_etl  (flag IN ('Fresh payment','Cross-sale-Fresh'))
User asks about RATE (Conv %, DC2C)        → booking_etl  (conversion_flag, demo_completed)
User asks about UNIQUE STUDENTS enrolled   → enrolled_student_etl
User asks about AD SPEND                    → marketing_campaign_etl  (Section 12)
User asks about CPL / ROAS / CAC / LTV      → Section 12 (booking_etl + marketing_campaign_etl + parent_etl)
```

---

# SECTION 9: OUT OF KB

If the user asks about a metric, table, or concept that does NOT appear anywhere in this document:

1. State clearly: "This metric is not defined in the Knowledge Base."
2. Do NOT invent SQL, guess flag values, or approximate with a similar metric.
3. Do NOT run any query.
4. Suggest: "Please add this metric to the Knowledge Base, then I can answer accurately."

Examples of questions to refuse: URI %, teacher attendance rate (if not in KB), impressions/clicks/reach (not yet in KB — Section 12 scope is spend + efficiency only), multi-touch attribution models, any metric not listed in Sections 1–6, 11, or 12 above.

---

# SECTION 10: MANDATORY REPORTING PAIRS

Never report these metrics alone — always include the companion.

| When user asks for | Always also report | Why |
|---|---|---|
| DC2C / Conv % | DC2C_3days + Funnel ATS | Recency bias; ATS shows revenue trade-off |
| L2C | L2C_7days | Recency bias for recent periods |
| Any metric, no region specified | Same metric Excl. SEA | Universal two-cut rule |
| Conv % RCA | Full funnel: L2DJ → DJ2DC → DC2C_3days | Locate leak before diagnosing cause |
| CPL / CAC | `total_spend_inr` + booking/parent count | Ratio without volume is misleading |
| ROAS / ROAS-6M | `total_spend_inr` + collection numerator | Revenue efficiency needs spend context |
| LTV per Parent | `net_collection_amt_one_yr` sum + `new_parent_count` | LTV without denominator is ambiguous |
| LTV/CAC | `net_collection_amt_one_yr` sum + `total_spend_inr` | Both sides of the ratio needed |
| Campaign performance / campaign report / campaign analysis | Full bundle — see ordered list below | End-to-end funnel view; no individual metric tells the story alone |


---

### Campaign Performance Bundle (Ordered)

When the user asks for **campaign performance**, **campaign report**, or **full funnel analysis**, report ALL metrics in this order — do not cherry-pick:

| # | Metric | Column / Source |
|---|---|---|
| 1 | Spends | `SUM(spends_inr)` — `marketing_campaign_etl` |
| 2 | Leads | `COUNT(DISTINCT student_id\|\|vertical_name)` — `booking_etl`, `booking_status = 'active'` |
| 3 | CPL | `spends / leads` — Overall or Paid variant per context |
| 4 | % Quality Leads | `perc_good_lqs` — `booking_quality_score >= 43` |
| 5 | % NRI | `COUNT(DISTINCT student_id\|\|vertical_name WHERE ethnicity_flag = 'Indian') / total leads × 100` — `booking_etl` (Section 7D) |
| 6 | Demo Eligible Leads | `COUNT(DISTINCT student_id\|\|vertical_name)` where `is_demo = 1` |
| 7 | DJ (Demo Joined count) | `COUNT(DISTINCT student_id\|\|vertical_name)` where `demo_joined = 1 AND is_demo = 1` |
| 8 | L2DJ | Demo joined / demo eligible leads × 100 |
| 9 | Deals / Demo Completed | `COUNT(DISTINCT student_id\|\|vertical_name)` where `demo_completed = 1 AND is_demo = 1` |
| 10 | DJ2DC | Demo completed / demo joined × 100 |
| 11 | L2DC | Demo completed / demo eligible leads × 100 |
| 12 | % Good DQS | `demo_class_score > 15` where `demo_completed = 1 AND is_demo = 1` |
| 13 | % Good SQS | `sales_pitch_audit_score > 7` where `demo_completed = 1 AND is_demo = 1` |
| 14 | DC2C | Conversions / demo completed × 100 |
| 15 | DC2C-3 days | Maturity-guarded 3-day conversion rate (`CURRENT_DATE - 4` guard) |
| 16 | L2C | Conversions / leads × 100 |
| 17 | L2C-7 days | Maturity-guarded 7-day lead-to-conversion (`CURRENT_DATE - 8` guard) |
| 18 | Funnel ATS | `AVG(first_collection_amount_inr)` where `conversion_flag = 1` |
| 19 | ROAS | `SUM(first_collection_amount_inr) / SUM(spends_inr)` |
| 20 | ROAS-6M | `SUM(net_collection_amount_first_6m) / SUM(spends_inr)` |

**Date alignment:** All booking-side metrics use `booking_creation_date` IST; quality/DJ/DC metrics use `demo_date` IST. Clarify date dimension with user if the report spans a date range.

**Variant rule:** If user says "paid campaign performance" apply paid filters (`attr_booking_source_grouped = 'paid'` + `attr_utm_campaign IS NOT NULL`) to all booking-side metrics. Otherwise use Overall variant.

---

# SECTION 11: URI FUNNEL METRICS (COHORT ANALYSIS)

*This section covers cohort-based URI funnel analysis. It answers questions about how a batch of students who entered the URI pool in a given time window performed — conversion rate, speed to renewal, ATS, and RPC. This is fundamentally different from the transaction-date URI metrics in Sections 1 & 2, which ask "how many renewals happened on day X." This section asks "of students who entered the pool in period X, how many eventually renewed?"*

---

## Routing

| If the user asks about... | Go to |
|---|---|
| uri pool size / pool due / pool size / how many students entered the uri pool | Section 11 — uri_pool_size |
| uri overall pool / total pool including direct payments | Section 11 — uri_pool_size (URI Overall variant) |
| uri team pool / rm team pool / team owned pool / pool excluding direct payments | Section 11 — uri_pool_size (URI Team variant) |
| uri cohort conversion / what % of uri pool renewed / uri funnel conversion rate | Section 11 — uri_conversion_rate |
| uri 7 day conversion / renewed within 7 days / uri % 7 day | Section 11 — uri_conversion_rate_7day |
| uri 30 day conversion / renewed within 30 days / uri % 30 day | Section 11 — uri_conversion_rate_30day |
| days to renew / renewal speed / how fast are renewals / payment efficiency / time to renewal | Section 11 — median_payment_efficiency |
| uri cohort ATS / uri average ticket size cohort / renewal ATS cohort / uri ATS / renewal ATS — ALWAYS clarify Overall vs Team before writing SQL | Section 11 — uri_cohort_ats |
| uri cohort RPC / uri revenue per class cohort / renewal RPC cohort / uri RPC / renewal RPC — ALWAYS clarify Overall vs Team before writing SQL | Section 11 — uri_cohort_rpc |
| uri funnel by RM / team lead wise uri / renewal performance by RM | Section 11 — all metrics, URI Team by RM variant, GROUP BY team_lead_name |
| uri team performance / rm team aggregate uri / team level uri (no breakdown) | Section 11 — all metrics, URI Team variant, no GROUP BY |

⚠️ **URI ATS and URI RPC disambiguation — two lenses even within Section 11:**

When user says "URI ATS" or "URI RPC" — with or without a time period or geo filter — **NEVER default to Section 2 payment_etl**. Always clarify:

| User intent | Go to |
|---|---|
| URI ATS / URI RPC as a transaction-date revenue metric ("how much per renewal last month") | Section 2 — URI_ats / URI_rpc from payment_etl |
| URI ATS / URI RPC for a pool cohort ("for students who entered the pool in April") | Section 11 — uri_cohort_ats / uri_cohort_rpc |
| URI ATS / URI RPC by RM / team lead | Section 11 — uri_cohort_ats / uri_cohort_rpc, URI Team by RM variant |

⛔ A time period like "Q1" or a geo like "USA Canada" does NOT resolve this ambiguity — both lenses support time and geo filters. Always ask before writing SQL.

---

## Three Variants — Know Which to Use

Every metric in this section has three variants. Always identify the correct one before writing SQL.

| Variant | When to use | `pool_type = 'payment'` | GROUP BY |
|---|---|---|---|
| **URI Overall** | Business-wide picture including self-initiated payments | Included | None (or optional vertical/region) |
| **URI Team** | RM-actionable pool aggregate — what the team owns | Excluded | None (or optional vertical/region) |
| **URI Team by RM** | Individual RM performance | Excluded | `team_lead_name` |

**Key rules:**
- URI Overall → include `pool_type = 'payment'` in both numerator and denominator
- URI Team and URI Team by RM → exclude `pool_type = 'payment'` from both numerator and denominator
- URI Team supports slices by `enrolled_vertical_name` and `business_region` when user asks
- When user says "by RM" or "team lead wise" → URI Team by RM
- When user says "team level" or "rm team" without asking for individual breakdown → URI Team
- When user says nothing about RM or team → URI Overall (but always confirm if context is ambiguous)

---

## Universal Rules — Apply to EVERY Query in This Section

These rules have NO exceptions. Apply them before writing any SQL for this section.

---

### Rule A — No IST Conversion (CRITICAL)

All date columns in `uri_performance_etl` are **already stored in IST**. Do NOT apply the `+ INTERVAL '5:30 hours'` offset used in `payment_etl` and `booking_etl`.

```sql
-- ✅ CORRECT for this table
WHERE pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'

-- ❌ WRONG — never do this for uri_performance_etl
WHERE DATE(pool_date_ist + INTERVAL '5:30 hours') = ...
```

⛔ Applying the IST offset here will silently shift your cohort window by 5.5 hours and pull in wrong records. This is the single most dangerous gotcha when switching between tables.

---

### Rule B — Mandatory Filters (required on every query)

```sql
AND pool_eligibility_flag = 'Valid Pool'
AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
```

| Filter | Why |
|---|---|
| `pool_eligibility_flag = 'Valid Pool'` | Excludes churned, refunded, credits-transferred, and not-yet-started students. Forgetting this inflates pool size with ineligible records. |
| `enrolled_course_name NOT IN (...)` | Applied Math, Applied Coding, and Business English are excluded from all URI funnel reporting. These are exact string matches — `ILIKE` is not needed. |

---

### Rule C — `pool_type = 'payment'` Exclusion for URI Team and URI Team by RM

For **URI Team** and **URI Team by RM** variants, always add to the WHERE clause:

```sql
AND pool_type != 'payment'
```

This applies to **both numerator and denominator** of every metric — pool size, conversion rate, ATS, RPC, and payment efficiency.

**Why:** `pool_type = 'payment'` means the student paid before the standard T-6 or 30-day expiry trigger fired. No RM action drove this — it is a self-initiated payment. Including these rows inflates the team's pool size and conversion count, misattributing organic renewals to RM performance.

**URI Overall** includes `pool_type = 'payment'` — do NOT add this filter for the Overall variant.

---

### Rule D — This Table Is for Funnel Analysis Only

`uri_performance_etl` contains `collection_amount_inr` and `classes_paid_for` columns. These are permitted **only** for cohort-level ATS and RPC calculations (Section 11). For all other collection reporting (total URI revenue, net collection, overall collection), always use `payment_etl` as defined in Section 2.

⛔ Never use `uri_performance_etl` as a substitute for `payment_etl` in Section 1 or Section 2 metrics.

---

### Rule E — Two Cuts for Global Queries

Unless the user specifies a region, always present results twice:
1. **Overall** — no region filter
2. **Excl. SEA** — `AND business_region NOT IN ('SEA', 'Indonesia', 'Vietnam')`

---

### Rule F — Cohort Date Column is `pool_date_ist`

All cohort windows are defined using `pool_date_ist` — the date the student first entered the pool in this cycle. Do not use `last_pool_date_ist`, `payment_date_ist`, or `created_at` for cohort bucketing.

| User says | SQL pattern |
|---|---|
| "April cohort" / "Apr-26" | `pool_date_ist >= '2026-04-01' AND pool_date_ist < '2026-05-01'` |
| "Q1 this year" | `pool_date_ist >= '2026-01-01' AND pool_date_ist < '2026-04-01'` |
| "last month" | `pool_date_ist >= DATE_TRUNC('month', CURRENT_DATE - INTERVAL '1 month')::date AND pool_date_ist < DATE_TRUNC('month', CURRENT_DATE)::date` |
| "last 30 days" | `pool_date_ist >= CURRENT_DATE - 30 AND pool_date_ist <= CURRENT_DATE - 1` |

---

## Table Reference

| Column | Use |
|---|---|
| `student_id` | Student identifier |
| `merged_course_id` | Course identifier (treat as course_id) |
| `pool_cycle` | Which renewal cycle — 1 = first renewal, 2 = second, etc. |
| `pool_date_ist` | Cohort entry date — use this for all date filtering |
| `pool_type` | Trigger type — `pending_credits`, `30_days_before_credit_expiry`, `payment` |
| `pool_eligibility_flag` | Always filter to `'Valid Pool'` |
| `payment_date_ist` | Renewal payment date — NULL if not yet converted |
| `payment_efficiency` | Days from pool entry to payment — NULL if not converted or pool_type = 'payment' |
| `collection_amount_inr` | Renewal payment amount in INR — cohort ATS/RPC use only |
| `classes_paid_for` | Classes purchased in renewal — cohort RPC use only |
| `enrolled_vertical_name` | Vertical — use for vertical breakdowns |
| `business_region` | Region — use for geo breakdowns and SEA exclusion |
| `class_type` | OTO or OTM |
| `team_lead_name` / `team_lead_id` | RM who owned the student at pool entry |
| `enrolled_course_name` | Course name — used for mandatory exclusion filter |

**Grain:** One row per `student_id + merged_course_id + pool_date_ist`. A student enrolled in two courses who both hit the pool in April = two rows.

---

## Metrics

---

### uri_pool_size or uri pool or pool size or pool due or uri pool due

**Definition:** Count of valid pool entries in a given cohort window — students who have entered the URI pool (via 6 credits remaining, 30-day expiry trigger, or direct payment) and are eligible for renewal outreach.

**SQL — URI Overall:**
```sql
SELECT
  COUNT(*) AS uri_pool_size
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
```

**SQL — URI Team (aggregate, excludes direct payments):**
```sql
SELECT
  COUNT(*) AS uri_pool_size_team
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
```

**SQL — URI Team by RM:**
```sql
SELECT
  team_lead_name,
  COUNT(*) AS uri_pool_size_rm
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
GROUP BY team_lead_name
ORDER BY uri_pool_size_rm DESC
```

**Gotcha:** `uri_pool_size` counts pool events, not unique students. A student enrolled in 2 courses who both hit the pool in April contributes 2 to the count. If the user asks "how many students entered the pool", use `COUNT(DISTINCT student_id)` instead.

**Gotcha:** URI Overall will always be ≥ URI Team since it includes `pool_type = 'payment'` entries. The difference between the two is the direct-payment pool count.

**Cross-validate (ECS):** Break `uri_pool_size` by `pool_type` — sum of `pending_credits` + `30_days_before_credit_expiry` + `payment` must equal URI Overall pool size. URI Team = `pending_credits` + `30_days_before_credit_expiry` only.

---

### uri_conversion_rate or uri conversion or cohort conversion rate or % renewed

**Definition:** Percentage of the valid pool that received a renewal payment, with no maturity guard. Point-in-time metric — will increase over time as more cohort members renew.

**SQL — URI Overall:**
```sql
SELECT
  COUNT(*) AS uri_pool_size,
  SUM(CASE WHEN payment_date_ist IS NOT NULL THEN 1 ELSE 0 END) AS uri_converted,
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN 1 ELSE 0 END) * 100.0
    / GREATEST(COUNT(*), 1), 2) AS uri_conversion_rate
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
```

**SQL — URI Team (aggregate):**
```sql
SELECT
  COUNT(*) AS uri_pool_size_team,
  SUM(CASE WHEN payment_date_ist IS NOT NULL THEN 1 ELSE 0 END) AS uri_converted_team,
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN 1 ELSE 0 END) * 100.0
    / GREATEST(COUNT(*), 1), 2) AS uri_conversion_rate_team
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
```

**SQL — URI Team by RM:**
```sql
SELECT
  team_lead_name,
  COUNT(*) AS uri_pool_size_rm,
  SUM(CASE WHEN payment_date_ist IS NOT NULL THEN 1 ELSE 0 END) AS uri_converted,
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN 1 ELSE 0 END) * 100.0
    / GREATEST(COUNT(*), 1), 2) AS uri_conversion_rate
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
GROUP BY team_lead_name
ORDER BY uri_conversion_rate DESC
```

**Gotcha:** This metric has no maturity guard — a cohort from last week will show a low conversion rate simply because not enough time has passed, not because performance is poor. For time-bound fair comparisons across cohorts, use `uri_conversion_rate_7day` or `uri_conversion_rate_30day` instead.

**Gotcha:** Always report `uri_pool_size` and `uri_converted` alongside the rate — a 60% conversion rate on a pool of 10 is very different from 60% on a pool of 500.

**Cross-validate (ECS):** `uri_converted + unconverted (payment_date_ist IS NULL)` must equal `uri_pool_size` for each variant. Verify this sum holds before reporting the rate.

---

### uri_conversion_rate_7day or 7 day uri conversion or uri % 7 day

**Definition:** Percentage of the valid pool that renewed within 7 days of their pool entry date. Maturity guard applied — only pool entries with at least 7 days of observation window are included. For URI Overall, `pool_type = 'payment'` entries are always counted as converted since payment occurred at pool entry (0 days). For URI Team and URI Team by RM, `pool_type = 'payment'` is excluded entirely.

**Maturity guard:** `pool_date_ist <= CURRENT_DATE - 7`

**SQL — URI Overall:**
```sql
SELECT
  COUNT(*) AS uri_pool_size_7day,
  SUM(CASE WHEN pool_type = 'payment'
        OR (payment_date_ist IS NOT NULL AND payment_efficiency <= 7)
      THEN 1 ELSE 0 END) AS uri_converted_7day,
  ROUND(SUM(CASE WHEN pool_type = 'payment'
        OR (payment_date_ist IS NOT NULL AND payment_efficiency <= 7)
      THEN 1 ELSE 0 END) * 100.0
    / GREATEST(COUNT(*), 1), 2) AS uri_conversion_rate_7day
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
  AND pool_date_ist <= CURRENT_DATE - 7
```

**SQL — URI Team (aggregate):**
```sql
SELECT
  COUNT(*) AS uri_pool_size_7day_team,
  SUM(CASE WHEN payment_date_ist IS NOT NULL
    AND payment_efficiency <= 7 THEN 1 ELSE 0 END) AS uri_converted_7day_team,
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL
    AND payment_efficiency <= 7 THEN 1 ELSE 0 END) * 100.0
    / GREATEST(COUNT(*), 1), 2) AS uri_conversion_rate_7day_team
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
  AND pool_date_ist <= CURRENT_DATE - 7
```

**SQL — URI Team by RM:**
```sql
SELECT
  team_lead_name,
  COUNT(*) AS uri_pool_size_7day,
  SUM(CASE WHEN payment_date_ist IS NOT NULL
    AND payment_efficiency <= 7 THEN 1 ELSE 0 END) AS uri_converted_7day,
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL
    AND payment_efficiency <= 7 THEN 1 ELSE 0 END) * 100.0
    / GREATEST(COUNT(*), 1), 2) AS uri_conversion_rate_7day
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
  AND pool_date_ist <= CURRENT_DATE - 7
GROUP BY team_lead_name
ORDER BY uri_conversion_rate_7day DESC
```

**Gotcha:** The maturity guard (`pool_date_ist <= CURRENT_DATE - 7`) applies to both numerator and denominator — pool entries from the last 7 days are excluded entirely. This ensures every row in the denominator has had a fair 7-day window. Never apply the maturity guard only to the numerator.

**Gotcha:** For URI Overall, `pool_type = 'payment'` entries always count as converted since payment occurred at pool entry (0 days elapsed). For URI Team and URI Team by RM, these are excluded entirely — the numerator uses `payment_date_ist IS NOT NULL AND payment_efficiency <= 7` only.

**Cross-validate (ECS):** `uri_conversion_rate_7day` ≤ `uri_conversion_rate` always for all three variants. Any inversion means a filter or logic error.

---

### uri_conversion_rate_30day or 30 day uri conversion or uri % 30 day

**Definition:** Percentage of the valid pool that renewed within 30 days of their pool entry date. Maturity guard applied — only pool entries with at least 30 days of observation window are included. For URI Overall, `pool_type = 'payment'` entries are always counted as converted. For URI Team and URI Team by RM, `pool_type = 'payment'` is excluded entirely.

**Maturity guard:** `pool_date_ist <= CURRENT_DATE - 30`

**SQL — URI Overall:**
```sql
SELECT
  COUNT(*) AS uri_pool_size_30day,
  SUM(CASE WHEN pool_type = 'payment'
        OR (payment_date_ist IS NOT NULL AND payment_efficiency <= 30)
      THEN 1 ELSE 0 END) AS uri_converted_30day,
  ROUND(SUM(CASE WHEN pool_type = 'payment'
        OR (payment_date_ist IS NOT NULL AND payment_efficiency <= 30)
      THEN 1 ELSE 0 END) * 100.0
    / GREATEST(COUNT(*), 1), 2) AS uri_conversion_rate_30day
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
  AND pool_date_ist <= CURRENT_DATE - 30
```

**SQL — URI Team (aggregate):**
```sql
SELECT
  COUNT(*) AS uri_pool_size_30day_team,
  SUM(CASE WHEN payment_date_ist IS NOT NULL
    AND payment_efficiency <= 30 THEN 1 ELSE 0 END) AS uri_converted_30day_team,
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL
    AND payment_efficiency <= 30 THEN 1 ELSE 0 END) * 100.0
    / GREATEST(COUNT(*), 1), 2) AS uri_conversion_rate_30day_team
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
  AND pool_date_ist <= CURRENT_DATE - 30
```

**SQL — URI Team by RM:**
```sql
SELECT
  team_lead_name,
  COUNT(*) AS uri_pool_size_30day,
  SUM(CASE WHEN payment_date_ist IS NOT NULL
    AND payment_efficiency <= 30 THEN 1 ELSE 0 END) AS uri_converted_30day,
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL
    AND payment_efficiency <= 30 THEN 1 ELSE 0 END) * 100.0
    / GREATEST(COUNT(*), 1), 2) AS uri_conversion_rate_30day
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
  AND pool_date_ist <= CURRENT_DATE - 30
GROUP BY team_lead_name
ORDER BY uri_conversion_rate_30day DESC
```

**Gotcha:** Given that the average URI journey takes 25–30 days, `uri_conversion_rate_30day` is the most meaningful conversion benchmark for a cohort — it captures the vast majority of renewals that will realistically happen. `uri_conversion_rate` (unbounded) is better for monitoring recent cohorts where the 30-day window hasn't closed yet.

**Gotcha:** For URI Overall, `pool_type = 'payment'` entries always count as converted. For URI Team variants, these are excluded — the numerator uses `payment_date_ist IS NOT NULL AND payment_efficiency <= 30` only.

**Gotcha:** For recent cohorts (e.g. current month), the maturity guard may exclude most or all rows, returning a NULL or zero result. This is expected — flag it to the user rather than reporting a misleading 0%.

**Cross-validate (ECS):** `uri_conversion_rate_7day` ≤ `uri_conversion_rate_30day` ≤ `uri_conversion_rate` — this ordering must always hold for all three variants independently. Any violation indicates a logic error.

---

### median_payment_efficiency or days to renew or renewal speed or time to renewal

**Definition:** Median number of days between pool entry date and renewal payment date, across all converted pool entries. Measures how quickly renewals are closing after a student enters the pool. `pool_type = 'payment'` is always excluded from this metric across all three variants since `payment_efficiency` is NULL for these rows.

**SQL — URI Overall:**
```sql
SELECT
  PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY payment_efficiency) AS median_payment_efficiency
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND payment_date_ist IS NOT NULL
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
```

**SQL — URI Team (aggregate):**
```sql
SELECT
  PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY payment_efficiency) AS median_payment_efficiency_team
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND payment_date_ist IS NOT NULL
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
```

**SQL — URI Team by RM:**
```sql
SELECT
  team_lead_name,
  PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY payment_efficiency) AS median_payment_efficiency
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND payment_date_ist IS NOT NULL
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
GROUP BY team_lead_name
ORDER BY median_payment_efficiency ASC
```

**Gotcha:** `pool_type = 'payment'` is excluded from this metric across ALL three variants — not just RM level. These rows have `payment_efficiency = NULL` since payment occurred simultaneously with pool entry. Including them would deflate the median. This means URI Overall and URI Team produce the same SQL for this metric — the only difference between variants is the GROUP BY.

**Gotcha:** This metric is computed only over converted rows (`payment_date_ist IS NOT NULL`). It measures speed among those who renewed — it says nothing about students who haven't renewed yet. A low median on a low conversion rate cohort is not a positive signal.

**Gotcha:** Always report alongside `uri_conversion_rate` — median days to renew is only meaningful in context of how many converted.

**Cross-validate (ECS):** Run `MIN(payment_efficiency)` and `MAX(payment_efficiency)` alongside the median. The median must fall between the two. A median of 0 after excluding `pool_type = 'payment'` suggests a data issue worth investigating.

---

### uri_cohort_ats or uri ATS cohort or average ticket size uri cohort or renewal ATS cohort

**Definition:** Average INR collected per renewal payment within the cohort — `SUM(collection_amount_inr) / COUNT(converted rows)`. Measures the average deal size for renewals originating from a given pool cohort.

⚠️ When user says "URI ATS" without explicit cohort context — always clarify whether they want Section 2 (`URI_ats` from `payment_etl`, transaction-date view) or Section 11 (`uri_cohort_ats`, cohort view) before writing SQL.

**SQL — URI Overall:**
```sql
SELECT
  SUM(CASE WHEN payment_date_ist IS NOT NULL THEN collection_amount_inr ELSE 0 END) AS uri_cohort_collection,
  SUM(CASE WHEN payment_date_ist IS NOT NULL THEN 1 ELSE 0 END) AS uri_converted,
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN collection_amount_inr ELSE 0 END)
    / NULLIF(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN 1 ELSE 0 END), 0), 2) AS uri_cohort_ats
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
```

**SQL — URI Team (aggregate):**
```sql
SELECT
  SUM(CASE WHEN payment_date_ist IS NOT NULL THEN collection_amount_inr ELSE 0 END) AS uri_cohort_collection_team,
  SUM(CASE WHEN payment_date_ist IS NOT NULL THEN 1 ELSE 0 END) AS uri_converted_team,
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN collection_amount_inr ELSE 0 END)
    / NULLIF(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN 1 ELSE 0 END), 0), 2) AS uri_cohort_ats_team
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
```

**SQL — URI Team by RM:**
```sql
SELECT
  team_lead_name,
  SUM(CASE WHEN payment_date_ist IS NOT NULL THEN collection_amount_inr ELSE 0 END) AS uri_cohort_collection,
  SUM(CASE WHEN payment_date_ist IS NOT NULL THEN 1 ELSE 0 END) AS uri_converted,
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN collection_amount_inr ELSE 0 END)
    / NULLIF(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN 1 ELSE 0 END), 0), 2) AS uri_cohort_ats
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
GROUP BY team_lead_name
ORDER BY uri_cohort_ats DESC
```

**Gotcha:** `collection_amount_inr` from `uri_performance_etl` is used here as an exception to Rule D — this is the only scenario where collection is read from this table. This is intentional because cohort-level ATS requires tying the payment back to the specific pool entry, which cannot be cleanly done by joining `payment_etl`. Do NOT use this table's collection for any other revenue reporting.

**Gotcha:** Do not confuse `uri_cohort_ats` with `URI_ats` from Section 2. `URI_ats` is measured on `transaction_date` from `payment_etl` and is a point-in-time revenue metric. `uri_cohort_ats` is measured on `pool_date_ist` cohort and reflects the average deal size for a specific pool entry batch.

**Cross-validate (ECS):** Run `uri_cohort_collection` and `uri_converted` separately. Verify their ratio matches `uri_cohort_ats`. Compare to `URI_ats` from Section 2 — large divergence is worth investigating.

---

### uri_cohort_rpc or uri RPC cohort or rate per class uri cohort or revenue per class uri cohort

**Definition:** Average INR per class purchased in renewal payments within the cohort — `SUM(collection_amount_inr) / SUM(classes_paid_for)`. Measures the per-class price realised for renewals originating from a given pool cohort.

⚠️ When user says "URI RPC" without explicit cohort context — always clarify whether they want Section 2 (`URI_rpc` from `payment_etl`, transaction-date view) or Section 11 (`uri_cohort_rpc`, cohort view) before writing SQL.

**SQL — URI Overall:**
```sql
SELECT
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN collection_amount_inr ELSE 0 END)
    / NULLIF(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN classes_paid_for ELSE 0 END), 0), 2) AS uri_cohort_rpc
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
```

**SQL — URI Team (aggregate):**
```sql
SELECT
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN collection_amount_inr ELSE 0 END)
    / NULLIF(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN classes_paid_for ELSE 0 END), 0), 2) AS uri_cohort_rpc_team
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
```

**SQL — URI Team by RM:**
```sql
SELECT
  team_lead_name,
  ROUND(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN collection_amount_inr ELSE 0 END)
    / NULLIF(SUM(CASE WHEN payment_date_ist IS NOT NULL THEN classes_paid_for ELSE 0 END), 0), 2) AS uri_cohort_rpc
FROM brightchamps.uri_performance_etl
WHERE pool_eligibility_flag = 'Valid Pool'
  AND enrolled_course_name NOT IN ('Applied Math', 'Applied Coding', 'Business English')
  AND pool_type != 'payment'
  AND pool_date_ist >= '2026-04-01'
  AND pool_date_ist < '2026-05-01'
GROUP BY team_lead_name
ORDER BY uri_cohort_rpc DESC
```

**Gotcha:** Same collection exception as `uri_cohort_ats` — `collection_amount_inr` and `classes_paid_for` are read from `uri_performance_etl` only for cohort-level RPC. Do not use this table for any broader revenue reporting.

**Gotcha:** `classes_paid_for` is the purchased renewal package size, not classes attended. `uri_cohort_rpc` is "price per purchased class in the renewal", consistent with how `URI_rpc` is defined in Section 2.

**Cross-validate (ECS):** Run `SUM(collection_amount_inr)` and `SUM(classes_paid_for)` over converted rows separately. Verify their ratio matches `uri_cohort_rpc`. Sanity: `uri_cohort_rpc` should be ≤ `uri_cohort_ats`. Compare to `URI_rpc` from Section 2 — large divergence warrants investigation.

---

## Mandatory Reporting Pairs

Never report these metrics alone — always include the companion.

| When user asks for | Always also report | Why |
|---|---|---|
| `uri_conversion_rate` | `uri_pool_size` + `uri_converted` count + `uri_conversion_rate_7day` | Rate without volume is misleading; 7-day gives maturity-adjusted view alongside overall |
| `uri_conversion_rate_7day` | `uri_conversion_rate` + `uri_conversion_rate_30day` | Gives short, overall, and medium-term view of the same cohort |
| `median_payment_efficiency` | `uri_conversion_rate` | Speed is only meaningful alongside how many converted |
| `uri_cohort_ats` | `uri_converted` count | ATS on a small converted base can be misleading |
| `uri_cohort_rpc` | `uri_cohort_ats` | RPC and ATS together show both per-class and per-deal economics |
| Any metric, no region specified | Same metric Excl. SEA (`business_region NOT IN ('SEA','Indonesia','Vietnam')`) | Universal two-cut rule (Rule E) |
| Any URI Team or URI Team by RM metric | Verify `pool_type != 'payment'` filter is applied | Without this, self-initiated renewals are misattributed to the team |
| Any metric with no variant specified | Clarify Overall vs Team before writing SQL | The two variants answer different business questions |

---

## Common Dimension Breakdowns

| Dimension | Column | Notes |
|---|---|---|
| Region / Geo | `business_region` | Same values as `booking_region_name` in booking_etl — use same alias resolution from Section 7A; for investor-view grouping apply `booking_region_investor` CASE from Section 7A (uri variant) |
| Vertical | `enrolled_vertical_name` | Purchased vertical — same alias resolution as Section 7B |
| Class type | `class_type` | `'OTO'` or `'OTM'` — direct exact match, unlike `payment_etl` which requires `ILIKE` |
| RM | `team_lead_name` / `team_lead_id` | Always apply `pool_type != 'payment'` when grouping by this dimension (URI Team by RM variant) |
| Pool trigger type | `pool_type` | `pending_credits`, `30_days_before_credit_expiry`, `payment` |
| Renewal cycle | `pool_cycle` | 1 = first renewal, 2 = second, etc. Include all cycles unless user specifies otherwise |
| Day on day / trend | `pool_date_ist` | `GROUP BY pool_date_ist` with appropriate date range filter |

---

---

# SECTION 12: MARKETING SPEND & EFFICIENCY METRICS

ℹ️ Business context → Section BC-9. Date rules → Section 0 Rule 7. Stitching rules → Section 0 Rule 8.

⛔ **Primary funnel table is `booking_etl`** — CPL denominator is `COUNT(DISTINCT student_id||vertical_name)` (student+vertical grain). Do NOT use `lead_etl` or `COUNT(DISTINCT lead_id)` for CPL.

**Scope:** Total spend, CPL, CPD, ROAS, ROAS-6M, CAC, LTV per Parent (First Year), LTV/CAC. Impressions/clicks/reach are out of scope until added later.

**Dashboard calculated-field formulas (authoritative — aggregate then divide):**

| Metric | Expression |
|---|---|
| CPL (Overall) | `sum({total_spend_inr}) / count(distinct {student_id}\|\|{vertical_name})` — all active bookings |
| CPL (Paid) | `sum({total_spend_inr}) / count(distinct {student_id}\|\|{vertical_name})` — paid channel only (`attr_booking_source_grouped = 'paid'`, `attr_utm_campaign IS NOT NULL`) |
| CPD (Overall) | `sum({total_spend_inr}) / count(distinct {student_id}\|\|{vertical_name})` — demo completed (`demo_completed = 1`) |
| CPD (Paid) | `sum({total_spend_inr}) / count(distinct {student_id}\|\|{vertical_name})` — demo completed + paid channel only |
| ROAS (Overall) | `sum({first_collection_amount_inr}) / sum({total_spend_inr})` — all active bookings |
| ROAS (Paid) | `sum({first_collection_amount_inr}) / sum({total_spend_inr})` — paid channel only (`attr_booking_source_grouped = 'paid'`, `attr_utm_campaign IS NOT NULL`) |
| ROAS-6M (Overall) | `sum({net_collection_amount_first_6m}) / sum({total_spend_inr})` — all active bookings |
| ROAS-6M (Paid) | `sum({net_collection_amount_first_6m}) / sum({total_spend_inr})` — paid channel only |
| CAC (Overall) | `sum({total_spend_inr}) / count(distinct {parent_id})` — `conversion_flag = 1` + `parent_type = 'new'` |
| CAC (Paid) | `sum({total_spend_inr}) / count(distinct {parent_id})` — `conversion_flag = 1` + `parent_type = 'new'` + paid channel |
| LTV per Parent (1-year) (Overall) | `sum({net_collection_amt_one_yr}) / count(distinct {parent_id})` — `conversion_flag = 1` + `parent_type = 'new'` |
| LTV per Parent (2-year) (Overall) | `sum({net_collection_amt_two_yr}) / count(distinct {parent_id})` — `conversion_flag = 1` + `parent_type = 'new'` |
| LTV per Parent (1-year) (Paid) | `sum({net_collection_amt_one_yr}) / count(distinct {parent_id})` — `conversion_flag = 1` + `parent_type = 'new'` + paid channel |
| LTV per Parent (2-year) (Paid) | `sum({net_collection_amt_two_yr}) / count(distinct {parent_id})` — `conversion_flag = 1` + `parent_type = 'new'` + paid channel |
| LTV/CAC (1-year) (Overall) | `sum({net_collection_amt_one_yr}) / sum({total_spend_inr})` — `conversion_flag = 1` + `parent_type = 'new'` |
| LTV/CAC (2-year) (Overall) | `sum({net_collection_amt_two_yr}) / sum({total_spend_inr})` — `conversion_flag = 1` + `parent_type = 'new'` |
| LTV/CAC (1-year) (Paid) | `sum({net_collection_amt_one_yr}) / sum({total_spend_inr})` — `conversion_flag = 1` + `parent_type = 'new'` + paid channel |
| LTV/CAC (2-year) (Paid) | `sum({net_collection_amt_two_yr}) / sum({total_spend_inr})` — `conversion_flag = 1` + `parent_type = 'new'` + paid channel |

---

## Key column definitions (from ETL)

| Column | Table | Definition |
|---|---|---|
| `first_collection_amount_inr` | `booking_etl` | INR collected on first conversion package (`pay` CTE). NULL → treat as **0** in ROAS |
| `net_collection_amount_first_6m` | `booking_etl` | Net collection in first **6 calendar months from first payment** per `student_id + course_id`; includes refunds |
| `parent_type` | `booking_etl` | `'new'` if no prior parent transaction before `booking_creation_date`; forced `'repeat'` if `student_type = 'repeat'` |
| `net_collection_amt_one_yr` | `parent_etl` | Net collection in first 365 days from parent's first payment |
| `attr_booking_source_grouped` | `booking_etl` | Use `= 'paid'` for paid acquisition funnel |
| `attr_utm_campaign` | `booking_etl` | Campaign stitch key — `UPPER(attr_utm_campaign) = UPPER(campaign_name)` |
| `campaign_name` | `stage_brightchamps.marketing_campaign_etl` | Raw campaign name — stitch key (`UPPER(campaign_name) = UPPER(attr_utm_campaign)`); also used for ILIKE-based vertical derivation when stitching with `booking_etl` |
| `vertical_name` | `stage_brightchamps.marketing_campaign_etl` | Campaign target vertical — direct column; use instead of ILIKE derivation on `campaign_name` |
| `attr_campaign_country` | `stage_brightchamps.marketing_campaign_etl` | Campaign targeting country — direct column; replaces the regex CASE derivation from `campaign_name` |
| `attr_campaign_region` | `stage_brightchamps.marketing_campaign_etl` | Campaign targeting region — direct column; native values: Africa / ANZ / EJTI / Europe / India / Indonesia / MEA_Focus / MEA_Other / Rest of the World / SEA / UK / USA_Canada / Vietnam |
| `ad_set_group_name` | `stage_brightchamps.marketing_campaign_etl` | Ad set group — sub-campaign grouping; stitch to `booking_etl` via `attr_utm_term` |
| `ad_id` | `stage_brightchamps.marketing_campaign_etl` | Ad ID — ad-level identifier; maps to `attr_utm_content` in `booking_etl` |

---

## Campaign Derived Dimensions

⛔ **Do NOT confuse with `booking_region_name` or `business_region_name`** — those reflect the student/lead geography from `booking_etl`. These dimensions are derived from the **campaign name** in `marketing_campaign_etl` and describe what vertical and geography the campaign was *targeting*.

| Derived column | Alias(es) | Source | Notes |
|---|---|---|---|
| `campaign_vertical` | campaign target vertical | `vertical_name` (direct column in stage table); ILIKE on `attr_utm_campaign` when stitching with `booking_etl` | No derivation needed for stage table queries |
| `campaign_country` | campaign geo / campaign targeting country | `attr_campaign_country` (direct column in stage table) | No regex derivation needed for stage table queries |
| `campaign_region` | campaign region | `attr_campaign_region` (direct column in stage table) | 13 native values — see column definition above |
| `campaign_region_group` | campaign region / campaign geo group | CASE on `attr_campaign_region` | Groups 13 values into 5 buckets: India / USA_Canada / Vietnam / SEA / ROW |
| `campaign_region_investor` | campaign investor view / investor region | derived from `campaign_region_group` | Vietnam / USA_Canada / ROW |

### campaign_vertical

`vertical_name` is a direct column in `stage_brightchamps.marketing_campaign_etl` — use it directly. When joined to `booking_etl`, `vertical_name` is available via the stitch join — no ILIKE derivation needed.

```sql
SELECT vertical_name AS campaign_vertical
FROM stage_brightchamps.marketing_campaign_etl
```

### campaign_country

`attr_campaign_country` is a direct column in `stage_brightchamps.marketing_campaign_etl` — use it directly. When joined to `booking_etl`, `attr_campaign_country` is available via the stitch join — no regex derivation needed.

⚠️ `campaign_country` ≠ `booking_region_name` or `business_region_name` — those reflect student/lead geography. `campaign_country` reflects campaign targeting intent. Never substitute one for the other.

```sql
SELECT attr_campaign_country AS campaign_country
FROM stage_brightchamps.marketing_campaign_etl
```

**Usage pattern — campaign spend by country and region:**
```sql
WITH campaigns AS (
  SELECT
    attr_campaign_country,
    attr_campaign_region,
    CASE
      WHEN attr_campaign_region = 'India'                THEN 'India'
      WHEN attr_campaign_region = 'USA_Canada'           THEN 'USA_Canada'
      WHEN attr_campaign_region = 'Vietnam'              THEN 'Vietnam'
      WHEN attr_campaign_region IN ('SEA', 'Indonesia')  THEN 'SEA'
      ELSE 'ROW'
    END AS campaign_region_group,
    campaign_name,
    spends_inr
  FROM stage_brightchamps.marketing_campaign_etl
  WHERE DATE(campaign_date_ist) = CURRENT_DATE - 1
    AND demo_flag != 'Recruitment Campaign'
    AND spends_inr > 0
)
SELECT
  attr_campaign_country,
  attr_campaign_region,
  campaign_region_group,
  CASE
    WHEN campaign_region_group NOT IN ('Vietnam', 'USA_Canada') THEN 'ROW'
    ELSE campaign_region_group
  END AS campaign_region_investor,
  SUM(spends_inr) AS total_spends,
  COUNT(DISTINCT campaign_name) AS campaigns
FROM campaigns
GROUP BY 1, 2, 3, 4
ORDER BY 5 DESC
```
---

### campaign_region_group

Derived from `attr_campaign_region` (direct column in stage table). Skips the `campaign_country` derivation step.

| Result value | `attr_campaign_region` values |
|---|---|
| `India` | India |
| `USA_Canada` | USA_Canada |
| `Vietnam` | Vietnam |
| `SEA` | SEA, Indonesia |
| `ROW` | Africa, ANZ, EJTI, Europe, MEA_Focus, MEA_Other, Rest of the World, UK |

```sql
CASE
  WHEN attr_campaign_region = 'India'                          THEN 'India'
  WHEN attr_campaign_region = 'USA_Canada'                     THEN 'USA_Canada'
  WHEN attr_campaign_region = 'Vietnam'                        THEN 'Vietnam'
  WHEN attr_campaign_region IN ('SEA', 'Indonesia')            THEN 'SEA'
  ELSE 'ROW'  -- covers: Africa, ANZ, EJTI, Europe, MEA_Focus, MEA_Other, Rest of the World, UK
END AS campaign_region_group
```

⚠️ Derive from `attr_campaign_region` directly. Do not chain through `campaign_country` for stage table queries.

---

### campaign_region_investor

Investor-view grouping built on top of `campaign_region_group`. Mirrors `booking_region_investor` logic — Vietnam and USA_Canada are named buckets; everything else is ROW.

| Result value | Condition |
|---|---|
| `Vietnam` | `campaign_region_group = 'Vietnam'` |
| `USA_Canada` | `campaign_region_group = 'USA_Canada'` |
| `ROW` | All others (India, SEA, ROW) |

```sql
CASE
  WHEN campaign_region_group NOT IN ('Vietnam', 'USA_Canada') THEN 'ROW'
  ELSE campaign_region_group
END AS campaign_region_investor
```

⚠️ Derive in order: `attr_campaign_region` → `campaign_region_group` → `campaign_region_investor`. Use a CTE or subquery to chain both derivations in a single query.

---

### total_spends or total spend or ad spend or marketing spend

**Definition:** Total INR spent on paid digital ads.

**KB default:**

```sql
SELECT SUM(spends_inr) AS total_spends
FROM stage_brightchamps.marketing_campaign_etl
WHERE DATE(campaign_date_ist) = CURRENT_DATE - 1
  AND demo_flag != 'Recruitment Campaign'
  AND spends_inr > 0
```

**Slice on any combination of:** `campaign_date_ist`, `campaign_source`, `campaign_name`, `campaign_origin`, `campaign_region`, `campaign_country`, `demo_flag`.

**SQL — by platform (FB vs Google):**
```sql
SELECT
  campaign_origin,
  SUM(spends_inr) AS total_spends
FROM stage_brightchamps.marketing_campaign_etl
WHERE DATE(campaign_date_ist) >= CURRENT_DATE - 7
  AND DATE(campaign_date_ist) <= CURRENT_DATE - 1
  AND demo_flag != 'Recruitment Campaign'
  AND spends_inr > 0
GROUP BY 1
```

**Cross-validate (ECS):** Channel breakdown (`campaign_origin`) should sum to total spend.

---

### cpl or cost per lead or cost per demo scheduled

**Definition:** Total spend divided by unique student-vertical count (student+vertical grain). Two variants — clarify which the user needs before writing SQL.

| Variant | When to use | Booking-side filters |
|---|---|---|
| **Overall CPL** | Total spend across all demos booked | `booking_status = 'active'` only |
| **Paid CPL** | Spend efficiency for paid acquisition channel | `booking_status = 'active'` + `attr_booking_source_grouped = 'paid'` + `attr_utm_campaign IS NOT NULL` |

**Denominator (both variants):** `COUNT(DISTINCT student_id||vertical_name)` from `booking_etl` — student + vertical grain.

**Numerator (both variants):** `SUM(spends_inr)` from `marketing_campaign_etl`, stitched per Section 0 Rule 8.

**SQL — Overall CPL (date-level):**
```sql
WITH spend AS (
  SELECT
    DATE(campaign_date_ist) AS dt,
    SUM(spends_inr) AS total_spends
  FROM stage_brightchamps.marketing_campaign_etl
  WHERE DATE(campaign_date_ist) = CURRENT_DATE - 1
    AND demo_flag != 'Recruitment Campaign'
    AND spends_inr > 0
  GROUP BY 1
),
demos AS (
  SELECT
    (booking_creation_date + INTERVAL '330 minutes')::date AS dt,
    COUNT(DISTINCT student_id||vertical_name) AS demo_count
  FROM stage_brightchamps.booking_etl
  WHERE booking_status = 'active'
    AND (booking_creation_date + INTERVAL '330 minutes')::date = CURRENT_DATE - 1
  GROUP BY 1
)
SELECT
  s.dt,
  s.total_spends,
  d.demo_count,
  s.total_spends / NULLIF(d.demo_count, 0) AS cpl
FROM spend s
LEFT JOIN demos d ON s.dt = d.dt
```

**SQL — Paid CPL (date-level):**
```sql
WITH spend AS (
  SELECT
    DATE(campaign_date_ist) AS dt,
    SUM(spends_inr) AS total_spends
  FROM stage_brightchamps.marketing_campaign_etl
  WHERE DATE(campaign_date_ist) = CURRENT_DATE - 1
    AND demo_flag != 'Recruitment Campaign'
    AND spends_inr > 0
  GROUP BY 1
),
demos AS (
  SELECT
    (booking_creation_date + INTERVAL '330 minutes')::date AS dt,
    COUNT(DISTINCT student_id||vertical_name) AS demo_count
  FROM stage_brightchamps.booking_etl
  WHERE booking_status = 'active'
    AND attr_booking_source_grouped = 'paid'
    AND attr_utm_campaign IS NOT NULL
    AND (booking_creation_date + INTERVAL '330 minutes')::date = CURRENT_DATE - 1
  GROUP BY 1
)
SELECT
  s.dt,
  s.total_spends,
  d.demo_count,
  s.total_spends / NULLIF(d.demo_count, 0) AS cpl
FROM spend s
LEFT JOIN demos d ON s.dt = d.dt
```

**SQL — date + country (either variant):**
```sql
-- Add campaign_country to spend GROUP BY; booking_country to bookings GROUP BY
-- Stitch campaigns via UPPER(attr_utm_campaign) = UPPER(campaign_name) when aggregating across campaigns
```

**Gotcha:** Never use `lead_count` from `marketing_campaign_etl` for CPL — it is a pre-allocated dashboard field, not a raw count. Always `SUM(spend) / COUNT(DISTINCT student_id||vertical_name)` at the dimension grain. Never average row-level CPL.

**Cross-validate (ECS):** `total_spends / demo_count = cpl` at aggregated level. Report `total_spends` and `demo_count` alongside CPL.

---

### cpd or cost per demo completed or cost per deal

**Definition:** Total spend divided by unique student-vertical count where the demo was completed (`demo_completed = 1`). Also referred to as **cost per deal** — "deals" and "demo completed" are used interchangeably. Same grain and structure as CPL — the only difference is the additional `demo_completed = 1` filter on the booking side.

| Variant | When to use | Booking-side filters |
|---|---|---|
| **Overall CPD** | Total spend per completed demo across all channels | `booking_status = 'active'` + `demo_completed = 1` |
| **Paid CPD** | Spend efficiency for paid channel completed demos | `booking_status = 'active'` + `demo_completed = 1` + `attr_booking_source_grouped = 'paid'` + `attr_utm_campaign IS NOT NULL` |

**Denominator (both variants):** `COUNT(DISTINCT student_id||vertical_name)` from `booking_etl` where `demo_completed = 1` — student + vertical grain, completed demos only.

**Numerator (both variants):** `SUM(spends_inr)` from `marketing_campaign_etl`, stitched per Section 0 Rule 8.

**SQL — Overall CPD (date-level):**
```sql
WITH spend AS (
  SELECT
    DATE(campaign_date_ist) AS dt,
    SUM(spends_inr) AS total_spends
  FROM stage_brightchamps.marketing_campaign_etl
  WHERE DATE(campaign_date_ist) = CURRENT_DATE - 1
    AND demo_flag != 'Recruitment Campaign'
    AND spends_inr > 0
  GROUP BY 1
),
demos AS (
  SELECT
    (booking_creation_date + INTERVAL '330 minutes')::date AS dt,
    COUNT(DISTINCT student_id||vertical_name) AS demo_completed_count
  FROM stage_brightchamps.booking_etl
  WHERE booking_status = 'active'
    AND demo_completed = 1
    AND (booking_creation_date + INTERVAL '330 minutes')::date = CURRENT_DATE - 1
  GROUP BY 1
)
SELECT
  s.dt,
  s.total_spends,
  d.demo_completed_count,
  s.total_spends / NULLIF(d.demo_completed_count, 0) AS cpd
FROM spend s
LEFT JOIN demos d ON s.dt = d.dt
```

**SQL — Paid CPD (date-level):**
```sql
WITH spend AS (
  SELECT
    DATE(campaign_date_ist) AS dt,
    SUM(spends_inr) AS total_spends
  FROM stage_brightchamps.marketing_campaign_etl
  WHERE DATE(campaign_date_ist) = CURRENT_DATE - 1
    AND demo_flag != 'Recruitment Campaign'
    AND spends_inr > 0
  GROUP BY 1
),
demos AS (
  SELECT
    (booking_creation_date + INTERVAL '330 minutes')::date AS dt,
    COUNT(DISTINCT student_id||vertical_name) AS demo_completed_count
  FROM stage_brightchamps.booking_etl
  WHERE booking_status = 'active'
    AND demo_completed = 1
    AND attr_booking_source_grouped = 'paid'
    AND attr_utm_campaign IS NOT NULL
    AND (booking_creation_date + INTERVAL '330 minutes')::date = CURRENT_DATE - 1
  GROUP BY 1
)
SELECT
  s.dt,
  s.total_spends,
  d.demo_completed_count,
  s.total_spends / NULLIF(d.demo_completed_count, 0) AS cpd
FROM spend s
LEFT JOIN demos d ON s.dt = d.dt
```

**SQL — date + country (either variant):**
```sql
-- Add campaign_country to spend GROUP BY; booking_country to bookings GROUP BY
-- Stitch campaigns via UPPER(attr_utm_campaign) = UPPER(campaign_name) when aggregating across campaigns
```

**Gotcha:** CPD > CPL always (fewer completions than schedules). When comparing CPD vs CPL, the ratio `CPL / CPD` gives the show rate implied by spend. Never use `lead_count` from `marketing_campaign_etl`. Never average row-level CPD — always `SUM(spend) / COUNT(DISTINCT student_id||vertical_name)` at the dimension grain.

**Cross-validate (ECS):** `total_spends / demo_completed_count = cpd` at aggregated level. Report `total_spends` and `demo_completed_count` alongside CPD. Cross-check: `cpd / cpl ≈ 1 / show_rate`.

---


### roas or return on ad spend

**Definition:** First collection INR divided by spend. Dashboard formula: `sum(first_collection_amount_inr) / sum(total_spend_inr)`. Two variants — clarify which the user needs before writing SQL.

| Variant | When to use | Booking-side filters |
|---|---|---|
| **Overall ROAS** | Total return across all channels | `booking_status = 'active'` only |
| **Paid ROAS** | Return on paid channel spend only | `booking_status = 'active'` + `attr_booking_source_grouped = 'paid'` + `attr_utm_campaign IS NOT NULL` |

**Numerator (both variants):** `SUM(COALESCE(first_collection_amount_inr, 0))` from `booking_etl`.

**Denominator (both variants):** `SUM(spends_inr)` from `marketing_campaign_etl`, same stitch as CPL.

**Date lens:** Spend day = booking creation day (IST).

**SQL — Overall ROAS:**
```sql
WITH spend AS (
  SELECT SUM(spends_inr) AS total_spends
  FROM stage_brightchamps.marketing_campaign_etl
  WHERE DATE(campaign_date_ist) = CURRENT_DATE - 1
    AND demo_flag != 'Recruitment Campaign'
    AND spends_inr > 0
),
collection AS (
  SELECT SUM(COALESCE(first_collection_amount_inr, 0)) AS first_collection_amount_inr
  FROM stage_brightchamps.booking_etl
  WHERE booking_status = 'active'
    AND (booking_creation_date + INTERVAL '330 minutes')::date = CURRENT_DATE - 1
)
SELECT
  s.total_spends,
  c.first_collection_amount_inr,
  c.first_collection_amount_inr / NULLIF(s.total_spends, 0) AS roas
FROM spend s, collection c
```

**SQL — Paid ROAS:**
```sql
WITH spend AS (
  SELECT SUM(spends_inr) AS total_spends
  FROM stage_brightchamps.marketing_campaign_etl
  WHERE DATE(campaign_date_ist) = CURRENT_DATE - 1
    AND demo_flag != 'Recruitment Campaign'
    AND spends_inr > 0
),
collection AS (
  SELECT SUM(COALESCE(first_collection_amount_inr, 0)) AS first_collection_amount_inr
  FROM stage_brightchamps.booking_etl
  WHERE booking_status = 'active'
    AND attr_booking_source_grouped = 'paid'
    AND attr_utm_campaign IS NOT NULL
    AND (booking_creation_date + INTERVAL '330 minutes')::date = CURRENT_DATE - 1
)
SELECT
  s.total_spends,
  c.first_collection_amount_inr,
  c.first_collection_amount_inr / NULLIF(s.total_spends, 0) AS roas
FROM spend s, collection c
```

**Gotcha:** No `conversion_flag` filter on numerator — sum all `first_collection_amount_inr` in scope (non-converted leads contribute 0). NULL `first_collection_amount_inr` → 0.

**Cross-validate (ECS):** Report `total_spends` and `first_collection_amount_inr` alongside ROAS.

---

### roas_6m or ROAS-6M or 6-month ROAS

**Definition:** Net collection in first 6 months from first payment, divided by spend. Dashboard formula: `sum(collection_amount_first_6m) / sum(total_spend_inr)` where `collection_amount_first_6m` = `net_collection_amount_first_6m`. Two variants — same Overall/Paid split as ROAS.

| Variant | When to use | Booking-side filters |
|---|---|---|
| **Overall ROAS-6M** | 6-month return across all channels | `booking_status = 'active'` only |
| **Paid ROAS-6M** | 6-month return on paid channel only | `booking_status = 'active'` + `attr_booking_source_grouped = 'paid'` + `attr_utm_campaign IS NOT NULL` |

**Numerator:** `SUM(COALESCE(net_collection_amount_first_6m, 0))` from `booking_etl`.

**Window (`roas` logic in `booking_etl` ETL):** `FLOOR(months_between(transaction_date, first_txn_date)) <= 6` from first payment per `student_id + course_id`. **Net** of refunds.

**SQL:** Same pattern as ROAS above — replace `first_collection_amount_inr` in collection CTE with `net_collection_amount_first_6m`. Add or omit paid filters per variant.

**Gotcha:** Recent cohorts may not have matured 6 months — include them but **state the maturity caveat**. Do not confuse with extrapolated ROAS (below).

**Maturity note:** Always mention when reporting recent dates: "ROAS-6M may understate true value for cohorts still within their 6-month window."

---

### roas_6m_extrapolated or extrapolated ROAS or projected ROAS-6M

**Definition:** Dashboard-only projected ROAS using regional historical ratios. Use **only when user explicitly asks for extrapolated/projected ROAS**.

**Logic (from dashboard dataset SQL):**
1. Compute `new_ratio_6m = SUM(net_collection_amount_first_6m) / SUM(first_collection_amount_inr)` by conversion month + `parent_region_name` where `conversion_flag = 1`
2. Apply ratio to each booking with `month_difference` between 7 and 12 months from regional benchmark
3. `roas_amount_e = first_collection_amount_inr * roas_ratio_6m`

**Gotcha:** This is an estimate, not actual collection. Default to standard ROAS-6M (above) unless user requests extrapolation.

---

### cac or cost per acquisition or cost per new parent

**Definition:** Spend divided by converted new parent count. Dashboard formula: `sum(total_spend_inr) / sum(new_parent_count)`. Two variants — clarify which the user needs before writing SQL.

| Variant | When to use | Booking-side filters |
|---|---|---|
| **Overall CAC** | All converted new parents regardless of channel | `conversion_flag = 1` + `parent_type = 'new'` |
| **Paid CAC** | Converted new parents via paid channel | `conversion_flag = 1` + `parent_type = 'new'` + `attr_booking_source_grouped = 'paid'` + `attr_utm_campaign IS NOT NULL` |

**Denominator (both variants):** `COUNT(DISTINCT parent_id)` where `conversion_flag = 1` AND `parent_type = 'new'` from `booking_etl`.

**SQL — Overall CAC:**
```sql
WITH spend AS (
  SELECT SUM(spends_inr) AS total_spends
  FROM stage_brightchamps.marketing_campaign_etl
  WHERE DATE(campaign_date_ist) = CURRENT_DATE - 1
    AND demo_flag != 'Recruitment Campaign'
    AND spends_inr > 0
),
new_parents AS (
  SELECT COUNT(DISTINCT parent_id) AS new_parent_count
  FROM stage_brightchamps.booking_etl
  WHERE conversion_flag = 1
    AND parent_type = 'new'
    AND (booking_creation_date + INTERVAL '330 minutes')::date = CURRENT_DATE - 1
)
SELECT
  s.total_spends,
  n.new_parent_count,
  s.total_spends / NULLIF(n.new_parent_count, 0) AS cac
FROM spend s, new_parents n
```

**SQL — Paid CAC:**
```sql
WITH spend AS (
  SELECT SUM(spends_inr) AS total_spends
  FROM stage_brightchamps.marketing_campaign_etl
  WHERE DATE(campaign_date_ist) = CURRENT_DATE - 1
    AND demo_flag != 'Recruitment Campaign'
    AND spends_inr > 0
),
new_parents AS (
  SELECT COUNT(DISTINCT parent_id) AS new_parent_count
  FROM stage_brightchamps.booking_etl
  WHERE conversion_flag = 1
    AND parent_type = 'new'
    AND attr_booking_source_grouped = 'paid'
    AND attr_utm_campaign IS NOT NULL
    AND (booking_creation_date + INTERVAL '330 minutes')::date = CURRENT_DATE - 1
)
SELECT
  s.total_spends,
  n.new_parent_count,
  s.total_spends / NULLIF(n.new_parent_count, 0) AS cac
FROM spend s, new_parents n
```

**Gotcha:** Denominator is `conversion_flag = 1` AND `parent_type = 'new'` from `booking_etl` — do NOT use `booking_status = 'active'`, `lead_etl`, or dashboard triple-join logic.

**Cross-validate (ECS):** Report `total_spends` and `new_parent_count` alongside CAC.

---

### ltv_per_parent or LTV per parent or LTV (1-year or 2-year)

**Definition:** Net collection per new converted parent over a fixed window (1-year or 2-year). Always clarify **both** dimensions before writing SQL: channel (Overall vs Paid) and window (1-year vs 2-year).

| Variant | Channel filter | Window column (`parent_etl`) |
|---|---|---|
| **Overall LTV (1-year)** | None | `net_collection_amt_one_yr` |
| **Overall LTV (2-year)** | None | `net_collection_amt_two_yr` |
| **Paid LTV (1-year)** | `attr_booking_source_grouped = 'paid'` + `attr_utm_campaign IS NOT NULL` | `net_collection_amt_one_yr` |
| **Paid LTV (2-year)** | `attr_booking_source_grouped = 'paid'` + `attr_utm_campaign IS NOT NULL` | `net_collection_amt_two_yr` |

**Denominator (all variants):** `COUNT(DISTINCT parent_id)` where `conversion_flag = 1` AND `parent_type = 'new'` from `booking_etl`.

**Numerator:** `SUM(pe.net_collection_amt_one_yr)` or `SUM(pe.net_collection_amt_two_yr)` from `brightchamps.parent_etl`, joined on `parent_id`.

**SQL — Overall LTV (1-year):**
```sql
WITH new_parents AS (
  SELECT DISTINCT parent_id
  FROM stage_brightchamps.booking_etl
  WHERE conversion_flag = 1
    AND parent_type = 'new'
    AND (booking_creation_date + INTERVAL '330 minutes')::date
        BETWEEN CURRENT_DATE - 7 AND CURRENT_DATE - 1
),
ltv AS (
  SELECT SUM(pe.net_collection_amt_one_yr) AS ltv_amount
  FROM brightchamps.parent_etl pe
  INNER JOIN new_parents np ON pe.parent_id = np.parent_id
)
SELECT
  COUNT(*) AS new_parent_count,
  l.ltv_amount,
  l.ltv_amount / NULLIF(COUNT(*), 0) AS ltv_per_parent
FROM new_parents np, ltv l
GROUP BY l.ltv_amount
```

**SQL — Overall LTV (2-year):**
```sql
WITH new_parents AS (
  SELECT DISTINCT parent_id
  FROM stage_brightchamps.booking_etl
  WHERE conversion_flag = 1
    AND parent_type = 'new'
    AND (booking_creation_date + INTERVAL '330 minutes')::date
        BETWEEN CURRENT_DATE - 7 AND CURRENT_DATE - 1
),
ltv AS (
  SELECT SUM(pe.net_collection_amt_two_yr) AS ltv_amount
  FROM brightchamps.parent_etl pe
  INNER JOIN new_parents np ON pe.parent_id = np.parent_id
)
SELECT
  COUNT(*) AS new_parent_count,
  l.ltv_amount,
  l.ltv_amount / NULLIF(COUNT(*), 0) AS ltv_per_parent
FROM new_parents np, ltv l
GROUP BY l.ltv_amount
```

**SQL — Paid LTV (1-year):**
```sql
WITH new_parents AS (
  SELECT DISTINCT parent_id
  FROM stage_brightchamps.booking_etl
  WHERE conversion_flag = 1
    AND parent_type = 'new'
    AND attr_booking_source_grouped = 'paid'
    AND attr_utm_campaign IS NOT NULL
    AND (booking_creation_date + INTERVAL '330 minutes')::date
        BETWEEN CURRENT_DATE - 7 AND CURRENT_DATE - 1
),
ltv AS (
  SELECT SUM(pe.net_collection_amt_one_yr) AS ltv_amount
  FROM brightchamps.parent_etl pe
  INNER JOIN new_parents np ON pe.parent_id = np.parent_id
)
SELECT
  COUNT(*) AS new_parent_count,
  l.ltv_amount,
  l.ltv_amount / NULLIF(COUNT(*), 0) AS ltv_per_parent
FROM new_parents np, ltv l
GROUP BY l.ltv_amount
```

**SQL — Paid LTV (2-year):**
```sql
WITH new_parents AS (
  SELECT DISTINCT parent_id
  FROM stage_brightchamps.booking_etl
  WHERE conversion_flag = 1
    AND parent_type = 'new'
    AND attr_booking_source_grouped = 'paid'
    AND attr_utm_campaign IS NOT NULL
    AND (booking_creation_date + INTERVAL '330 minutes')::date
        BETWEEN CURRENT_DATE - 7 AND CURRENT_DATE - 1
),
ltv AS (
  SELECT SUM(pe.net_collection_amt_two_yr) AS ltv_amount
  FROM brightchamps.parent_etl pe
  INNER JOIN new_parents np ON pe.parent_id = np.parent_id
)
SELECT
  COUNT(*) AS new_parent_count,
  l.ltv_amount,
  l.ltv_amount / NULLIF(COUNT(*), 0) AS ltv_per_parent
FROM new_parents np, ltv l
GROUP BY l.ltv_amount
```

**Gotcha:** `net_collection_amt_one_yr` = 365 days from first payment; `net_collection_amt_two_yr` = 730 days. Recent cohorts may not have matured to the window — always state maturity caveat. Denominator is `conversion_flag = 1` AND `parent_type = 'new'` from `booking_etl` — do NOT use `booking_status = 'active'` or `lead_etl`. 2-year LTV will be NULL/understated for cohorts under 2 years old.

**Cross-validate (ECS):** Report `ltv_amount` sum and `new_parent_count` alongside LTV. Verify `2yr LTV ≥ 1yr LTV` for mature cohorts.

---

### ltv_cac or LTV/CAC or LTV to CAC ratio

**Definition:** Net collection divided by total spend for the same cohort. Always clarify **both** dimensions: channel (Overall vs Paid) and window (1-year vs 2-year).

| Variant | Numerator column | Booking-side filters |
|---|---|---|
| **Overall LTV/CAC (1-year)** | `net_collection_amt_one_yr` | `conversion_flag = 1` + `parent_type = 'new'` |
| **Overall LTV/CAC (2-year)** | `net_collection_amt_two_yr` | `conversion_flag = 1` + `parent_type = 'new'` |
| **Paid LTV/CAC (1-year)** | `net_collection_amt_one_yr` | `conversion_flag = 1` + `parent_type = 'new'` + paid filters |
| **Paid LTV/CAC (2-year)** | `net_collection_amt_two_yr` | `conversion_flag = 1` + `parent_type = 'new'` + paid filters |

**Formula (all variants):** `SUM(net_collection_amt_one_yr or two_yr) / SUM(spends_inr)` — **not** per-parent average of ratios.

**SQL — Overall LTV/CAC (1-year):**
```sql
WITH spend AS (
  SELECT SUM(spends_inr) AS total_spends
  FROM stage_brightchamps.marketing_campaign_etl
  WHERE DATE(campaign_date_ist) = CURRENT_DATE - 1
    AND demo_flag != 'Recruitment Campaign'
    AND spends_inr > 0
),
new_parents AS (
  SELECT DISTINCT b.parent_id
  FROM stage_brightchamps.booking_etl b
  WHERE b.conversion_flag = 1
    AND b.parent_type = 'new'
    AND (b.booking_creation_date + INTERVAL '330 minutes')::date = CURRENT_DATE - 1
),
ltv AS (
  SELECT SUM(pe.net_collection_amt_one_yr) AS ltv_amount
  FROM brightchamps.parent_etl pe
  INNER JOIN new_parents np ON pe.parent_id = np.parent_id
)
SELECT
  s.total_spends,
  l.ltv_amount,
  l.ltv_amount / NULLIF(s.total_spends, 0) AS ltv_cac
FROM spend s, ltv l
```

**SQL — Overall LTV/CAC (2-year):** Same as above — replace `net_collection_amt_one_yr` with `net_collection_amt_two_yr`.

**SQL — Paid LTV/CAC (1-year):**
```sql
WITH spend AS (
  SELECT SUM(spends_inr) AS total_spends
  FROM stage_brightchamps.marketing_campaign_etl
  WHERE DATE(campaign_date_ist) = CURRENT_DATE - 1
    AND demo_flag != 'Recruitment Campaign'
    AND spends_inr > 0
),
new_parents AS (
  SELECT DISTINCT b.parent_id
  FROM stage_brightchamps.booking_etl b
  WHERE b.conversion_flag = 1
    AND b.parent_type = 'new'
    AND b.attr_booking_source_grouped = 'paid'
    AND b.attr_utm_campaign IS NOT NULL
    AND (b.booking_creation_date + INTERVAL '330 minutes')::date = CURRENT_DATE - 1
),
ltv AS (
  SELECT SUM(pe.net_collection_amt_one_yr) AS ltv_amount
  FROM brightchamps.parent_etl pe
  INNER JOIN new_parents np ON pe.parent_id = np.parent_id
)
SELECT
  s.total_spends,
  l.ltv_amount,
  l.ltv_amount / NULLIF(s.total_spends, 0) AS ltv_cac
FROM spend s, ltv l
```

**SQL — Paid LTV/CAC (2-year):** Same as Paid (1-year) — replace `net_collection_amt_one_yr` with `net_collection_amt_two_yr`.

**Gotcha:** Same cohort and dimension grain on both sides. Maturity caveat applies — 2-year numerator will be NULL/understated for cohorts under 2 years old. `LTV/CAC = (LTV per parent) / (CAC)` — verify numerically. Never average row-level ratios.

**Cross-validate (ECS):** `LTV/CAC (1yr) = net_collection_amt_one_yr / total_spends`; `LTV/CAC (2yr) = net_collection_amt_two_yr / total_spends` at aggregate level.

---

## Source Table Drill-Down (Below Campaign Grain)

`marketing_campaign_etl` is campaign-level only. For adset/ad/adgroup drill-down, query tryouts sources directly (IST dates, no `+5:30`):

| Platform | Table | Notes |
|---|---|---|
| FB / Meta | `tryouts.performance_marketing_spends` | Dedup on ad-level fields in ETL |
| Google legacy | `tryouts.performance_marketing_google_spends` | `date_of_day < '2026-04-01'`, `campaign` empty/null |
| Google new | `tryouts.google_campaign_location_daily_metrics` | `date >= '2026-04-01'`, use `cost_inr` |

⛔ `marketing_etl` table exists but is **not used** for this KB — use `marketing_campaign_etl` instead.


# SECTION 13 — PAID CLASS METRICS

## SECTION 13 — BUSINESS CONTEXT & UNIVERSAL RULES FOR PAID CLASS METRICS

### Source Tables
| Table | Use for |
|---|---|
| `brightchamps.paid_class_etl` | Schedule/status-level metrics: classes_scheduled, cancellations, incomplete_classes, classes_breakup, cancellation lead time. No `business_region_name` column — join to `brightchamps.student_etl` on `student_id` for regional cuts. `vertical_name` is native, no join needed. **`paid_class_status_id = 16` (soft delete) exists in this table and must be explicitly excluded.** |
| `stage_brightchamps.paid_class_metrics_etl` | Teacher/student/engagement-level metrics: join behavior, duration, quality scores, feedback, assignments, quizzes, PTM. `business_region_name` and `vertical_name` are both native — no join needed. **`paid_class_status_id = 16` does not exist in this table.** |

### Status Mapping
| ID | Status |
|---|---|
| 12 | Pending |
| 13 | Completed |
| 14 | Cancelled by parent |
| 15 | Cancelled by teacher |
| 16 | Ignore / soft delete (exists only in `paid_class_etl`) |
| 17 | Incomplete |
| 18 | Paused due to no-show |

Most engagement/quality metrics (PQS, PTM-QS, feedback, assignments, quizzes, on-time/drop-off behavior) default to **completed only (13)**. Schedule-level metrics (classes_scheduled, cancellations, classes_breakup) span multiple statuses by design — check each entry's status scope individually.

### Universal Exclusion
`course_id != 16` applies to every metric in this section, no exceptions.

### Class Mode Classification (OTO / OTM Regular / OTM Master Class)
```sql
CASE
  WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
  WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
  ELSE 'OTO'
END
```
Master Class is always reported as its own row — never merged into OTM Regular. This breakdown applies to every metric in this section unless explicitly noted otherwise (e.g., PQS/PTM-QS metrics, which are OTO-only).

### Grain Rules
- **OTO:** one row = one student = one class. Dedupe on `paid_class_id` for class-level counts.
- **OTM Regular / Master Class:** one row = one student = one group class. Dedupe on `group_class_id` for class-level counts (valid because `paid_class_status_id`, `cancelled_at`, `class_start_at`, and teacher-side join behavior are uniform across all student rows sharing a `group_class_id` — confirmed).
- **Student/teacher-individual behaviors** (join-time mismatch, feedback, ratings, assignment/quiz completion, scores) are row-level — no dedupe, even for OTM, since these vary per student.

### Grain Disclosure Rule
Whenever results for any metric in this section are calculated and shared with the user, the metric's plain-language grain one-liner (found in that metric's Gotcha section) must be included alongside the numbers — not just buried in documentation. This keeps it clear to a non-technical reader what's actually being counted (e.g., whether a group class with 10 students contributes one entry or ten). Quick reference for all 24 metrics:

| Metric | Grain one-liner |
|---|---|
| classes_scheduled | A class with 10 students is still counted once — this counts classes themselves, not how many students were in them. |
| cancellations_by_parent | A cancelled class is counted once, no matter how many students were enrolled in it. |
| cancellations_by_teacher | Same as above — counted once per class, not per student in it. |
| incomplete_classes | An incomplete class is counted once, regardless of how many students were in it. |
| classes_breakup | Every number here is a class count, not a student count — a class with many students still counts once. |
| cancellation_pct_by_parent | This percentage is based on classes, not students — a group class with 10 students that gets cancelled is one cancelled class, not ten. |
| cancellation_pct_by_teacher | Same as above — based on classes, not the number of students in them. |
| avg_time_to_cancellation_by_parent | This average is per class, not per student — a group class with several students contributes one lead-time number, not one for each student in it. |
| avg_time_to_cancellation_by_teacher | Same as above — one number per class, regardless of class size. |
| student_joined_teacher_no_show (TNJSJ) | Counted per student — if 5 students were in a group class and the teacher never showed up, that's 5 separate entries here, one for each student affected, not just one for the whole class. |
| teacher_joined_student_no_show (TJSNJ) | Counted per student — if the teacher showed up but several students in a group class didn't, each missing student is counted separately. |
| on_time_class_start | Counted per student — in a group class, each student's own arrival time is checked individually, so one class can produce several entries, one per student. |
| early_dropoff | Counted per student — each student's own time in class is measured separately, so a group class can show up multiple times here if several students left early. |
| perfect_class_pct | Counted per student — a "perfect class" mark is given to each student individually, so in a group class some students can be marked perfect while others aren't, for the same session. |
| avg_pqs_score / pqs_bucket_pct | This only applies to one-on-one classes — group classes aren't scored this way, so there's no group-class number to compare here at all. |
| avg_ptm_qs / ptm_qs_bucket_pct | Same as above — this only applies to one-on-one classes, group classes aren't included. |
| parent_ptm_join_pct | Same as above — one-on-one classes only. |
| on_time_teacher_join / late_teacher_join | This looks only at the teacher, so a group class is counted once no matter how many students were in it — the teacher was either on time or not, for the class as a whole. |
| avg_student_feedback_rating / feedback_rating_bucket_pct | Counted per student — each student gives their own rating, so a group class can have several ratings attached to it, one per student who responded. |
| feedback_submit_lag | Counted per student — each student's feedback timing is their own, so a group class can contribute multiple timing entries, one per student who left feedback. |
| assignment_completion_pct | Counted per student — each student's assignment progress is tracked on its own, so a group class can contribute several entries, one per student. |
| assignment_avg_score_pct | Counted per student — each student's score is their own, so a group class can have multiple scores attached to it, one per student. |
| quiz_completion_pct | Counted per student — same as assignments, each student's quiz progress is tracked individually within a group class. |
| quiz_avg_score_pct | Counted per student — each student's quiz score is their own, so a group class can have multiple scores attached, one per student. |

### Regional Cut (Excl. SEA)
Same as the rest of the KB: `business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')`. Always present Overall + Excl. SEA unless the user specifies a region.

### IST Timezone
Same Rule 1 as the rest of the KB — all timestamps are UTC, convert with `+ INTERVAL '5:30 hours'` for date filtering.

### Postgres Casting Note (recurring across duration/lag/percentile metrics)
`EXTRACT(EPOCH FROM ...)` returns `double precision`; PostgreSQL's two-argument `ROUND()` only accepts `numeric` — cast with `::numeric` before rounding. Separately, `PERCENTILE_CONT(...) WITHIN GROUP (...)` always returns `double precision` regardless of input type — its result must independently be cast `::numeric` before `ROUND()` will accept it. Both casts are required wherever this pattern recurs.

### Teacher-Level Breakdown Join Rule
Whenever any metric in this section is asked for **by teacher**, join `class_teacher_id` (from either `brightchamps.paid_class_etl` or `stage_brightchamps.paid_class_metrics_etl`) to `brightchamps.teacher_etl` on `teacher_id`. This brings in all four standard teacher dimensions — always output them together:
- `te.teacher_id` — unique teacher identifier.
- `te.teacher_name` — human-readable label instead of raw IDs.
- `te.status AS teacher_status` — whether the teacher is currently active or not.
- `te.type AS teacher_type` — `'full_time'` / `'part_time'` classification.

Additional attributes available on demand from `brightchamps.teacher_etl`:
- `te.joined_at` — date the teacher joined BrightChamps; use for tenure-based analysis (e.g. performance of new vs experienced teachers).
- `te.terminated_at` — date the teacher was deboarded or terminated; NULL means the teacher is still active. Useful for attrition analysis and for filtering to teachers active within a given window.

This join applies universally across every metric in Section 13 whenever a teacher-level cut is requested — add it to the `base` CTE rather than building a separate teacher-specific query pattern each time. Example pattern:
```sql
INNER JOIN brightchamps.teacher_etl te ON pc.class_teacher_id = te.teacher_id
```
(or `pcm.class_teacher_id` if querying off `stage_brightchamps.paid_class_metrics_etl`). `teacher_etl` is confirmed unique on `teacher_id`.

### Completion Definition Caveat (SEA + LingoChamps)
For SEA region and LingoChamps vertical, `paid_class_status_id = 13` ("completed") can be assigned based on teacher join alone — student presence is not required. This applies regardless of OTO/OTM. This means the "completed" population in SEA/LingoChamps is not directly comparable to the rest of the data for any metric that assumes completion implies actual two-sided engagement. Where precision matters, apply the combined **Excl. SEA + LingoChamps** cut (see `early_dropoff`, metric #13). For other completed-only metrics in this section, this is called out as a gotcha rather than a full additional cut — check each metric's gotcha individually.

---

## 1. classes_scheduled or number of classes scheduled

**Definition:** Total volume of paid classes placed on the calendar for a given period, anchored on `class_start_at` (IST). Counts gross scheduling volume regardless of eventual outcome. Status scope: `paid_class_status_id IN (12, 13, 14, 15, 17, 18)`.

**Source table:** `brightchamps.paid_class_etl`.

**Grain:** OTO → `paid_class_id`. OTM Regular/Master Class → `group_class_id`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    pc.paid_class_id,
    pc.group_class_id,
    pc.class_type
  FROM brightchamps.paid_class_etl pc
  WHERE pc.class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND pc.class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND pc.paid_class_status_id IN (12, 13, 14, 15, 17, 18)
    AND pc.course_id != 16
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(DISTINCT COALESCE(group_class_id, paid_class_id)) AS classes_scheduled
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:**
```sql
WITH base AS (
  SELECT
    pc.paid_class_id,
    pc.group_class_id,
    pc.class_type
  FROM brightchamps.paid_class_etl pc
  INNER JOIN brightchamps.student_etl se ON pc.student_id = se.student_id
  WHERE pc.class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND pc.class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND pc.paid_class_status_id IN (12, 13, 14, 15, 17, 18)
    AND pc.course_id != 16
    AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(DISTINCT COALESCE(group_class_id, paid_class_id)) AS classes_scheduled
FROM base
GROUP BY 1
```

**Gotcha:** Anchored on `class_start_at`, not `class_created_date`. Verify `student_etl` is unique on `student_id` before joining. `course_id = 16` excluded. Master Class always its own row. A class with 10 students is still counted once here — this counts classes themselves, not how many students were in them.

**Cross-validate (ECS):** Sum of (OTO + OTM Regular + OTM Master Class) should equal the sum of the per-status breakdown (pending + completed + cancelled-by-parent + cancelled-by-teacher + incomplete + paused) for the same date.

---

## 2. cancellations_by_parent or classes cancelled by parent

**Definition:** Count of classes cancelled by the parent (`paid_class_status_id = 14`), anchored on `class_start_at`.

**Source table:** `brightchamps.paid_class_etl`.

**Grain:** Same as classes_scheduled.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    pc.paid_class_id,
    pc.group_class_id,
    pc.class_type
  FROM brightchamps.paid_class_etl pc
  WHERE pc.class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND pc.class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND pc.paid_class_status_id = 14
    AND pc.course_id != 16
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(DISTINCT COALESCE(group_class_id, paid_class_id)) AS cancellations_by_parent
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:**
```sql
WITH base AS (
  SELECT
    pc.paid_class_id,
    pc.group_class_id,
    pc.class_type
  FROM brightchamps.paid_class_etl pc
  INNER JOIN brightchamps.student_etl se ON pc.student_id = se.student_id
  WHERE pc.class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND pc.class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND pc.paid_class_status_id = 14
    AND pc.course_id != 16
    AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(DISTINCT COALESCE(group_class_id, paid_class_id)) AS cancellations_by_parent
FROM base
GROUP BY 1
```

**Gotcha:** Anchored on `class_start_at`, not `cancelled_at`. Reason-level detail (`cancel_reason`) lives in the metrics table, not here. Since `paid_class_status_id` is uniform per `group_class_id`, this only captures cancellations where the **entire group class** was cancelled — an individual student dropping out of a group class that still proceeded for others won't show here; that surfaces under `student_joined_teacher_no_show` instead. `course_id = 16` excluded. Master Class reported separately. A cancelled class is counted once, no matter how many students were enrolled in it.

**Cross-validate (ECS):** `cancellations_by_parent + cancellations_by_teacher + completed + pending + incomplete + paused` for a date/class_mode should equal `classes_scheduled` for that same date/class_mode.

---

## 3. cancellations_by_teacher or classes cancelled by teacher

**Definition:** Same as cancellations_by_parent, with `paid_class_status_id = 15`.

**Source table:** `brightchamps.paid_class_etl`.

**SQL:** Identical structure to cancellations_by_parent, with `paid_class_status_id = 15` and output column `cancellations_by_teacher`.

**Gotcha:** Same caveats as cancellations_by_parent. Same as above — counted once per class, not per student in it.

**Cross-validate (ECS):** Same combined-status identity as cancellations_by_parent.

---

## 4. incomplete_classes or number of incomplete classes

**Definition:** Count of classes that started but ended in an incomplete state (`paid_class_status_id = 17`), anchored on `class_start_at`.

**Source table:** `brightchamps.paid_class_etl`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    pc.paid_class_id,
    pc.group_class_id,
    pc.class_type
  FROM brightchamps.paid_class_etl pc
  WHERE pc.class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND pc.class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND pc.paid_class_status_id = 17
    AND pc.course_id != 16
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(DISTINCT COALESCE(group_class_id, paid_class_id)) AS incomplete_classes
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:** Same pattern, with the `student_etl` join and region filter added.

**Gotcha:** "Incomplete" (17) is distinct from cancelled (14/15) and paused/no-show (18) — don't merge unless explicitly asked for a combined "non-completed" view. Root-cause detail requires the metrics table's duration/join-time columns. `course_id = 16` excluded. An incomplete class is counted once, regardless of how many students were in it.

**Cross-validate (ECS):** `cancellations_by_parent + cancellations_by_teacher + incomplete_classes + completed + pending + paused` for a date/class_mode should equal `classes_scheduled`.

---

## 5. classes_breakup or breakup of classes / status-wise class breakdown

**Definition:** Cross-tabulated view of class volume by `paid_class_status` × class mode for a given date. Composite report combining classes_scheduled, cancellations, and incomplete_classes into one query. Supports both raw counts and % of each status within its class_mode.

**Source table:** `brightchamps.paid_class_etl`.

**SQL — Overall (counts):**
```sql
WITH base AS (
  SELECT
    pc.paid_class_id,
    pc.group_class_id,
    pc.class_type,
    pc.paid_class_status
  FROM brightchamps.paid_class_etl pc
  WHERE pc.class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND pc.class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND pc.paid_class_status_id IN (12, 13, 14, 15, 17, 18)
    AND pc.course_id != 16
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  paid_class_status,
  COUNT(DISTINCT COALESCE(group_class_id, paid_class_id)) AS class_count
FROM base
GROUP BY 1, 2
ORDER BY 1, 2
```

**SQL — Overall (% of each status, within class_mode):**
```sql
WITH base AS (
  SELECT
    pc.paid_class_id,
    pc.group_class_id,
    pc.class_type,
    pc.paid_class_status
  FROM brightchamps.paid_class_etl pc
  WHERE pc.class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND pc.class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND pc.paid_class_status_id IN (12, 13, 14, 15, 17, 18)
    AND pc.course_id != 16
),
classified AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    paid_class_status,
    COALESCE(group_class_id, paid_class_id) AS class_key
  FROM base
)
SELECT
  class_mode,
  paid_class_status,
  COUNT(DISTINCT class_key) AS class_count,
  ROUND(100.0 * COUNT(DISTINCT class_key) / SUM(COUNT(DISTINCT class_key)) OVER (PARTITION BY class_mode), 2) AS pct_of_class_mode
FROM classified
GROUP BY class_mode, paid_class_status
ORDER BY class_mode, paid_class_status
```

**SQL — Excl. SEA:** Same structure for both versions, with `student_etl` join and region filter added to `base`.

**Gotcha:** This is a routing shortcut, not a new formula — for a single-status ask, point to the individual metric instead. Percentage denominator is within each class_mode, not blended across modes. `course_id = 16` excluded. Master Class always its own row. Every number here is a class count, not a student count — a class with many students still counts once.

**Cross-validate (ECS):** `SUM(class_count)` across all 6 statuses for a class_mode = `classes_scheduled` for that class_mode/date. `SUM(pct_of_class_mode)` within each class_mode = 100% (rounding allowed).

---

## 6. student_joined_teacher_no_show or classes where student joined but teacher didn't or teacher no shows or TNJSJ (Teacher Not Joined, Student Joined)

**Definition:** Row-level count of student-class instances, restricted to incomplete classes (`paid_class_status_id = 17`), where `student_class_join_time IS NOT NULL` but `teacher_class_join_time IS NULL`. Anchored on `class_start_at`.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level — `COUNT(*)`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 17
    AND course_id != 16
    AND student_class_join_time IS NOT NULL
    AND teacher_class_join_time IS NULL
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(*) AS student_joined_teacher_no_show
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:** Same structure, add `AND business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` to `base` (column native to this table).

**Gotcha:** Uses `class_join_time`, not `dashboard_join_time`. Restricted to status 17 only — doesn't capture teacher no-shows resulting in cancellation (14/15) or paused (18). `course_id = 16` excluded. Counted per student — if 5 students were in a group class and the teacher never showed up, that's 5 separate entries here, one for each student affected, not just one for the whole class.

**Cross-validate (ECS):** `student_joined_teacher_no_show ≤ incomplete_classes` for the same date/class_mode (OTO matches 1:1; OTM can exceed the class-level count since multiple students can be affected per group class).

---

## 7. teacher_joined_student_no_show or classes where teacher joined but student didn't or student no shows or TJSNJ (Teacher Joined, Student Not Joined)

**Definition:** Same logic reversed — `teacher_class_join_time IS NOT NULL` and `student_class_join_time IS NULL`, restricted to `paid_class_status_id = 17`.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**SQL:** Identical structure to student_joined_teacher_no_show, with the join condition reversed and output column `teacher_joined_student_no_show`.

**Gotcha:** Same caveats as the reverse metric. For OTM, the teacher is shared across the group — if the whole group no-showed, this returns one row per absent student. Counted per student — if the teacher showed up but several students in a group class didn't, each missing student is counted separately.

**Cross-validate (ECS):** Same subset relationship as the reverse metric.

---

## 8. cancellation_pct_by_parent or parent cancellation %

**Definition:** `cancellations_by_parent / classes_scheduled`, as a %, within each class_mode. Denominator is `classes_scheduled` (all 6 statuses), not completed-only.

**Source table:** `brightchamps.paid_class_etl`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    pc.paid_class_id,
    pc.group_class_id,
    pc.class_type,
    pc.paid_class_status_id
  FROM brightchamps.paid_class_etl pc
  WHERE pc.class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND pc.class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND pc.paid_class_status_id IN (12, 13, 14, 15, 17, 18)
    AND pc.course_id != 16
),
classified AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    COALESCE(group_class_id, paid_class_id) AS class_key,
    paid_class_status_id
  FROM base
)
SELECT
  class_mode,
  COUNT(DISTINCT class_key) AS classes_scheduled,
  COUNT(DISTINCT CASE WHEN paid_class_status_id = 14 THEN class_key END) AS cancellations_by_parent,
  ROUND(100.0 * COUNT(DISTINCT CASE WHEN paid_class_status_id = 14 THEN class_key END)
        / NULLIF(COUNT(DISTINCT class_key), 0), 2) AS cancellation_pct_by_parent
FROM classified
GROUP BY class_mode
```

**SQL — Excl. SEA:** Same structure with `student_etl` join and region filter added to `base`.

**Gotcha:** Denominator must stay at all 6 statuses, not narrowed to completed-only. Computed within each class_mode. `course_id = 16` excluded. This percentage is based on classes, not students — a group class with 10 students that gets cancelled is one cancelled class, not ten.

**Cross-validate (ECS):** `cancellation_pct_by_parent + cancellation_pct_by_teacher + pct of (completed + pending + incomplete + paused)` should sum to 100% within each class_mode.

---

## 9. cancellation_pct_by_teacher or teacher cancellation %

**Definition:** Same as cancellation_pct_by_parent, with `paid_class_status_id = 15`.

**Source table:** `brightchamps.paid_class_etl`.

**SQL:** Identical structure, replacing 14 with 15 and renaming output columns to `cancellations_by_teacher` / `cancellation_pct_by_teacher`.

**Gotcha / Cross-validate:** Same as cancellation_pct_by_parent. Same as above — based on classes, not the number of students in them.

---

## 10. avg_time_to_cancellation_by_parent or average/median time between cancellation and class time (parent)

**Definition:** Average and median gap between `cancelled_at` and `class_start_at`, in hours. Anchored/filtered on `class_start_at`, restricted to `paid_class_status_id = 14`.

**Source table:** `brightchamps.paid_class_etl`.

**Grain:** Dedupe on `group_class_id`/`paid_class_id` before averaging (status, `cancelled_at`, `class_start_at` are uniform across student rows of the same group class — dedup avoids overweighting larger classes).

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    pc.paid_class_id,
    pc.group_class_id,
    pc.class_type,
    pc.class_start_at,
    pc.cancelled_at
  FROM brightchamps.paid_class_etl pc
  WHERE pc.class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND pc.class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND pc.paid_class_status_id = 14
    AND pc.course_id != 16
    AND pc.cancelled_at IS NOT NULL
),
classified AS (
  SELECT DISTINCT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    COALESCE(group_class_id, paid_class_id) AS class_key,
    (EXTRACT(EPOCH FROM (class_start_at - cancelled_at)) / 3600.0)::numeric AS lead_time_hours
  FROM base
)
SELECT
  class_mode,
  COUNT(DISTINCT class_key) AS cancellations_by_parent,
  ROUND(AVG(lead_time_hours), 2) AS avg_lead_time_hrs,
  ROUND((PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY lead_time_hours))::numeric, 2) AS median_lead_time_hrs
FROM classified
GROUP BY class_mode
```

**SQL — Excl. SEA:** Same structure with `student_etl` join and region filter added to `base`.

**Gotcha:** `DISTINCT` in `classified` is essential for OTM. A negative/near-zero lead time signals a data quality edge case. Median is generally more reliable since lead time distributions are typically right-skewed. Postgres casting rule applies (see Section 13 intro). `course_id = 16` excluded. This average is per class, not per student — a group class with several students contributes one lead-time number, not one for each student in it.

**Cross-validate (ECS):** Report `cancellations_by_parent` alongside both averages — a large mean-median gap signals skew. Spot-check rows.

---

## 11. avg_time_to_cancellation_by_teacher or average/median time between cancellation and class time (teacher)

**Definition:** Same as #10, with `paid_class_status_id = 15`.

**Source table:** `brightchamps.paid_class_etl`.

**SQL:** Identical structure to #10, replacing 14 with 15 and renaming outputs to `cancellations_by_teacher`.

**Gotcha / Cross-validate:** Same as #10. Same as above — one number per class, regardless of class size.

---

## 12. on_time_class_start or on-time class start rate

**Definition:** A class-student instance is "on time" if both teacher's and student's `class_join_time` are at or before `class_start_at + 5 minutes`. Early joins always count as on-time. Restricted to completed classes only (`paid_class_status_id = 13`). Reports count and %.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level — `COUNT(*)`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    class_start_at,
    student_class_join_time,
    teacher_class_join_time
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(*) AS completed_instances,
  COUNT(*) FILTER (
    WHERE student_class_join_time IS NOT NULL
      AND teacher_class_join_time IS NOT NULL
      AND student_class_join_time <= class_start_at + INTERVAL '5 minutes'
      AND teacher_class_join_time <= class_start_at + INTERVAL '5 minutes'
  ) AS on_time_count,
  ROUND(
    100.0 * COUNT(*) FILTER (
      WHERE student_class_join_time IS NOT NULL
        AND teacher_class_join_time IS NOT NULL
        AND student_class_join_time <= class_start_at + INTERVAL '5 minutes'
        AND teacher_class_join_time <= class_start_at + INTERVAL '5 minutes'
    ) / NULLIF(COUNT(*), 0)::numeric, 2
  ) AS on_time_pct
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:** Same structure, add region filter (native column, no join needed).

**Gotcha:** Both join times must be non-null to qualify. Restricted to completed only. `course_id = 16` excluded. SEA region and LingoChamps vertical can mark a class 'completed' based on teacher join alone, regardless of student presence — this metric's completed-only population may not be fully comparable across regions/verticals as a result; see Section 13 Completion Definition Caveat. Counted per student — in a group class, each student's own arrival time is checked individually, so one class can produce several entries, one per student.

**Cross-validate (ECS):** `on_time_count ≤ completed_instances` always.

---

## 13. early_dropoff or early drop-off rate

**Definition:** A class-student instance is an "early drop-off" if `common_duration` (seconds) is strictly less than 75% of `class_duration` (minutes, converted to seconds). Restricted to completed classes only. Reports count and %.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level — `COUNT(*)`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    class_duration,
    common_duration
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND class_duration IS NOT NULL
    AND common_duration IS NOT NULL
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(*) AS completed_instances,
  COUNT(*) FILTER (
    WHERE common_duration::numeric / (class_duration * 60) < 0.75
  ) AS early_dropoff_count,
  ROUND(
    100.0 * COUNT(*) FILTER (
      WHERE common_duration::numeric / (class_duration * 60) < 0.75
    ) / NULLIF(COUNT(*), 0)::numeric, 2
  ) AS early_dropoff_pct
FROM base
GROUP BY 1
```

**SQL — Excl. SEA + LingoChamps:** This cut combines region and vertical exclusion, since both populations share the teacher-join-only completion quirk (see Completion Definition Caveat).
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    class_duration,
    common_duration
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND class_duration IS NOT NULL
    AND common_duration IS NOT NULL
    AND business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')
    AND vertical_name != 'LingoChamps'
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(*) AS completed_instances,
  COUNT(*) FILTER (
    WHERE common_duration::numeric / (class_duration * 60) < 0.75
  ) AS early_dropoff_count,
  ROUND(
    100.0 * COUNT(*) FILTER (
      WHERE common_duration::numeric / (class_duration * 60) < 0.75
    ) / NULLIF(COUNT(*), 0)::numeric, 2
  ) AS early_dropoff_pct
FROM base
GROUP BY 1
```

**Gotcha:** Unit mismatch is the critical trap — `class_duration` is minutes, `common_duration` is seconds; always multiply by 60. Both columns must be non-null. Threshold is strictly `< 0.75`. `common_duration` preferred over individual student/teacher durations. This metric uses **Excl. SEA + LingoChamps** instead of the standard Excl. SEA cut, because SEA region and LingoChamps vertical can mark a class 'completed' based on teacher join alone, regardless of student presence — see Section 13 Completion Definition Caveat. Using `vertical_name != 'LingoChamps'` will also silently exclude rows where `vertical_name IS NULL`, since NULL comparisons evaluate to NULL, not TRUE — worth checking NULL volume before trusting this cut. `course_id = 16` excluded. Counted per student — each student's own time in class is measured separately, so a group class can show up multiple times here if several students left early.

**Cross-validate (ECS):** `early_dropoff_count ≤ completed_instances`.

---

## 14. perfect_class_pct or perfect class %

**Definition:** % of completed instances flagged `perfect_class = TRUE`. Can vary per student within the same `group_class_id` — row-level grain, no dedupe for OTM.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    perfect_class
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(*) AS completed_instances,
  COUNT(*) FILTER (WHERE perfect_class = TRUE) AS perfect_class_count,
  ROUND(100.0 * COUNT(*) FILTER (WHERE perfect_class = TRUE) / NULLIF(COUNT(*), 0)::numeric, 2) AS perfect_class_pct
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:** Same structure, add region filter.

**Gotcha:** Don't dedupe to class-level for OTM — `perfect_class` can legitimately vary per student. Treat `NULL` as excluded from both numerator and denominator, not as `FALSE`. `course_id = 16` excluded. Counted per student — a "perfect class" mark is given to each student individually, so in a group class some students can be marked perfect while others aren't, for the same session.

**Cross-validate (ECS):** `perfect_class_count ≤ completed_instances`.

---

## 15. avg_pqs_score and pqs_bucket_pct or average PQS score and PQS bucket breakdown

**Definition:** Average `teacher_pqs_score` and % distribution across buckets (Bad: 0–5, OK: 6–8, Good: ≥9). **OTO only — PQS is not calculated for group classes.** Restricted to completed classes only. `NULL` scores reported as a separate "No PQS Data" bucket in the distribution, but excluded from the overall average's denominator.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level, OTO only (`group_class_id IS NULL`). No class_mode breakdown.

**SQL — Bucket distribution:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    teacher_pqs_score
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND group_class_id IS NULL
),
bucketed AS (
  SELECT
    CASE
      WHEN teacher_pqs_score IS NULL THEN 'No PQS Data'
      WHEN teacher_pqs_score BETWEEN 0 AND 5 THEN 'Bad'
      WHEN teacher_pqs_score BETWEEN 6 AND 8 THEN 'OK'
      WHEN teacher_pqs_score >= 9 THEN 'Good'
    END AS pqs_bucket,
    teacher_pqs_score
  FROM base
)
SELECT
  pqs_bucket,
  COUNT(*) AS instance_count,
  ROUND(100.0 * COUNT(*) / NULLIF((SELECT COUNT(*) FROM bucketed), 0)::numeric, 2) AS pqs_bucket_pct,
  ROUND(AVG(teacher_pqs_score), 2) AS avg_pqs_score_in_bucket
FROM bucketed
GROUP BY pqs_bucket
ORDER BY pqs_bucket
```

**SQL — Overall average:**
```sql
SELECT
  ROUND(AVG(teacher_pqs_score), 2) AS avg_pqs_score,
  COUNT(*) AS scored_instances
FROM stage_brightchamps.paid_class_metrics_etl
WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
  AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
  AND paid_class_status_id = 13
  AND course_id != 16
  AND group_class_id IS NULL
  AND teacher_pqs_score IS NOT NULL
```

**SQL — Excl. SEA:** Same structure for both, add region filter.

**Gotcha:** No class_mode breakdown — OTO-only by definition. `avg_pqs_score` excludes "No PQS Data" from its denominator; the bucket % distribution includes it as its own bucket. `teacher_pqs_score`, `ptm_qs`, and `parent_joined_ptm` can be populated for incomplete (17) classes too, but these metrics deliberately restrict to completed-only (13) for comparability — don't silently expand scope if asked for an "all attempted" view. `course_id = 16` excluded. This only applies to one-on-one classes — group classes aren't scored this way, so there's no group-class number to compare here at all.

**Cross-validate (ECS):** `SUM(instance_count)` across Bad + OK + Good + No PQS Data = total completed OTO instances. `scored_instances` = Bad + OK + Good combined.

---

## 16. avg_ptm_qs and ptm_qs_bucket_pct or average PTM-QS and PTM-QS bucket breakdown

**Definition:** Average `ptm_qs` and % distribution across buckets (Bad: 0–9, OK: 10–21, Good: ≥22). **OTO only.** Restricted to completed classes only. Wherever `ptm_qs` is calculated, these are URI PTMs (regular classes where parent and RM join to pitch). Unlike PQS, `NULL` `ptm_qs` is excluded entirely (no separate bucket).

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level, OTO only. No class_mode breakdown.

**SQL — Bucket distribution:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    ptm_qs
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND group_class_id IS NULL
    AND ptm_qs IS NOT NULL
),
bucketed AS (
  SELECT
    CASE
      WHEN ptm_qs BETWEEN 0 AND 9 THEN 'Bad'
      WHEN ptm_qs BETWEEN 10 AND 21 THEN 'OK'
      WHEN ptm_qs >= 22 THEN 'Good'
    END AS ptm_qs_bucket,
    ptm_qs
  FROM base
)
SELECT
  ptm_qs_bucket,
  COUNT(*) AS instance_count,
  ROUND(100.0 * COUNT(*) / NULLIF((SELECT COUNT(*) FROM bucketed), 0)::numeric, 2) AS ptm_qs_bucket_pct,
  ROUND(AVG(ptm_qs), 2) AS avg_ptm_qs_in_bucket
FROM bucketed
GROUP BY ptm_qs_bucket
ORDER BY ptm_qs_bucket
```

**SQL — Overall average:**
```sql
SELECT
  ROUND(AVG(ptm_qs), 2) AS avg_ptm_qs,
  COUNT(*) AS scored_instances
FROM stage_brightchamps.paid_class_metrics_etl
WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
  AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
  AND paid_class_status_id = 13
  AND course_id != 16
  AND group_class_id IS NULL
  AND ptm_qs IS NOT NULL
```

**SQL — Excl. SEA:** Same structure for both, add region filter.

**Gotcha:** No class_mode breakdown — OTO-only. `NULL` `ptm_qs` excluded entirely, unlike PQS's "No Data" bucket — `scored_instances` and `SUM(instance_count)` should match exactly. Don't confuse with `parent_joined_ptm` (attendance flag, not quality score). Restricted to completed-only by design (see PQS gotcha re: incomplete classes). `course_id = 16` excluded. Same as above — this only applies to one-on-one classes, group classes aren't included.

**Cross-validate (ECS):** `SUM(instance_count)` across Bad + OK + Good = `scored_instances`.

---

## 17. parent_ptm_join_pct or % of PTMs where parent joined

**Definition:** Distribution of `parent_joined_ptm` across three states — Joined (1), Not Joined (0), Could Not Determine (-1) — out of all PTM instances identified by `ptm_qs IS NOT NULL` (proxy denominator, since PTM scheduling can't be independently determined). **OTO only.** Restricted to completed classes only.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level, OTO only.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    parent_joined_ptm
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND group_class_id IS NULL
    AND ptm_qs IS NOT NULL
),
bucketed AS (
  SELECT
    CASE
      WHEN parent_joined_ptm = 1 THEN 'Joined'
      WHEN parent_joined_ptm = 0 THEN 'Not Joined'
      WHEN parent_joined_ptm = -1 THEN 'Could Not Determine'
    END AS join_status
  FROM base
)
SELECT
  join_status,
  COUNT(*) AS instance_count,
  ROUND(100.0 * COUNT(*) / NULLIF((SELECT COUNT(*) FROM bucketed), 0)::numeric, 2) AS pct_of_ptm_instances
FROM bucketed
GROUP BY join_status
ORDER BY join_status
```

**SQL — Excl. SEA:** Same structure, add region filter.

**Gotcha:** `parent_joined_ptm` is an integer (-1/0/1), not boolean — never use `= TRUE`. `ptm_qs IS NOT NULL` is a proxy denominator, not a guaranteed PTM-scheduled flag. The denominator isn't shown directly in this output — cross-reference `scored_instances` from the avg_ptm_qs query if needed. "Could Not Determine" % is a data quality signal worth watching. No class_mode breakdown — OTO-only. `course_id = 16` excluded. Same as above — one-on-one classes only.

**Cross-validate (ECS):** `SUM(instance_count)` across all three states = `scored_instances` from the avg_ptm_qs query (same denominator).

---

## 18. on_time_teacher_join and late_teacher_join or teacher punctuality breakdown

**Definition:** Each completed class instance bucketed into **On Time** (joined at/before `class_start_at`, or within a 5-minute buffer if `teacher_consecutive_class = 1`), **Late** (joined after the allowed threshold), or **Did Not Join** (`teacher_class_join_time IS NULL`). `teacher_consecutive_class = NULL` is treated the same as `0` (no buffer). Class-level grain (deduped to `group_class_id` for OTM) — teacher behavior is shared across all students in a group class.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    class_start_at,
    teacher_class_join_time,
    teacher_consecutive_class
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
),
classified AS (
  SELECT DISTINCT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    COALESCE(group_class_id, paid_class_id) AS class_key,
    class_start_at,
    teacher_class_join_time,
    teacher_consecutive_class
  FROM base
),
bucketed AS (
  SELECT
    class_mode,
    class_key,
    CASE
      WHEN teacher_class_join_time IS NULL THEN 'Did Not Join'
      WHEN teacher_class_join_time <= class_start_at + (CASE WHEN teacher_consecutive_class = 1 THEN INTERVAL '5 minutes' ELSE INTERVAL '0 minutes' END) THEN 'On Time'
      ELSE 'Late'
    END AS join_status
  FROM classified
)
SELECT
  class_mode,
  join_status,
  COUNT(*) AS class_count,
  ROUND(100.0 * COUNT(*) / SUM(COUNT(*)) OVER (PARTITION BY class_mode), 2) AS pct_of_class_mode
FROM bucketed
GROUP BY class_mode, join_status
ORDER BY class_mode, join_status
```

**SQL — Excl. SEA:** Same structure, add region filter to `base`.

**Gotcha:** "Did Not Join" on a completed class is an edge case worth investigating if it appears with meaningful frequency. `teacher_consecutive_class = NULL` treated as `0` (no buffer). `DISTINCT` in `classified` is essential for OTM. `course_id = 16` excluded. This looks only at the teacher, so a group class is counted once no matter how many students were in it — the teacher was either on time or not, for the class as a whole.

**Cross-validate (ECS):** `SUM(class_count)` across On Time + Late + Did Not Join for a class_mode = deduped completed class count for that class_mode/date. `SUM(pct_of_class_mode)` = 100%.

---

## 19. avg_student_feedback_rating and feedback_rating_bucket_pct or average student feedback and % by star rating

**Definition:** Average `student_class_rating` and % distribution across rating values 1–5. Restricted to completed classes only. `NULL` ratings (no feedback submitted) excluded entirely from both. Row-level grain — feedback is individual per student, no class-level dedupe even for OTM.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**SQL — Bucket % by rating:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    student_class_rating
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND student_class_rating IS NOT NULL
),
classified AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    student_class_rating
  FROM base
)
SELECT
  class_mode,
  student_class_rating,
  COUNT(*) AS rating_count,
  ROUND(100.0 * COUNT(*) / SUM(COUNT(*)) OVER (PARTITION BY class_mode), 2) AS pct_of_class_mode
FROM classified
GROUP BY class_mode, student_class_rating
ORDER BY class_mode, student_class_rating
```

**SQL — Average rating:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    student_class_rating
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND student_class_rating IS NOT NULL
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(*) AS rated_instances,
  ROUND(AVG(student_class_rating), 2) AS avg_student_feedback_rating
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:** Same structure for both, add region filter.

**Gotcha:** `student_class_rating` is known to be sparse — always check `rated_instances` before trusting the average/%. `NULL` ratings excluded entirely (differs from PQS's "No Data" bucket pattern). `course_id = 16` excluded. Counted per student — each student gives their own rating, so a group class can have several ratings attached to it, one per student who responded.

**Cross-validate (ECS):** `SUM(rating_count)` across 1–5 within a class_mode = `rated_instances` for that class_mode/date. `SUM(pct_of_class_mode)` = 100%.

---

## 20. feedback_submit_lag or time between class end and feedback submission

**Definition:** Average and median gap between scheduled class end (`class_start_at + class_duration` minutes) and `student_feedback_date`, in hours. Feedback is optional — only non-null `student_feedback_date` rows included. Restricted to completed classes only. Row-level grain.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    class_start_at,
    class_duration,
    student_feedback_date
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND student_feedback_date IS NOT NULL
),
classified AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    (EXTRACT(EPOCH FROM (student_feedback_date - (class_start_at + (class_duration || ' minutes')::interval))) / 3600.0)::numeric AS feedback_lag_hours
  FROM base
)
SELECT
  class_mode,
  COUNT(*) AS feedback_instances,
  ROUND(AVG(feedback_lag_hours), 2) AS avg_feedback_lag_hrs,
  ROUND((PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY feedback_lag_hours))::numeric, 2) AS median_feedback_lag_hrs
FROM classified
GROUP BY class_mode
```

**SQL — Excl. SEA:** Same structure, add region filter.

**Gotcha:** Class end is the *scheduled* end, not actual end based on left-times. `class_duration` is minutes — cast via `(class_duration || ' minutes')::interval`. Postgres casting rule applies for both `EXTRACT(EPOCH ...)` and `PERCENTILE_CONT(...)`. Negative lag = data quality flag. `student_class_rating` sparsity applies here too. `course_id = 16` excluded. Counted per student — each student's feedback timing is their own, so a group class can contribute multiple timing entries, one per student who left feedback.

**Cross-validate (ECS):** `feedback_instances ≤` count of completed instances with non-null `student_class_rating`. Spot-check row-level gaps.

---

## 21. assignment_completion_pct or % assignment completion

**Definition:** Average of per-row `(assignment_done / assignment_exists)`, as a %. `assignment_exists`/`assignment_done` are **integer counts** (more than one assignment can be given per instance), not booleans. Computed only where `assignment_exists > 0`. Restricted to completed classes only. Row-level grain.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    (assignment_done::numeric / assignment_exists) * 100 AS completion_pct_row
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND assignment_exists > 0
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(*) AS assignment_given_count,
  ROUND(AVG(completion_pct_row), 2) AS assignment_completion_pct
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:** Same structure, add region filter.

**Gotcha:** `assignment_done > assignment_exists` per row is a data anomaly to flag, not cap silently. This averages per-row ratios, not a quantity-weighted pooled ratio — a row with 1-of-1 done counts equally to a row with 5-of-5 done. `assignment_exists > 0` is the row-inclusion filter (not a boolean check). `course_id = 16` excluded. Counted per student — each student's assignment progress is tracked on its own, so a group class can contribute several entries, one per student.

**Cross-validate (ECS):** `assignment_completion_pct` should fall within 0–100%; values above 100% signal a data anomaly to investigate.

---

## 22. assignment_avg_score_pct or average assignment score %

**Definition:** Average of per-row `(assignment_obtained_score / assignment_total_score) × 100`, computed only where `assignment_done > 0` and `assignment_total_score > 0`. Average of individual percentages, not a pooled sum-based ratio.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    (assignment_obtained_score::numeric / NULLIF(assignment_total_score, 0)) * 100 AS score_pct
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND assignment_done > 0
    AND assignment_total_score > 0
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(*) AS scored_instances,
  ROUND(AVG(score_pct), 2) AS assignment_avg_score_pct
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:** Same structure, add region filter.

**Gotcha:** `NULLIF` guards against divide-by-zero. `assignment_done > 0` replaces a boolean check, consistent with assignment_completion_pct. Score columns are assumed to be row-level aggregates summed across however many assignments existed — verify against ETL logic if accuracy is questioned. `course_id = 16` excluded. Counted per student — each student's score is their own, so a group class can have multiple scores attached to it, one per student.

**Cross-validate (ECS):** `scored_instances ≤ assignment_given_count` from the completion metric for the same date/class_mode.

---

## 23. quiz_completion_pct or % quiz completion

**Definition:** Identical to assignment_completion_pct, using `quiz_done` / `quiz_exists` in place of `assignment_done` / `assignment_exists`. Same integer-count behavior.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    (quiz_done::numeric / quiz_exists) * 100 AS completion_pct_row
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND quiz_exists > 0
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(*) AS quiz_given_count,
  ROUND(AVG(completion_pct_row), 2) AS quiz_completion_pct
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:** Same structure, add region filter.

**Gotcha:** Same caveats as assignment_completion_pct — average of per-row ratios, `quiz_done > quiz_exists` is a data anomaly to flag. `quiz_exists > 0` is the row-inclusion filter. `course_id = 16` excluded. Counted per student — same as assignments, each student's quiz progress is tracked individually within a group class.

**Cross-validate (ECS):** Same 0–100% sanity check as assignment_completion_pct.

---

## 24. quiz_avg_score_pct or average quiz score %

**Definition:** Identical to assignment_avg_score_pct, using `quiz_obtained_score` / `quiz_total_score` and `quiz_done > 0`.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    (quiz_obtained_score::numeric / NULLIF(quiz_total_score, 0)) * 100 AS score_pct
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND quiz_done > 0
    AND quiz_total_score > 0
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(*) AS scored_instances,
  ROUND(AVG(score_pct), 2) AS quiz_avg_score_pct
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:** Same structure, add region filter.

**Gotcha:** Same caveats as assignment_avg_score_pct. `course_id = 16` excluded. Counted per student — each student's quiz score is their own, so a group class can have multiple scores attached, one per student.

**Cross-validate (ECS):** `scored_instances ≤ quiz_given_count` from the completion metric for the same date/class_mode.

---

*End of Section 13. RM-related metrics remain deferred per prior scope decision. `is_same_ip` flagged as a potential future metric but not yet built — revisit when ready.*
