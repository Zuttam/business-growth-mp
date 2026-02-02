# Ad Alchemist

Expert advertising agent for Meta, Google, X.com, and YouTube paid campaigns.

## Overview

Ad Alchemist transforms your advertising ideas into high-performing campaigns. It provides expert guidance on campaign structure, audience targeting, creative strategy, and performance optimization.

## Features

### Advertising Strategist Agent

An expert agent that triggers on advertising-related queries:
- Campaign planning and strategy design
- Audience definition and targeting recommendations
- Creative brief generation (headlines, hooks, visual direction)
- Budget allocation recommendations
- Performance monitoring and optimization
- A/B testing strategy

### Meta Ads Skill

Comprehensive workflow for Meta (Facebook/Instagram) advertising:

**Plan Campaign** (`/meta-ads` → plan)
- Discovery questions to understand goals
- Audience strategy design
- Campaign structure recommendations
- Creative brief generation with headlines, hooks, and visual direction
- Complete campaign plan saved to local files

**Monitor Campaign** (`/meta-ads` → monitor)
- Performance analysis against benchmarks
- Diagnostic framework for identifying issues
- Optimization recommendations
- Action plan with priorities
- Performance tracking over time

### Reference Documentation

Detailed reference guides for Meta advertising:
- **Campaign Structure**: Objectives, hierarchy, budget strategies
- **Audience Targeting**: Broad, interest, lookalike, custom audiences
- **Creative Best Practices**: Hooks, headlines, UGC, video specs
- **Metrics & KPIs**: Benchmarks, definitions, analysis framework
- **Optimization Rules**: When and how to optimize campaigns

## Data Storage

Campaign data is stored in:
```
~/.business_growth/marketing/paid/
├── BUSINESS.md           # Shared business context
└── meta/
    ├── DECISIONS.md      # Saved preferences
    └── campaigns/
        └── campaign_<name>/
            ├── PLAN.md        # Campaign strategy
            ├── PERFORMANCE.md # Metrics tracking
            └── assets/        # Creative prompts
```

## 2026 Meta Ads Best Practices

This plugin incorporates the latest Meta advertising best practices:

1. **Simplified Structure**: 2 campaigns (test + scale) outperforms fragmentation
2. **Creative is Targeting**: Andromeda algorithm uses creative signals
3. **Advantage+ First**: Primary growth engine for 65% of US advertisers
4. **UGC Wins**: Native-looking "ugly ads" outperform polished content
5. **Hook is Everything**: First 3 seconds / 125 characters determine success
6. **50 Events Rule**: Ad sets need 50 conversions in 7 days to exit learning
7. **Mobile-First**: 90% of inventory is vertical (9:16)
8. **Scale Gradually**: 20-50% weekly budget increases

## Installation

This plugin is part of the Business Growth Marketplace. To install:

1. Add `ad-alchemist` to your Claude Code plugins
2. The hook will automatically create the required directory structure
3. Start asking about advertising to trigger the agent

## Usage Examples

**Planning a campaign:**
```
"I want to run Facebook ads for my SaaS product"
"Help me plan a Meta ads campaign for lead generation"
"Create a campaign strategy for my e-commerce store"
```

**Monitoring performance:**
```
"Review my campaign performance"
"My Facebook ads aren't converting, help me optimize"
"Analyze these metrics and tell me what to improve"
```

**Getting guidance:**
```
"What's a good CTR for Facebook ads?"
"How should I structure my ad creative?"
"When should I scale my campaign budget?"
```

## Author

Created by Matan Zutta
