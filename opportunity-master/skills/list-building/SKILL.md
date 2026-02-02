---
name: list-building
description: Build targeted lists of potential buyers from LinkedIn based on ICP criteria. Use when user wants to find prospects, build buyer lists, search LinkedIn for customers, or define their ideal buyer profile. Not for competitor research. Can be invoked with optional criteria (e.g., "VP Engineering at Series B SaaS companies in SF").
---

# List Building Skill

Build targeted lists of potential buyers from LinkedIn based on Ideal Customer Profile (ICP) criteria. This skill is for prospecting - finding people who might buy your product or service, not for competitive analysis.

## Process

### Step 0: Load Defaults & Check Scope

**First, check for saved decisions:**

Read `.business_growth/sales/DECISIONS.md` if it exists. This file stores global defaults like:
- Buyer persona and target titles
- Target industries and exclusions
- Company segment preferences
- Sales Navigator availability
- Competitors to exclude

**If DECISIONS.md exists:**
Ask the user: "I found your saved preferences. Want to use these defaults, or customize for this specific list?"
- **(A) Use defaults** → Skip to Step 1, only ask list-specific questions (target lead count, any overrides)
- **(B) Customize** → Go through the full discovery questions below
- **(C) Update defaults** → Go through questions and save new answers to DECISIONS.md

**If DECISIONS.md doesn't exist:**
Go through the full discovery process and offer to save answers as defaults at the end.

---

### Step 0b: Full Discovery (if not using defaults)

**Gather context:**
- Check existing lists in `.business_growth/sales/lead_lists/` to understand prior work
- Review any existing ICP definitions or campaign history

**Ask clarifying questions (one at a time):**
- Prefer multiple choice when options are clear
- Focus on understanding: **purpose**, **constraints**, **success criteria**

**Global questions (save to DECISIONS.md):**
- "Who is your buyer? What role typically makes or influences the purchase decision?"
- "What problem does your product solve for them?"
- "Any industries where your buyers typically work? (e.g., security, fintech, healthcare)"
- "Any spaces to exclude? (e.g., no agencies, no consulting firms, no competitors)"
- "Company segment: (A) SMB (< 50 employees), (B) Mid-market (50-500), (C) Enterprise (500+), or (D) Any size?"
- "Do you have LinkedIn Sales Navigator?"

**List-specific questions (always ask):**
- "What's the goal for this specific list - demos, trials, partnerships?"
- "How many leads are you looking to have in this list?"
- "Any specific geography or filters for this list?"

**Explore approaches:**
After understanding requirements, propose 2-3 different approaches:
- Present options conversationally with trade-offs
- Lead with your recommended approach and explain why

**Save decisions:**
If user went through full discovery, ask: "Want me to save these as your defaults for future lists?"
If yes, create/update `.business_growth/sales/DECISIONS.md`

### Step 1: Define ICP Criteria

Once you understand the user's goals from Step 0, nail down the specific buyer criteria. Fill in any gaps by asking targeted questions (one at a time):

- **Buyer Persona**: Who buys? Decision-maker vs. influencer vs. end-user
- **Target Titles**: VP Engineering, Head of Product, CTO, Director of Sales, etc.
- **Target Industries/Verticals**: Where do your buyers work? Security, fintech, healthcare, SaaS, etc.
- **Company Segment**: SMB (< 50), mid-market (50-500), enterprise (500+)
- **Company Characteristics**: Funding stage, revenue range, tech stack
- **Geography**: Countries, states, cities
- **Exclusions**: Industries to skip, competitors, company types to avoid
- **Additional Filters**: Years in role, keywords, specific companies to include/exclude

### Step 2: Create ICP Document

Generate a meaningful snake_case name based on the ICP criteria (e.g., `list_sf_series_b_vp_engineering`). Keep names concise (3-5 words max), lowercase with underscores, no special characters.

Save ICP definition to `.business_growth/sales/lead_lists/list_<name>/icp.md`:

```markdown
# ICP Definition

## Buyer Profile
- **Buyer Persona**: <decision-maker / influencer / end-user>
- **Titles**: <list of titles>
- **Problem We Solve**: <what pain point does this buyer have?>

## Target Companies
- **Industries/Verticals**: <list of industries>
- **Company Segment**: <SMB / Mid-market / Enterprise>
- **Company Size**: <employee count or revenue range>
- **Funding Stage**: <stages>
- **Geography**: <locations>

## Exclusions
- **Industries to Skip**: <e.g., agencies, consulting, government>
- **Competitors**: <companies to exclude>
- **Other Exclusions**: <e.g., no startups under 10 people>

## List Goals
- **Target Lead Count**: <estimated number of leads>
- **Sales Navigator**: <yes/no>

## Search Strategy
- **LinkedIn Search URL**: <url>
- **Filters Applied**: <description>

## Notes
<any additional context>
```

