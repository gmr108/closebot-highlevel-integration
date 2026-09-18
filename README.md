# closebot highlevel integration: How to Connect CloseBot to GoHighLevel, What It Actually Costs, and When It Beats GHL's Native AI

If you searched for closebot highlevel integration, you probably already have GoHighLevel open in one tab and a lead that went cold in another. The question is rarely "what is CloseBot" — it is "how do I actually wire this thing up, what will it cost me per month, and is it worth paying on top of a CRM subscription I already have?"

Short version: the connection itself takes minutes. It's an OAuth handshake, not an API project. The parts that catch people out are the token costs nobody budgets for, the difference between the Free/Business/Agency tracks, and the fact that CloseBot is not a GHL feature — it's a separate subscription that lives on top of your CRM.

Here's the whole picture, with prices checked against CloseBot's current plans page.

## What the CloseBot + HighLevel integration actually is

CloseBot is a conversational AI agent platform built for appointment setting. It connects to HighLevel (and HubSpot, LeadConnector, and custom CRMs) and takes over the text-based conversations already flowing through your CRM: SMS, email, live chat, and any channel you've wired into the GHL Conversations inbox.

That last part matters more than it sounds. CloseBot does not connect to Instagram, WhatsApp, or Messenger on its own. Those channels belong to your CRM. If your GHL sub-account has Instagram DMs flowing into its inbox, CloseBot can answer them. If Instagram isn't connected in GoHighLevel, there's nothing for the agent to reply to. CloseBot is the brain; HighLevel is the nervous system.

The integration type is a native app connection — CloseBot's HighLevel app is the most-installed sub-account app in the HighLevel marketplace, according to CloseBot's own pricing breakdown. You authorize it per sub-account, and it reads and writes to your CRM: tags, custom fields, pipeline stages, calendars, and conversation history.

One structural note before you start: CloseBot V2 splits accounts. Agency-level accounts build and manage the agents. Sub-accounts can connect to HighLevel or LeadConnector, upload knowledge documents, edit their own business info, and view dashboards — but they can't rewrite the agent logic. If you're an agency handing clients a live dashboard, that's a feature. If you're a solo operator, it's just one less thing to click.

## Before you connect: what has to be in place first

Four things, and skipping any of them is where most "it's not working" threads start.

1. **A HighLevel sub-account you can authorize.** The OAuth flow asks you to pick a specific sub-account, not your whole agency. Connecting the wrong one is the single most common setup mistake.
2. **A calendar inside that sub-account.** The agent books into GHL calendars. If nothing is bookable, the agent qualifies leads and then has nowhere to send them.
3. **Your AI provider account.** CloseBot V2 requires your own API key from an AI provider and does not cover provider token costs — those are billed by OpenAI, Anthropic, or whoever you pick. CloseBot supports OpenAI, Anthropic, Gemini, Grok, and DeepSeek, and you can set provider preference per persona with automatic fallback if the primary model fails.
4. **A defined objective.** CloseBot agents are objective-driven, not script-driven. You write the goal ("qualify the lead, collect address and budget, book a 30-minute estimate"), attach knowledge, and the agent reasons through the conversation rather than following a keyword tree.

