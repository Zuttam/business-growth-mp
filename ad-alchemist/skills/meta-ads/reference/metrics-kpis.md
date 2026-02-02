# Metrics & KPIs Reference

## Primary Metrics by Objective

| Objective | Primary KPI | Secondary KPIs |
|-----------|------------|----------------|
| Awareness | Reach, CPM | Frequency, Ad Recall Lift |
| Traffic | CPC, CTR | Landing Page Views, Bounce Rate |
| Engagement | CPE | Comments, Shares, Saves |
| Leads | CPL, Lead Volume | Form Completion Rate, Lead Quality |
| App Install | CPI | In-App Events, Retention |
| Sales | ROAS, CPA | Conversion Rate, AOV, LTV |

## Metric Definitions

### Delivery Metrics

**Impressions**
- Number of times your ad was shown
- One person can generate multiple impressions

**Reach**
- Number of unique people who saw your ad
- Always ≤ Impressions

**Frequency**
- Average times each person saw your ad
- Formula: Impressions ÷ Reach
- Watch for: > 3 (audience fatigue)

**CPM (Cost Per Mille)**
- Cost per 1,000 impressions
- Formula: (Spend ÷ Impressions) × 1,000
- Indicates: Auction competitiveness

### Engagement Metrics

**CTR (Click-Through Rate)**
- Percentage of impressions that resulted in clicks
- Formula: (Clicks ÷ Impressions) × 100
- Types: Link CTR (to website), All CTR (any click)

**CPC (Cost Per Click)**
- Cost for each link click
- Formula: Spend ÷ Link Clicks

**Engagement Rate**
- All post interactions ÷ Reach
- Includes: Likes, comments, shares, saves

### Conversion Metrics

**Conversions**
- Completed desired actions (purchases, sign-ups, etc.)
- Based on Pixel or Conversions API data

**Conversion Rate**
- Percentage of clicks that convert
- Formula: (Conversions ÷ Link Clicks) × 100

**CPA (Cost Per Action/Acquisition)**
- Cost for each conversion
- Formula: Spend ÷ Conversions

**ROAS (Return on Ad Spend)**
- Revenue generated per dollar spent
- Formula: Conversion Value ÷ Spend
- Example: 3x ROAS = $3 revenue per $1 spent

### Video Metrics

**Video Views**
- 3-second views (most common)
- ThruPlays (15+ seconds or complete)

**Hook Rate**
- Percentage watching past 3 seconds
- Formula: (3-sec views ÷ Impressions) × 100
- Target: > 30%

**Hold Rate**
- Percentage watching to completion
- Formula: (Completions ÷ 3-sec views) × 100
- Target: > 15%

**Average Watch Time**
- Mean duration viewers watched
- Good indicator of content quality

## Benchmarks (2026)

### By Industry

| Industry | Avg CTR | Avg CPC | Avg CPM | Avg Conv Rate |
|----------|---------|---------|---------|---------------|
| E-commerce | 1.0-1.5% | $0.50-1.50 | $8-15 | 2-4% |
| B2B/SaaS | 0.5-1.0% | $1.50-4.00 | $10-20 | 1-3% |
| Lead Gen | 0.8-1.5% | $1.00-3.00 | $8-18 | 5-15% |
| App Install | 0.5-1.0% | $0.50-2.00 | $5-12 | 1-3% |
| Local | 1.0-2.0% | $0.50-2.00 | $6-12 | 3-8% |

### General Guidelines

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| CTR | < 0.5% | 0.5-1% | 1-2% | > 2% |
| CPC | > $3 | $1-3 | $0.50-1 | < $0.50 |
| CPM | > $20 | $10-20 | $5-10 | < $5 |
| Frequency | > 5 | 3-5 | 2-3 | < 2 |
| Hook Rate | < 20% | 20-30% | 30-40% | > 40% |

*Note: Benchmarks vary significantly by industry, region, and objective*

## Learning Phase

### What Is Learning Phase?

Meta's algorithm needs data to optimize. During learning phase:
- Performance fluctuates
- CPA may be higher
- Algorithm is testing and learning

