# Campaign Structure Reference

## Campaign Hierarchy

```
Campaign (1)
├── Objective: What you want to achieve
├── Budget: Campaign-level (CBO) or ad set level
└── Special Ad Categories: Housing, Credit, Employment, Politics

Ad Set (many per campaign)
├── Audience: Who sees your ads
├── Placements: Where ads appear
├── Budget: If not using CBO
├── Schedule: When ads run
└── Optimization: What to optimize for

Ad (many per ad set)
├── Creative: Image, video, carousel
├── Copy: Primary text, headline, description
├── CTA: Call-to-action button
└── URL: Destination link
```

## Campaign Objectives (2026)

Meta simplified objectives into 6 categories:

### 1. Awareness
**Use when**: Building brand recognition, reaching maximum people
**Optimizes for**: Reach, ad recall lift, video views
**Best for**: New brands, product launches, seasonal awareness

### 2. Traffic
**Use when**: Driving website visits, app opens
**Optimizes for**: Link clicks, landing page views
**Best for**: Content marketing, blog traffic, app engagement

### 3. Engagement
**Use when**: Getting social interactions
**Optimizes for**: Post engagement, page likes, event responses
**Best for**: Building social proof, community growth

### 4. Leads
**Use when**: Collecting contact information
**Optimizes for**: Form submissions, calls, messages
**Best for**: B2B, service businesses, high-consideration purchases

### 5. App Promotion
**Use when**: Driving app installs or in-app actions
**Optimizes for**: App installs, app events
**Best for**: Mobile apps, games

### 6. Sales
**Use when**: Driving purchases or conversions
**Optimizes for**: Purchases, add to cart, initiate checkout
**Best for**: E-commerce, direct response

## Recommended Campaign Structures

### Structure 1: Test & Scale (Recommended)

Best for most advertisers. Simple, effective, scalable.

```
Campaign 1: [Product] Testing
├── Budget: 30-40% of total
├── Objective: Sales/Leads
├── Ad Set 1: Broad Audience
│   └── 3-5 creative variations
├── Ad Set 2: Interest Stack A
│   └── 3-5 creative variations
└── Ad Set 3: Interest Stack B
    └── 3-5 creative variations

Campaign 2: [Product] Scale
├── Budget: 60-70% of total
├── Type: Advantage+ Shopping/App
└── Contains winning creatives from testing
```

### Structure 2: Full Funnel

For established brands with significant traffic.

```
Campaign 1: TOFU - Awareness
├── Objective: Awareness
├── Audience: Broad, interests
└── Creative: Educational, entertaining

Campaign 2: MOFU - Consideration
├── Objective: Traffic/Engagement
├── Audience: Video viewers, engagers
└── Creative: Product-focused, social proof

Campaign 3: BOFU - Conversion
├── Objective: Sales
├── Audience: Website visitors, cart abandoners
└── Creative: Urgency, offers, testimonials
```

### Structure 3: Advantage+ Only

For e-commerce with good Pixel data.

```
Campaign 1: Advantage+ Shopping
├── Budget: 80% of total
├── Existing customer budget cap: 20-30%
└── 5-10 creative variations

Campaign 2: Retargeting (Manual)
├── Budget: 20% of total
├── Audience: Cart abandoners, past purchasers
└── Dynamic product ads
```

## Budget Strategies

### Campaign Budget Optimization (CBO)

**How it works**: Meta distributes budget across ad sets based on performance

**Pros**:
- Automatic optimization
- Reduces manual management
- Often better overall performance

**Cons**:
- Less control over individual ad set spend
- Can starve testing ad sets

**When to use**: Most campaigns, especially when you have 3+ ad sets

### Ad Set Budget (ABO)

**How it works**: You set fixed budget for each ad set

**Pros**:
- Full control over spend distribution
- Better for testing specific audiences
- Ensures all ad sets get data

**Cons**:
- Requires more manual management
- May not optimize as efficiently

**When to use**: Testing phase, when you need guaranteed data on specific audiences

### Budget Recommendations by Spend Level

| Daily Budget | Recommended Approach |
|--------------|---------------------|
| < $50 | 1-2 ad sets max, ABO or CBO |
| $50-200 | 2-4 ad sets, CBO recommended |
| $200-500 | CBO with ad set minimums |
| $500-2000 | CBO + Advantage+ campaign |
| > $2000 | Multiple campaigns, Advantage+ primary |

## Special Ad Categories

Required declaration for:

1. **Credit**: Credit cards, loans, mortgages
2. **Employment**: Job listings, employment services
3. **Housing**: Real estate, rentals, home equity
4. **Social Issues, Elections, Politics**: Political ads

**Restrictions when selected**:
- No age targeting
- No gender targeting
- No detailed targeting exclusions
- Limited zip code targeting
- No lookalike audiences (use Special Ad Audiences instead)

## Campaign Settings Checklist

### Must Configure
- [ ] Campaign objective
- [ ] Special ad categories (if applicable)
- [ ] Campaign budget (if using CBO)
- [ ] Campaign bid strategy

### Ad Set Level
- [ ] Audience targeting
- [ ] Placements (Advantage+ recommended)
- [ ] Budget and schedule (if ABO)
- [ ] Optimization event
- [ ] Attribution window

### Ad Level
- [ ] Creative format
- [ ] Primary text
- [ ] Headline
- [ ] Description
- [ ] Call-to-action
- [ ] Destination URL
- [ ] URL parameters (UTMs)

## Bid Strategies

### Lowest Cost (Default)
- Meta gets you the most results for your budget
- No cost control
- Best for: Starting out, maximizing volume

### Cost Cap
- Sets maximum CPA target
- May reduce volume to hit target
- Best for: Scaling while maintaining efficiency

### Bid Cap
- Sets maximum bid per auction
- Most control, lowest volume
- Best for: Strict cost requirements

### Minimum ROAS
- Sets target return on ad spend
- Requires value-based optimization
- Best for: E-commerce with varied product values

## Attribution Windows

### Click-Through Attribution
- **7-day click** (default): Conversion within 7 days of ad click
- **1-day click**: Conversion within 1 day of ad click

### View-Through Attribution
- **1-day view** (default): Conversion within 1 day of seeing ad
- **None**: No view-through attribution

### Recommendations
- Start with **7-day click, 1-day view** (default)
- For impulse purchases: **1-day click, 1-day view**
- For long sales cycles: **7-day click, 1-day view**
- For strict attribution: **1-day click only**
