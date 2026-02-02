---
name: plan-campaign
description: |
  Campaign planning workflow for Meta ads. Use when creating new campaigns,
  designing campaign structure, defining audiences, or creating creative briefs.
---

# Meta Ads Campaign Planning Workflow

Follow these steps sequentially to create a complete campaign plan.

---

## Step 0: Load Business Context

Check for existing business context:

```
/business_growth/marketing/paid/BUSINESS.md
```

If it exists, read it to understand:
- Business model and value proposition
- Target customer profile
- Previous campaign learnings
- Brand voice and messaging guidelines

If it doesn't exist, note that we'll need to gather this information.

---

## Step 1: Discovery Questions

**STOP and ask these questions. Wait for user input before proceeding.**

Present these questions to the user:

1. **Campaign Objective**: What's the primary goal?
   - Awareness (brand discovery)
   - Traffic (website visits)
   - Leads (form submissions, sign-ups)
   - Sales (purchases, conversions)
   - App Installs

2. **Landing Page**: What URL will ads drive to?

3. **Budget**:
   - Daily budget OR lifetime budget?
   - Amount?

4. **Geography**: What locations should we target?

5. **Product/Service**: Brief description of what you're promoting

6. **Timeline**: When should the campaign start? Any end date?

7. **Existing Audiences** (optional):
   - Do you have a customer email list?
   - Is your Meta Pixel installed and tracking?
   - Any past campaigns we can learn from?

---

## Step 2: Audience Strategy Design

Based on discovery answers, design the audience strategy.

### Recommended Approach by Budget

| Daily Budget | Recommended Strategy |
|--------------|---------------------|
| < $50/day | Single broad audience OR single interest stack |
| $50-200/day | 2-3 ad sets: Broad + 1-2 interest stacks |
| $200-500/day | 3-4 ad sets: Broad + Lookalikes + Interests |
| > $500/day | Advantage+ Shopping/App + Testing campaign |

### Define Core Audiences

For each audience, specify:
- **Name**: Descriptive name for the ad set
- **Targeting Type**: Broad / Interest-based / Lookalike / Custom
- **Details**: Specific interests, lookalike source, or custom audience definition
- **Exclusions**: Who to exclude (existing customers, past purchasers)

### Audience Documentation Template

```markdown
### Audience: [Name]
- **Type**: [Broad/Interest/Lookalike/Custom]
- **Targeting**: [Specific details]
- **Age**: [Range]
- **Gender**: [All/Male/Female]
- **Placements**: [Advantage+ or Manual selection]
- **Exclusions**: [List]
- **Rationale**: [Why this audience]
```

---

## Step 3: Campaign Structure Design

Design the campaign architecture.

### Recommended Structure (2026 Best Practice)

**For Testing Phase:**
```
Campaign: [Product] - Testing
├── Ad Set: Broad Audience
│   ├── Ad: Creative Variant A
│   ├── Ad: Creative Variant B
│   └── Ad: Creative Variant C
├── Ad Set: Interest Stack 1
│   ├── Ad: Creative Variant A
│   ├── Ad: Creative Variant B
│   └── Ad: Creative Variant C
└── Ad Set: Lookalike 1% (if available)
    ├── Ad: Creative Variant A
    ├── Ad: Creative Variant B
    └── Ad: Creative Variant C
```

**For Scaling (after finding winners):**
```
Campaign: [Product] - Scale (Advantage+)
└── Uses winning creatives with Advantage+ targeting
```

### Budget Allocation

| Ad Set | % of Budget | Rationale |
|--------|-------------|-----------|
| Broad | 40-50% | Let algorithm find best performers |
| Interest 1 | 20-30% | Test hypothesis |
| Interest 2 | 20-30% | Alternative hypothesis |

### Settings Checklist

- [ ] Campaign Budget Optimization (CBO): ON
- [ ] Bid Strategy: Lowest Cost (start) or Cost Cap (scale)
- [ ] Attribution: 7-day click, 1-day view
- [ ] Placements: Advantage+ (recommended) or Manual
- [ ] Schedule: Run continuously or dayparting

---

## Step 4: Creative Brief Generation

Create the creative brief for ad production.

### Headlines (5-7 words, benefit-focused)

Generate 5 headline variations using these formulas:
1. **Direct Benefit**: "[Get/Achieve] [Desired Outcome]"
2. **Problem-Solution**: "Stop [Pain Point]. Start [Benefit]"
3. **Social Proof**: "[Number] [People] Already [Action]"
4. **Urgency**: "[Limited Time] [Offer]"
5. **Question**: "[Pain Point Question]?"

### Primary Text Hooks (First 125 characters)

Generate 5 hook variations using these patterns:
1. **Pattern Interrupt**: Start with unexpected statement
2. **Call Out Audience**: "Hey [specific audience]..."
3. **Bold Claim**: State your biggest differentiator
4. **Story Open**: "I used to [problem], until..."
5. **Question Hook**: "What if you could [benefit]?"

### Full Primary Text Template

```
[HOOK - 125 characters max]

[BODY - 2-3 short paragraphs]
• Benefit 1
• Benefit 2
• Benefit 3

[CTA - Clear next step]
```

### Visual Creative Direction

For each ad, specify:
- **Format**: 9:16 (Reels/Stories) / 4:5 (Feed) / 1:1 (Feed)
- **Style**: UGC / Polished / Static / Carousel / Video
- **Key Visual**: What should be shown
- **Text Overlay**: Any on-image text
- **AI Prompt** (if generating): Detailed prompt for image generation

### Creative Variations Matrix

| Ad Name | Headline | Hook | Visual Style | Format |
|---------|----------|------|--------------|--------|
| Ad A | Headline 1 | Hook 1 | UGC Video | 9:16 |
| Ad B | Headline 2 | Hook 2 | Static Image | 4:5 |
| Ad C | Headline 3 | Hook 3 | Carousel | 1:1 |

---

## Step 5: Save Campaign Plan

Save the complete campaign plan to:

```
/business_growth/marketing/paid/meta/campaigns/campaign_[name]/PLAN.md
```

### Plan Document Structure

```markdown
# Campaign Plan: [Name]

**Created**: [Date]
**Objective**: [Objective]
**Budget**: [Amount] [Daily/Lifetime]
**Status**: Planning

## Business Context
[Summary of product/service and goals]

## Audience Strategy
[Audience definitions from Step 2]

## Campaign Structure
[Structure from Step 3]

## Creative Brief
[Creative specifications from Step 4]

## Success Metrics
- Target CPA: $[X]
- Target ROAS: [X]x
- Target CTR: [X]%

## Launch Checklist
- [ ] Pixel verified
- [ ] Creatives produced
- [ ] Copy approved
- [ ] UTM parameters set
- [ ] Conversion events configured

## Next Steps
1. [Action item]
2. [Action item]
3. [Action item]
```

---

## Completion

After saving the plan:

1. Summarize the campaign strategy for the user
2. List the creative assets that need to be produced
3. Provide clear next steps for implementation
4. Offer to help with creative production prompts or campaign monitoring
