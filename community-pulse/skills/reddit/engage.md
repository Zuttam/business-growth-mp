# Reddit Engagement

## Prerequisites

Before engaging:
1. Business context must exist at `.business_growth/marketing/social/BUSINESS.md`
2. Threads should be discovered and saved to `.business_growth/marketing/social/reddit/threads.md`
3. User must be logged into Reddit in the browser

---

## Option 1: Comment on Existing Thread

### 1.1: Load and Evaluate Threads

```
Read .business_growth/marketing/social/reddit/threads.md
```

Evaluate thread fit based on:
- **Recency**: Is the thread still active? (< 24h ideal, < 7d acceptable)
- **Engagement**: Are people still commenting?
- **Relevance**: Can we provide genuine value?
- **Rules**: Does the subreddit allow this type of engagement?

### 1.2: Draft Proposed Comment

Craft a comment that:
- Directly addresses the question/problem
- Provides genuine value or insight
- Is NOT salesy or promotional
- Mentions product/service ONLY if directly relevant and helpful
- Matches the subreddit's tone and norms

### 1.3: ASK USER FOR APPROVAL

**CRITICAL**: Present to user:
```
Thread: <title>
Subreddit: r/<name>
URL: <url>
Thread Context: <brief summary of what OP is asking>

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
navigate (thread URL) → read_page (verify thread) →
find ("comment box" or "Add a comment") → form_input (comment text) →
computer (click submit/comment button) → screenshot (verify posted)
```

### 1.5: Log Engagement

Update `.business_growth/marketing/social/reddit/engagement_log.md`:

```markdown
# Reddit Engagement Log

## Summary
- **Total Engagements**: <count>
- **Comments**: <count>
- **Posts**: <count>
- **Last Activity**: <timestamp>

## History

### <date>

#### <timestamp> - Comment
- **Thread**: <title>
- **Subreddit**: r/<name>
- **URL**: <url>
- **Content**:
> <comment text>
- **Status**: posted
- **Notes**: <any observations>

---
```

Also update thread status in `threads.md` to "engaged".

---

## Option 2: Create New Post

### 2.1: Identify Target Subreddit

Based on business context, select subreddit where:
- Target audience is active
- Post type is allowed (check rules)
- Content would provide value to community

### 2.2: Research Subreddit Rules

Navigate to subreddit and check:
- Sidebar rules
- Posting guidelines
- Flair requirements
- Self-promotion policies

**Many subreddits ban promotional content. Verify before drafting.**

### 2.3: Draft Post

Create post that:
- Provides genuine value (guide, insight, question, resource)
- Follows subreddit rules and format
- Uses appropriate flair if required
- Is NOT overtly promotional

### 2.4: ASK USER FOR APPROVAL

**CRITICAL**: Present to user:
```
Target Subreddit: r/<name>
Subreddit Rules Summary: <key rules>

Post Title: <title>

Post Body:
---
<drafted post content>
---

Flair: <if applicable>

Should I create this post? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

### 2.5: Create Post via Browser MCP

Upon approval:
```
navigate (subreddit) → find ("Create Post" or "+" button) →
computer (click) → form_input (title) → form_input (body) →
select flair if needed → computer (click post/submit) → screenshot (verify)
```

### 2.6: Log Engagement

Update `engagement_log.md` with post details and status.

---

## Engagement Philosophy

### Do's
- Provide genuine value in every interaction
- Answer questions with helpful, relevant information
- Share insights that demonstrate expertise
- Be transparent about who you are when appropriate
- Respect community rules and norms

### Don'ts
- Never spam or self-promote aggressively
- Don't engage in threads where your product isn't genuinely relevant
- Avoid generic responses - be specific and helpful
- Don't ignore subreddit rules
- Never create fake accounts or astroturf
