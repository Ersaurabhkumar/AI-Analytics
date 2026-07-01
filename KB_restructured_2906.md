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
| completed classes / how many classes were completed | Section 13 (completed_classes) |
| breakup of classes / status-wise classes / class status distribution / % of each status | Section 13 — Dimensions (class_status) |
| cancelled by parent / parent cancellation / parent cancellation % | Section 13 (cancellations_by_parent, cancellation_pct_by_parent) |
| cancelled by teacher / teacher cancellation / teacher cancellation % | Section 13 (cancellations_by_teacher, cancellation_pct_by_teacher) |
| time to parent cancellation / how much notice parent gave before cancelling / cancellation lead time parent | Section 13 (time_to_parent_cancellation) |
| time to teacher cancellation / how much notice teacher gave before cancelling / cancellation lead time teacher | Section 13 (time_to_teacher_cancellation) |
| incomplete classes / classes that didn't finish | Section 13 (incomplete_classes) |
| on time class start / punctuality / both joined on time | Section 13 (on_time_class_start) |
| on time teacher join / teacher punctuality / late teacher / teacher late joining | Section 13 (on_time_teacher_join) |
| early drop off / dropped out early / left before class finished | Section 13 (early_dropoff) |
| perfect class / perfect class % | Section 13 (perfect_class_pct) |
| PQS / teacher PQS score / average PQS | Section 13 (avg_pqs_score) |
| % good PQS / good PQS rate | Section 13 (pct_good_pqs) |
| PQS buckets / PQS distribution / Bad OK Good PQS | Section 13 — Dimensions (pqs_bucket) |
| PTM-QS / PTM quality score / average PTM-QS | Section 13 (avg_ptm_qs) |
| % good PTM-QS / good PTM-QS rate | Section 13 (pct_good_ptm_qs) |
| PTM-QS buckets / PTM-QS distribution | Section 13 — Dimensions (ptm_qs_bucket) |
| parent joined PTM / % parent attendance PTM / parent PTM join rate | Section 13 (parent_ptm_join_pct) |
| student feedback rating / average rating | Section 13 (avg_student_feedback_rating) |
| 5 star feedback / % 5 star rating | Section 13 (pct_5_star_feedback) |
| low rating / 1 and 2 star feedback / negative feedback % | Section 13 (pct_low_star_feedback) |
| time to submit feedback / feedback submission lag / how long to submit feedback | Section 13 (time_to_submit_feedback) |
| assignment completion / % assignment done | Section 13 (assignment_completion_pct) |
| assignment score / average assignment score % | Section 13 (assignment_avg_score_pct) |
| assignment grade / assignment score distribution / assignment score bands | Section 13 (assignment_grade_pct) |
| quiz completion / % quiz done | Section 13 (quiz_completion_pct) |
| quiz score / average quiz score % | Section 13 (quiz_avg_score_pct) |
| quiz grade / quiz score distribution / quiz score bands | Section 13 (quiz_grade_pct) |
| teacher no show / teacher didn't join / teacher absent | Section 13 (teacher_no_show_pct) |
| student no show / student didn't join / student absent | Section 13 (student_no_show_pct) |
| joining behavior / teacher joined student joined / TJSJ TNJSJ TJSNJ TNJSNJ / both joined / neither joined | Section 13 — Joining Behavior Breakdown (TJSJ_pct, TNJSJ_pct, TJSNJ_pct, TNJSNJ_pct) |
| OTO vs OTM vs Master Class for paid classes | Section 13 — Business Context (Class Mode Classification) |
| calls made / total calls / call volume by vendor | Section 14 — RIGOUR METRICS (#1) |
| unique parents touched / unique reach / unique calls by vendor (DISTINCT parent_id) | Section 14 — RIGOUR METRICS (#2) |
| connectivity / connectivity % / connected calls / picked + not picked / connectivity by region | Section 14 — RIGOUR METRICS (#3) |
| pickup rate / picked out of connected | Section 14 — RIGOUR METRICS (#4) |
| pickup rate on dialled / picked out of dialled | Section 14 — RIGOUR METRICS (#5) |
| total duration / call duration by date week month vendor | Section 14 — RIGOUR METRICS (#6) |
| talk time / talk duration by date week month vendor | Section 14 — RIGOUR METRICS (#7) |
| avg calls per SM per day | Section 14 — RIGOUR METRICS (#8) |
| avg unique parents touched connected picked per SM per day / avg unique reach per SM | Section 14 — RIGOUR METRICS (#9) |
| avg total duration per SM per day / avg duration per SM / avg talk time per SM per day | Section 14 — RIGOUR METRICS (#10) |
| list of active SM by region | Section 14 — RIGOUR METRICS (#11) |
| SMs not touching 25 unique parents / low reach SM / below picked-parent target | Section 14 — RIGOUR METRICS (#12) |
| SMs with less than 60 mins call time / low duration SM / below duration floor | Section 14 — RIGOUR METRICS (#13) |
| underperforming SM / SM missing rigour targets / shortfall list | Section 14 — RIGOUR METRICS (#14) |
| weekly calls / week level metrics / calls per week / avg calls per SM per day over a week | Section 14 — RIGOUR METRICS (14.E) |
| monthly rollup / month level rigour / avg per SM per day over a month | Section 14 — RIGOUR METRICS (14.E) |
| weekly by manager / weekly by business leader / week × team manager rollup | Section 14 — RIGOUR METRICS (14.E) |
| rigour / agent dialling / dialling discipline / total agents on-off weekoff | Section 14 — RIGOUR METRICS |
| teacher performance / teacher scorecard / teacher assessment / how is teacher performing / paid class teacher metrics | Section 13 — Teacher Performance Framework |

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
| unified_call_etl | `stage_brightchamps.unified_call_etl` | Call (one row per `reference_key`) | Section 14 call log: counts, `call_duration` (talk time), `total_duration_seconds`, `call_status_category` (Picked/Not Picked/Failed), `vendor`, `vendor_category` (`Dialler`/`Manual-Call`/`AI-Call`), `parent_id` (unique-call key). `start_time`/`end_time` UTC | `agent_email` NULL for Knowlarity/AI calls (excluded from SM-scoped joins) |
| neo_lead_eligibility_etl | `stage_brightchamps.neo_lead_eligibility_etl` | SM-day | Section 14 roster: active, week_off, regions, role, manager, business_leader | `ROLE = 'Hunter'`, `regions NOT ILIKE '%SEA%'`, `regions NOT ILIKE '%Vietnam%'` |
| zoho_employees | `prashashak.zoho_employees` | Employee | Section 14 exit-date override | Email normalised: `split_part(email,'@',1) || '@team.brightchamps.com'` |

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

**Source Tables**

| Table | Use for |
|---|---|
| `stage_brightchamps.marketing_campaign_etl` | **Spend data** — ad spend at campaign, adset, and ad-name level (`total_spend_inr`, `campaign_name`, `adset_name`, `ad_name`, `campaign_origin`, `campaign_source`). This is the only table that holds spend figures. Used as the numerator source for CPL, CPD, ROAS, ROAS-6M, CAC, LTV/CAC. |
| `stage_brightchamps.booking_etl` | **Bookings & funnel data** — demo bookings, demo completions, conversions, and collection amounts (`student_id`, `vertical_name`, `demo_completed`, `first_collection_amount_inr`, `net_collection_amount_first_6m`, `conversion_flag`, `parent_type`, `attr_utm_campaign`). Used as the denominator source for CPL/CPD and the revenue source for ROAS/LTV. CPL denominator is `COUNT(DISTINCT student_id\|\|vertical_name)` — **do NOT use `lead_etl` or `COUNT(DISTINCT lead_id)`**. |

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
| `brightchamps.paid_class_etl` | Schedule/status-level metrics: classes_scheduled, completed_classes, cancellations, incomplete_classes, cancellation lead time. No `business_region_name` column — join to `brightchamps.student_etl` on `student_id` for regional cuts. `vertical_name` is native, no join needed. **`paid_class_status_id = 16` (soft delete) exists in this table and must be explicitly excluded.** |
| `stage_brightchamps.paid_class_metrics_etl` | Teacher/student/engagement-level metrics: join behavior, duration, quality scores, feedback, assignments, quizzes, PTM. `vertical_name` is native — no join needed. **`business_region_name` is unreliable in this table — always join `brightchamps.student_etl se ON pcm.student_id = se.student_id` and use `se.business_region_name` for regional cuts.** `student_id` is confirmed always populated. **`paid_class_status_id = 16` does not exist in this table.** |

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

Most engagement/quality metrics (PQS, PTM-QS, feedback, assignments, quizzes) default to **completed only (13)**. Join behavior metrics (teacher_no_show_pct, student_no_show_pct, Joining Behavior Breakdown, on_time_teacher_join, early_dropoff) use **attempted (13+17)** as their scope. Schedule-level metrics (classes_scheduled, cancellations) span multiple statuses by design — check each entry's status scope individually.

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

### Metrics Definition Table

| # | Metric Name | Source Table | Status Filter | OTO/OTM Scope | Grain | One-line Definition |
|---|---|---|---|---|---|---|
| 1 | classes_scheduled | paid_class_etl | 12,13,14,15,17,18 | OTO + OTM Regular + OTM Master | Teacher-level | Total number of classes placed on the calendar for the day, across all outcomes |
| 2 | completed_classes | paid_class_etl | 13 | OTO + OTM Regular + OTM Master | Teacher-level | Total number of classes that reached a completed status on the day |
| 3 | cancellations_by_parent | paid_class_etl | 14 | OTO + OTM Regular + OTM Master | Teacher-level | Number of classes cancelled by the parent or family |
| 4 | cancellations_by_teacher | paid_class_etl | 15 | OTO + OTM Regular + OTM Master | Teacher-level | Number of classes cancelled by the teacher |
| 5 | incomplete_classes | paid_class_etl | 17 | OTO + OTM Regular + OTM Master | Teacher-level | Number of classes that started but did not reach a completed or cancelled outcome |
| 6 | cancellation_pct_by_parent | paid_class_etl | 12,13,14,15,17,18 | OTO + OTM Regular + OTM Master | Teacher-level | Parent cancellations as a % of total scheduled classes for the day |
| 7 | cancellation_pct_by_teacher | paid_class_etl | 12,13,14,15,17,18 | OTO + OTM Regular + OTM Master | Teacher-level | Teacher cancellations as a % of total scheduled classes for the day |
| 8 | time_to_parent_cancellation | paid_class_etl | 14 | OTO + OTM Regular + OTM Master | Teacher-level | Avg and median hours between when the parent cancelled and when the class was scheduled to start |
| 9 | time_to_teacher_cancellation | paid_class_etl | 15 | OTO + OTM Regular + OTM Master | Teacher-level | Avg and median hours between when the teacher cancelled and when the class was scheduled to start |
| 10 | on_time_class_start | paid_class_metrics_etl | 13 | OTO + OTM Regular + OTM Master | Student-level | Number and % of completed instances where both teacher and student joined within 5 minutes of scheduled start |
| 11 | early_dropoff | paid_class_metrics_etl | 13+17 (TJSJ scope) | OTO + OTM Regular + OTM Master | Student-level | Number and % of instances (where both parties joined) where time together was less than 75% of scheduled class duration |
| 12 | perfect_class_pct | paid_class_metrics_etl | 13 | OTO + OTM Regular + OTM Master | Student-level | % of completed instances marked as a perfect class (teacher on time + 75% duration met + quiz done); lagging — quiz completion takes ~7 days |
| 13 | avg_pqs_score | paid_class_metrics_etl | 13 | OTO only | Student-level | Average teacher PQS score across completed OTO classes where a score was recorded |
| 14 | avg_ptm_qs | paid_class_metrics_etl | 13 | OTO only | Student-level | Average PTM quality score across completed OTO classes where a PTM was conducted |
| 15 | parent_ptm_join_pct | paid_class_metrics_etl | 13 | OTO only | Student-level | % split of parent PTM attendance into: Joined / Not Joined / Could Not Determine |
| 16 | on_time_teacher_join | paid_class_metrics_etl | 13+17 (teacher joined) | OTO + OTM Regular + OTM Master | Teacher-level | % split of attempted classes (where teacher joined) into On Time vs Late |
| 17 | avg_student_feedback_rating | paid_class_metrics_etl | 13 | OTO + OTM Regular + OTM Master | Student-level | Average star rating (1–5) given by students after a completed class; only rated instances included |
| 18 | time_to_submit_feedback | paid_class_metrics_etl | 13 | OTO + OTM Regular + OTM Master | Student-level | Avg and median hours between scheduled class end and when the student submitted feedback |
| 19 | assignment_completion_pct | paid_class_metrics_etl | 13 | OTO + OTM Regular + OTM Master | Student-level | Total assignments completed as a % of total assignments given, across all completed class instances |
| 20 | assignment_avg_score_pct | paid_class_metrics_etl | 13 | OTO + OTM Regular + OTM Master | Student-level | Average score obtained as a % of total marks, for students who completed their assignments |
| 21 | quiz_completion_pct | paid_class_metrics_etl | 13 | OTO + OTM Regular + OTM Master | Student-level | Total quizzes completed as a % of total quizzes given, across all completed class instances |
| 22 | quiz_avg_score_pct | paid_class_metrics_etl | 13 | OTO + OTM Regular + OTM Master | Student-level | Average score obtained as a % of total marks, for students who attempted their quizzes |
| 23 | teacher_no_show_pct | paid_class_metrics_etl | 13+17 | OTO + OTM Regular + OTM Master | Teacher-level | % of attempted classes where the teacher never entered the live session; OTM counted once per class |
| 24 | student_no_show_pct | paid_class_metrics_etl | 13+17 | OTO + OTM Regular + OTM Master | Student-level | % of attempted instances where the student never entered the live session; each student counted separately |
| 25 | TJSJ_pct | paid_class_metrics_etl | 13+17 | OTO + OTM Regular + OTM Master | Student-level | % of attempted instances where both teacher and student entered the live session |
| 26 | TNJSJ_pct | paid_class_metrics_etl | 13+17 | OTO + OTM Regular + OTM Master | Student-level | % of attempted instances where the student joined but the teacher did not |
| 27 | TJSNJ_pct | paid_class_metrics_etl | 13+17 | OTO + OTM Regular + OTM Master | Student-level | % of attempted instances where the teacher joined but the student did not |
| 28 | TNJSNJ_pct | paid_class_metrics_etl | 13+17 | OTO + OTM Regular + OTM Master | Student-level | % of attempted instances where neither teacher nor student entered the live session |
| 29 | pct_good_pqs | paid_class_metrics_etl | 13 | OTO only | Student-level | % of scored OTO instances where the teacher's PQS score falls in the Good band (≥ 9) |
| 30 | pct_good_ptm_qs | paid_class_metrics_etl | 13 | OTO only | Student-level | % of PTM-scored OTO instances where the PTM-QS score falls in the Good band (≥ 22) |
| 31 | pct_5_star_feedback | paid_class_metrics_etl | 13 | OTO + OTM Regular + OTM Master | Student-level | % of rated instances where the student gave a 5-star rating |
| 32 | pct_low_star_feedback | paid_class_metrics_etl | 13 | OTO + OTM Regular + OTM Master | Student-level | % of rated instances where the student gave a 1 or 2-star rating |
| 33 | assignment_grade_pct | paid_class_metrics_etl | 13 | OTO + OTM Regular + OTM Master | Student-level | % distribution of completed assignments across score bands — High (≥75%), Medium (50–74%), Low (30–49%), At Risk (<30%) |
| 34 | quiz_grade_pct | paid_class_metrics_etl | 13 | OTO + OTM Regular + OTM Master | Student-level | % distribution of completed quizzes across score bands — High (≥75%), Medium (50–74%), Low (30–49%), At Risk (<30%) |

### Dimensions Table

Dimensions are breakdowns that slice metrics — they are not standalone metrics themselves. Use these when a metric result needs to be viewed by a category.

| Dimension Name | Source | Values / Buckets | Typically slices... |
|---|---|---|---|
| class_status | `paid_class_etl.paid_class_status` / `paid_class_status_id` | Pending (12), Completed (13), Cancelled by Parent (14), Cancelled by Teacher (15), Incomplete (17), Paused/No-show (18) | classes_scheduled and any schedule-level metric |
| class_mode | Derived from `group_class_id` + `class_type` | OTO, OTM - Regular, OTM - Master Class | All metrics in Section 13 |
| pqs_bucket | Derived from `teacher_pqs_score` | Bad (0–5), OK (6–8), Good (≥9), No PQS Data (NULL) | avg_pqs_score |
| ptm_qs_bucket | Derived from `ptm_qs` | Bad (0–9), OK (10–21), Good (≥22) | avg_ptm_qs |
| assignment_grade_bucket | Derived from `(assignment_obtained_score / assignment_total_score) × 100` | High (≥75%), Medium (50–74.99%), Low (30–49.99%), At Risk (<30%) | assignment_grade_pct |
| quiz_grade_bucket | Derived from `(quiz_obtained_score / quiz_total_score) × 100` | High (≥75%), Medium (50–74.99%), Low (30–49.99%), At Risk (<30%) | quiz_grade_pct |
| business_region | `brightchamps.student_etl.business_region_name` | All regions; standard cut excludes SEA / Indonesia / Vietnam | All metrics in Section 13 |
| vertical | `vertical_name` (native on both source tables) | All verticals; LingoChamps excluded alongside SEA for early_dropoff | All metrics in Section 13 |

---

### Grain Disclosure Rule
Whenever results for any metric in this section are calculated and shared with the user, the metric's plain-language grain one-liner (found in that metric's Gotcha section) must be included alongside the numbers — not just buried in documentation. This keeps it clear to a non-technical reader what's actually being counted (e.g., whether a group class with 10 students contributes one entry or ten). Quick reference for all 34 metrics:

| Metric | Grain one-liner |
|---|---|
| classes_scheduled | A class with 10 students is still counted once — this counts classes themselves, not how many students were in them. |
| completed_classes | Same as classes_scheduled — a completed group class with 10 students is counted once, not once per student. |
| cancellations_by_parent | A cancelled class is counted once, no matter how many students were enrolled in it. |
| cancellations_by_teacher | Same as above — counted once per class, not per student in it. |
| incomplete_classes | An incomplete class is counted once, regardless of how many students were in it. |
| cancellation_pct_by_parent | This percentage is based on classes, not students — a group class with 10 students that gets cancelled is one cancelled class, not ten. |
| cancellation_pct_by_teacher | Same as above — based on classes, not the number of students in them. |
| time_to_parent_cancellation | This average is per class, not per student — a group class with several students contributes one lead-time number, not one for each student in it. |
| time_to_teacher_cancellation | Same as above — one number per class, regardless of class size. |
| on_time_class_start | Counted per student — in a group class, each student's own arrival time is checked individually, so one class can produce several entries, one per student. |
| early_dropoff | Counted per student — each student's own time in class is measured separately; denominator is instances where both teacher and student joined. |
| perfect_class_pct | Counted per student — a "perfect class" mark is given to each student individually, so in a group class some students can be marked perfect while others aren't, for the same session. |
| avg_pqs_score | This only applies to one-on-one classes — group classes aren't scored this way, so there's no group-class number to compare here at all. |
| avg_ptm_qs | Same as above — this only applies to one-on-one classes, group classes aren't included. |
| parent_ptm_join_pct | Same as above — one-on-one classes only. |
| on_time_teacher_join | A group class is counted once regardless of how many students were in it — teacher join behavior is the same for the whole session. Denominator is attempted classes where teacher joined. |
| avg_student_feedback_rating | Counted per student — each student gives their own rating, so a group class can have several ratings attached to it, one per student who responded. |
| time_to_submit_feedback | Counted per student — each student's feedback timing is their own, so a group class can contribute multiple timing entries, one per student who left feedback. |
| assignment_completion_pct | Counted per student — each student's assignment progress is tracked on its own, so a group class can contribute several entries, one per student. |
| assignment_avg_score_pct | Counted per student — each student's score is their own, so a group class can have multiple scores attached to it, one per student. |
| quiz_completion_pct | Counted per student — same as assignments, each student's quiz progress is tracked individually within a group class. |
| quiz_avg_score_pct | Counted per student — each student's quiz score is their own, so a group class can have multiple scores attached, one per student. |
| teacher_no_show_pct | Teacher-level — a group class where the teacher didn't show up is counted once regardless of how many students were enrolled. |
| student_no_show_pct | Counted per student — if 5 students were in a group class and none of them joined, that's 5 separate entries, not one for the whole class. |
| TJSJ_pct | Counted per student — each student's join status is checked individually, so a group class can have some students in TJSJ and others in TJSNJ. |
| TNJSJ_pct | Counted per student — if the teacher didn't join but all 5 students did, that's 5 rows in this bucket, not one. |
| TJSNJ_pct | Counted per student — if the teacher joined but 3 of 5 students didn't, those 3 absent students contribute 3 rows here. |
| TNJSNJ_pct | Counted per student — if a group class had zero attendance from either side, each enrolled student appears as a separate row. |
| pct_good_pqs | One-on-one classes only — each OTO instance contributes one score, no group-class entries. |
| pct_good_ptm_qs | Same as above — one-on-one classes only. |
| pct_5_star_feedback | Counted per student — each student's rating is their own, so a group class can contribute multiple entries. |
| pct_low_star_feedback | Same as above — counted per student. |
| assignment_grade_pct | Counted per student — each student's score is their own; a group class contributes one row per student with a completed assignment. |
| quiz_grade_pct | Same as above — counted per student. |

---

### Regional Cut (Excl. SEA)
Same as the rest of the KB: `business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')`. Always present Overall + Excl. SEA unless the user specifies a region.

**Source of `business_region_name` differs by table:**
- `brightchamps.paid_class_etl` → join `brightchamps.student_etl se ON pc.student_id = se.student_id`, filter on `se.business_region_name`
- `stage_brightchamps.paid_class_metrics_etl` → same join pattern: `brightchamps.student_etl se ON pcm.student_id = se.student_id`, filter on `se.business_region_name`. The native `business_region_name` column on this table is unreliable and must never be used directly.

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

### Teacher Performance Framework (Paid Class Journey)

When teacher performance is assessed in the context of the paid class journey (post-enrollment), always report the following 13 metrics together in this order. Reporting a subset is permitted only when the user explicitly requests specific metrics.

| # | Metric | Section 13 entry | OTO/OTM scope | Source table |
|---|---|---|---|---|
| 1 | `classes_scheduled` | §1 | OTO + OTM Regular + OTM Master | `paid_class_etl` |
| 2 | `cancellation_pct_by_teacher` | §7 | OTO + OTM Regular + OTM Master | `paid_class_etl` |
| 3 | `teacher_no_show_pct` | §23 | OTO + OTM Regular + OTM Master | `paid_class_metrics_etl` |
| 4 | `perfect_class_pct` | §12 | OTO + OTM Regular + OTM Master | `paid_class_metrics_etl` |
| 5 | `avg_pqs_score` | §13 | **OTO only** | `paid_class_metrics_etl` |
| 6 | `pct_good_pqs` | §29 | **OTO only** | `paid_class_metrics_etl` |
| 7 | `avg_student_feedback_rating` | §17 | OTO + OTM Regular + OTM Master | `paid_class_metrics_etl` |
| 8 | `pct_5_star_feedback` | §31 | OTO + OTM Regular + OTM Master | `paid_class_metrics_etl` |
| 9 | `pct_low_star_feedback` | §32 | OTO + OTM Regular + OTM Master | `paid_class_metrics_etl` |
| 10 | `assignment_completion_pct` | §19 | OTO + OTM Regular + OTM Master | `paid_class_metrics_etl` |
| 11 | `assignment_avg_score_pct` | §20 | OTO + OTM Regular + OTM Master | `paid_class_metrics_etl` |
| 12 | `quiz_completion_pct` | §21 | OTO + OTM Regular + OTM Master | `paid_class_metrics_etl` |
| 13 | `quiz_avg_score_pct` | §22 | OTO + OTM Regular + OTM Master | `paid_class_metrics_etl` |

⚠️ **PQS metrics (#5, #6) are OTO only** — for OTM classes these two rows will be NULL / not applicable. Always present them alongside the `class_mode` breakdown so it is clear which rows carry a PQS score and which do not.

**Teacher dimension:** Always join `brightchamps.teacher_etl te ON class_teacher_id = te.teacher_id` and output `te.teacher_id`, `te.teacher_name`, `te.status AS teacher_status`, `te.type AS teacher_type` as the identifying grain. See Teacher-Level Breakdown Join Rule above.

**Default scope:** All class modes (OTO + OTM Regular + OTM Master Class) as separate rows, Overall + Excl. SEA cuts, unless the user specifies otherwise.

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

## 2. completed_classes or number of completed classes

**Definition:** Count of paid classes that reached completed status (`paid_class_status_id = 13`), anchored on `class_start_at`. The core denominator for most engagement and quality metrics in this section.

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
    AND pc.paid_class_status_id = 13
    AND pc.course_id != 16
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(DISTINCT COALESCE(group_class_id, paid_class_id)) AS completed_classes
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
    AND pc.paid_class_status_id = 13
    AND pc.course_id != 16
    AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(DISTINCT COALESCE(group_class_id, paid_class_id)) AS completed_classes
FROM base
GROUP BY 1
```

**Gotcha:** Anchored on `class_start_at`. SEA region and LingoChamps vertical can mark a class completed based on teacher join alone, regardless of student presence — see Section 13 Completion Definition Caveat. `course_id = 16` excluded. A completed group class with 10 students is counted once, not once per student.

**Cross-validate (ECS):** `completed_classes + cancellations_by_parent + cancellations_by_teacher + incomplete_classes + pending + paused` for a date/class_mode should equal `classes_scheduled` for that date/class_mode.

---

## 3. cancellations_by_parent or classes cancelled by parent

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

**Gotcha:** Anchored on `class_start_at`, not `cancelled_at`. Reason-level detail (`cancel_reason`) lives in the metrics table, not here. Since `paid_class_status_id` is uniform per `group_class_id`, this only captures cancellations where the **entire group class** was cancelled — an individual student dropping out of a group class that still proceeded for others is a separate scenario. `course_id = 16` excluded. Master Class reported separately. A cancelled class is counted once, no matter how many students were enrolled in it.

**Cross-validate (ECS):** `cancellations_by_parent + cancellations_by_teacher + completed + pending + incomplete + paused` for a date/class_mode should equal `classes_scheduled` for that same date/class_mode.

---

## 4. cancellations_by_teacher or classes cancelled by teacher

**Definition:** Same as cancellations_by_parent, with `paid_class_status_id = 15`.

**Source table:** `brightchamps.paid_class_etl`.

**SQL:** Identical structure to cancellations_by_parent, with `paid_class_status_id = 15` and output column `cancellations_by_teacher`.

**Gotcha:** Same caveats as cancellations_by_parent. Same as above — counted once per class, not per student in it.

**Cross-validate (ECS):** Same combined-status identity as cancellations_by_parent.

---

## 5. incomplete_classes or number of incomplete classes

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

## 6. cancellation_pct_by_parent or parent cancellation %

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

## 7. cancellation_pct_by_teacher or teacher cancellation %

**Definition:** Same as cancellation_pct_by_parent, with `paid_class_status_id = 15`.

**Source table:** `brightchamps.paid_class_etl`.

**SQL:** Identical structure, replacing 14 with 15 and renaming output columns to `cancellations_by_teacher` / `cancellation_pct_by_teacher`.

**Gotcha / Cross-validate:** Same as cancellation_pct_by_parent. Same as above — based on classes, not the number of students in them.

---

## 8. time_to_parent_cancellation or average/median time from cancellation to scheduled class start (parent)

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

## 9. time_to_teacher_cancellation or average/median time from cancellation to scheduled class start (teacher)

**Definition:** Same as #10, with `paid_class_status_id = 15`.

**Source table:** `brightchamps.paid_class_etl`.

**SQL:** Identical structure to #10, replacing 14 with 15 and renaming outputs to `cancellations_by_teacher`.

**Gotcha / Cross-validate:** Same as #10. Same as above — one number per class, regardless of class size.

---

## 10. on_time_class_start or on-time class start rate

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

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause of the `base` CTE, and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Note: alias the metrics table as `pcm` when adding this join to avoid ambiguity.

**Gotcha:** Both join times must be non-null to qualify. Restricted to completed only. `course_id = 16` excluded. SEA region and LingoChamps vertical can mark a class 'completed' based on teacher join alone, regardless of student presence — this metric's completed-only population may not be fully comparable across regions/verticals as a result; see Section 13 Completion Definition Caveat. Counted per student — in a group class, each student's own arrival time is checked individually, so one class can produce several entries, one per student.

**Cross-validate (ECS):** `on_time_count ≤ completed_instances` always.

---

## 11. early_dropoff or early drop-off rate

**Definition:** Out of all instances where both teacher and student joined (`teacher_class_join_time IS NOT NULL` AND `student_class_join_time IS NOT NULL`), the count and % where `common_duration` (seconds) is strictly less than 75% of `class_duration` (minutes, converted to seconds). Early drop-off is a subset of TJSJ — if either party never joined, the instance is excluded entirely. Status is not used as a filter; the join condition acts as the scope boundary.

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
    AND course_id != 16
    AND teacher_class_join_time IS NOT NULL
    AND student_class_join_time IS NOT NULL
    AND class_duration IS NOT NULL
    AND common_duration IS NOT NULL
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(*) AS both_joined_instances,
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

**SQL — Excl. SEA + LingoChamps:** This cut combines region and vertical exclusion since both populations share the teacher-join-only completion quirk, which could inflate the both-joined denominator artificially — see Section 13 Completion Definition Caveat.
```sql
WITH base AS (
  SELECT
    pcm.paid_class_id,
    pcm.group_class_id,
    pcm.class_type,
    pcm.class_duration,
    pcm.common_duration
  FROM stage_brightchamps.paid_class_metrics_etl pcm
  INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id
  WHERE pcm.class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND pcm.class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND pcm.course_id != 16
    AND pcm.teacher_class_join_time IS NOT NULL
    AND pcm.student_class_join_time IS NOT NULL
    AND pcm.class_duration IS NOT NULL
    AND pcm.common_duration IS NOT NULL
    AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')
    AND pcm.vertical_name != 'LingoChamps'
)
SELECT
  CASE
    WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
    WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
    ELSE 'OTO'
  END AS class_mode,
  COUNT(*) AS both_joined_instances,
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

**Gotcha:** Unit mismatch is the critical trap — `class_duration` is minutes, `common_duration` is seconds; always multiply `class_duration` by 60. Threshold is strictly `< 0.75`. Denominator is TJSJ instances (both joined) — not all completed classes, not all attempted classes. No status filter applied — scope is determined entirely by join condition. A NULL `common_duration` where both parties joined is a data quality flag worth investigating separately; such rows are excluded by the `common_duration IS NOT NULL` filter. This metric uses **Excl. SEA + LingoChamps** instead of the standard Excl. SEA cut — SEA region and LingoChamps vertical can mark a class completed on teacher join alone, which would falsely inflate the both-joined denominator. `vertical_name != 'LingoChamps'` will silently exclude rows where `vertical_name IS NULL` — check NULL volume before trusting this cut. `course_id = 16` excluded. Counted per student — each student's own time in class is measured separately.

**Cross-validate (ECS):** `early_dropoff_count ≤ both_joined_instances`. `both_joined_instances` should align with `TJSJ_count` from the Joining Behavior Breakdown (accounting for the additional `class_duration` and `common_duration` NOT NULL filters).

---

## 12. perfect_class_pct or perfect class %

**Definition:** % of completed instances flagged `perfect_class = TRUE`. Can vary per student within the same `group_class_id` — row-level grain, no dedupe for OTM.

**⚠ Lagging metric:** `perfect_class` depends partly on quiz completion, which has a median lag of ~7 days post class. Numbers for recent dates will trend upward as students complete quizzes — avoid drawing conclusions on dates within the last 7 days. Always surface this caveat when sharing this metric.

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

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause of the `base` CTE, and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Note: alias the metrics table as `pcm` when adding this join to avoid ambiguity.

**Gotcha:** Don't dedupe to class-level for OTM — `perfect_class` can legitimately vary per student. Treat `NULL` as excluded from both numerator and denominator, not as `FALSE`. `course_id = 16` excluded. Counted per student — a "perfect class" mark is given to each student individually, so in a group class some students can be marked perfect while others aren't, for the same session.

**Cross-validate (ECS):** `perfect_class_count ≤ completed_instances`.

---

## 13. avg_pqs_score or average PQS score

**Definition:** Average `teacher_pqs_score` across completed OTO classes. **OTO only — PQS is not calculated for group classes.** `NULL` scores excluded from the average's denominator. For bucket distribution (Bad/OK/Good), see Dimensions → `pqs_bucket`.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level, OTO only (`group_class_id IS NULL`). No class_mode breakdown.

**SQL — Overall:**
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

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** No class_mode breakdown — OTO-only by definition. `NULL` scores excluded from denominator; always report `scored_instances` alongside the average. `teacher_pqs_score` can be populated for incomplete (17) classes too, but this metric restricts to completed-only (13) for comparability — don't silently expand scope. `course_id = 16` excluded. This only applies to one-on-one classes — group classes aren't scored this way.

**Cross-validate (ECS):** `scored_instances` here = Bad + OK + Good combined from the `pqs_bucket` dimension query (excludes "No PQS Data" rows).

---

## 14. avg_ptm_qs or average PTM-QS score

**Definition:** Average `ptm_qs` across completed OTO classes. **OTO only.** Restricted to rows where `ptm_qs IS NOT NULL` — these are URI PTMs (regular classes where parent and RM join to pitch). For bucket distribution (Bad/OK/Good), see Dimensions → `ptm_qs_bucket`.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level, OTO only. No class_mode breakdown.

**SQL — Overall:**
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

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** No class_mode breakdown — OTO-only. `NULL` `ptm_qs` excluded entirely — `scored_instances` reflects only PTM-scored rows. Don't confuse with `parent_joined_ptm` (attendance flag, not quality score). Restricted to completed-only by design (see PQS gotcha re: incomplete classes). `course_id = 16` excluded.

**Cross-validate (ECS):** `scored_instances` here = `SUM(instance_count)` across Bad + OK + Good from the `ptm_qs_bucket` dimension query (same denominator).

---

## 15. parent_ptm_join_pct or % of PTMs where parent joined

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

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause of the `base` CTE, and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Note: alias the metrics table as `pcm` when adding this join to avoid ambiguity.

**Gotcha:** `parent_joined_ptm` is an integer (-1/0/1), not boolean — never use `= TRUE`. `ptm_qs IS NOT NULL` is a proxy denominator, not a guaranteed PTM-scheduled flag. The denominator isn't shown directly in this output — cross-reference `scored_instances` from the avg_ptm_qs query if needed. "Could Not Determine" % is a data quality signal worth watching. No class_mode breakdown — OTO-only. `course_id = 16` excluded. Same as above — one-on-one classes only.

**Cross-validate (ECS):** `SUM(instance_count)` across all three states = `scored_instances` from the avg_ptm_qs query (same denominator).

---

## 16. on_time_teacher_join or teacher punctuality breakdown

**Definition:** Out of all attempted classes (completed + incomplete, `paid_class_status_id IN (13, 17)`) where `teacher_class_join_time IS NOT NULL`, each instance is bucketed into **On Time** (joined at/before `class_start_at`, or within a 5-minute buffer if `teacher_consecutive_class = 1`) or **Late** (joined after the allowed threshold). `teacher_consecutive_class = NULL` treated as `0` (no buffer). Class-level grain — deduped to `group_class_id` for OTM since teacher join behavior is session-constant.

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
    AND paid_class_status_id IN (13, 17)
    AND course_id != 16
    AND teacher_class_join_time IS NOT NULL
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

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause of the `base` CTE and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** Denominator is teacher-joined attempted classes only — `teacher_no_show_pct` captures the excluded population (where teacher didn't join). Together they account for all attempted classes. `DISTINCT` in `classified` is essential for OTM. `teacher_consecutive_class = NULL` treated as `0`. `course_id = 16` excluded. A group class is counted once regardless of how many students were in it — teacher join behavior is the same for the whole session.

**Cross-validate (ECS):** `SUM(class_count)` across On Time + Late = total teacher-joined attempted classes for that class_mode/date. `SUM(pct_of_class_mode)` = 100%.

---

## 17. avg_student_feedback_rating or average student feedback rating

**Definition:** Average `student_class_rating` across completed classes. `NULL` ratings (no feedback submitted) excluded entirely. Row-level grain — feedback is individual per student, no class-level dedupe even for OTM. Star rating distribution (1–5 breakdown) is deferred to a separate metric definition.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**SQL — Overall:**
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

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause of the `base` CTE, and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Note: alias the metrics table as `pcm` when adding this join to avoid ambiguity.

**Gotcha:** `student_class_rating` is known to be sparse — always check `rated_instances` before trusting the average. `NULL` ratings excluded entirely. `course_id = 16` excluded. Counted per student — each student gives their own rating, so a group class can have several ratings attached to it, one per student who responded.

**Cross-validate (ECS):** `rated_instances` ≤ completed instances for the same date/class_mode.

---

## 18. time_to_submit_feedback or average/median time from class end to feedback submission

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

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause of the `base` CTE, and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Note: alias the metrics table as `pcm` when adding this join to avoid ambiguity.

**Gotcha:** Class end is the *scheduled* end, not actual end based on left-times. `class_duration` is minutes — cast via `(class_duration || ' minutes')::interval`. Postgres casting rule applies for both `EXTRACT(EPOCH ...)` and `PERCENTILE_CONT(...)`. Negative lag = data quality flag. `student_class_rating` sparsity applies here too. `course_id = 16` excluded. Counted per student — each student's feedback timing is their own, so a group class can contribute multiple timing entries, one per student who left feedback.

**Cross-validate (ECS):** `feedback_instances ≤` count of completed instances with non-null `student_class_rating`. Spot-check row-level gaps.

---

## 19. assignment_completion_pct or % assignment completion

**Definition:** `SUM(assignment_done) / SUM(assignment_exists)`, expressed as a %. `assignment_exists` and `assignment_done` are integer counts — more than one assignment can exist or be completed per instance. This is a pooled ratio across all instances, not an average of per-row ratios — a student with 4 assignments weighs more heavily than a student with 1, correctly reflecting actual assignment volume. Computed only where `assignment_exists > 0`. Restricted to completed classes only. Row-level grain.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    assignment_done,
    assignment_exists
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
  SUM(assignment_exists) AS assignment_given_count,
  SUM(assignment_done) AS assignment_done_count,
  ROUND(100.0 * SUM(assignment_done)::numeric / NULLIF(SUM(assignment_exists), 0), 2) AS assignment_completion_pct
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause of the `base` CTE, and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Note: alias the metrics table as `pcm` when adding this join to avoid ambiguity.

**Gotcha:** `assignment_done > assignment_exists` per row is a data anomaly to flag, not cap silently. This is a pooled SUM/SUM ratio — a student with more assignments weighs more heavily in the overall % than one with fewer, which is intentional. `assignment_given_count` is now `SUM(assignment_exists)`, not a row count — it reflects the total number of assignments given, not the number of student-class instances with assignments. `assignment_exists > 0` is the row-inclusion filter. `course_id = 16` excluded. Counted per student — each student's assignment progress is tracked on its own, so a group class can contribute several entries, one per student.

**Cross-validate (ECS):** `assignment_done_count ≤ assignment_given_count` always. `assignment_completion_pct` should fall within 0–100%; values above 100% signal a data anomaly (assignment_done > assignment_exists on one or more rows) to investigate.

---

## 20. assignment_avg_score_pct or average assignment score %

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

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause of the `base` CTE, and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Note: alias the metrics table as `pcm` when adding this join to avoid ambiguity.

**Gotcha:** `NULLIF` guards against divide-by-zero. `assignment_done > 0` replaces a boolean check, consistent with assignment_completion_pct. Score columns are assumed to be row-level aggregates summed across however many assignments existed — verify against ETL logic if accuracy is questioned. `course_id = 16` excluded. Counted per student — each student's score is their own, so a group class can have multiple scores attached to it, one per student.

**Cross-validate (ECS):** `scored_instances ≤ assignment_given_count` from the completion metric for the same date/class_mode.

---

## 21. quiz_completion_pct or % quiz completion

**Definition:** `SUM(quiz_done) / SUM(quiz_exists)`, expressed as a %. Identical logic to assignment_completion_pct — pooled ratio, not average of per-row ratios. Computed only where `quiz_exists > 0`. Restricted to completed classes only. Row-level grain.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    paid_class_id,
    group_class_id,
    class_type,
    quiz_done,
    quiz_exists
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
  SUM(quiz_exists) AS quiz_given_count,
  SUM(quiz_done) AS quiz_done_count,
  ROUND(100.0 * SUM(quiz_done)::numeric / NULLIF(SUM(quiz_exists), 0), 2) AS quiz_completion_pct
FROM base
GROUP BY 1
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause of the `base` CTE, and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Note: alias the metrics table as `pcm` when adding this join to avoid ambiguity.

**Gotcha:** Same caveats as assignment_completion_pct — pooled SUM/SUM ratio, `quiz_done > quiz_exists` is a data anomaly to flag. `quiz_given_count` is `SUM(quiz_exists)`, not a row count. `quiz_exists > 0` is the row-inclusion filter. `course_id = 16` excluded. Counted per student — same as assignments, each student's quiz progress is tracked individually within a group class.

**Cross-validate (ECS):** `quiz_done_count ≤ quiz_given_count` always. Same 0–100% sanity check as assignment_completion_pct.

---

## 22. quiz_avg_score_pct or average quiz score %

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

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause of the `base` CTE, and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Note: alias the metrics table as `pcm` when adding this join to avoid ambiguity.

**Gotcha:** Same caveats as assignment_avg_score_pct. `course_id = 16` excluded. Counted per student — each student's quiz score is their own, so a group class can have multiple scores attached, one per student.

**Cross-validate (ECS):** `scored_instances ≤ quiz_given_count` from the completion metric for the same date/class_mode.

---

## 23. teacher_no_show_pct or teacher no-show rate

**Definition:** Out of all attempted classes (completed + incomplete, `paid_class_status_id IN (13, 17)`), the count and % where `teacher_class_join_time IS NULL` — the teacher was expected but never entered the live class. Anchored on `class_start_at`.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Class-level. OTO → `paid_class_id`. OTM → dedupe on `group_class_id` (teacher join behavior is uniform across all student rows of the same group class). Teacher-level breakdown available on request via `teacher_etl` join.

**SQL — Overall:**
```sql
WITH attempted AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    COALESCE(group_class_id, paid_class_id) AS class_key,
    teacher_class_join_time
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id IN (13, 17)
    AND course_id != 16
)
SELECT
  class_mode,
  COUNT(DISTINCT class_key) AS attempted_classes,
  COUNT(DISTINCT CASE WHEN teacher_class_join_time IS NULL THEN class_key END) AS teacher_no_show_count,
  ROUND(
    100.0 * COUNT(DISTINCT CASE WHEN teacher_class_join_time IS NULL THEN class_key END)
    / NULLIF(COUNT(DISTINCT class_key), 0)::numeric, 2
  ) AS teacher_no_show_pct
FROM attempted
GROUP BY 1
ORDER BY 1
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** OTM deduplication is critical — without `DISTINCT class_key`, a group class with 10 students inflates both numerator and denominator tenfold. `DISTINCT` on `class_key` collapses this correctly since teacher join behavior is session-constant. `course_id = 16` excluded. For OTM, a group class where the teacher didn't show up is counted once regardless of how many students were enrolled.

**Cross-validate (ECS):** `teacher_no_show_count ≤ attempted_classes` always. Together with `on_time_teacher_join`, these two metrics account for all attempted classes — `teacher_no_show_pct` covers the excluded population of `on_time_teacher_join`.

---

## 24. student_no_show_pct or student no-show rate

**Definition:** Out of all attempted instances (completed + incomplete, `paid_class_status_id IN (13, 17)`), the count and % where `student_class_join_time IS NULL` — the student was expected but never entered the live class. Anchored on `class_start_at`.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level — `COUNT(*)` for both numerator and denominator. For OTM, each student in a group class is counted separately — no dedupe.

**SQL — Overall:**
```sql
WITH attempted AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    student_class_join_time
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id IN (13, 17)
    AND course_id != 16
)
SELECT
  class_mode,
  COUNT(*) AS attempted_instances,
  COUNT(*) FILTER (WHERE student_class_join_time IS NULL) AS student_no_show_count,
  ROUND(
    100.0 * COUNT(*) FILTER (WHERE student_class_join_time IS NULL)
    / NULLIF(COUNT(*), 0)::numeric, 2
  ) AS student_no_show_pct
FROM attempted
GROUP BY 1
ORDER BY 1
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** No deduplication for OTM — each student row is intentionally counted separately since student attendance is individual. Contrast with `teacher_no_show_pct` which dedupes to class-level. `course_id = 16` excluded. Counted per student — if 5 students were in a group class and none of them joined, that's 5 separate entries, not one for the whole class.

**Cross-validate (ECS):** `student_no_show_count ≤ attempted_instances` always. Compare against `teacher_no_show_pct` (class-level) to understand whether no-shows are supply-side or demand-side.

---

### Joining Behavior Breakdown
A set of 4 mutually exclusive metrics that decompose all attempted instances (`paid_class_status_id IN (13, 17)`) by whether the teacher and student each joined the live session. The 4 percentages always sum to 100% within each class_mode for a given date. Grain is row-level (student POV) across all 4 — for OTM, each student row is counted separately. Best queried together in a single SQL using 4 `COUNT(*) FILTER` expressions off the same CTE rather than run as 4 separate queries.

---

## 25. TJSJ_pct or teacher joined student joined %

**Definition:** Out of all attempted instances, the % where both `teacher_class_join_time IS NOT NULL` and `student_class_join_time IS NOT NULL`. Anchored on `class_start_at`.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level — `COUNT(*)`.

**SQL — Overall:**
```sql
WITH attempted AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    teacher_class_join_time,
    student_class_join_time
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id IN (13, 17)
    AND course_id != 16
)
SELECT
  class_mode,
  COUNT(*) AS attempted_instances,
  COUNT(*) FILTER (WHERE teacher_class_join_time IS NOT NULL AND student_class_join_time IS NOT NULL) AS TJSJ_count,
  ROUND(
    100.0 * COUNT(*) FILTER (WHERE teacher_class_join_time IS NOT NULL AND student_class_join_time IS NOT NULL)
    / NULLIF(COUNT(*), 0)::numeric, 2
  ) AS TJSJ_pct
FROM attempted
GROUP BY 1
ORDER BY 1
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** This is the "healthy" bucket — both parties present. Will largely align with completed classes (status 13) but can include status 17 rows where both joined but the session still ended incomplete. `course_id = 16` excluded. Counted per student — for OTM, each student's join status is checked individually.

**Cross-validate (ECS):** `TJSJ_pct + TNJSJ_pct + TJSNJ_pct + TNJSNJ_pct = 100%` within each class_mode/date. `TJSJ_count` should align with `both_joined_instances` from `early_dropoff` (before the class_duration/common_duration NULL filters are applied).

---

## 26. TNJSJ_pct or teacher not joined student joined %

**Definition:** Out of all attempted instances, the % where `teacher_class_join_time IS NULL` and `student_class_join_time IS NOT NULL`. Anchored on `class_start_at`.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level — `COUNT(*)`.

**SQL — Overall:**
```sql
WITH attempted AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    teacher_class_join_time,
    student_class_join_time
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id IN (13, 17)
    AND course_id != 16
)
SELECT
  class_mode,
  COUNT(*) AS attempted_instances,
  COUNT(*) FILTER (WHERE teacher_class_join_time IS NULL AND student_class_join_time IS NOT NULL) AS TNJSJ_count,
  ROUND(
    100.0 * COUNT(*) FILTER (WHERE teacher_class_join_time IS NULL AND student_class_join_time IS NOT NULL)
    / NULLIF(COUNT(*), 0)::numeric, 2
  ) AS TNJSJ_pct
FROM attempted
GROUP BY 1
ORDER BY 1
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** Student showed up but teacher was absent — the most impactful failure mode from a student experience perspective. `course_id = 16` excluded. Counted per student — for OTM, if the teacher didn't join but all 5 students did, that's 5 rows in this bucket.

**Cross-validate (ECS):** `TJSJ_pct + TNJSJ_pct + TJSNJ_pct + TNJSNJ_pct = 100%` within each class_mode/date.

---

## 27. TJSNJ_pct or teacher joined student not joined %

**Definition:** Out of all attempted instances, the % where `teacher_class_join_time IS NOT NULL` and `student_class_join_time IS NULL`. Anchored on `class_start_at`.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level — `COUNT(*)`.

**SQL — Overall:**
```sql
WITH attempted AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    teacher_class_join_time,
    student_class_join_time
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id IN (13, 17)
    AND course_id != 16
)
SELECT
  class_mode,
  COUNT(*) AS attempted_instances,
  COUNT(*) FILTER (WHERE teacher_class_join_time IS NOT NULL AND student_class_join_time IS NULL) AS TJSNJ_count,
  ROUND(
    100.0 * COUNT(*) FILTER (WHERE teacher_class_join_time IS NOT NULL AND student_class_join_time IS NULL)
    / NULLIF(COUNT(*), 0)::numeric, 2
  ) AS TJSNJ_pct
FROM attempted
GROUP BY 1
ORDER BY 1
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** Teacher showed up but student was absent. For OTM, each absent student is a separate row — a group class where the teacher joined but 3 of 5 students didn't contributes 3 rows here and 2 to TJSJ. `course_id = 16` excluded.

**Cross-validate (ECS):** `TJSJ_pct + TNJSJ_pct + TJSNJ_pct + TNJSNJ_pct = 100%` within each class_mode/date.

---

## 28. TNJSNJ_pct or teacher not joined student not joined %

**Definition:** Out of all attempted instances, the % where both `teacher_class_join_time IS NULL` and `student_class_join_time IS NULL` — neither party entered the live session. Anchored on `class_start_at`.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level — `COUNT(*)`.

**SQL — Overall:**
```sql
WITH attempted AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    teacher_class_join_time,
    student_class_join_time
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id IN (13, 17)
    AND course_id != 16
)
SELECT
  class_mode,
  COUNT(*) AS attempted_instances,
  COUNT(*) FILTER (WHERE teacher_class_join_time IS NULL AND student_class_join_time IS NULL) AS TNJSNJ_count,
  ROUND(
    100.0 * COUNT(*) FILTER (WHERE teacher_class_join_time IS NULL AND student_class_join_time IS NULL)
    / NULLIF(COUNT(*), 0)::numeric, 2
  ) AS TNJSNJ_pct
FROM attempted
GROUP BY 1
ORDER BY 1
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** Ghost sessions — neither party showed up. Could signal scheduling errors, communication failures, or system issues. `course_id = 16` excluded. For OTM, each enrolled student appears as a separate row even though the group class had zero attendance from either side.

**Cross-validate (ECS):** `TJSJ_pct + TNJSJ_pct + TJSNJ_pct + TNJSNJ_pct = 100%` within each class_mode/date.

---

## 29. pct_good_pqs or % good PQS

**Definition:** Out of all completed OTO instances where `teacher_pqs_score IS NOT NULL`, the % where `teacher_pqs_score >= 9` (Good bucket). OTO only.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level, OTO only (`group_class_id IS NULL`). No class_mode breakdown.

**SQL — Overall:**
```sql
SELECT
  COUNT(*) AS scored_instances,
  COUNT(*) FILTER (WHERE teacher_pqs_score >= 9) AS good_pqs_count,
  ROUND(
    100.0 * COUNT(*) FILTER (WHERE teacher_pqs_score >= 9)
    / NULLIF(COUNT(*), 0)::numeric, 2
  ) AS pct_good_pqs
FROM stage_brightchamps.paid_class_metrics_etl
WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
  AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
  AND paid_class_status_id = 13
  AND course_id != 16
  AND group_class_id IS NULL
  AND teacher_pqs_score IS NOT NULL
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** Denominator is scored instances only — classes where `teacher_pqs_score IS NULL` are excluded entirely. Always report `scored_instances` alongside the % for context. OTO only — group classes are not PQS scored. `course_id = 16` excluded.

**Cross-validate (ECS):** `good_pqs_count ≤ scored_instances`. `scored_instances` here should match `scored_instances` from `avg_pqs_score` for the same date.

---

## 30. pct_good_ptm_qs or % good PTM-QS

**Definition:** Out of all completed OTO instances where `ptm_qs IS NOT NULL`, the % where `ptm_qs >= 22` (Good bucket). OTO only. URI PTMs only.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level, OTO only (`group_class_id IS NULL`). No class_mode breakdown.

**SQL — Overall:**
```sql
SELECT
  COUNT(*) AS scored_instances,
  COUNT(*) FILTER (WHERE ptm_qs >= 22) AS good_ptm_qs_count,
  ROUND(
    100.0 * COUNT(*) FILTER (WHERE ptm_qs >= 22)
    / NULLIF(COUNT(*), 0)::numeric, 2
  ) AS pct_good_ptm_qs
FROM stage_brightchamps.paid_class_metrics_etl
WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
  AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
  AND paid_class_status_id = 13
  AND course_id != 16
  AND group_class_id IS NULL
  AND ptm_qs IS NOT NULL
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** Denominator is scored instances only — `ptm_qs IS NULL` rows excluded entirely, which will be the majority of rows since PTMs don't happen every class. Always report `scored_instances` alongside the % for context. OTO only. `course_id = 16` excluded.

**Cross-validate (ECS):** `good_ptm_qs_count ≤ scored_instances`. `scored_instances` here should match `scored_instances` from `avg_ptm_qs` for the same date.

---

## 31. pct_5_star_feedback or 5 star student feedback %

**Definition:** Out of all completed instances where `student_class_rating IS NOT NULL`, the % where `student_class_rating = 5`. Row-level grain — each student's rating is their own.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level — `COUNT(*)`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    student_class_rating
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND student_class_rating IS NOT NULL
)
SELECT
  class_mode,
  COUNT(*) AS rated_instances,
  COUNT(*) FILTER (WHERE student_class_rating = 5) AS five_star_count,
  ROUND(
    100.0 * COUNT(*) FILTER (WHERE student_class_rating = 5)
    / NULLIF(COUNT(*), 0)::numeric, 2
  ) AS pct_5_star_feedback
FROM base
GROUP BY 1
ORDER BY 1
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** Denominator is rated instances only — always report `rated_instances` alongside the % given how sparse feedback can be. `rated_instances` should match across `avg_student_feedback_rating`, `pct_5_star_feedback`, and `pct_low_star_feedback` for the same date/class_mode — all three share the same denominator. `course_id = 16` excluded. Counted per student.

**Cross-validate (ECS):** `five_star_count ≤ rated_instances`. `rated_instances` should match `rated_instances` from `avg_student_feedback_rating` for the same date/class_mode.

---

## 32. pct_low_star_feedback or 1 and 2 star student feedback %

**Definition:** Out of all completed instances where `student_class_rating IS NOT NULL`, the % where `student_class_rating IN (1, 2)`. Row-level grain — each student's rating is their own.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level — `COUNT(*)`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    student_class_rating
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND student_class_rating IS NOT NULL
)
SELECT
  class_mode,
  COUNT(*) AS rated_instances,
  COUNT(*) FILTER (WHERE student_class_rating IN (1, 2)) AS low_star_count,
  ROUND(
    100.0 * COUNT(*) FILTER (WHERE student_class_rating IN (1, 2))
    / NULLIF(COUNT(*), 0)::numeric, 2
  ) AS pct_low_star_feedback
FROM base
GROUP BY 1
ORDER BY 1
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** Denominator is rated instances only — always report `rated_instances` alongside the %. Low star ratings (1–2) are a direct dissatisfaction signal — spikes here warrant immediate investigation. `rated_instances` should match across all three feedback metrics for the same date/class_mode. `course_id = 16` excluded. Counted per student.

**Cross-validate (ECS):** `low_star_count ≤ rated_instances`. `rated_instances` should match `rated_instances` from `avg_student_feedback_rating` and `pct_5_star_feedback` for the same date/class_mode.

---

## 33. assignment_grade_pct or assignment score grade distribution %

**Definition:** Out of all completed instances where `assignment_done > 0` and `assignment_total_score > 0`, the % distribution across 4 score bands based on `(assignment_obtained_score / assignment_total_score) × 100`:
- **High:** ≥ 75%
- **Medium:** 50% – 74.99%
- **Low:** 30% – 49.99%
- **At Risk:** < 30%

The 4 bands sum to 100% of scored instances. Row-level grain — each student's score is their own.

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level — `COUNT(*)`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    CASE
      WHEN (assignment_obtained_score::numeric / NULLIF(assignment_total_score, 0)) * 100 >= 75 THEN 'High'
      WHEN (assignment_obtained_score::numeric / NULLIF(assignment_total_score, 0)) * 100 >= 50 THEN 'Medium'
      WHEN (assignment_obtained_score::numeric / NULLIF(assignment_total_score, 0)) * 100 >= 30 THEN 'Low'
      ELSE 'At Risk'
    END AS grade_bucket
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND assignment_done > 0
    AND assignment_total_score > 0
)
SELECT
  class_mode,
  grade_bucket,
  COUNT(*) AS instance_count,
  ROUND(
    100.0 * COUNT(*) / SUM(COUNT(*)) OVER (PARTITION BY class_mode)::numeric, 2
  ) AS assignment_grade_pct
FROM base
GROUP BY class_mode, grade_bucket
ORDER BY class_mode, grade_bucket
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** Denominator is scored completed instances only — rows where `assignment_done = 0` or `assignment_total_score = 0` are excluded. `SUM(assignment_grade_pct)` across all 4 bands within a class_mode = 100%. At Risk is the most actionable band — spikes here warrant investigation. `course_id = 16` excluded. Counted per student.

**Cross-validate (ECS):** `SUM(instance_count)` across all 4 bands for a class_mode = `scored_instances` from `assignment_avg_score_pct` for the same date/class_mode.

---

## 34. quiz_grade_pct or quiz score grade distribution %

**Definition:** Identical logic to `assignment_grade_pct`, using `quiz_obtained_score / quiz_total_score × 100` and filter `quiz_done > 0 AND quiz_total_score > 0`. Same 4 bands: High (≥75%), Medium (50–74.99%), Low (30–49.99%), At Risk (<30%).

**Source table:** `stage_brightchamps.paid_class_metrics_etl`.

**Grain:** Row-level — `COUNT(*)`.

**SQL — Overall:**
```sql
WITH base AS (
  SELECT
    CASE
      WHEN group_class_id IS NOT NULL AND class_type = 'online_master_class' THEN 'OTM - Master Class'
      WHEN group_class_id IS NOT NULL THEN 'OTM - Regular'
      ELSE 'OTO'
    END AS class_mode,
    CASE
      WHEN (quiz_obtained_score::numeric / NULLIF(quiz_total_score, 0)) * 100 >= 75 THEN 'High'
      WHEN (quiz_obtained_score::numeric / NULLIF(quiz_total_score, 0)) * 100 >= 50 THEN 'Medium'
      WHEN (quiz_obtained_score::numeric / NULLIF(quiz_total_score, 0)) * 100 >= 30 THEN 'Low'
      ELSE 'At Risk'
    END AS grade_bucket
  FROM stage_brightchamps.paid_class_metrics_etl
  WHERE class_start_at >= DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours' - INTERVAL '1 day'
    AND class_start_at <  DATE(current_timestamp + INTERVAL '5:30 hours') - INTERVAL '5:30 hours'
    AND paid_class_status_id = 13
    AND course_id != 16
    AND quiz_done > 0
    AND quiz_total_score > 0
)
SELECT
  class_mode,
  grade_bucket,
  COUNT(*) AS instance_count,
  ROUND(
    100.0 * COUNT(*) / SUM(COUNT(*)) OVER (PARTITION BY class_mode)::numeric, 2
  ) AS quiz_grade_pct
FROM base
GROUP BY class_mode, grade_bucket
ORDER BY class_mode, grade_bucket
```

**SQL — Excl. SEA:** Same structure, with `INNER JOIN brightchamps.student_etl se ON pcm.student_id = se.student_id` added to the `FROM` clause and `AND se.business_region_name NOT IN ('SEA', 'Indonesia', 'Vietnam')` added to the `WHERE` clause. Alias the metrics table as `pcm`.

**Gotcha:** Denominator is scored completed instances only — rows where `quiz_done = 0` or `quiz_total_score = 0` are excluded. Same band logic and caveats as `assignment_grade_pct`. `course_id = 16` excluded. Counted per student.

**Cross-validate (ECS):** `SUM(instance_count)` across all 4 bands for a class_mode = `scored_instances` from `quiz_avg_score_pct` for the same date/class_mode.

---

*End of Section 13. RM-related metrics remain deferred per prior scope decision. `is_same_ip` flagged as a potential future metric but not yet built — revisit when ready.*


# SECTION 14: RIGOUR METRICS (CALL ACTIVITY)

Use this section for any question about **call / dialling activity** — raw call volumes, vendor breakdowns, connectivity and pickup rates, durations, and SM (Hunter) dialling rigour.

**SM = Hunter = Sales Person = Sales Rep** (`ROLE = 'Hunter'`). Interchangeable.

**Source Tables**

| Table | Use for |
|---|---|
| `stage_brightchamps.unified_call_etl` | **Call-log family (14.A)** — total calls, unique parents, connectivity %, pickup rates, total duration, talk time (#1–#7). One row per call (`reference_key`). `start_time`/`end_time` in UTC — always convert to IST (+ 330 min). No SM roster join needed. |
| `stage_brightchamps.neo_lead_eligibility_etl` | **SM-scoped family (14.B / 14.B.2 / 14.E)** — SM roster, one row per agent per `snapshot_date`. Drives active status, week-off flag, business region, role, manager and business-leader hierarchy. Required for per-SM averages (#8–#10), rigour lists (#11–#14), and weekly rollups (14.E). |
| `prashashak.zoho_employees` | **Exit-date override only (R6)** — corrects stale `active = 'Yes'` records for SMs who have left. Never queried standalone; always accessed via the `zoho_status` CTE at the top of every 14.B query. |

**Two query families:**
1. **Call-log family (14.A)** — runs directly off `unified_call_etl`. No roster join, no USA roll-back, no India filter. Date = raw `start_time` IST. Covers vendor / vendor_category / connectivity / pickup / duration aggregates (#1–#7).
2. **SM-scoped family (14.B)** — joins calls to the roster via `agent_email`, applies the active override, week-off logic, **USA shift roll-back**, and the **India Manual-Call rule**. Covers per-SM averages (#8–#10), and rigour lists in sub-section 14.B.2 (#11–#14).

---

## Dimensions Table

Dimensions are breakdowns that slice Section 14 metrics — they are not standalone metrics themselves. Add a GROUP BY on the dimension column to get the metric broken down by that dimension.

| Dimension | Source | Values / Buckets | Typically slices... |
|---|---|---|---|
| vendor | `unified_call_etl.vendor` | Telephony provider names (e.g., Exotel, Knowlarity) | #1, #2, #6, #7 |
| vendor_category | `unified_call_etl.vendor_category` | `Dialler`, `Manual-Call`, `AI-Call` | #1 (GROUP BY variant), #6, #7 |
| call_status_category | `unified_call_etl.call_status_category` | `Picked`, `Not Picked`, `Failed` | #3, #4, #5 |
| business_region | Derived from `neo_lead_eligibility_etl.regions` | USA (US-CANADA), INDIA, ROW | #8–#14 (14.B/14.B.2) |
| active | `neo_lead_eligibility_etl.active` with Zoho override (R6) | `Yes` / `No` | All SM-scoped metrics (#8–#14) |
| week_off | Derived from `neo_lead_eligibility_etl.week_off` + `snapshot_day` (R7) | On week off (1) / Not on week off (0) | #11–#14 (14.B.2 Rigour Lists) |
| date (day / week / month) | `start_time + 330 min` IST (14.A); `snapshot_date` (14.B / 14.E) | Day, week (Monday-start), month | All metrics |

---

## 14.0 — Universal Rules

**R1 — IST conversion.** `start_time`/`end_time` are UTC. Convert with `+ INTERVAL '330 minutes'` (= 5h30m) before any date logic.

**R2 — Connected / Picked definitions (drive all rates).**
- **Picked** = `call_status_category = 'Picked'`
- **Not Picked** = `call_status_category = 'Not Picked'`
- **Connected** = Picked + Not Picked
- **Failed** = excluded from connected, but KEPT in total dialled.

**R3 — The three rates.**
| Rate | Formula |
|---|---|
| Connectivity % | Connected ÷ Total dialled × 100 |
| Pickup rate on connected | Picked ÷ Connected × 100 |
| Pickup rate on dialled | Picked ÷ Total dialled × 100 |

**R4 — vendor_category values (exact strings):** `'Dialler'`, `'Manual-Call'`, `'AI-Call'`.

**R5 — Unique calls = `COUNT(DISTINCT parent_id)`** (unique parent/customer reached). Plain call count = `COUNT(reference_key)`.

**R6 — Active override (SM-scoped only).**
```sql
CASE WHEN nle.active = 'Yes' AND zs.date_of_exit IS NOT NULL
       AND zs.date_of_exit < nle.snapshot_date::date THEN 'No'
     ELSE nle.active END AS active
```
Zoho email normalised: `split_part(email,'@',1) || '@team.brightchamps.com'`. `zoho_status.date_of_exit = COALESCE(date_of_exit::date, CURRENT_DATE)`.

**R7 — Week-off flag (SM-scoped).** On week off if `week_off ILIKE '%' || snapshot_day || '%'`, `snapshot_day = TO_CHAR(nle.snapshot_date,'FMDay')`.

**R8 — Population hierarchy (SM-scoped).** `Total Agents = on weekoff + not on weekoff`, all over `active = 'Yes'`. **Every call average divides by "not on weekoff" active agents only**, and week-off agents' calls are excluded from all numerators.

**R9 — USA shift roll-back (SM-scoped only, US-CANADA only).** Attribute calls to a shift-date, not the raw IST date:
```sql
CASE WHEN nle.regions ILIKE '%US-CANADA%'
          AND (uce.start_time + interval '330 minutes')::time < time '18:00'
       THEN date(uce.start_time + interval '330 minutes') - 1
     ELSE date(uce.start_time + interval '330 minutes')
END = date(nle.snapshot_date)
```
Roll-back applies ONLY to US-CANADA agents. All other regions use the IST calendar date as-is. Never applied in the call-log family (14.A).

**R10 — India Manual-Call rule (SM-scoped only).** India dialler/AI feeds carry no call data; only Manual calls exist for India. India-region agents contribute ONLY `vendor_category = 'Manual-Call'`; non-India agents contribute all categories:
```sql
AND (
  (nle.regions ILIKE '%INDIA%' AND uce.vendor_category = 'Manual-Call')
  OR nle.regions NOT ILIKE '%INDIA%'
)
```

**R11 — Agent-dialled only (SM-scoped).** Join on `lower(trim(nle.email)) = lower(trim(uce.agent_email))`. `agent_email` is NULL for Knowlarity-vendor and AI calls, so those never attribute to an SM.

**R12 — Region cut (SM-scoped).** Roster always excludes SEA + Vietnam (`regions NOT ILIKE '%SEA%' AND regions NOT ILIKE '%Vietnam%'`). Region buckets: USA = `regions ILIKE '%US-CANADA%'`; INDIA = `regions ILIKE '%INDIA%'`; ROW = the rest.

**R13 — Duration units.** `call_duration` = actual talk time; `total_duration_seconds` = ringing + talk. Both in seconds; report averages/totals in **minutes** (`/ 60.0`) unless the user asks for seconds.

**R14 — Date windows.** Default = yesterday IST. Day: `= DATE(...) - 1`. Particular date: `= 'YYYY-MM-DD'`. Week/month: use a range on the IST-converted date (`>= start AND < end`) or `date_trunc('week'|'month', ...)`.

---

## 14.A — CALL-LOG FAMILY (off `unified_call_etl` directly)

No roster join. Date dimension = `date(start_time + interval '330 minutes')` (IST). Swap the date predicate for day/date/week/month as needed.

---

## 1. Total calls

**Definition:** Total call count (`COUNT(reference_key)`) grouped by vendor name (telephony provider). Answers "how many calls did vendor X make?". For unique parent reach by vendor, see #2.

**Source table:** `stage_brightchamps.unified_call_etl`

**Grain:** One row per `vendor`. Default window: yesterday IST. Swap date predicate for a specific date, week, or month as needed.

**SQL — Overall:**
```sql
SELECT vendor,
       COUNT(reference_key) AS calls
FROM stage_brightchamps.unified_call_etl
WHERE date(start_time + interval '330 minutes') = DATE(current_timestamp + interval '5:30 hours') - 1
GROUP BY vendor
ORDER BY calls DESC;
```

**GROUP BY vendor_category variant:** To break down total calls by call mode (Dialler / Manual-Call / AI-Call), swap `vendor` for `vendor_category`:
```sql
SELECT vendor_category,
       COUNT(reference_key) AS calls
FROM stage_brightchamps.unified_call_etl
WHERE date(start_time + interval '330 minutes') = DATE(current_timestamp + interval '5:30 hours') - 1
GROUP BY vendor_category
ORDER BY calls DESC;
```
Exact `vendor_category` values (R4): `'Dialler'`, `'Manual-Call'`, `'AI-Call'`.

**SQL — Excl. SEA:** Not applicable — call-log family has no roster join and `unified_call_etl` carries no agent region dimension. To restrict to non-SEA agents, switch to the SM-scoped family (14.B).

**Gotcha:** `vendor` can be NULL for some legacy rows. Filter `WHERE vendor IS NOT NULL` if NULL rows are unexpected in the output.

**Cross-validate:** `SUM(calls across all vendor rows) = total_dialled` from #3 for the same date. For unique parent reach per vendor, use #2 — `calls >= unique_parents` for every vendor row.

---

## 2. Unique parents touched

**Definition:** Count of distinct parents (`COUNT(DISTINCT parent_id)`) contacted, grouped by vendor name. Measures unique reach per telephony provider — one parent called by the same vendor 3 times counts as 1. For total call volume by vendor, see #1.

**Source table:** `stage_brightchamps.unified_call_etl`

**Grain:** One row per `vendor`. Default window: yesterday IST.

**SQL — Overall:**
```sql
SELECT vendor,
       COUNT(DISTINCT parent_id) AS unique_parents
FROM stage_brightchamps.unified_call_etl
WHERE date(start_time + interval '330 minutes') = DATE(current_timestamp + interval '5:30 hours') - 1
GROUP BY vendor
ORDER BY unique_parents DESC;
```

**SQL — Excl. SEA:** Not applicable — call-log family has no roster join and `unified_call_etl` carries no agent region dimension.

**Gotcha:** A parent called by two different vendors will appear in both vendors' `unique_parents` count — the SUM across vendors overstates true global unique reach. For a single global distinct-parent figure across all vendors, use `SELECT COUNT(DISTINCT parent_id) FROM ... WHERE [date filter]`.

**Cross-validate:** `unique_parents <= calls` from #1 for every vendor row (a parent can be called multiple times). `SUM(unique_parents across vendors) >= true global DISTINCT parent count` (parents may be contacted by multiple vendors).

---

## 3. Connectivity %

**Definition:** Of all calls dialled, how many were connected (Picked + Not Picked)? Connectivity % = Connected ÷ Total dialled × 100. `'Failed'` calls count in total dialled but are excluded from connected (R2, R3).

**Source table:** `stage_brightchamps.unified_call_etl`

**Grain:** Scalar (one row). Default window: yesterday IST.

**SQL — Overall:**
```sql
SELECT
  COUNT(reference_key)                                                              AS total_dialled,
  COUNT(reference_key) FILTER (WHERE call_status_category IN ('Picked','Not Picked')) AS connected,
  ROUND(100.0 * COUNT(reference_key) FILTER (WHERE call_status_category IN ('Picked','Not Picked'))
        / NULLIF(COUNT(reference_key),0), 2)                                          AS connectivity_pct
FROM stage_brightchamps.unified_call_etl
WHERE date(start_time + interval '330 minutes') = DATE(current_timestamp + interval '5:30 hours') - 1;
```

**SM-scoped by-region variant:** For connectivity broken down by business region (USA / INDIA / ROW) with active/week-off filtering, use the 14.B shared base CTE and GROUP BY business_region. This applies R6 (active override), R7 (week-off), R9 (USA roll-back), R10 (India Manual-Call), R12 (SEA/Vietnam exclusion):
```sql
SELECT business_region,
       SUM(calls_by_agent)  FILTER (WHERE active='Yes' AND is_week_off=0) AS dialled,
       SUM(connected_calls) FILTER (WHERE active='Yes' AND is_week_off=0) AS connected,
       ROUND(100.0 * SUM(connected_calls) FILTER (WHERE active='Yes' AND is_week_off=0)
             / NULLIF(SUM(calls_by_agent) FILTER (WHERE active='Yes' AND is_week_off=0),0), 2) AS connectivity_pct
FROM per_agent
GROUP BY business_region;
```
SEA already excluded by default via R12. Regions present: USA, INDIA, ROW only.

**SQL — Excl. SEA:** Not applicable for the raw call-log cut — call-log family has no region dimension. The SM-scoped by-region variant above already excludes SEA.

**Gotcha:** Failed calls stay in the denominator intentionally. Dropping them inflates connectivity and hides dialler issues. `total_dialled = connected + failed_count`. SM-scoped connectivity differs from the raw cut: excludes SEA/Vietnam agents, week-off agents' calls, and AI/Knowlarity calls not attributed to any agent (NULL `agent_email`).

**Cross-validate:** `connected <= total_dialled` and `0 <= connectivity_pct <= 100`. `connected = picked (#4) + not_picked`. `SUM(calls by vendor from #1) = total_dialled here`.

---

## 4. Pickup rate on connected

**Definition:** Of all connected calls (Picked + Not Picked), how many were actually answered? Pickup rate on connected = Picked ÷ Connected × 100 (R3). Isolates parent answer behaviour independently of network failures.

**Source table:** `stage_brightchamps.unified_call_etl`

**Grain:** Scalar (one row). Default window: yesterday IST.

**SQL — Overall:**
```sql
SELECT
  COUNT(reference_key) FILTER (WHERE call_status_category IN ('Picked','Not Picked')) AS connected,
  COUNT(reference_key) FILTER (WHERE call_status_category = 'Picked')                 AS picked,
  ROUND(100.0 * COUNT(reference_key) FILTER (WHERE call_status_category = 'Picked')
        / NULLIF(COUNT(reference_key) FILTER (WHERE call_status_category IN ('Picked','Not Picked')),0), 2)
        AS pickup_rate_on_connected
FROM stage_brightchamps.unified_call_etl
WHERE date(start_time + interval '330 minutes') = DATE(current_timestamp + interval '5:30 hours') - 1;
```

**SQL — Excl. SEA:** Not applicable — call-log family has no region dimension.

**Gotcha:** Denominator is connected calls only (not total dialled). Use #4 to isolate parent answer behaviour; use #5 for overall end-to-end campaign efficiency that includes network failures.

**Cross-validate:** `picked <= connected` and `0 <= pickup_rate_on_connected <= 100`. `connected` here must equal `connected` from #3 for the same date. `picked` must equal `picked` from #5.

---

## 5. Pickup rate on dialled

**Definition:** Of all calls dialled (including Failed), how many were answered? Pickup rate on dialled = Picked ÷ Total dialled × 100 (R3). A compound rate reflecting both network connectivity and parent answer behaviour.

**Source table:** `stage_brightchamps.unified_call_etl`

**Grain:** Scalar (one row). Default window: yesterday IST.

**SQL — Overall:**
```sql
SELECT
  COUNT(reference_key)                                                AS total_dialled,
  COUNT(reference_key) FILTER (WHERE call_status_category = 'Picked') AS picked,
  ROUND(100.0 * COUNT(reference_key) FILTER (WHERE call_status_category = 'Picked')
        / NULLIF(COUNT(reference_key),0), 2)                          AS pickup_rate_on_dialled
FROM stage_brightchamps.unified_call_etl
WHERE date(start_time + interval '330 minutes') = DATE(current_timestamp + interval '5:30 hours') - 1;
```

**SQL — Excl. SEA:** Not applicable — call-log family has no region dimension.

**Gotcha:** `pickup_rate_on_dialled <= connectivity_pct` always — you cannot pick up more calls than are connected. If this inequality breaks, there is a data issue.

**Cross-validate:** `pickup_rate_on_dialled = connectivity_pct × pickup_rate_on_connected / 100` (within rounding). `total_dialled` must equal #3's `total_dialled`. `picked` must equal #4's `picked`.

---

## 6. Total duration

**Definition:** Sum of `total_duration_seconds` (ringing + talk) in minutes, optionally broken down by `vendor_category`. Represents total time the dialling system was active on calls — includes ringing time even for unanswered calls.

**Source table:** `stage_brightchamps.unified_call_etl`

**Grain:** One row per `vendor_category` (drop GROUP BY for a scalar total). Reported in **minutes** (`/ 60.0`). Default window: yesterday IST.

**SQL — Overall:**
```sql
SELECT
  vendor_category,
  ROUND(SUM(total_duration_seconds)/60.0, 2) AS total_duration_min
FROM stage_brightchamps.unified_call_etl
WHERE date(start_time + interval '330 minutes') = DATE(current_timestamp + interval '5:30 hours') - 1
GROUP BY vendor_category;   -- drop GROUP BY / add WHERE vendor = '...' as needed
```

**Week/month variants:** Replace the date predicate with `date_trunc('week', start_time + interval '330 minutes') = date_trunc('week', DATE(current_timestamp + interval '5:30 hours'))` or `date_trunc('month', ...)` for month-to-date.

**SQL — Excl. SEA:** Not applicable — call-log family has no region dimension. For SM-level duration breakdown, use the 14.B SM-scoped family.

**Gotcha:** `total_duration_seconds` includes ringing time; `call_duration` is talk-only (#7). Both in seconds — divide by 60.0 for minutes.

**Cross-validate:** `SUM(total_duration_min across vendor_category rows) = scalar total_duration_min` (drop GROUP BY). `total_duration_min >= total_talktime_min` from #7 for every vendor_category — total duration always includes ringing so it is always >= talk time.

---

## 7. Total talk time

**Definition:** Sum of `call_duration` (actual seconds speaking with the parent) in minutes, optionally by `vendor_category`. `call_duration = 0` for Not Picked and Failed calls — only Picked calls contribute meaningful talk time.

**Source table:** `stage_brightchamps.unified_call_etl`

**Grain:** One row per `vendor_category` (drop GROUP BY for scalar). Reported in **minutes**. Default window: yesterday IST.

**SQL — Overall:**
```sql
SELECT
  vendor_category,
  ROUND(SUM(call_duration)/60.0, 2) AS total_talktime_min
FROM stage_brightchamps.unified_call_etl
WHERE date(start_time + interval '330 minutes') = DATE(current_timestamp + interval '5:30 hours') - 1
GROUP BY vendor_category;
```

**Week/month variants:** Replace the date predicate with `date_trunc('week'|'month', start_time + interval '330 minutes')` as needed.

**SQL — Excl. SEA:** Not applicable — call-log family has no region dimension. For SM-level talk time breakdown, use the 14.B SM-scoped family.

**Gotcha:** `call_duration = 0` for Not Picked and Failed rows, so talk-time totals are naturally lower than total duration — this is expected, not a data issue. The ratio `talktime / total_duration` is your effective talk ratio.

**Cross-validate:** `total_talktime_min <= total_duration_min` from #6 per vendor_category. `SUM(talktime across vendor_categories) = scalar total_talktime` (drop GROUP BY). Ratio `talktime / total_duration` typically 40–70% depending on vendor and pickup rate.

---

## 14.B — SM-SCOPED FAMILY (calls joined to the roster)

Joins calls to the SM roster via `agent_email`. Applies: active override (R6), week-off logic (R7), USA shift roll-back (R9), India Manual-Call rule (R10), agent-dialled-only filter (R11), SEA/Vietnam exclusion (R12). Default window = yesterday IST.

**Shared base CTE** — used by all SM-scoped questions (#8–#14). Paste this before the final SELECT of each question.

```sql
WITH
  zoho_status AS (
    SELECT employee_id,
           split_part(email,'@',1) || '@team.brightchamps.com' AS email,
           coalesce(date_of_exit::date, CURRENT_DATE) AS date_of_exit
    FROM prashashak.zoho_employees
  ),
  call_per_shift_date AS (
    SELECT
      date(nle.snapshot_date) AS snapshot_date,
      TO_CHAR(nle.snapshot_date,'FMDay') AS snapshot_day,
      nle.email,
      nle.role,
      nle.week_off,
      nle1.email AS manager_email,
      nle2.email AS business_leader_email,
      CASE WHEN nle.regions ILIKE '%US-CANADA%' THEN 'USA'
           WHEN nle.regions ILIKE '%INDIA%'     THEN 'INDIA'
           ELSE 'ROW' END AS business_region,
      CASE WHEN nle.active = 'Yes' AND zs.date_of_exit IS NOT NULL
                AND zs.date_of_exit < nle.snapshot_date::date THEN 'No'
           ELSE nle.active END AS active,
      uce.reference_key,
      uce.parent_id,
      uce.call_status_category,
      uce.call_duration,
      uce.total_duration_seconds,
      uce.vendor_category
    FROM stage_brightchamps.neo_lead_eligibility_etl nle
      LEFT JOIN zoho_status zs ON zs.email = nle.email
      LEFT JOIN stage_brightchamps.neo_lead_eligibility_etl nle1
        ON nle.manager = nle1.name AND nle.snapshot_date = nle1.snapshot_date
      LEFT JOIN stage_brightchamps.neo_lead_eligibility_etl nle2
        ON nle.business_leader = nle2.name AND nle.snapshot_date = nle2.snapshot_date
      LEFT JOIN stage_brightchamps.unified_call_etl uce
        ON lower(trim(nle.email)) = lower(trim(uce.agent_email))
        AND CASE WHEN nle.regions ILIKE '%US-CANADA%'
                      AND (uce.start_time + interval '330 minutes')::time < time '18:00'
                   THEN date(uce.start_time + interval '330 minutes') - 1
                 ELSE date(uce.start_time + interval '330 minutes') END = date(nle.snapshot_date)
        AND (
          (nle.regions ILIKE '%INDIA%' AND uce.vendor_category = 'Manual-Call')
          OR nle.regions NOT ILIKE '%INDIA%'
        )
    WHERE nle.ROLE = 'Hunter'   -- plain Hunter only; use ILIKE '%Hunter%' to include OJT-Hunter / Team Lead-Hunter / Training-Hunter
      AND nle.regions NOT ILIKE '%SEA%'
      AND nle.regions NOT ILIKE '%Vietnam%'
      AND date(nle.snapshot_date) = DATE(current_timestamp + interval '5:30 hours') - 1
  ),
  per_agent AS (
    SELECT snapshot_date, snapshot_day, email, business_region, manager_email, business_leader_email, active,
           MAX(CASE WHEN week_off ILIKE '%' || snapshot_day || '%' THEN 1 ELSE 0 END) AS is_week_off,
           COUNT(reference_key)                                                        AS calls_by_agent,
           COUNT(DISTINCT parent_id)                                                   AS unique_calls,
           COUNT(reference_key) FILTER (WHERE call_status_category IN ('Picked','Not Picked')) AS connected_calls,
           COUNT(DISTINCT parent_id) FILTER (WHERE call_status_category IN ('Picked','Not Picked')) AS unique_connected,
           COUNT(reference_key) FILTER (WHERE call_status_category = 'Picked')          AS picked_calls,
           COUNT(DISTINCT parent_id) FILTER (WHERE call_status_category = 'Picked')      AS unique_picked,
           SUM(call_duration)                                                          AS talk_time_seconds,
           SUM(total_duration_seconds)                                                 AS total_duration_seconds
    FROM call_per_shift_date
    GROUP BY 1,2,3,4,5,6,7
  )
-- Replace the line below with the final SELECT from each question (#8–#14):
SELECT * FROM per_agent;
```

---

## 8. Avg calls per SM per day

**Definition:** Total team calls ÷ active not-on-weekoff SM count for the date. Measures average call productivity per Hunter per working day (R8). For avg unique parents per SM, see #9. For avg total duration per SM, see #10.

**Source table:** `stage_brightchamps.unified_call_etl` + `stage_brightchamps.neo_lead_eligibility_etl` + `prashashak.zoho_employees` (shared base CTE above).

**Grain:** Scalar (one row). Default window: yesterday IST.

**SQL — Overall:**
```sql
SELECT
  ROUND(SUM(calls_by_agent)::numeric FILTER (WHERE active='Yes' AND is_week_off=0)
        / NULLIF(COUNT(DISTINCT email) FILTER (WHERE active='Yes' AND is_week_off=0),0), 2) AS avg_calls_per_sm
FROM per_agent;
```

**SQL — Excl. SEA:** Already excluded by default via R12.

**Gotcha:** Denominator = active + not-on-weekoff SMs. SMs who dialled zero calls are in the denominator (correctly penalising the average) but contribute 0 to the numerator.

**Cross-validate:** `avg_calls_per_sm × COUNT(DISTINCT email active not-on-weekoff) ≈ SUM(calls_by_agent) FILTER (WHERE active='Yes' AND is_week_off=0)` (within rounding). `avg_calls_per_sm <= MAX(calls_by_agent)` across any individual SM in `per_agent`.

---

## 9. Avg unique parents touched, connected & picked per SM per day

**Definition:** Average number of distinct parents reached per active not-on-weekoff Hunter per day, at three funnel stages: **Touched** (any call attempt, regardless of outcome), **Connected** (call reached the device — Picked + Not Picked), **Picked** (parent actually answered). All three share the same denominator (R8) and are returned in a single query.

**Source table:** `stage_brightchamps.unified_call_etl` + `stage_brightchamps.neo_lead_eligibility_etl` + `prashashak.zoho_employees` (shared base CTE above).

**Grain:** Scalar (three columns). Default window: yesterday IST.

**SQL — Overall:**
```sql
SELECT
  ROUND(SUM(unique_calls)::numeric     FILTER (WHERE active='Yes' AND is_week_off=0)
        / NULLIF(COUNT(DISTINCT email) FILTER (WHERE active='Yes' AND is_week_off=0),0), 2) AS avg_unique_touched_per_sm,
  ROUND(SUM(unique_connected)::numeric FILTER (WHERE active='Yes' AND is_week_off=0)
        / NULLIF(COUNT(DISTINCT email) FILTER (WHERE active='Yes' AND is_week_off=0),0), 2) AS avg_unique_connected_per_sm,
  ROUND(SUM(unique_picked)::numeric    FILTER (WHERE active='Yes' AND is_week_off=0)
        / NULLIF(COUNT(DISTINCT email) FILTER (WHERE active='Yes' AND is_week_off=0),0), 2) AS avg_unique_picked_per_sm
FROM per_agent;
```

**SQL — Excl. SEA:** Already excluded by default via R12.

**Gotcha:** `unique_calls`, `unique_connected`, and `unique_picked` in `per_agent` are each `COUNT(DISTINCT parent_id)` computed **per agent**. Summing these across SMs slightly overcounts when the same parent was contacted by more than one SM — a parent shared across two agents counts once in each agent's total. For an average-per-SM metric this is the correct approach (it reflects each SM's individual reach). Do not compare `SUM(unique_calls across active SMs)` directly to a company-level `COUNT(DISTINCT parent_id)` — use `COUNT(DISTINCT parent_id)` on the raw `call_per_shift_date` CTE instead.

The three columns form a natural funnel: `avg_unique_touched_per_sm >= avg_unique_connected_per_sm >= avg_unique_picked_per_sm` always. The rigour target for unique picked is 25/day per SM (#12).

**Cross-validate:** `avg_unique_touched_per_sm >= avg_unique_connected_per_sm >= avg_unique_picked_per_sm` (funnel order). Denominator = active not-on-weekoff SM count, same as #8 and #10. `avg_unique_picked_per_sm × active_not_on_weekoff_sm_count ≈ SUM(unique_picked) FILTER (WHERE active='Yes' AND is_week_off=0)`.

---

## 10. Avg duration & talk time per SM per day

**Definition:** Two related averages per active not-on-weekoff Hunter per working day (R8, R13), returned in a single query:
- **`avg_total_dur_min_per_sm`** — total duration (ringing + talk) ÷ SM count, in minutes. Includes time spent on ringing even for unanswered calls.
- **`avg_talk_time_min_per_sm`** — talk time only (`call_duration`) ÷ SM count, in minutes. Excludes ringing; zero for Not Picked and Failed calls.

For avg calls per SM, see #8. For avg unique parents per SM, see #9.

**Source table:** `stage_brightchamps.unified_call_etl` + `stage_brightchamps.neo_lead_eligibility_etl` + `prashashak.zoho_employees` (shared base CTE above).

**Grain:** Scalar (two columns). Default window: yesterday IST.

**SQL — Overall:**
```sql
SELECT
  ROUND(SUM(total_duration_seconds)::numeric FILTER (WHERE active='Yes' AND is_week_off=0)
        / NULLIF(COUNT(DISTINCT email) FILTER (WHERE active='Yes' AND is_week_off=0),0)
        / 60.0, 2) AS avg_total_dur_min_per_sm,
  ROUND(SUM(talk_time_seconds)::numeric      FILTER (WHERE active='Yes' AND is_week_off=0)
        / NULLIF(COUNT(DISTINCT email) FILTER (WHERE active='Yes' AND is_week_off=0),0)
        / 60.0, 2) AS avg_talk_time_min_per_sm
FROM per_agent;
```

**SQL — Excl. SEA:** Already excluded by default via R12.

**Gotcha:** `avg_total_dur_min_per_sm >= avg_talk_time_min_per_sm` always — total duration includes ringing on top of talk time. The gap between the two reflects time spent on unanswered calls. Both use the same denominator as #8 and #9 (active not-on-weekoff SM count). The 60 min rigour floor in #13 is checked against `total_duration_seconds`, not talk time.

**Cross-validate:** `avg_total_dur_min_per_sm >= avg_talk_time_min_per_sm` (must hold — total >= talk). `avg_total_dur_min_per_sm × active_not_on_weekoff_sm_count ≈ SUM(total_duration_seconds)/60` for active not-on-weekoff SMs. `avg_talk_time_min_per_sm × active_not_on_weekoff_sm_count ≈ SUM(talk_time_seconds)/60` for active not-on-weekoff SMs.

---

## 14.B.2 — SM RIGOUR LISTS (row-level operational queries)

These entries return lists of SMs for manager follow-up and operational reporting — they are row-level queries, not aggregate metrics. The same shared base CTE from 14.B applies to all entries below.

---

## 11. Active SM list

**Definition:** All active SMs on the target date grouped by business region (USA / INDIA / ROW). Includes both on-weekoff and not-on-weekoff SMs — a full active roster snapshot.

**Source table:** `stage_brightchamps.neo_lead_eligibility_etl` + `prashashak.zoho_employees` (base CTE above; no call data required for this list).

**Grain:** One row per active SM. Default window: yesterday IST.

**SQL — Overall:**
```sql
SELECT business_region, email
FROM per_agent
WHERE active='Yes'
ORDER BY business_region, email;
```

**SQL — Excl. SEA:** Already excluded by default via R12.

**Gotcha:** Includes week-off SMs (`is_week_off=1`). Add `AND is_week_off=0` to restrict to "should be dialling today" SMs.

**Cross-validate:** `COUNT(#11 rows where is_week_off=0) = active not-on-weekoff SM count` (#8–#10 denominator). Total active SM count = on-weekoff + not-on-weekoff; filter by `is_week_off=1` or `is_week_off=0` to see each group. COUNT here should be stable day-over-day unless roster changes occur.

---

## 12. SMs below 25 unique parents

**Definition:** Active, not-on-weekoff SMs below the daily unique-picked-parents target (default 25). "Meaningfully touching" = the parent answered the call (`call_status_category = 'Picked'`), counted as `COUNT(DISTINCT parent_id)` where Picked. Returns a detail list and a count summary.

**Source table:** `stage_brightchamps.unified_call_etl` + `stage_brightchamps.neo_lead_eligibility_etl` + `prashashak.zoho_employees` (shared base CTE above).

**Grain:** One row per underperforming SM (detail list) or scalar (count summary). Default window: yesterday IST. Threshold: 25 unique picked parents/day (configurable).

**SQL — Overall:**
```sql
-- Detail list
SELECT business_region, email,
       unique_picked       AS unique_parents_picked,
       picked_calls,
       calls_by_agent
FROM per_agent
WHERE active = 'Yes' AND is_week_off = 0 AND unique_picked < 25
ORDER BY unique_picked ASC, business_region, email;

-- Count summary
SELECT
  COUNT(DISTINCT email) FILTER (WHERE active='Yes' AND is_week_off=0)                       AS sm_eligible,
  COUNT(DISTINCT email) FILTER (WHERE active='Yes' AND is_week_off=0 AND unique_picked < 25) AS sm_below_25_picked_parents
FROM per_agent;
```

**SQL — Excl. SEA:** Already excluded by default via R12.

**Gotcha:** Target is unique PICKED parents (parent answered), not just dialled. An SM who dialled 100 parents but none answered scores 0 unique_picked and appears here. `avg_unique_picked_per_sm` from #9 is the company-wide average for the same metric this list is measuring.

**Cross-validate:** `sm_below_25_picked_parents <= sm_eligible`. Every SM in the detail list must have `unique_picked < 25`. Zero-call SMs will appear here with `unique_picked = 0`. `sm_eligible` here = active not-on-weekoff SM count from #8–#10 denominator.

---

## 13. SMs below 60 min call time

**Definition:** Active, not-on-weekoff SMs below the daily total-duration floor (default 60 minutes). "Call time" = `total_duration_seconds` (ringing + talk), not just talk time. Returns a detail list and a count summary.

**Source table:** `stage_brightchamps.unified_call_etl` + `stage_brightchamps.neo_lead_eligibility_etl` + `prashashak.zoho_employees` (shared base CTE above).

**Grain:** One row per underperforming SM (detail) or scalar (count). Default window: yesterday IST. Threshold: 60 min = 3,600 seconds (configurable).

**SQL — Overall:**
```sql
-- Detail list
SELECT business_region, email,
       ROUND(total_duration_seconds/60.0, 2) AS total_duration_min,
       ROUND(talk_time_seconds/60.0, 2)      AS talk_time_min,
       calls_by_agent
FROM per_agent
WHERE active = 'Yes' AND is_week_off = 0 AND total_duration_seconds < 60 * 60
ORDER BY total_duration_seconds ASC, business_region, email;

-- Count summary
SELECT
  COUNT(DISTINCT email) FILTER (WHERE active='Yes' AND is_week_off=0)                                   AS sm_eligible,
  COUNT(DISTINCT email) FILTER (WHERE active='Yes' AND is_week_off=0 AND total_duration_seconds < 3600) AS sm_below_60min
FROM per_agent;
```

**SQL — Excl. SEA:** Already excluded by default via R12.

**Gotcha:** Threshold is TOTAL duration (ringing + talk), not talk time alone. If you want a talk-time floor instead, replace `total_duration_seconds` with `talk_time_seconds`. 60 * 60 = 3600 seconds.

**Cross-validate:** `sm_below_60min <= sm_eligible`. Zero-call SMs will appear here with `total_duration_seconds = 0`. `sm_eligible` here = `sm_eligible` from #12 (same population). Every SM in #13 detail must show `total_duration_min < 60`.

---

## 14. Combined shortfall list

**Definition:** Active, not-on-weekoff SMs missing at least one of the two daily targets: fewer than 25 unique picked parents (#12) OR less than 60 min total duration (#13). One row per SM with both flag columns so a manager sees which target(s) were missed.

**Source table:** `stage_brightchamps.unified_call_etl` + `stage_brightchamps.neo_lead_eligibility_etl` + `prashashak.zoho_employees` (shared base CTE above).

**Grain:** One row per underperforming SM. Default window: yesterday IST. Thresholds: 25 unique picked parents/day, 60 min total duration/day (both configurable).

**SQL — Overall:**
```sql
SELECT business_region, email,
       unique_picked                              AS unique_parents_picked,
       ROUND(total_duration_seconds/60.0, 2)      AS total_duration_min,
       calls_by_agent,
       CASE WHEN unique_picked < 25          THEN 'Yes' ELSE 'No' END AS below_25_picked_parents,
       CASE WHEN total_duration_seconds < 3600 THEN 'Yes' ELSE 'No' END AS below_60_min
FROM per_agent
WHERE active = 'Yes' AND is_week_off = 0
  AND (unique_picked < 25 OR total_duration_seconds < 3600)
ORDER BY unique_picked ASC, total_duration_seconds ASC;
```

**SQL — Excl. SEA:** Already excluded by default via R12.

**Gotcha:** The WHERE uses OR — an SM missing only one target is included. SMs missing both will show both flags as 'Yes'. Zero-call SMs always appear here (missing both targets).

**Cross-validate:** Every row in #14 must appear in #12 detail list OR #13 detail list (or both). `COUNT(#14) = COUNT(#12 detail) + COUNT(#13 detail) - COUNT(SMs missing both targets)` (inclusion-exclusion). `COUNT(#14) <= active not-on-weekoff SM count`.

---

## 14.E — WEEKLY (and MONTHLY) ROLLUPS — SM-day basis

**Definition:** Week-level (or month-level) call metrics — total calls, avg calls per SM per day, avg total duration and talk time per SM per day — aggregated over an agent-day base. Denominator = active not-on-weekoff SM-days (NOT distinct SMs), so an SM working 5 of 7 days counts as 5 SM-days. Consistent with daily #8–#10 and rolls up cleanly to manager/BL/company level.

**Source table:** `stage_brightchamps.unified_call_etl` + `stage_brightchamps.neo_lead_eligibility_etl` + `prashashak.zoho_employees` (same three tables as 14.B, extended to a date range).

**Grain:** One row per (week_start, group_by_level). Durations in **hours** (`/ 3600.0`) for weekly rollups.

**Conventions:**
- Week = Monday-start via `date_trunc('week', snapshot_date)`. For month: `date_trunc('month', ...)`.
- Week-off = exact match `week_off = snapshot_day` (one week-off day per agent — confirmed).
- USA roll-back (R9) and India Manual-Call rule (R10) baked into the agent-day base, same as 14.B.

**SQL — Overall:**
```sql
WITH
  zoho_status AS (
    SELECT employee_id,
           split_part(email,'@',1) || '@team.brightchamps.com' AS email,
           coalesce(date_of_exit::date, CURRENT_DATE) AS date_of_exit
    FROM prashashak.zoho_employees
  ),
  call_per_shift_date AS (
    SELECT
      date(nle.snapshot_date) AS snapshot_date,
      TO_CHAR(nle.snapshot_date,'FMDay') AS snapshot_day,
      nle.email,
      nle.role,
      nle.week_off,
      nle1.email AS manager_email,
      nle2.email AS business_leader_email,
      CASE WHEN nle.active = 'Yes' AND zs.date_of_exit IS NOT NULL
                AND zs.date_of_exit < nle.snapshot_date::date THEN 'No'
           ELSE nle.active END AS active,
      uce.reference_key,
      uce.call_duration,
      uce.total_duration_seconds
    FROM stage_brightchamps.neo_lead_eligibility_etl nle
      LEFT JOIN zoho_status zs ON zs.email = nle.email
      LEFT JOIN stage_brightchamps.neo_lead_eligibility_etl nle1
        ON nle.manager = nle1.name AND nle.snapshot_date = nle1.snapshot_date
      LEFT JOIN stage_brightchamps.neo_lead_eligibility_etl nle2
        ON nle.business_leader = nle2.name AND nle.snapshot_date = nle2.snapshot_date
      LEFT JOIN stage_brightchamps.unified_call_etl uce
        ON lower(trim(nle.email)) = lower(trim(uce.agent_email))
        AND CASE WHEN nle.regions ILIKE '%US-CANADA%'
                      AND (uce.start_time + interval '330 minutes')::time < time '18:00'
                   THEN date(uce.start_time + interval '330 minutes') - 1
                 ELSE date(uce.start_time + interval '330 minutes') END = date(nle.snapshot_date)
        AND (
          (nle.regions ILIKE '%INDIA%' AND uce.vendor_category = 'Manual-Call')
          OR nle.regions NOT ILIKE '%INDIA%'
        )
    WHERE nle.ROLE = 'Hunter'
      AND nle.regions NOT ILIKE '%SEA%'
      AND nle.regions NOT ILIKE '%Vietnam%'
      -- widen to the week/month of interest, e.g. last full week:
      AND date(nle.snapshot_date) >= date_trunc('week', DATE(current_timestamp + interval '5:30 hours')) - interval '7 days'
      AND date(nle.snapshot_date) <  date_trunc('week', DATE(current_timestamp + interval '5:30 hours'))
  ),
  agg AS (   -- ONE ROW PER AGENT PER DAY
    SELECT
      snapshot_date, snapshot_day, email, manager_email, business_leader_email,
      MAX(active)   AS active,
      MAX(week_off) AS week_off,
      MAX(CASE WHEN week_off = snapshot_day THEN 1 ELSE 0 END)        AS on_weekoff,
      MAX(CASE WHEN reference_key IS NOT NULL THEN 1 ELSE 0 END)       AS dialled,
      COUNT(reference_key)                       AS agent_call_count,
      COALESCE(SUM(total_duration_seconds),0)    AS agent_total_duration,
      COALESCE(SUM(call_duration),0)             AS agent_call_time
    FROM call_per_shift_date
    GROUP BY snapshot_date, snapshot_day, email, manager_email, business_leader_email
  )
SELECT
  date_trunc('week', snapshot_date)::date AS week_start,
  business_leader_email,                       -- drop for company-level; swap to manager_email for TM-level
  COUNT(*) FILTER (WHERE active='Yes')                                      AS total_agent_days,
  COUNT(*) FILTER (WHERE active='Yes' AND on_weekoff=1)                     AS agent_weekoff_days,
  COUNT(*) FILTER (WHERE active='Yes' AND on_weekoff=0)                     AS active_sm_days,        -- DENOMINATOR
  COUNT(*) FILTER (WHERE active='Yes' AND on_weekoff=0 AND dialled=1)       AS agents_dialled_days,
  COUNT(*) FILTER (WHERE active='Yes' AND on_weekoff=0 AND dialled=0)       AS agents_not_dialled_days,
  SUM(agent_call_count) FILTER (WHERE active='Yes' AND on_weekoff=0)        AS total_calls_in_week,
  ROUND(
    SUM(agent_call_count) FILTER (WHERE active='Yes' AND on_weekoff=0)::numeric
    / NULLIF(COUNT(*) FILTER (WHERE active='Yes' AND on_weekoff=0),0), 2)   AS avg_calls_per_sm_per_day,
  ROUND(
    (SUM(agent_call_time) FILTER (WHERE active='Yes' AND on_weekoff=0)::numeric
     / NULLIF(COUNT(*) FILTER (WHERE active='Yes' AND on_weekoff=0),0)) / 3600.0, 2)
                                                                            AS avg_talk_time_per_sm_per_day_hours,
  ROUND(
    (SUM(agent_total_duration) FILTER (WHERE active='Yes' AND on_weekoff=0)::numeric
     / NULLIF(COUNT(*) FILTER (WHERE active='Yes' AND on_weekoff=0),0)) / 3600.0, 2)
                                                                            AS avg_total_duration_per_sm_per_day_hours
FROM agg
GROUP BY 1, 2
ORDER BY 1 DESC, 2;
```

**Grain variants (change SELECT/GROUP BY only — the `agg` base is unchanged):**
- **Week only (all SMs):** `GROUP BY 1`, drop `business_leader_email` from SELECT.
- **Week × Business Leader:** as written (`GROUP BY 1, 2` with `business_leader_email`).
- **Week × Team Manager:** swap `business_leader_email` → `manager_email`.
- **Month level:** replace `date_trunc('week', ...)` with `date_trunc('month', ...)` in both the SELECT and the date-range predicate.

**SQL — Excl. SEA:** Already excluded by default via roster filter (`regions NOT ILIKE '%SEA%' AND regions NOT ILIKE '%Vietnam%'`).

**Gotcha:** SM-day denominator, NOT distinct SMs. Week-offs are excluded from both numerator and denominator. Week = Monday-start; durations in hours (not minutes). Don't divide by distinct agents — it understates the rate and is distorted by week-offs.

**Cross-validate:** `avg_calls_per_sm_per_day × active_sm_days = total_calls_in_week` (within rounding). `total_agent_days = agent_weekoff_days + active_sm_days`. `agents_dialled_days + agents_not_dialled_days = active_sm_days`. Sum of `total_calls_in_week` across all weeks in a date range should equal the sum of daily active not-on-weekoff SM calls across the same days.

---

## 14.C — Gotchas

- **Two families, two date logics.** Call-log (14.A) uses raw `start_time` IST with no roll-back and no India filter. SM-scoped (14.B) applies USA roll-back + India Manual-Call rule. Do not cross them.
- **India = Manual-Call only** in SM-scoped queries. Including Dialler/AI for India agents over-joins empty/foreign rows.
- **USA roll-back is US-CANADA only.** Forgetting it mis-dates US calls.
- **Denominator discipline:** every SM average divides by *not-on-weekoff active* agents; week-off agents' calls are excluded from numerators too.
- **NULL agent_email** (Knowlarity / AI) never attributes to an SM — SM-scoped metrics are human-dialled only.
- **RM (Relationship Manager) is a post-enrollment / URI-stage role and is excluded from call rigour.** The base CTE filters `ROLE = 'Hunter'`; to include OJT/Team Lead/Training Hunter variants, widen to `role ILIKE '%Hunter%'` and confirm scope with the user.
- **Failed** stays in total dialled but is excluded from connected and picked.
- **Unique parent double-count (#9):** `unique_calls`, `unique_connected`, `unique_picked` in `per_agent` are per-agent DISTINCT counts — SUM across SMs overcounts parents touched by more than one SM. For a company-level global unique-parent figure, run `COUNT(DISTINCT parent_id)` on `call_per_shift_date` directly, not `SUM(unique_calls)` across `per_agent`.
- **Threshold targets (#12–#14)** apply to active + not-on-weekoff SMs only. "Meaningfully touching" = unique PICKED parents, default 25/day. "Call time" floor = TOTAL duration (`total_duration_seconds`), default 60 min/day. #14 combines with OR (misses at least one target).
- **Weekly/monthly rollups (14.E)** use an SM-DAY denominator, NOT distinct SMs. Week = Monday-start, week-off = exact `week_off = snapshot_day`, durations in HOURS. "Avg per SM per day" over a week = weekly total ÷ active-not-weekoff SM-days.

---

*End of Section 14.*