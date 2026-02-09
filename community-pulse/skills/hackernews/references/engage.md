# Hacker News Engagement

## Prerequisites

Before engaging:
1. Business context must exist at `.business_growth/marketing/social/BUSINESS.md`
2. Threads should be discovered and saved to `.business_growth/marketing/social/hackernews/{YYYY-MM}/{YYYY-MM-DD}.md`
3. User must be logged into Hacker News in the browser (use login skill or log in manually)

---

## Option 1: Comment on Existing Thread

### 1.1: Load and Evaluate Threads

```
Read .business_growth/marketing/social/hackernews/{YYYY-MM}/{YYYY-MM-DD}.md
```

If today's file doesn't exist, check previous days or run Research first.

Evaluate thread fit based on:
- **Recency**: Is the thread still active? (< 24h ideal, < 3d acceptable on HN)
- **Engagement**: Are people still commenting?
- **Relevance**: Can we provide genuine value?
- **Depth**: Does the thread have room for a substantive contribution?

### 1.2: Draft Proposed Comment

Craft a comment that:
- Provides substantive, thoughtful insight (HN rewards depth)
- Shares genuine expertise, data, or first-hand experience
- Is NOT promotional or marketing-speak
- Avoids buzzwords, hype, or shallow takes
- Adds to the conversation rather than repeating existing points
- Mentions product/service ONLY if directly relevant and genuinely helpful

### 1.3: ASK USER FOR APPROVAL

**CRITICAL**: Present to user:
```
Thread: <title>
Type: <story/ask/show>
URL: <url>
Thread Context: <brief summary of discussion>

Proposed Comment:
---
<drafted comment>
---

Should I post this comment? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

### 1.4: Post Comment via Browser MCP

Upon approval:
```
navigate (thread URL) → find ("reply" link near relevant comment or main reply box) →
computer (left_click on reply) → find (textarea) → form_input (comment text) →
find ("add comment" button) → computer (left_click) → screenshot (verify posted)
```

### 1.5: Log Engagement

Update today's file at `.business_growth/marketing/social/hackernews/{YYYY-MM}/{YYYY-MM-DD}.md`, appending to the `## Engagement Log` section:

```markdown
### HH:MM - Comment
- **Thread**: <title>
- **URL**: <url>
- **Content**:
> <comment text>
- **Status**: posted
- **Notes**: <any observations>

---
```

Also update the thread's status in the Discovered Threads table to "engaged".

---

## Option 2: Submit New Post

### 2.1: Determine Post Type

HN supports three main post types:
- **Story**: Link to an article, blog post, or resource via the URL field
- **Ask HN**: Question to the community (prefix title with "Ask HN: ")
- **Show HN**: Share something you've built (prefix title with "Show HN: ")

### 2.2: Draft Post

Create a post that:
- Provides genuine value (interesting content, useful tool, thoughtful question)
- Follows HN guidelines (no clickbait titles, no self-promotion spam)
- Uses a factual, understated title (HN community edits sensationalized titles)
- For Show HN: clearly explains what it does and why it's interesting

### 2.3: ASK USER FOR APPROVAL

**CRITICAL**: Present to user:
```
Post Type: <Story / Ask HN / Show HN>
Title: <title>
URL: <url, if story or Show HN>

Post Body (if applicable):
---
<text content>
---

Should I submit this post to Hacker News? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

### 2.4: Submit Post via Browser MCP

Upon approval:
```
navigate (https://news.ycombinator.com/submit) →
find ("title" input) → form_input (title) →
find ("url" input) → form_input (url) [OR find ("text" textarea) → form_input (text)] →
find ("submit" button) → computer (left_click) → screenshot (verify posted)
```

### 2.5: Log Engagement

Update today's file at `.business_growth/marketing/social/hackernews/{YYYY-MM}/{YYYY-MM-DD}.md`, appending to the `## Engagement Log` section:

```markdown
### HH:MM - Post (<type>)
- **Title**: <title>
- **URL**: <submitted URL or HN thread URL>
- **Content**:
> <post text, if any>
- **Status**: posted
- **Notes**: <any observations>

---
```

---

## HN Engagement Philosophy

### Do's
- Provide substantive, well-reasoned comments
- Share first-hand experience and specific data
- Engage with intellectual curiosity
- Acknowledge nuance and trade-offs
- Reference relevant sources or research
- Be transparent about affiliations

### Don'ts
- Never use marketing speak or buzzwords
- Don't post shallow "great post!" comments
- Avoid self-promotion unless directly relevant and disclosed
- Don't engage in flame wars or personal attacks
- Never game the system (ask for upvotes, use multiple accounts)
- Don't submit the same link repeatedly
- Avoid commenting on topics outside your expertise with generic takes

### HN-Specific Guidelines
- **Karma matters**: Low-karma accounts have limited posting ability
- **Flagging**: Promotional or off-topic content gets flagged and killed
- **Downvotes**: Available to users with 500+ karma; low-quality comments get buried
- **Rate limits**: HN limits submission frequency, especially for newer accounts
- **Title edits**: Moderators may edit sensationalized titles
- **Duplicate detection**: HN flags duplicate URL submissions
