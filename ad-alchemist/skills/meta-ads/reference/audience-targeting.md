# Audience Targeting Reference

## Targeting Philosophy (2026)

> "In the Andromeda era, creative IS targeting. Your ad creative determines who sees it as much as your audience settings."

### Key Principles

1. **Broader is often better**: Meta's algorithm finds converters within broad audiences
2. **Let creative do the targeting**: Speak directly to your ideal customer in the ad
3. **Layer, don't narrow**: Add interests rather than using AND conditions
4. **Trust the algorithm**: Advantage+ audiences often outperform manual targeting

## Audience Types

### 1. Broad Targeting

**What it is**: Minimal restrictions - just location, age (if needed), language

**When to use**:
- Daily budget > $100
- Good Pixel data (1000+ conversions)
- Strong, clear creative that self-selects audience

**Setup**:
```
Location: [Target country/region]
Age: 18-65+ (or slight restriction if needed)
Gender: All
Detailed Targeting: None
```

**Why it works**: Algorithm has maximum flexibility to find converters

### 2. Interest-Based Targeting

**What it is**: Target based on interests, behaviors, demographics

**When to use**:
- Testing which interests correlate with conversions
- Smaller budgets that need direction
- New accounts with limited Pixel data

**Setup strategies**:

**Interest Stack** (Recommended):
```
Include people who match:
Interest A OR Interest B OR Interest C
(Creates larger combined audience)
```

**Interest Layering**:
```
Include people who match:
Interest A AND Interest B
(Creates smaller, more specific audience)
```

**Behavior + Interest**:
```
Include: Purchase Behavior: Engaged Shoppers
AND Interest: [Product category]
```

### 3. Lookalike Audiences

**What it is**: Find people similar to your existing customers

**Source audiences** (best to worst):
1. Purchase/conversion events (best)
2. High-value customers (top 25% LTV)
3. Add-to-cart events
4. Website visitors (90-day)
5. Email list (1000+ emails)
6. Page/profile engagers (weakest)

**Lookalike sizes**:

| Size | Reach | Similarity |
|------|-------|------------|
| 1% | ~2.5M (US) | Highest match |
| 1-2% | ~2.5M | High match |
| 2-5% | ~7.5M | Medium match |
| 5-10% | ~12.5M | Lower match, higher reach |

**Recommendations**:
- Start with 1% for conversion campaigns
- Use 2-5% for scaling
- Use 5-10% for awareness

### 4. Custom Audiences

**What it is**: Target people who've already interacted with your business

**Types**:

**Website Custom Audiences**:
```
All website visitors (180 days)
Product page visitors (30 days)
Add to cart (14 days)
Purchase (180 days) - for exclusion
```

**Customer List**:
```
Email list upload
Phone number list
App user IDs
```

**Engagement Custom Audiences**:
```
Video viewers (25%, 50%, 75%, 95%)
Page/profile engagers
Ad engagers
Instagram engagers
Facebook page engagers
```

### 5. Advantage+ Audience

**What it is**: Meta's AI-powered audience expansion

**How it works**:
- You provide targeting "suggestions"
- Algorithm can go beyond your suggestions if it finds converters
- More data = better performance

**When to use**:
- Scaling campaigns
- When manual targeting hits ceiling
- Good Pixel data available

**Setup**:
```
Audience Controls: [Set hard limits]
Targeting Suggestions: [Provide initial direction]
Let Advantage+ expand: ON
```

## Exclusion Strategies

### Must-Have Exclusions

**For prospecting campaigns**:
```
Exclude:
- Purchase (30-180 days)
- Current customers (customer list)
- Existing subscribers (if lead gen)
```

**For retargeting campaigns**:
```
Exclude:
- Purchase (7-30 days) - recent buyers
- Excluded products/categories
```

### Common Exclusions

| Exclusion | Use Case |
|-----------|----------|
| Past purchasers | Avoid showing ads to existing customers |
| Email subscribers | If running lead gen, exclude existing leads |
| Employees | Avoid wasted spend |
| Competitors' employees | If targeting by employer |
| Website visitors | For pure prospecting |

## Audience Sizing Guidelines

### Minimum Audience Sizes

| Objective | Minimum Audience Size |
|-----------|----------------------|
| Awareness | 1M+ |
| Traffic | 500K+ |
| Conversions | 1M+ for CBO, 500K for ABO |
| Retargeting | 1K minimum, 10K+ ideal |

### Audience Too Small Symptoms
- High CPMs
- Frequency climbs quickly
- Limited delivery
- No learning phase exit

### Audience Too Large Symptoms
- Usually not a problem with good creative
- May need higher budget to see patterns

## Targeting by Funnel Stage

### TOFU (Top of Funnel) - Awareness
```
Broad targeting
OR Interests: Large categories
OR Lookalike: 5-10%
Goal: Reach new audiences cheaply
```

### MOFU (Middle of Funnel) - Consideration
```
Video viewers (50%+)
Website visitors (30-90 days)
Engagers (likes, comments, shares)
Goal: Nurture interested prospects
```

### BOFU (Bottom of Funnel) - Conversion
```
Add to cart (7-14 days)
Product page viewers (7-14 days)
High-intent website visitors
Email subscribers who haven't purchased
Goal: Convert warm prospects
```

## Special Targeting Scenarios

### B2B Targeting
```
Job Titles: [Specific titles]
Industries: [Relevant industries]
Company Size: [If available]
Behaviors: Business page admins
Interests: Industry publications, tools
```

### Local Business Targeting
```
Location: [Radius around business]
+ Drop pin targeting
+ Exclude irrelevant areas
Interests: Local events, local pages
```

### E-commerce Targeting
```
Behaviors: Engaged Shoppers
Interests: Product category
Lookalike: Purchasers
Advantage+: Primary strategy
```

## Testing Audiences

### Audience Testing Framework

1. **Start broad**: Let algorithm find patterns
2. **Test 2-3 hypotheses**: Different interest stacks
3. **Build lookalikes**: From your best converters
4. **Scale winners**: Move budget to top performers

### Testing Structure

```
Campaign: Audience Testing
├── Ad Set 1: Broad (control)
├── Ad Set 2: Interest Hypothesis A
├── Ad Set 3: Interest Hypothesis B
└── Ad Set 4: Lookalike 1%

Same creative across all ad sets
Run until statistical significance (50+ conversions each)
```

## Audience Troubleshooting

| Problem | Likely Cause | Solution |
|---------|--------------|----------|
| No delivery | Audience too small | Expand targeting |
| High CPM | Competitive audience | Broaden or change time |
| High frequency | Audience exhausted | Expand or refresh |
| Poor conversion | Wrong audience | Test new hypotheses |
| Good CTR, no sales | Audience quality | Narrow or use lookalikes |