CloseBot publishes a walkthrough called [48 Second Setup](https://docs.closebot.com/en/articles/11395273-48-second-setup) for registering and connecting a first source, which is a fair indication of how much friction the company thinks there should be. If you want to see the connection flow for yourself without paying, 👉 [👉 Start on the free tier and connect a HighLevel sub-account here](https://app.closebot.com/a?fpr=li87).

## Step-by-step: connecting a HighLevel sub-account to CloseBot

This is the documented flow, and it hasn't changed much since V2 launched.

1. Open CloseBot and go to the **Sources** page.
2. Click to add a new source and choose **HighLevel Sub-Account**.
3. Hit **Connect**. An OAuth popup opens.
4. Sign in to HighLevel if you aren't already, then choose the workspace or account you want to authorize.
5. In the permissions tab that opens, scroll to the bottom and approve the CloseBot app permissions.
6. Select the sub-account you want to connect, then return to the CloseBot tab.
7. Back in CloseBot, click **Add Source**. You land on the Sources list, and the new connection should be listed there.

If the sub-account doesn't appear in step six, you're usually logged into the wrong agency-level HighLevel account. If the source appears in CloseBot but conversations don't reach an agent, the problem is almost always that no Job Flow is listening to that source yet.

Worth knowing: Sources come with filters. You can restrict an agent to specific conversations rather than letting it answer everything in the sub-account, which is how most people keep a bot away from existing client threads while they're testing.

## From blank agent to booked appointment

A connected source does nothing by itself. In CloseBot V2, work happens through Job Flows: each flow connects a source, a persona, and the objectives the agent works through. The persona carries voice and tone — including things like response timing and small stylistic quirks — separately from the agent logic, which means one persona can serve several agents across different industries.

Then the GHL side does what GHL does best. The agent updates tags and custom fields as the conversation progresses, and those tags drive your existing workflows. The common patterns people describe are straightforward: a tag that says the lead is ready to book triggers a scheduling link, a do-not-disturb tag tells the agent to stop replying, and a qualified tag hands the contact to a human closer.

Before anything goes live, run conversations through the testing portal. You can roll back changes, and you can pause the AI mid-conversation for a human takeover — which is the feature that makes this bearable in a regulated or high-ticket sales environment. CloseBot also flags questions the agent can't answer confidently through Smart FAQ, then follows up with every lead who asked that question once you've supplied the answer. That last mechanic is the difference between a hallucinated discount and a handled objection.

## Which channels the agent replies on

Text-based channels inside your CRM, plus email. CloseBot has supported email replies for about two years, which is longer than most GHL-native AI tooling, and the agent can see images customers send. The site states support for 40+ languages, driven by the underlying models.

The honest limitation: the channel coverage is only as good as your CRM's coverage. Live chat on your GHL site, SMS through your GHL number, and Instagram or WhatsApp conversations that route into GHL all work. A channel that never reaches HighLevel never reaches CloseBot.

## What it costs: base plans, message fees, and the part people forget

Here's the full plan lineup from CloseBot's current plans page. Nothing is hidden behind a quote form except the Growth tier.

| Plan | What's included | Price | Billing | Purchase |
| --- | --- | --- | --- | --- |
| Free | 100 monthly messages, 1 agent, 1 user seat, 1 MB knowledge storage, unlimited account connections | $0 | Always free | [ Start free and connect your first source](https://app.closebot.com/a?fpr=li87) |
| Core (Business) | Message costs included in the base price, 15+ templates, human support, add-on users ($5/seat), add-on storage and agents | From $64/mo | Monthly, or $53/mo billed as $640/yr on annual | [ See the Business plan tiers](https://app.closebot.com/a?fpr=li87) |
| Core (Agency) | Unlimited messages at $0.012/message rebillable, white-label client portal, rebill all costs, invite additional users, extra storage and agents | $397/mo | Monthly, roughly $331/mo equivalent on annual billing | [ Set up the Agency plan with rebilling](https://app.closebot.com/a?fpr=li87) |
| Growth | HIPAA compliance, quarterly audits, 99.99% priority uptime, priority support, 50+ templates, SLAs | Custom quote | Custom | [ Talk to CloseBot about Growth pricing](https://app.closebot.com/a?fpr=li87) |

Two details that change the math:

**The Business track scales with message volume, not seat count.** The plans page slider moves from 500 messages up to 100K+, and the price climbs with it — the current page shows roughly $84/mo at 1,000 messages, $176 at 5,000, and around $1,059 at 100,000. The entry price buys you 500 included messages; go over your ceiling and overage is charged at a 2x rate drawn from your wallet. If you're at 50,000 messages a month, the Agency plan at $397 plus $0.012/message is the cheaper shape.

**Token costs sit outside the subscription.** Message fees pay CloseBot for routing your agent's work. Token costs go to your AI provider. CloseBot's own pricing breakdown puts token spend at roughly $0.0025–$0.01 per message depending on the model, and notes that a switch to DeepSeek can cut that to about a quarter of OpenAI's rate on comparable quality. In their worked example, a 102-sub-account account doing 24,720 messages a month pays $397 base + $148 in message fees + $255 in OpenAI tokens, or $617 total on DeepSeek instead of $809.

> One number to watch: CloseBot's help center and older blog posts still list the agency message rate at $0.006/message. The current plans page says $0.012/message. Budget for the higher figure until support tells you otherwise.

A free plan caveat too: over 100 messages, the Free tier bills $0.08 per message, and storage is capped at 1 MB with no way to expand it. Business plans include 1 MB and let you add storage in the $0.10–$3.00 per MB per month range. Agency accounts pay $0.006 per MB per day and can mark that up to clients like everything else.

And the cost most reviews bury: CloseBot runs on top of a CRM, so your bill is never just CloseBot. HighLevel's own plans start at $97/month for Starter, $297 for Unlimited, and $497 for Agency Pro. A business wanting about 1,000 AI messages a month is realistically looking at $84 (CloseBot) plus $97 (GHL Starter) before WhatsApp fees or token spend.

## CloseBot vs HighLevel's native Conversation AI

HighLevel ships its own conversational AI. It's included in the platform and it handles basic replies. The question is whether it books appointments as reliably as a purpose-built agent, and here the two products diverge sharply.

|  | HighLevel Conversation AI | CloseBot |
| --- | --- | --- |
| Pricing | $0.02/message rebillable, or AI Employee at $97/sub-account/month for unlimited usage | $64–$397/mo base, plus message costs on the Agency track |
| AI providers | OpenAI-dependent | OpenAI, Anthropic, Gemini, Grok, DeepSeek, selectable per persona with fallback |
| Channels | Text channels inside GHL | Same channels plus email; reads images |
| Custom fields | Recently raised to 20 fields | Unlimited |
| Booking | Conversation AI booking, no drag-and-drop builder | Objective-based drag-and-drop builder, conversational rescheduling and cancellations across calendar types |

The $97-per-sub-account unlimited option is where the economics flip. On 102 sub-accounts that's $9,894/month against CloseBot's $809 in the same scenario. On four sub-accounts, HighLevel's unlimited tier is roughly $388 and CloseBot's agency plan is $403.50 — near parity. Scale is what makes one route cheaper than the other, and the direction of the saving is not the same for both.

Treat the performance claims as vendor claims. CloseBot states that side-by-side split testing showed a 10% quality gap in conversational booking and cites up to 20% more bookings from retrying failed calendar slots rather than telling a lead the slot is taken. Those numbers come from CloseBot, not an independent audit. What you can verify yourself is the structural difference: five model providers with automatic fallback, unlimited custom field updating, and an agent that reasons through an objective instead of matching keywords. Whether that's worth $300/month depends entirely on how many appointments you're losing at the moment.

## What tends to break after you connect

A few failure modes come up repeatedly in agency communities, and they're worth knowing before you blame the tool.

**Booking behaviour changed between versions.** A June 2025 thread in r/gohighlevel describes an agency whose V2 agent stopped creating calendar appointments automatically the way V1 did. CloseBot's official account replied pointing people to 24/7 live chat support and a weekly schedule of 10+ hours of office hours calls. If booking silently stops, that's your first stop, not a support ticket queue.

**Wrong source, right agent.** Connecting the wrong sub-account during OAuth produces a source that looks healthy in CloseBot and never sees a single conversation.

**Provider limits, not agent failures.** If your OpenAI account hits a spending cap, the agent has nothing to think with. The persona-level provider fallback exists for exactly this, but it only helps if you've configured a second provider.

**No Job Flow listening.** Sources and Job Flows are separate objects. Connected source, no flow, no replies.

**Support expectations.** CloseBot's blog states roughly 12 minutes average wait before a human joins a support chat, and the company maintains a community of 2,000+ members with courses and daily calls. For a tool where a broken agent costs booked appointments, that support layer is part of what the subscription buys.

## Who this integration actually fits

The integration is close to ideal if you run a marketing agency selling AI setting to clients under your own brand. White-label client portals, client seats, Stripe-based rebilling, and per-message cost pass-through turn a software expense into a margin line — and you can reprice both messages and token usage however you like. Agencies on the platform report billing clients anywhere from $100 to $10,000+ per month for the same service.

It fits less well if you're a solo operator whose leads arrive as Instagram DMs and who doesn't run a CRM. You'd be buying GoHighLevel purely to host CloseBot. The agent quality is genuinely good; the architecture just assumes a CRM is already the centre of your operation.

Middle ground: a business running its own pipeline — real estate, home services, healthcare, coaching — using the Business plans where message costs are bundled into the base price. That's $64/month to start with 500 messages included, which is a low-risk way to test whether an agent books better than whoever is currently answering the phone. 👉 [👉 Compare all CloseBot plans and start with the free tier](https://app.closebot.com/a?fpr=li87).

## FAQ

**Does CloseBot connect to GoHighLevel natively?**
Yes. It's a native app-style connection authorized per HighLevel sub-account through OAuth, and CloseBot is the most-installed sub-account app in HighLevel's marketplace according to its own published comparison.

**How long does the connection take?**
The OAuth flow itself takes a couple of minutes. CloseBot documents a "48 second setup" for registering and connecting a first source. Building an agent worth going live with takes longer — most people describe getting a first agent tested and live the same day.

**Do I need my own API keys?**
CloseBot V2 requires your own AI provider account, and provider token costs are not included in the subscription. You can choose between OpenAI, Anthropic, Gemini, Grok, and DeepSeek, and set a fallback provider at the persona level.

**Is there a free plan?**
Yes, and it's free forever as long as you stay under 100 messages a month. You get 1 agent, 1 seat, 1 MB of storage, and unlimited account connections. Paid plans also come with a 7-day trial before billing starts. CloseBot states plainly that there are no refunds, so the trial is where you do your testing.

**Can I use CloseBot without GoHighLevel?**
Yes. It also connects to HubSpot, LeadConnector, and custom CRMs, and it works standalone without a CRM at all. You just need a text channel for the agent to work in.

**What happens when the AI gets stuck?**
It flags the question through Smart FAQ instead of inventing an answer, and you can pause the agent on any individual conversation to take over as a human. Once you've answered the flagged question, CloseBot can automatically follow up with every lead who asked it.

## The bottom line

The CloseBot–HighLevel connection is the easy part; it's an OAuth click and a Job Flow configuration. The decision that actually matters is which track you're on. Agencies that rebill clients should be looking at the $397 Agency plan and the $0.012-per-message rate, because the rebilling and white-label portal only exist there. Businesses running their own pipeline are better served by the all-inclusive Business plans where message costs are baked into the price, starting at $64/month.

Either way, add up the CRM subscription and your AI provider token spend before you commit. The subscription is the visible cost; the tokens and the platform underneath are the ones that decide whether the setup pays for itself.
