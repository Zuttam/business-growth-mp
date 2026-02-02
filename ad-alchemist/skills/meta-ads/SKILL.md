---
name: meta-ads
description: |
  Use when working with Meta (Facebook/Instagram) advertising campaigns.
  Triggers on: "meta ads", "facebook ads", "instagram ads", "create campaign",
  "plan campaign", "ad performance", "optimize ads", "campaign metrics",
  "audience targeting", "ad creative", "ROAS", "CPA", "CTR optimization"
---

# Meta Ads Skill Router

This skill routes to the appropriate Meta advertising workflow based on the user's intent.

## Step 1: Determine Intent

Analyze the user's request to determine which workflow is needed:

**Plan Campaign** (`plan-campaign.md`) - Use when:
- Creating a new campaign from scratch
- Designing campaign structure
- Defining audiences for a new campaign
- Creating ad creative briefs
- Setting up budget allocation
- User says: "create", "plan", "design", "new campaign", "launch"

**Monitor Campaign** (`monitor-campaign.md`) - Use when:
- Reviewing campaign performance
- Analyzing metrics
- Making optimization decisions
- Troubleshooting underperforming ads
- User says: "check", "review", "analyze", "optimize", "performance", "metrics"

## Step 2: Load the Workflow

Based on intent, read and follow the appropriate workflow file:

- For planning: Read `plan-campaign.md` in this directory
- For monitoring: Read `monitor-campaign.md` in this directory

## Step 3: Load Reference as Needed

During the workflow, consult reference documentation as needed:
- `reference/campaign-structure.md` - Campaign hierarchy and objectives
- `reference/audience-targeting.md` - Audience strategies
- `reference/creative-best-practices.md` - Creative guidelines
- `reference/metrics-kpis.md` - Performance benchmarks
- `reference/optimization-rules.md` - When and how to optimize

## Quick Reference: 2026 Meta Ads Best Practices

1. **Simplified Structure**: 2 campaigns (test + scale) outperforms fragmented approaches
2. **Creative is Targeting**: Andromeda algorithm uses creative signals for delivery
3. **Advantage+ First**: 65% of US advertisers use it as primary growth engine
4. **UGC Wins**: Native-looking "ugly ads" outperform polished content
5. **Hook is Everything**: First 3 seconds / 125 characters determine success
6. **50 Events Rule**: Ad sets need 50 conversions in 7 days to exit learning
7. **Mobile-First**: 90% of inventory is vertical (9:16)
8. **Scale Gradually**: 20-50% weekly budget increases to avoid learning resets
