# LinkedIn Research & Content Discovery

## Prerequisites

Before starting research:
1. Load LinkedIn engagement strategy from `.business_growth/marketing/social/linkedin/strategy.md`
2. Load business context from `.business_growth/marketing/social/BUSINESS.md`
3. If either is missing, create them first (see steps below)

---

## Step 0: Load LinkedIn Engagement Strategy

```
Read .business_growth/marketing/social/linkedin/strategy.md
```

If file doesn't exist, ask the user: **"No LinkedIn engagement strategy found. Would you like to create one? This defines your overall approach to LinkedIn — target audiences, content pillars, engagement rules, and goals."**

If user says **yes**, gather the following and create the file:
- **Goal**: What do you want to achieve on LinkedIn? (thought leadership, lead generation, brand awareness, network building)
- **Target Audiences**: Who do you want to reach? (job titles, industries, company sizes)
- **Content Pillars**: What topics/expertise should posts and comments focus on?
- **Engagement Rules**: Any constraints? (e.g., comment-first strategy, max posts per week, avoid competitors' posts)
- **Writing Style & Voice** (MANDATORY): The user's personal writing style — must be captured accurately (see Style Discovery below)
- **Hashtag Strategy**: Key hashtags to use and monitor
- **Metrics to Track**: What signals success? (impressions, comments, connection requests, profile views)

### Style Discovery (Mandatory)

Before creating the strategy file, learn the user's authentic writing voice:

1. **Check for existing content**: Look for past engagement logs in `.business_growth/marketing/social/linkedin/` and other platform directories (`.business_growth/marketing/social/*/`) — read any previous comments/posts the user has approved and posted
2. **If existing content found**: Analyze the writing patterns and present a style characterization to the user covering:
   - Sentence structure (short/punchy vs. long/detailed vs. conversational)
   - Vocabulary level (casual, technical, formal, mixed)
   - Common patterns (asks questions, uses analogies, leads with data, uses humor, tells stories)
   - Distinctive phrases, expressions, or quirks

   **Ask the user**: *"Based on your past posts, here's how I'd describe your writing style: [characterization]. Does this capture your voice accurately? Any adjustments?"*

3. **If no existing content found**: Ask the user to either:
   - Provide 2-3 example comments/posts they've written (on any platform)
   - Describe their writing style in their own words
   - Point to a social profile where their writing can be reviewed via browser

**Wait for explicit user approval of the style characterization before saving the strategy.**

Create `.business_growth/marketing/social/linkedin/strategy.md` with format:

```markdown
# LinkedIn Engagement Strategy

## Goal
<what we want to achieve on LinkedIn>

## Target Audiences
| Audience | Job Titles | Industries | Why |
|----------|-----------|------------|-----|
| <segment> | <titles> | <industries> | <reason> |

## Content Pillars
- <pillar 1>: <description>
- <pillar 2>: <description>

## Engagement Rules
- <rule 1>
- <rule 2>

## Writing Style & Voice
- **Tone**: <e.g., authoritative expert, collaborative peer, industry insider>
- **Sentence Style**: <e.g., short and punchy, detailed and thorough, conversational>
- **Vocabulary**: <e.g., casual, technical, formal, mixed>
- **Patterns**: <e.g., leads with questions, uses analogies, data-driven, uses humor>
- **Distinctive Traits**: <specific phrases, expressions, or quirks the user uses>
- **Avoid**: <what does NOT sound like the user>

> Style approved by user: yes

## Hashtag Strategy
- Primary: <hashtags to use regularly>
- Monitor: <hashtags to watch for engagement opportunities>

## Metrics & Goals
- <metric>: <target>

## Last Updated: <timestamp>
```

If user says **no**, proceed without a strategy (use business context alone).

---

## Step 1: Load Business Context

```
Read .business_growth/marketing/social/BUSINESS.md
```

If file doesn't exist, proceed to Step 1b. Otherwise, skip to Step 2.

---

## Step 1b: Create Business Context (if missing)

Ask user for:
- Product/service description
- Company name and website
- Target audience and their pain points
- Value proposition and differentiators
- Tone and messaging guidelines

Create `.business_growth/marketing/social/BUSINESS.md` with format:

```markdown
# Business Profile for Social Marketing

## Business Overview
- **Product/Service**: <description>
- **Company Name**: <name>
- **Website**: <url>

## Target Audience
- **Primary Persona**: <description>
- **Pain Points**: <list>
- **Where They Hang Out**: <platforms/communities>

## Value Proposition
- **Main Value**: <description>
- **Key Differentiators**: <list>

## Messaging Guidelines
- **Tone**: <professional/casual/technical/etc.>
- **Topics to Promote**: <list>
- **Topics to Avoid**: <list>

## Last Updated: <timestamp>
```

---

## Step 2: Generate LinkedIn Search Strategy

Based on the engagement strategy (if available) and business context, determine:
- **Target Keywords**: What topics, problems, or questions does the audience discuss?
- **Target Hashtags**: Use hashtags from strategy.md if defined, otherwise identify relevant LinkedIn hashtags (e.g., #SaaS, #StartupLife, #ProductManagement)
- **People/Companies to Follow**: Who are thought leaders and key companies in the space?
- **Content Types**: Posts, articles, polls, carousels
- **Engagement Rules**: Respect any constraints defined in the strategy (e.g., comment-first approach, tone requirements)

---

## Step 3: Navigate LinkedIn via Browser MCP

```
tabs_context_mcp → tabs_create_mcp → navigate (https://www.linkedin.com/feed/)
```

Search across multiple LinkedIn sources:

### 3a: Feed
- Navigate to `https://www.linkedin.com/feed/`
- Scan feed for relevant posts from connections and followed topics

### 3b: Keyword Search (Content)
For each search keyword:
- Navigate to `https://www.linkedin.com/search/results/content/?keywords=<keyword>`
- Sort by recent or top posts
- Scroll to load more results

### 3c: People Search
For target people/roles:
- Navigate to `https://www.linkedin.com/search/results/people/?keywords=<keyword>`
- Look for thought leaders, potential connections, industry experts

### 3d: Hashtag Pages
For each target hashtag:
- Navigate to `https://www.linkedin.com/feed/hashtag/<hashtag>/` (without the # symbol)
- Scan recent posts under that hashtag

---

## Step 4: Extract Data

### Posts
For each relevant post found:
- **Author**: Name and headline
- **Snippet**: First 1-2 lines of the post
- **URL**: Full post URL
- **Reactions**: Number of reactions (likes, etc.)
- **Comments**: Number of comments
- **Age**: How old is the post
- **Relevance**: Why this post is relevant (brief note)
- **Status**: new | evaluated | engaged | skipped

### People to Follow
For each relevant person discovered:
- **Name**: Full name
- **Headline**: Professional headline
- **URL**: Profile URL
- **Relevance**: Why this person is worth following (brief note)
- **Status**: new | followed | skipped

Use `read_page`, `get_page_text`, and `screenshot` to capture information.

---

## Step 5: Save to Date-Based Storage

Determine today's date and create the storage path:
```
mkdir -p .business_growth/marketing/social/linkedin/{YYYY-MM}
```

Create/update `.business_growth/marketing/social/linkedin/{YYYY-MM}/{YYYY-MM-DD}.md`:

```markdown
# LinkedIn Activity - {YYYY-MM-DD}

## Search Strategy
- **Keywords**: keyword1, keyword2, keyword3
- **Hashtags**: #hashtag1, #hashtag2, #hashtag3
- **Search Time**: HH:MM

## People to Follow
| Time | Name | Headline | URL | Relevance | Status |
|------|------|----------|-----|-----------|--------|
| HH:MM | Jane Doe | VP Product at Acme | https://linkedin.com/in/... | Industry thought leader | new |

## Discovered Posts

### High Priority
| Time | Author | Snippet | URL | Reactions | Comments | Age | Relevance | Status |
|------|--------|---------|-----|-----------|----------|-----|-----------|--------|
| HH:MM | John Smith | How we scaled our... | https://linkedin.com/feed/... | 234 | 45 | 2h | Discusses our target problem | new |

### Medium Priority
| Time | Author | Snippet | URL | Reactions | Comments | Age | Relevance | Status |
|------|--------|---------|-----|-----------|----------|-----|-----------|--------|

### Low Priority / Archive
| Time | Author | Snippet | URL | Reactions | Comments | Age | Relevance | Status |
|------|--------|---------|-----|-----------|----------|-----|-----------|--------|

## Engagement Log

(Entries added by engage.md)
```

If the file already exists for today, append new posts and people to the appropriate sections without overwriting existing entries.

---

## What Makes a Good LinkedIn Engagement Target

Prioritize posts that:
- Have **active comment sections** with ongoing discussion
- Are from **industry thought leaders** with aligned audiences
- Contain **questions or polls** that invite participation
- Have **fewer than 50 comments** (easier to get visibility)
- Cover **trending topics** in your niche
- Were posted **within the last 24 hours** (LinkedIn algorithm favors early engagement)
- Are from people in your **target network** (2nd-degree connections, industry peers)

---

## Output

After completing research, you should have:
1. LinkedIn engagement strategy saved in `strategy.md` (if user chose to create one)
2. Business context saved in `BUSINESS.md`
3. Search strategy documented
4. Discovered posts saved to `{YYYY-MM}/{YYYY-MM-DD}.md` with priority rankings
5. People to follow identified and logged
