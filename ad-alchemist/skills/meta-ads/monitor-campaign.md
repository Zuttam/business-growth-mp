---
name: monitor-campaign
description: |
  Campaign monitoring and optimization workflow for Meta ads. Use when reviewing
  performance, analyzing metrics, or making optimization decisions.
---

# Meta Ads Campaign Monitoring Workflow

Follow these steps to analyze campaign performance and generate optimization recommendations.

---

## Step 1: Load Campaign Context

Check for existing campaign plan and performance data:

```
.business_growth/marketing/paid/meta/campaigns/campaign_[name]/
├── PLAN.md         # Original campaign strategy
└── PERFORMANCE.md  # Historical performance data
```

If monitoring an existing campaign:
- Read the PLAN.md to understand goals and strategy
- Read PERFORMANCE.md for historical context

If this is a new campaign being monitored for the first time:
- Ask for the campaign name to create the tracking file

---

## Step 2: Gather Current Metrics

**Option A: User Provides Metrics**

Ask the user to provide current performance data:

| Metric | Value |
|--------|-------|
| Date Range | |
| Amount Spent | |
| Impressions | |
| Reach | |
| Frequency | |
| Clicks (Link) | |
| CTR (Link) | |
| CPC | |
| CPM | |
| Conversions | |
| CPA | |
| Conversion Value | |
| ROAS | |

**Option B: Browser Automation (if available)**

If user grants access to Ads Manager:
1. Navigate to Ads Manager
2. Select the campaign
3. Extract metrics from the dashboard
4. Screenshot for records

---

## Step 3: Performance Analysis

### Benchmark Comparison

Compare metrics against industry benchmarks:

| Metric | Your Value | Benchmark | Status |
|--------|-----------|-----------|--------|
| CTR | [X]% | 1-2% | 🟢/🟡/🔴 |
| CPC | $[X] | $0.50-2.00 | 🟢/🟡/🔴 |
| CPM | $[X] | $5-15 | 🟢/🟡/🔴 |
| Frequency | [X] | <3 | 🟢/🟡/🔴 |
| CPA | $[X] | [Target] | 🟢/🟡/🔴 |
| ROAS | [X]x | [Target]x | 🟢/🟡/🔴 |

### Status Indicators
- 🟢 **Green**: Meeting or exceeding targets
- 🟡 **Yellow**: Within acceptable range, monitor closely
- 🔴 **Red**: Below targets, action needed

### Learning Phase Check

For each ad set, verify:
- Has it received 50+ conversion events in the last 7 days?
- If not, it's still in learning phase - avoid major changes

### Diagnostic Questions

Based on metrics, identify the issue:

**High CPM + Low CTR** → Creative isn't resonating
- Creative fatigue
- Wrong audience
- Weak hook

**Good CTR + Low Conversions** → Landing page issue
- Page load speed
- Message mismatch
- Poor mobile experience

**Good Conversions + High CPA** → Efficiency problem
- Audience too narrow
- Bid strategy needs adjustment
- Scale too fast

**High Frequency** → Audience exhaustion
- Expand audiences
- Refresh creatives
- Add new ad sets

---

## Step 4: Generate Recommendations

Based on analysis, provide specific recommendations.

### Creative Recommendations

If CTR is below benchmark:
- [ ] Test new hooks (first 125 characters)
- [ ] Try different visual styles (UGC vs polished)
- [ ] Test new formats (video vs static)
- [ ] Refresh imagery (creative fatigue after 3-4 weeks)

### Audience Recommendations

If audience issues detected:
- [ ] Expand to broader targeting
- [ ] Test new interest combinations
- [ ] Create new lookalike audiences
- [ ] Adjust exclusions

### Budget Recommendations

Based on performance:
- **Scaling Up**: If CPA is at or below target, increase budget by 20-50% weekly
- **Scaling Down**: If CPA is 2x+ target, reduce budget or pause
- **Reallocation**: Shift budget from underperforming to top-performing ad sets

### Bid Strategy Recommendations

| Current Situation | Recommendation |
|------------------|----------------|
| Learning phase, limited data | Stay with Lowest Cost |
| Stable performance, want to scale | Consider Cost Cap |
| Hitting spend limits | Raise Cost Cap or try Bid Cap |
| Erratic CPA | Add Cost Cap for stability |

---

## Step 5: Action Plan

Create a prioritized action plan:

### Immediate Actions (Today)
1. [Highest priority action]
2. [Second priority action]

### This Week
1. [Medium-term action]
2. [Medium-term action]

### Next Review
- Schedule next review in [X] days
- Key metrics to watch: [List]

---

## Step 6: Update Tracking

Save the analysis to:

```
.business_growth/marketing/paid/meta/campaigns/campaign_[name]/PERFORMANCE.md
```

### Performance Log Entry

```markdown
## Performance Review: [Date]

### Metrics Snapshot
| Metric | Value | vs Target | vs Last Period |
|--------|-------|-----------|----------------|
| Spend | $X | - | +X% |
| Conversions | X | X% of target | +X% |
| CPA | $X | X% of target | -X% |
| ROAS | Xx | X% of target | +X% |
| CTR | X% | - | +X% |
| Frequency | X | - | +X% |

### Key Observations
1. [Observation]
2. [Observation]
3. [Observation]

### Actions Taken
1. [Action]
2. [Action]

### Next Review
- Date: [Date]
- Watch for: [Key things to monitor]
```

---

## Completion

After the analysis:

1. Summarize the campaign health (healthy, needs attention, critical)
2. Present the top 3 recommendations with rationale
3. Confirm any actions the user wants to take
4. Schedule the next review checkpoint