### Step 3: Search LinkedIn

1. Get browser context with `tabs_context_mcp`
2. Navigate to the appropriate search tool:
   - **With Sales Navigator**: Go to `linkedin.com/sales/search/people` - better filters (company size, seniority, years in role), higher limits, lead saving
   - **Without Sales Navigator**: Use standard LinkedIn search at `linkedin.com/search/results/people/`
3. Apply search filters based on ICP
4. Take screenshot to verify results
5. Adjust filters if results don't match expected count

**Important Rate Limits**:
- **Sales Navigator**: ~100 profile views/day, can save leads to lists
- **Standard LinkedIn**: ~30 profiles/hour, ~100/day
- Space out searches to avoid restrictions

### Step 4: Extract Lead Data

For each prospect, capture:
- **Name**: Full name
- **Title**: Current job title
- **Company**: Current employer
- **LinkedIn URL**: Profile URL
- **Location**: Geographic location
- **Headline**: Profile headline

Use `read_page` to extract structured data from search results or profiles.

### Step 5: Save Lead List

Create `.business_growth/sales/lead_lists/list_<name>/LIST.md`:

```markdown
# Lead List: <Descriptive Name>

## Metadata
- **List ID**: list_<name>   # e.g., list_sf_series_b_vp_engineering
- **Created**: <ISO timestamp>
- **Source**: LinkedIn Search
- **ICP**: See icp.md
- **Total Leads**: <count>

## Leads

### 1. <Full Name>
- **LinkedIn**: <url>
- **Role**: <title> at <company>
- **Location**: <location>
- **Headline**: <headline>

### 2. <Full Name>
- **LinkedIn**: <url>
- **Role**: <title> at <company>
- **Location**: <location>
- **Headline**: <headline>

<!-- Continue for all leads -->
```

### Step 6: Report Summary

Provide summary to user:
- Total leads found
- Breakdown by title/company/location
- Recommendations for next steps (create campaign, research top prospects)
- Any issues encountered (rate limits, restricted profiles)

## Browser Tools Used

| Tool | Purpose |
|------|---------|
| `tabs_context_mcp` | Get browser context |
| `tabs_create_mcp` | Create new tab for LinkedIn |
| `navigate` | Go to LinkedIn search |
| `read_page` | Extract search results and profiles |
| `find` | Locate search filters and results |
| `form_input` | Enter search criteria |
| `computer` | Click, scroll, screenshot |

## Tips for Better Results

1. **Use Boolean search**: Combine terms with AND, OR, NOT
2. **Leverage 2nd degree connections**: Often higher response rates
3. **Check for recent activity**: Active profiles are more responsive
4. **Note shared connections**: Useful for warm introductions
5. **Save search URL**: Can rerun later for new prospects

## Next Steps After List Building

Suggest to user:
1. Use `/opportunity-master:lead-research` to research top prospects
2. Use `/opportunity-master:campaign-creation` to create outreach campaign
3. Review and prioritize list before outreach

## Global Decisions File

The `.business_growth/sales/DECISIONS.md` file stores user preferences to avoid repetitive questions:

```markdown
# Sales Decisions & Defaults

## Last Updated
<ISO timestamp>

## Buyer Profile
- **Buyer Persona**: <decision-maker / influencer / end-user>
- **Target Titles**: <list of titles>
- **Problem We Solve**: <what pain point do we address?>

## Target Market
- **Industries/Verticals**: <list of industries>
- **Company Segment**: <SMB / Mid-market / Enterprise>
- **Geography**: <default regions>

## Exclusions
- **Industries to Skip**: <e.g., agencies, consulting, government>
- **Competitors**: <companies to always exclude>
- **Other Exclusions**: <company types to avoid>

## Tools
- **Sales Navigator**: <yes/no>

## Notes
<any other standing preferences>
```

**When to update DECISIONS.md:**
- First time running list-building or lead-research
- When user says "update my defaults"
- When user's ICP fundamentally changes
