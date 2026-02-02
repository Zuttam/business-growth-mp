# Optimization Rules Reference

## Golden Rules of Optimization

1. **Don't optimize too early**: Wait for statistical significance (50+ conversions)
2. **Don't optimize too often**: Major changes reset learning
3. **One change at a time**: Isolate variables to understand impact
4. **Trust the data**: Don't let emotions drive decisions
5. **Document everything**: Track what works for future campaigns

## When to Optimize

### The 7-Day Rule

- **Days 1-3**: Let it run. Don't touch anything.
- **Days 4-7**: Review trends. Make minor adjustments if needed.
- **Day 7+**: Make data-driven optimization decisions.

### Trigger Points for Action

| Signal | Action Threshold | Response |
|--------|-----------------|----------|
| CPA 2x+ target | After 7 days | Pause or major change |
| CPA 1.5x target | After 7 days | Test new creative/audience |
| Frequency > 3 | Any time | Expand audience or refresh creative |
| CTR drops 50%+ | After 3 days | Creative fatigue - refresh |
| Zero conversions | After 7 days | Troubleshoot or pause |
| No delivery | After 3 days | Check bid, audience, creative |

## Optimization Playbook

### Scenario 1: High CPA

**Diagnostic Questions:**
1. Is CTR good but conversions low? → Landing page issue
2. Is CTR low? → Creative issue
3. Is CPM high? → Audience too competitive or small
4. Is frequency high? → Audience exhaustion

**Actions to Take:**

If CTR is the problem:
- [ ] Test new hooks (first 125 characters)
- [ ] Try different creative formats
- [ ] Test UGC vs polished creative
- [ ] Review audience/creative match

If landing page is the problem:
- [ ] Check page load speed (< 3 seconds)
- [ ] Verify message match (ad ↔ page)
- [ ] Test mobile experience
- [ ] Simplify conversion path

If audience is the problem:
- [ ] Expand to broader targeting
- [ ] Test new interest combinations
- [ ] Create fresh lookalike audiences
- [ ] Remove restrictive exclusions

### Scenario 2: Creative Fatigue

**Symptoms:**
- CTR declining week over week
- Frequency climbing
- Same creative running 3+ weeks

**Actions to Take:**
1. Don't pause working ads immediately
2. Add new creative variations to test alongside
3. Iterate on winning concepts (new hooks, same idea)
4. Test new concepts if iteration isn't working
5. Gradually shift budget to new winners

### Scenario 3: No Delivery / Learning Limited

**Common Causes:**
- Audience too small (< 100K)
- Budget too low (< $20/day per ad set)
- Bid too low (if using bid cap)
- Event too rare (if using cost cap)
- Creative rejected

**Actions to Take:**
- [ ] Expand audience (remove restrictions)
- [ ] Increase budget (minimum $20-50/day per ad set)
- [ ] Switch to "Lowest Cost" bid strategy
- [ ] Use higher-funnel optimization event
- [ ] Review creative for policy violations

### Scenario 4: Ready to Scale

**Signals You're Ready:**
- CPA at or below target for 7+ days
- Consistent performance (low variance)
- Exited learning phase
- Room to expand audience

**Scaling Rules:**

**Budget Scaling:**
```
Conservative: +20% every 7 days
Moderate: +30-50% every 7 days
Aggressive: +50-100% (only for Advantage+)
```

**Why gradual scaling?**
- Large budget increases reset learning
- Algorithm needs time to adjust
- Protects against performance collapse

**Scaling Strategies:**

1. **Vertical Scaling** (increase budget)
   - Safest approach
   - 20-50% weekly increases
   - Monitor for CPA creep

2. **Horizontal Scaling** (add new ad sets)
   - Test new audiences
   - Duplicate winning creative to new ad sets
   - More testing capacity

3. **Campaign Duplication**
   - Launch new campaign with proven creative
   - Different objective or audience
   - Increases overall presence

## Budget Management

### Budget Reallocation

**When to reallocate:**
- Ad set significantly outperforming (CPA 50%+ better)
- Ad set significantly underperforming (CPA 50%+ worse)
- After 7 days of data

