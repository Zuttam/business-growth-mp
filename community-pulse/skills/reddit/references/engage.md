# Reddit Engagement

## Prerequisites

Before engaging:
1. Business context must exist at `.business_growth/marketing/social/BUSINESS.md`
2. Threads should be discovered and saved to `.business_growth/marketing/social/reddit/{YYYY-MM}/{YYYY-MM-DD}.md`
3. User must be logged into Reddit in the browser (use login skill or log in manually)

---

## Option 1: Comment on Existing Thread

### 1.1: Load and Evaluate Threads

```
Read .business_growth/marketing/social/reddit/{YYYY-MM}/{YYYY-MM-DD}.md
```

If today's file doesn't exist, check previous days or run Research first.

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

Update today's file at `.business_growth/marketing/social/reddit/{YYYY-MM}/{YYYY-MM-DD}.md`, appending to the `## Engagement Log` section:

```markdown
### HH:MM - Comment
- **Thread**: <title>
- **Subreddit**: r/<name>
- **URL**: <url>
- **Content**:
> <comment text>
- **Status**: posted
- **Notes**: <any observations>

---
```

Also update the thread's status in the Discovered Threads table to "engaged".

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

Update today's file at `.business_growth/marketing/social/reddit/{YYYY-MM}/{YYYY-MM-DD}.md`, appending to the `## Engagement Log` section with post details and status.

## Option 3: Check Notifications & Follow Up

Run this as part of every daily engagement session, ideally before posting new comments. Check each active profile for replies, upvotes, and threads that need attention.

### 3.1: Load Active Profiles

```
Read .business_growth/marketing/social/reddit/.env.profiles.local
```

Identify all profiles that have posted in the last 3 days by checking recent daily comment files.

### 3.2: Log Into Each Profile & Check Notifications

For each profile that has recent activity:

```
Log in (see login.md) → navigate to https://www.reddit.com/notifications →
screenshot → read_page or get_page_text
```

Review notifications for:
- **Direct replies** to your comments (highest priority - someone engaged with you)
- **Upvote milestones** on your comments (signals resonance)
- **OP replies** to your comments (very high priority - the thread author responded)
- **Mentions** or tags in other threads

### 3.3: Evaluate Which Replies Need a Response

Not every reply needs a follow-up. Respond when:
- Someone asks a follow-up question
- OP engages with your comment directly
- Someone challenges your point with a substantive argument (opportunity to deepen credibility)
- A reply creates an opening to add more value without being pushy

Skip responding when:
- The reply is just agreement ("great point", "+1")
- The thread has gone cold (>48h since last activity)
- Engaging would look like you're trying to get the last word
- The reply is hostile or trolling (never engage with bad faith)

### 3.4: Draft & Post Follow-Up Replies

For replies worth responding to:

```
navigate (comment permalink) → find (Reply button under the reply) →
computer (click) → type (response) → computer (click submit) → screenshot
```

Follow-up reply guidelines:
- Keep it shorter than your original comment
- Be conversational, not lecturing
- Thank OP if they validated your point
- Add one new insight max - don't repeat yourself
- Match the energy of the person you're replying to

### 3.5: ASK USER FOR APPROVAL

**CRITICAL**: Before posting any follow-up reply, present to user:
```
Profile: <profile name>
Thread: <title>
Their reply: <what they said>

Proposed response:
---
<drafted reply>
---

Should I post this reply? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

### 3.6: Log Follow-Ups

Update the daily comments file with a follow-up section:

```markdown
## Follow-Up Activity - {YYYY-MM-DD}

### Profile: <username>
- **Thread**: <title> (r/<subreddit>)
- **Original comment**: Comment <#> from <date>
- **Their reply**: <summary of what they said>
- **Our response**: <what we replied>
- **Upvotes on original**: <current count>
```

### 3.7: Check Previously Engaged Threads

Also spot-check 2-3 threads from the past 2-3 days (already tracked in threads.md "PREVIOUSLY ENGAGED THREADS" section):
- Has the comment gained upvotes? (signal of resonance)
- Has the thread grown significantly? (opportunity for a second natural comment if the conversation evolved)
- Has anyone replied that we missed via notifications?

Update the next day's threads.md with current engagement numbers.

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
