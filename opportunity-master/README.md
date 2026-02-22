# Opportunity Master Plugin

A Claude Code plugin for sales automation with specialized SDR and Account Executive agents for LinkedIn-based prospecting and pipeline management.

## Features

### Agents

| Agent | Purpose |
|-------|---------|
| **SDR Agent** | Lead generation, LinkedIn prospecting, outreach campaigns |
| **Account Executive Agent** | Pipeline management, deal progression, sales strategy |

### Skills

| Skill | Command | Description |
|-------|---------|-------------|
| List Building | `/opportunity-master:list-building` | Build targeted lead lists from LinkedIn |
| Campaign Creation | `/opportunity-master:campaign-creation` | Create outreach campaigns with messaging sequences |
| Campaign Execution | `/opportunity-master:campaign-execution` | Execute campaigns and track progress |
| Lead Research | `/opportunity-master:lead-research` | Research prospects for personalization |

## Prerequisites

- **Claude in Chrome Extension**: Required for LinkedIn browser automation
- Browser must be open with LinkedIn logged in

## Installation

Add to your project's `.claude/settings.json`:

```json
{
  "enabledPlugins": {
    "opportunity-master@plugin-marketplace": true
  }
}
```

Or run with plugin directory:

```bash
claude --plugin-dir /path/to/plugin-marketplace/opportunity-master
```

## Data Storage

All data is stored in the `.business_growth/sales/` directory of your project. Directories are automatically created when the relevant agent starts:
- SDR Agent creates: `campaigns/`, `templates/`
- Account Executive Agent creates: `opportunities/`

```
.business_growth/sales/
├── DECISIONS.md                       # Global defaults
├── campaigns/                         # Campaigns (ICP, leads, outreach, execution)
│   └── campaign_<name>/               # e.g., campaign_fintech_vp_eng
│       ├── icp.md                     # ICP definition
│       ├── LIST.md                    # Lead list
│       ├── CAMPAIGN.md                # Outreach strategy + sequence
│       └── leads/
│           └── <lead_name>/           # e.g., john_smith_acme
│               ├── execution.md       # Action log
│               └── research.md        # Lead research
├── opportunities/                     # Sales opportunities (AE agent)
│   └── opp_<name>.md                  # e.g., opp_acme_corp_enterprise_deal
└── templates/                         # Reusable message templates
```

**Naming Convention**: All entity names use snake_case (lowercase with underscores), include key identifying info, and are kept concise (3-5 words max).

## Usage Examples

### Build a Lead List

```
/opportunity-master:list-building campaign_fintech_vp_eng VP Engineering at Series B SaaS companies in San Francisco
```

### Create an Outreach Campaign

```
/opportunity-master:campaign-creation campaign_fintech_vp_eng
```

### Execute Campaign Actions

```
/opportunity-master:campaign-execution campaign_fintech_vp_eng run
```

### Research a Prospect

```
/opportunity-master:lead-research campaign_fintech_vp_eng https://linkedin.com/in/johndoe
```

## LinkedIn Rate Limits

The plugin advises on LinkedIn's usage limits:

| Action | Limit |
|--------|-------|
| Profile views | ~30/hour, ~100/day |
| Connection requests | ~20-25/day |
| Messages | ~50-100/day |

Campaign execution uses a manual check-in approach - you invoke the skill periodically to process pending actions, giving you control over pacing.

## Workflow Example

1. **Create Campaign** → Start by naming your campaign (e.g., `campaign_fintech_vp_eng`)
2. **Define ICP & Build List** → Use list-building to define ICP and find prospects (saves `icp.md` + `LIST.md` to campaign folder)
3. **Research Top Leads** → Use lead-research to personalize outreach (saves `research.md` per lead)
4. **Create Outreach** → Design messaging sequence (saves `CAMPAIGN.md` to campaign folder)
5. **Execute** → Run campaign with periodic check-ins (creates `execution.md` per lead)
6. **Convert** → When leads respond, AE agent helps with pipeline

## Version History

- **0.1.0** - Initial release with SDR/AE agents and core skills

## Author

Hissuno
