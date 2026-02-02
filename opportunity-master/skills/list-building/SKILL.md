---
name: list-building
description: Build targeted lead lists from LinkedIn based on ICP criteria. Use when user wants to find prospects, build lead lists, search LinkedIn, define ICP, or gather potential customers.
user-invocable: true
arguments:
  - name: criteria
    description: ICP criteria or search terms (e.g., "VP Engineering at Series B SaaS companies in SF")
    required: false
---

# List Building Skill

Build targeted lead lists from LinkedIn based on Ideal Customer Profile (ICP) criteria.

## Process

### Step 1: Define ICP Criteria

If no criteria provided, ask the user about:

1. **Target Titles**: What job titles are you targeting?
   - Examples: VP Engineering, Head of Product, CTO, Director of Sales

2. **Company Characteristics**:
   - Industry (SaaS, FinTech, Healthcare, etc.)
   - Company size (employee count or revenue)
   - Funding stage (Seed, Series A-D, Public)

3. **Geography**: What locations?
   - Countries, states, cities

4. **Additional Filters**:
   - Years in role
   - Keywords in profile
   - Specific companies to include/exclude

### Step 2: Create ICP Document

Generate a meaningful snake_case name based on the ICP criteria (e.g., `list_sf_series_b_vp_engineering`). Keep names concise (3-5 words max), lowercase with underscores, no special characters.

Save ICP definition to `/business_growth/sales/lead_lists/list_<name>/icp.md`:

```markdown
# ICP Definition

## Target Profile
- **Titles**: <list of titles>
- **Industries**: <list of industries>
- **Company Size**: <range>
- **Funding Stage**: <stages>
- **Geography**: <locations>

## Search Strategy
- **LinkedIn Search URL**: <url>
- **Filters Applied**: <description>

## Notes
<any additional context>
```

### Step 3: Search LinkedIn

1. Get browser context with `tabs_context_mcp`
2. Navigate to LinkedIn search (or Sales Navigator if available)
3. Apply search filters based on ICP
4. Take screenshot to verify results

**Important Rate Limits**:
- View ~30 profiles per hour maximum
- Limit to 100 profile views per day
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

Create `/business_growth/sales/lead_lists/list_<name>/LIST.md`:

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