### Exiting Learning Phase

**Requirement**: 50 conversion events in 7 days per ad set

**Tips for faster exit**:
- Use higher-funnel events (ATC vs Purchase) if conversion volume is low
- Consolidate ad sets to concentrate data
- Ensure adequate budget ($50+ per day per ad set)
- Avoid significant edits that reset learning

### Edits That Reset Learning

- Budget changes > 20%
- Bid strategy changes
- Audience changes
- Creative additions/removals
- Optimization event changes
- Extended pauses (7+ days)

### Edits That Don't Reset Learning

- Small budget changes (< 20%)
- Bid amount tweaks
- Ad scheduling
- Adding new ads to existing ad set

## Performance Analysis Framework

### The Diagnostic Tree

```
Is CPA above target?
├── Yes → Check CTR
│   ├── CTR is low → Creative problem
│   │   ├── Hook not engaging
│   │   ├── Visual not stopping scroll
│   │   └── Wrong audience/creative match
│   └── CTR is good → Conversion problem
│       ├── Landing page issue
│       ├── Offer not compelling
│       ├── Message mismatch
│       └── Tracking issue
└── No → Is volume sufficient?
    ├── Yes → Scale opportunity
    └── No → Budget/audience constraint
```

### Metric Relationships

**High CPM + Low CTR**
- Creative isn't resonating
- Audience mismatch
- Solution: New creative, test audiences

**Good CTR + High CPA**
- Landing page problem
- Offer problem
- Audience quality issue
- Solution: Improve page, refine audience

**Good CTR + Good CPA + Low Volume**
- Audience too small
- Budget too low
- Learning phase stuck
- Solution: Expand audience, increase budget

**High Frequency + Rising CPA**
- Audience exhaustion
- Creative fatigue
- Solution: Expand audience, refresh creative

## Attribution

### Attribution Models

**Last-Click**
- Credit goes to last clicked ad
- Undervalues awareness/consideration

**Data-Driven (Recommended)**
- Meta's algorithm assigns credit
- Most accurate for Meta campaigns

**Incrementality**
- Measures true lift from ads
- Requires holdout testing

### Attribution Windows

| Window | Best For |
|--------|----------|
| 1-day click | Impulse purchases, immediate conversions |
| 7-day click | Most e-commerce, considered purchases |
| 1-day view | Awareness contribution measurement |

### Comparing to Other Platforms

- Meta typically shows higher conversions than GA4
- Expected variance: 20-50% higher in Meta
- Reasons: View-through, cross-device, different attribution models

## Reporting Best Practices

### Daily Monitoring

Check these metrics daily:
- Spend vs budget
- CPA vs target
- Any ads in "Learning Limited"
- Major performance swings

### Weekly Analysis

Review these weekly:
- CTR trends
- Frequency (audience fatigue)
- Creative performance comparison
- Audience performance comparison

### Monthly Review

Deep dive monthly:
- ROAS and profitability
- Top/bottom performers
- Audience insights
- Creative learning
- Strategic adjustments

### Reporting Template

```markdown
## Weekly Performance Report: [Date Range]

### Summary
- Total Spend: $X
- Total Conversions: X
- Blended CPA: $X
- Blended ROAS: Xx

### Highlights
- [Top performing creative/audience]
- [Biggest win this week]

### Concerns
- [Underperformers]
- [Rising CPAs]

### Actions Taken
- [Changes made]

### Next Week Focus
- [Priorities]
```

## Key Metric Formulas

| Metric | Formula |
|--------|---------|
| CTR | (Clicks ÷ Impressions) × 100 |
| CPC | Spend ÷ Clicks |
| CPM | (Spend ÷ Impressions) × 1,000 |
| CPA | Spend ÷ Conversions |
| ROAS | Revenue ÷ Spend |
| Frequency | Impressions ÷ Reach |
| Conv Rate | (Conversions ÷ Clicks) × 100 |
| Hook Rate | (3-sec views ÷ Impressions) × 100 |
| Hold Rate | (Completions ÷ 3-sec views) × 100 |