**How to reallocate:**
1. Reduce underperformer by 20-30%
2. Increase winner by same amount
3. Monitor for 3-5 days
4. Repeat if trend continues

### Pause Criteria

Pause an ad set when:
- [ ] CPA is 2x+ target after 7+ days
- [ ] Zero conversions after 500+ link clicks
- [ ] Frequency > 5 with declining performance
- [ ] Consistent underperformance vs other ad sets

### Don't Pause When:
- Still in learning phase (< 50 conversions)
- Less than 7 days of data
- Only slight underperformance (< 30% worse)
- Seasonal fluctuation expected

## Creative Optimization

### A/B Testing Framework

**Test One Variable at a Time:**
```
Round 1: Test hooks (same body, different hooks)
Round 2: Winner hook + test headlines
Round 3: Winner combo + test formats
Round 4: Winner combo + test audiences
```

**Statistical Significance:**
- Need 50+ conversions per variation
- Minimum 20 conversions for directional read
- Wait for consistent trend (3+ days)

### Creative Refresh Cadence

| Campaign Type | Refresh Frequency |
|---------------|-------------------|
| Always-on | Every 3-4 weeks |
| Promotional | Per promotion |
| Retargeting | Every 2-3 weeks |
| Seasonal | Per season |

### Managing Creative Inventory

**Recommended:**
- 3-5 active ads per ad set
- 2-3 concepts being tested at any time
- Pipeline of new concepts for refresh

**Creative Status Tracking:**
```
Active: Currently running well
Testing: Gathering data
Learning: Good but need more data
Fatigued: Performance declining
Paused: Stopped due to poor performance
```

## Audience Optimization

### Audience Expansion

When to expand:
- CPA at target but limited scale
- Frequency climbing
- Audience < 500K

How to expand:
1. Remove age/gender restrictions
2. Add related interests
3. Use larger lookalike sizes (2-5%)
4. Enable Advantage+ Audience

### Audience Consolidation

When to consolidate:
- Many ad sets with limited budget each
- Most ad sets stuck in learning
- Similar performance across ad sets

How to consolidate:
1. Combine similar audiences into one
2. Move to Campaign Budget Optimization
3. Let algorithm distribute budget

## Bid Strategy Optimization

### Bid Strategy Selection

| Situation | Recommended Strategy |
|-----------|---------------------|
| Starting out | Lowest Cost |
| Need volume | Lowest Cost |
| Need efficiency | Cost Cap |
| Strict CPA requirement | Bid Cap |
| E-commerce scaling | Min ROAS |

### When to Change Bid Strategy

**From Lowest Cost to Cost Cap:**
- When CPA is acceptable but want to scale
- Set cost cap at 110-120% of current CPA
- Gives algorithm efficiency target while scaling

**From Cost Cap to Lowest Cost:**
- When delivery is limited
- When you need more volume, even at higher CPA

## Troubleshooting Guide

### No Conversions

```
Check: Is Pixel firing correctly?
├── No → Fix Pixel implementation
└── Yes → Check: Is traffic reaching landing page?
    ├── No → Review ad/URL/tracking
    └── Yes → Check: Is conversion path working?
        ├── No → Fix landing page/funnel
        └── Yes → Check: Is audience right?
            ├── Maybe not → Test new audiences
            └── Yes → Check: Is offer compelling?
                └── Test new offers/creative
```

### Sudden Performance Drop

1. **Check for external factors**
   - Competitor activity
   - Seasonality
   - News/events affecting audience

2. **Check for technical issues**
   - Pixel firing correctly?
   - Landing page working?
   - Payment method active?

3. **Check for platform changes**
   - Algorithm updates
   - Policy changes
   - Increased competition

4. **Check campaign settings**
   - Budget depleted?
   - Schedule ended?
   - Audience exhausted?

### Performance Never Stabilizes

Possible causes:
- Audience too small (high variance)
- Too few conversions (insufficient data)
- Too much optimization (constant changes)
- Highly variable customer behavior

Solutions:
- Expand audiences
- Increase budget
- Stop making changes
- Use higher-funnel events temporarily
