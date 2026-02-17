# X Research & Tweet Discovery

## Prerequisites

Before starting research:
1. Load X engagement strategy from `.business_growth/marketing/social/x/strategy.md`
2. Load business context from `.business_growth/marketing/social/BUSINESS.md`
3. If either is missing, create them first (see steps below)

---

## Step 0: Load X Engagement Strategy

```
Read .business_growth/marketing/social/x/strategy.md
```

If file doesn't exist, ask the user: **"No X engagement strategy found. Would you like to create one? This defines your overall approach to X — accounts to engage with, content themes, hashtag strategy, and goals."**

If user says **yes**, gather the following and create the file:
- **Goal**: What do you want to achieve on X? (thought leadership, community building, traffic, brand awareness)
- **Accounts to Monitor**: Who are key voices, competitors, and thought leaders to engage with?
- **Content Themes**: What topics/expertise should tweets and replies focus on?
- **Engagement Rules**: Any constraints? (e.g., reply-first strategy, max tweets per day, avoid controversial topics)
- **Tone & Voice**: How should tweets/replies sound? (witty expert, helpful peer, data-driven analyst)
- **Hashtag Strategy**: Key hashtags to use (1-2 per tweet max on X)
- **Metrics to Track**: What signals success? (impressions, replies, followers, profile visits)

Create `.business_growth/marketing/social/x/strategy.md` with format:

```markdown
# X Engagement Strategy

## Goal
<what we want to achieve on X>

## Accounts to Monitor
| Account | Why | Audience |
|---------|-----|----------|
| @example | <reason> | <who follows them> |

## Content Themes
- <theme 1>: <description>
- <theme 2>: <description>

## Engagement Rules
- <rule 1>
- <rule 2>

## Tone & Voice
<description of how tweets/replies should sound>

## Hashtag Strategy
- Primary: <hashtags to use>
- Monitor: <hashtags to watch>

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

## Step 2: Generate X Search Strategy

Based on the engagement strategy (if available) and business context, determine:
- **Search Keywords**: What topics, problems, or questions does the audience tweet about?
- **Target Hashtags**: Use hashtags from strategy.md if defined, otherwise identify relevant hashtags (e.g., #buildinpublic, #indiehackers, #SaaS)
- **Accounts to Monitor**: Use accounts from strategy.md if defined, otherwise identify thought leaders, competitors, and key voices in the space
- **Content Types**: Tweets, threads, polls, spaces
- **Engagement Rules**: Respect any constraints defined in the strategy (e.g., max tweets per day, tone requirements)

---

## Step 3: Navigate X via Browser MCP

```
tabs_context_mcp → tabs_create_mcp → navigate (https://x.com/home)
```

Search across multiple X sources:

### 3a: Keyword Search (Tweets)
For each search keyword:
- Navigate to `https://x.com/search?q=<keyword>&f=live` (Latest tab)
- Also try `https://x.com/search?q=<keyword>&f=top` (Top tab)
- Scroll to load more results

### 3b: People Search
For target people/roles:
- Navigate to `https://x.com/search?q=<keyword>&f=user`
- Look for thought leaders, industry experts, potential connections

### 3c: Trending Topics
- Navigate to `https://x.com/explore/tabs/trending`
- Scan for trending topics related to the business domain

### 3d: Specific Account Timelines
For known key accounts:
- Navigate to `https://x.com/<username>`
- Scan recent tweets for relevant discussions

---

## Step 4: Extract Data

### Tweets
For each relevant tweet found:
- **Author**: Handle and display name
- **Snippet**: Tweet content (or first part for long tweets)
- **URL**: Full tweet URL
- **Likes**: Number of likes
- **Replies**: Number of replies
- **Retweets**: Number of retweets
- **Age**: How old is the tweet
- **Relevance**: Why this tweet is relevant (brief note)
- **Status**: new | evaluated | engaged | skipped

### People to Follow
For each relevant person discovered:
- **Handle**: @username
- **Name**: Display name
- **Bio**: Bio/description
- **URL**: Profile URL
- **Relevance**: Why this person is worth following (brief note)
- **Status**: new | followed | skipped

Use `read_page`, `get_page_text`, and `screenshot` to capture information.

---

## Step 5: Save to Date-Based Storage

Determine today's date and create the storage path:
```
mkdir -p .business_growth/marketing/social/x/{YYYY-MM}
```

Create/update `.business_growth/marketing/social/x/{YYYY-MM}/{YYYY-MM-DD}.md`:

```markdown
# X Activity - {YYYY-MM-DD}

## Search Strategy
- **Keywords**: keyword1, keyword2, keyword3
- **Hashtags**: #hashtag1, #hashtag2, #hashtag3
- **Accounts Monitored**: @account1, @account2, @account3
- **Search Time**: HH:MM

## People to Follow
| Time | Handle | Name | Bio | URL | Relevance | Status |
|------|--------|------|-----|-----|-----------|--------|
| HH:MM | @janedoe | Jane Doe | Building AI tools | https://x.com/janedoe | Industry thought leader | new |

## Discovered Tweets

### High Priority
| Time | Author | Snippet | URL | Likes | Replies | Retweets | Age | Relevance | Status |
|------|--------|---------|-----|-------|---------|----------|-----|-----------|--------|
| HH:MM | @johnsmith | What tools do you use for... | https://x.com/... | 120 | 45 | 30 | 2h | Asking about our domain | new |

### Medium Priority
| Time | Author | Snippet | URL | Likes | Replies | Retweets | Age | Relevance | Status |
|------|--------|---------|-----|-------|---------|----------|-----|-----------|--------|

### Low Priority / Archive
| Time | Author | Snippet | URL | Likes | Replies | Retweets | Age | Relevance | Status |
|------|--------|---------|-----|-------|---------|----------|-----|-----------|--------|

## Engagement Log

(Entries added by engage.md)
```

If the file already exists for today, append new tweets and people to the appropriate sections without overwriting existing entries.

---

## What Makes a Good X Engagement Target

Prioritize tweets that:
- Have **active reply threads** with ongoing conversation
- Are from **accounts with aligned audiences** (similar follower demographics)
- Contain **questions or debates** that invite participation
- Are **viral tweets early in their lifecycle** (< 2h old, gaining traction)
- Are from accounts where **your expertise adds a unique angle**
- Have a **high reply-to-like ratio** (indicates discussion, not just passive engagement)
- Are from people you want to **build a relationship with**

---

## Output

After completing research, you should have:
1. X engagement strategy saved in `strategy.md` (if user chose to create one)
2. Business context saved in `BUSINESS.md`
3. Search strategy documented
4. Discovered tweets saved to `{YYYY-MM}/{YYYY-MM-DD}.md` with priority rankings
5. People to follow identified and logged
