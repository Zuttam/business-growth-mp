# How to Check LinkedIn Connection Accepts

## The Right Method

**Use the LinkedIn Connections page** — it's the fastest and most reliable way.

1. Navigate to: `https://www.linkedin.com/mynetwork/invite-connect/connections/`
2. It defaults to **"Sort by: Recently added"** — most recent accepts appear at the top
3. Scroll through recent connections
4. Cross-reference names against campaign lead lists in `.business_growth/sales/campaigns/<campaign_id>/LIST.md`
5. Any lead name that appears on the connections page = they accepted

## What NOT to Do

| Method | Why It Fails |
|--------|-------------|
| Sent Invitations tab | Accepted connections disappear from there — unreliable |
| Individual profile checks | Too slow, one-by-one is not scalable |
| Notifications tab | Connection accepts get buried under other notifications |
| Messaging "Connections" filter | Only shows existing connections you've already messaged |

## Handling Accepts

For each accepted connection:

### 1. Check Current Step
Read their execution file at:
`.business_growth/sales/campaigns/<campaign_id>/leads/<lead_name>/execution.md`

### 2. Send Welcome Message (if on Step 1)
If they're on Step 1 (connection request) and accepted:
- Load the Step 2 welcome message template from `CAMPAIGN.md`
- Personalize with `{{first_name}}` and any other tokens
- Navigate to LinkedIn Messaging, find their conversation
- Type and send the message

### 3. Update Execution File

```markdown
## Status
- **Current**: in_progress
- **Current Step**: 2
- **Next Action**: follow_up_message
- **Next Action Time**: <+5 days from now>

## Action Log

### <timestamp>
- **Step**: 1
- **Type**: connection_request
- **Outcome**: Accepted (<date>)

### <timestamp>
- **Step**: 2
- **Type**: message
- **Content**: <actual welcome message sent>
- **Outcome**: sent
```

### 4. Update Campaign Metrics
Update the campaign's `CAMPAIGN.md` performance metrics with new accept counts.

## Rate Limits When Sending Welcome Messages

Space messages **30-60 seconds apart** when sending Step 2 to multiple accepts in one session.
