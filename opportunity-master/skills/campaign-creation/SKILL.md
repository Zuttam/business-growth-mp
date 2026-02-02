---
name: campaign-creation
description: Create LinkedIn outreach campaigns with personalized messaging sequences. Use when user wants to create a campaign, design outreach, write messaging sequences, or set up automated follow-ups. Can be invoked with optional list_id argument (e.g., list_abc123).
---

# Campaign Creation Skill

Create LinkedIn outreach campaigns with multi-touch messaging sequences targeting specific lead lists.

## Process

### Step 0: Load Defaults

**Check for saved decisions:**

Read `.business_growth/sales/DECISIONS.md` if it exists. This provides:
- Problem we solve (for value prop messaging)
- Buyer persona (for tone and framing)
- Target industries (for relevant examples)

**If DECISIONS.md exists:**
Ask: "Want to use your saved buyer profile for messaging, or customize for this campaign?"
- **(A) Use defaults** → Pre-fill value proposition, skip those questions
- **(B) Customize** → Ask campaign-specific messaging questions

### Step 1: Select Target Lead List

If `list_id` not provided:
1. Search for existing lead lists in `.business_growth/sales/lead_lists/`
2. Display available lists with metadata
3. Ask user to select target list

Verify the list exists and load its contents.

### Step 2: Define Campaign Strategy

Ask user about campaign goals and messaging (skip questions answered in DECISIONS.md if using defaults):

1. **Campaign Goal**: What's the desired outcome?
   - Book meetings
   - Generate interest
   - Share content
   - Event invitations

2. **Value Proposition**: What's the main value for prospects? *(may come from DECISIONS.md)*
   - Problem you solve
   - Key benefits
   - Differentiation

3. **Social Proof**: What credibility elements to include?
   - Customer logos
   - Metrics/results
   - Awards/recognition

4. **Call to Action**: What should prospects do?
   - Reply to message
   - Book a call
   - Visit landing page

### Step 3: Design Message Sequence

Create a multi-touch sequence. Recommended structure:

| Step | Type | Timing | Purpose |
|------|------|--------|---------|
| 1 | Connection Request | Immediate | Initial outreach |
| 2 | Welcome Message | On accept | Build rapport |
| 3 | Value Message | +3 days | Share value |
| 4 | Follow-up | +5 days | Re-engage |
| 5 | Break-up | +7 days | Final attempt |

For each step, create:
- **Template**: Message text with personalization tokens
- **Subject** (for InMails): Compelling subject line
- **Personalization notes**: What to customize per lead

### Step 4: Create Message Templates

Write templates using personalization tokens:
- `{{first_name}}` - Lead's first name
- `{{company}}` - Lead's company
- `{{title}}` - Lead's job title
- `{{headline}}` - Lead's headline
- `{{custom}}` - Custom personalization from research

**Example Connection Request**:
```
Hi {{first_name}}, I noticed you're leading {{title}} at {{company}}.

I've been helping similar teams [value prop]. Would love to connect and share some insights that might be relevant.
```

### Step 5: Save Campaign

Generate a meaningful snake_case name based on campaign purpose and target audience (e.g., `campaign_q1_outreach_fintech`, `campaign_product_launch_series_a`). Keep names concise (3-5 words max), lowercase with underscores, no special characters.

Create `.business_growth/sales/campaigns/campaign_<name>/CAMPAIGN.md`:

```markdown
# Campaign: <Campaign Name>

## Metadata
- **Campaign ID**: campaign_<name>   # e.g., campaign_q1_outreach_fintech
- **Status**: pending
- **Target List**: <list_id>
- **Created**: <ISO timestamp>
- **Last Updated**: <ISO timestamp>

## Goal
<campaign objective>

## Messaging Strategy

### Value Proposition
<core value prop>

### Social Proof
<credibility elements>

### Call to Action
<desired action>

## Sequence

### Step 1: Connection Request
- **Type**: connection_request
- **Timing**: Immediate
- **Template**:
```
<connection request template>
```

### Step 2: Welcome Message
- **Type**: message
- **Timing**: On connection accept
- **Template**:
```
<welcome message template>
```

### Step 3: Value Message
- **Type**: message
- **Timing**: 3 days after Step 2
- **Template**:
```
<value message template>
```

### Step 4: Follow-up
- **Type**: message
- **Timing**: 5 days after Step 3
- **Template**:
```
<follow-up template>
```

### Step 5: Break-up
- **Type**: message
- **Timing**: 7 days after Step 4
- **Template**:
```
<break-up template>
```

## Performance Metrics
- **Leads Targeted**: <count from list>
- **Connection Requests Sent**: 0
- **Connections Accepted**: 0
- **Messages Sent**: 0
- **Replies Received**: 0
- **Meetings Booked**: 0

## Notes
<any additional context>
```

### Step 6: Confirm and Provide Next Steps

Summarize the campaign:
- Target list and lead count
- Sequence length and timing
- Key messaging themes

Suggest next steps:
1. Review and edit templates as needed
2. Use `/opportunity-master:lead-research` to personalize for top prospects
3. Use `/opportunity-master:campaign-execution` to start outreach

## Template Best Practices

### Connection Requests (300 char limit)
- Keep under 250 characters for full visibility
- Reference something specific about them
- Don't pitch in the connection request
- End with reason to connect

### Direct Messages
- Personalize opening line
- Keep first message short (2-3 sentences)
- Focus on their problems, not your product
- Clear, low-friction CTA
- No attachments in first message

### Follow-ups
- Reference previous message
- Add new value (insight, content, case study)
- Vary the approach each time
- Know when to stop (3-5 touches max)

## Campaign Statuses

| Status | Meaning |
|--------|---------|
| `pending` | Created but not started |
| `running` | Actively executing sequence |
| `paused` | Temporarily stopped |
| `done` | Sequence completed for all leads |
