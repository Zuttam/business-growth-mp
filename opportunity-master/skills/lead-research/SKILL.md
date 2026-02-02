---
name: lead-research
description: Research LinkedIn prospects to find personalization opportunities and ice breakers. Use when user wants to research a lead, personalize outreach, find ice breakers, or understand a prospect better. Can be invoked with linkedin_url, lead_name, or campaign_id.
---

# Lead Research Skill

Research LinkedIn prospects to gather personalization opportunities, ice breakers, and conversation starters for more effective outreach.

## Process

### Step 0: Load Defaults

**First, check for saved decisions:**

Read `.business_growth/sales/DECISIONS.md` if it exists. This file stores:
- Sales Navigator availability
- Buyer persona and problem we solve (useful for framing research)
- Target industries (helps identify relevant talking points)
- Competitors to avoid mentioning

**If DECISIONS.md exists and has Sales Navigator info:**
- Use the saved preference, no need to ask again
- Reference the buyer persona to focus research on relevant pain points

**If DECISIONS.md doesn't exist or missing Sales Navigator:**
Ask: "Do you have LinkedIn Sales Navigator? It provides deeper profile insights."

**Why Sales Navigator matters**:
- **With Sales Navigator**: Access full profile info, see who viewed them, more activity history, notes/tags
- **Without Sales Navigator**: Standard profile view, may have limited visibility for non-connections

**Offer to save:** If user answers and no DECISIONS.md exists, offer to save this preference.

### Step 1: Identify Target Lead

If `linkedin_url` provided:
- Use directly for research

If `lead_name` provided:
- Search in lead lists under `.business_growth/sales/lead_lists/`
- Find matching lead and get LinkedIn URL

If neither provided:
- Ask user for LinkedIn URL or lead name
- Or offer to research leads from a specific campaign/list

### Step 2: Navigate to LinkedIn Profile

1. Get browser context with `tabs_context_mcp`
2. Navigate to profile:
   - **With Sales Navigator**: Use `linkedin.com/sales/lead/<id>` format for richer data
   - **Without Sales Navigator**: Use standard `linkedin.com/in/<username>` URL
3. Take screenshot to verify profile loaded
4. Check for any access restrictions (may need to be connected for full profile)

### Step 3: Extract Profile Information

Use `read_page` to extract:

**Basic Info**:
- Full name
- Current title and company
- Location
- Profile headline
- Connection degree

**About Section**:
- Summary/bio content
- Key themes and interests
- Communication style

**Experience**:
- Current role details
- Previous companies
- Career progression
- Time in current role

**Education**:
- Schools attended
- Degrees and fields
- Graduation years

**Skills & Endorsements**:
- Top skills
- Endorsement counts

### Step 4: Analyze Recent Activity

Scroll to activity section and extract:

**Recent Posts** (last 30 days):
- Topics they post about
- Engagement levels
- Opinions and perspectives

**Reactions & Comments**:
- Content they engage with
- Thought leaders they follow
- Interests indicated

**Articles Written**:
- Published content
- Expertise areas

### Step 5: Identify Personalization Opportunities

Analyze gathered data for:

**Conversation Starters**:
- Recent post to reference
- Shared connections
- Common background (school, company)
- Mutual interests

**Pain Point Signals**:
- Job changes (new role = open to tools)
- Company growth signals
- Hiring activity
- Complaints or challenges mentioned

**Rapport Builders**:
- Hobbies and interests
- Causes they support
- Content preferences

**Timing Signals**:
- Best time to reach out
- Upcoming events
- Recent achievements to congratulate

### Step 6: Generate Ice Breakers

Create 3-5 personalized ice breakers based on research:

**Types of Ice Breakers**:
1. **Content Reference**: "Loved your post about X..."
2. **Shared Connection**: "I see we both know Y..."
3. **Common Background**: "Fellow [school/company] alum here..."
4. **Industry Insight**: "Given your focus on X, thought you'd find..."
5. **Congratulations**: "Congrats on the recent [achievement]..."

### Step 7: Save Research

Determine save location:
- If `campaign_id` provided: `.business_growth/sales/campaigns/campaign_<name>/leads/<lead_name>/research.md`
- Otherwise: `.business_growth/sales/lead_research/<lead_name>/research.md`

**Lead Naming**: Generate meaningful snake_case names for leads based on their name and company (e.g., `john_smith_acme`, `sarah_jones_techcorp`). Keep names concise, lowercase with underscores, no special characters.

Create research file:

```markdown
# Lead Research: <Full Name>

## Research Metadata
- **Researched**: <ISO timestamp>
- **LinkedIn**: <url>
- **Campaign**: <campaign_id if applicable>

## Profile Overview

### Current Position
- **Title**: <title>
- **Company**: <company>
- **Duration**: <time in role>
- **Location**: <location>

### Background
- **Previous Role**: <most recent previous>
- **Education**: <school, degree>
- **Career Theme**: <progression summary>

### About
<summary of their bio/about section>

## Recent Activity (Last 30 Days)

### Posts
1. **<date>**: <topic/summary>
   - Engagement: <likes/comments>
   - Key quote: "<relevant excerpt>"

2. **<date>**: <topic/summary>
   - Engagement: <likes/comments>

### Engagement Patterns
- Topics they engage with: <list>
- Thought leaders followed: <names>
- Activity level: Low / Medium / High

## Personalization Opportunities

### Strong Signals
1. <signal with context>
2. <signal with context>

### Potential Pain Points
1. <inferred pain point>
2. <inferred pain point>

### Shared Context
- Connections: <mutual connections>
- Background: <shared experiences>
- Interests: <common interests>

## Recommended Ice Breakers

### Option 1: Content Reference
"<personalized message referencing their recent post>"

**Why this works**: <explanation>

### Option 2: Industry Insight
"<message offering relevant insight>"

**Why this works**: <explanation>

### Option 3: Mutual Connection
"<message leveraging shared connection or background>"

**Why this works**: <explanation>

## Outreach Recommendations

### Best Approach
<recommended outreach strategy>

### Timing
<best time/day to reach out>

### Tone
<recommended communication style based on their profile>

### Topics to Avoid
<anything that might not resonate>

## Raw Notes
<any additional observations>
```

### Step 8: Report Summary

Provide user with:
- Key findings summary
- Top 2-3 personalization angles
- Recommended ice breaker
- Suggested next steps

## Browser Tools Used

| Tool | Purpose |
|------|---------|
| `tabs_context_mcp` | Get browser context |
| `navigate` | Go to LinkedIn profile |
| `read_page` | Extract profile content |
| `computer` | Scroll to load more content, screenshot |

## Research Quality Tips

### Good Personalization
- Specific and recent (last 30 days)
- Shows genuine interest
- Relevant to outreach purpose
- Not creepy or over-researched

### Avoid
- Mentioning personal/family info
- Referencing very old content
- Being too detailed (feels stalky)
- Generic compliments
- Assumptions about their problems

## Integration with Campaign Execution

When research is saved to a campaign lead folder:
- `{{custom}}` token in templates can reference research findings
- Campaign execution skill will use research for personalization
- Higher quality outreach leads to better response rates
