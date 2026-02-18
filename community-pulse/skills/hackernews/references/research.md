# Hacker News Research & Thread Discovery

## Prerequisites

Before starting research:
1. Load Hacker News engagement strategy from `.business_growth/marketing/social/hackernews/strategy.md`
2. Load business context from `.business_growth/marketing/social/BUSINESS.md`
3. If either is missing, create them first (see steps below)

---

## Step 0: Load Hacker News Engagement Strategy

```
Read .business_growth/marketing/social/hackernews/strategy.md
```

If file doesn't exist, ask the user: **"No Hacker News engagement strategy found. Would you like to create one? This defines your overall approach to HN — topics of expertise, engagement rules, and goals."**

If user says **yes**, gather the following and create the file:
- **Goal**: What do you want to achieve on HN? (thought leadership, community presence, traffic, feedback on product)
- **Expertise Areas**: What technical topics can you comment on with genuine depth?
- **Content Themes**: What types of discussions are most relevant? (technical deep-dives, industry analysis, product feedback)
- **Engagement Rules**: Any constraints? (e.g., never self-promote directly, only comment when adding unique insight, max comments per day)
- **Writing Style & Voice** (MANDATORY): The user's personal writing style — must be captured accurately (see Style Discovery below)
- **Sections to Focus**: Which HN sections matter most? (front page, Ask HN, Show HN, new)
- **Metrics to Track**: What signals success? (karma, replies, upvotes, referral traffic)

### Style Discovery (Mandatory)

Before creating the strategy file, learn the user's authentic writing voice:

1. **Check for existing content**: Look for past engagement logs in `.business_growth/marketing/social/hackernews/` and other platform directories (`.business_growth/marketing/social/*/`) — read any previous comments/posts the user has approved and posted
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

Create `.business_growth/marketing/social/hackernews/strategy.md` with format:

```markdown
# Hacker News Engagement Strategy

## Goal
<what we want to achieve on HN>

## Expertise Areas
- <area 1>: <depth of knowledge and angle>
- <area 2>: <depth of knowledge and angle>

## Content Themes
- <theme 1>: <description>
- <theme 2>: <description>

## Engagement Rules
- <rule 1>
- <rule 2>

## Writing Style & Voice
- **Tone**: <e.g., technical expert, curious builder, data-driven analyst>
- **Sentence Style**: <e.g., short and punchy, detailed and thorough, conversational>
- **Vocabulary**: <e.g., casual, technical, formal, mixed>
- **Patterns**: <e.g., leads with questions, uses analogies, data-driven, uses humor>
- **Distinctive Traits**: <specific phrases, expressions, or quirks the user uses>
- **Avoid**: <what does NOT sound like the user>

> Style approved by user: yes

## Sections to Focus
- <section>: <why and how often>

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

## Step 2: Generate HN Search Strategy

Based on the engagement strategy (if available) and business context, determine:
- **Search Keywords**: What technical topics, problems, or questions relate to the business?
- **Thread Types**: Stories, Ask HN, Show HN, comments
- **Sections to Monitor**: Use sections from strategy.md if defined, otherwise cover front page, new, ask, show, best
- **Engagement Rules**: Respect any constraints defined in the strategy (e.g., expertise-only commenting, tone requirements)

---

## Step 3: Navigate Hacker News via Browser MCP

```
tabs_context_mcp → tabs_create_mcp → navigate (https://news.ycombinator.com)
```

Search across multiple HN sources:

### 3a: Front Page & New
- Navigate to `https://news.ycombinator.com` (front page)
- Navigate to `https://news.ycombinator.com/newest` (new stories)
- Scan titles for relevant topics

### 3b: Algolia Search (keyword-based)
For each search keyword:
- Navigate to `https://hn.algolia.com/?q=<keyword>`
- Filter by date range (last 24h, last week, last month)
- Sort by date or popularity

### 3c: Ask HN
- Navigate to `https://news.ycombinator.com/ask`
- Look for questions related to the business domain

### 3d: Show HN
- Navigate to `https://news.ycombinator.com/show`
- Look for products/projects in the same space (competitors, complementary tools)

---

## Step 4: Extract Thread Data

For each relevant thread found:
- **Title**: Thread title
- **URL**: Full HN thread URL (e.g., `https://news.ycombinator.com/item?id=...`)
- **Points**: Number of upvotes
- **Comments**: Number of comments
- **Age**: How old is the thread
- **Type**: story | ask | show | comment
- **Relevance**: Why this thread is relevant (brief note)
- **Status**: new | evaluated | engaged | skipped

Use `read_page`, `get_page_text`, and `screenshot` to capture thread information.

---

## Step 5: Save to Date-Based Storage

Determine today's date and create the storage path:
```
mkdir -p .business_growth/marketing/social/hackernews/{YYYY-MM}
```

Create/update `.business_growth/marketing/social/hackernews/{YYYY-MM}/{YYYY-MM-DD}.md`:

```markdown
# Hacker News Activity - {YYYY-MM-DD}

## Search Strategy
- **Keywords**: keyword1, keyword2, keyword3
- **Sections Searched**: front page, new, ask, show, algolia
- **Search Time**: HH:MM

## Discovered Threads

### High Priority
| Time | Title | Type | URL | Points | Comments | Age | Relevance | Status |
|------|-------|------|-----|--------|----------|-----|-----------|--------|
| HH:MM | Thread title | story | https://... | 120 | 45 | 2h | Asking about X | new |

### Medium Priority
| Time | Title | Type | URL | Points | Comments | Age | Relevance | Status |
|------|-------|------|-----|--------|----------|-----|-----------|--------|

### Low Priority / Archive
| Time | Title | Type | URL | Points | Comments | Age | Relevance | Status |
|------|-------|------|-----|--------|----------|-----|-----------|--------|

## Engagement Log

(Entries added by engage.md)
```

If the file already exists for today, append new threads to the appropriate priority sections without overwriting existing entries.

---

## Output

After completing research, you should have:
1. Hacker News engagement strategy saved in `strategy.md` (if user chose to create one)
2. Business context saved in `BUSINESS.md`
3. Search strategy documented
4. Discovered threads saved to `{YYYY-MM}/{YYYY-MM-DD}.md` with priority rankings
