---
title: 'GitHub Copilot The Token Strikes Back'
description: 'GitHub Copilot The Token Strikes Back'
pubDate: 'May 04 2026'
heroImage: '/blogimages/gh-billing-p1/ThatsNoMoonGH.png'
---

![GitHub Billing Crawl - Star Wars style opening crawl about GitHub Copilot tokens](/blogimages/gh-billing-p1/GitHubBillingCrawl.png)

---

## Take a Breath

Ok, before we begin, I want you all to just take a breath.

It is going to be ok.

Billing schemes and prices change. We know this. It has happened before, and it will happen again.

In this case, GitHub made a decision to keep Copilot billing and pricing relatively simple. That worked for adoption, but it also meant someone was shovelling truckloads of money into the GPU fires to keep everything running.

That was never going to be sustainable forever.

So here we are.

The token meter has arrived.

That does not mean the change is harmless. It does not mean developers are wrong to be annoyed. It also does not mean Copilot is doomed, AI-assisted development is over, or we all need to retreat to a moisture farm and pretend autocomplete was enough.

What it does mean is that the mental model is changing.

We need to stop thinking only in terms of how many Copilot chats we send, and start asking better questions:

- How much context did I ask the model to read?

- How much did it generate?

- Which model did I use?

- Was this a small developer-assistance task, or a large agentic workflow?

This post is not here to sugar-coat the change. It is also not here to give in to despair.

The goal is to cut through the dark side of misinformation, lay out what GitHub has actually announced, and talk about what developers and organisations should do next.

---

## What Is Actually Changing?

GitHub Copilot is moving to usage-based billing with GitHub AI Credits from **June 1, 2026**.

Instead of counting premium requests, Copilot plans will include a monthly allocation of AI Credits. Usage will be calculated from model token consumption, including input tokens, output tokens, and cached tokens.

The important distinction is this:

> The subscription price may not be changing, but what is included inside that subscription is changing.

That matters.

Under the new model, GitHub AI Credits become the billing unit for Copilot model usage.

The simple version:

```text
1 AI Credit = USD $0.01
1,000 AI Credits = USD $10
1,900 AI Credits = USD $19
3,900 AI Credits = USD $39
```

Code completions and Next Edit suggestions remain included. The bigger impact is around the experiences that consume model capacity more directly: Copilot Chat, premium models, CLI, code review, coding agents, and larger agentic interactions.

There is another wrinkle here as well: some features may have more than one cost dimension. For example, GitHub has said Copilot code review will consume AI Credits from June 1, 2026, and may also consume GitHub Actions minutes for private repositories when GitHub-hosted runners are used.

That is a useful signal for how we should think about this whole shift. AI-assisted development is not always just “a chat message with a price.” Sometimes it is model usage, tool execution, automation, runner time, and workflow orchestration all stacked together.

So no, this does not mean every single Copilot interaction is suddenly treated the same way. But it does mean the expensive parts of AI-assisted development are becoming more visible.

And frankly, that was probably inevitable.

Cloud compute has always had a bill. AI compute just wore a nicer cloak for a while.

---

## The New Billing Unit: AI Credits

AI Credits are best understood as a wrapper around token cost.

The model matters. The number of tokens matters. The shape of the task matters.

A quick question to a lightweight model is cheap. A long-running workflow that asks a frontier model to inspect a large repository, generate code, run through iterations, and explain itself is not.

This is the shift:

```text
Old mental model:
How many requests do I get?

New mental model:
How much model work am I asking for?
```

That is the part many teams will need to internalise.

The unit of concern is no longer just the chat message. It is the amount of input, output, context, and model capability involved in completing the task.

Tiny prompt, tiny context, lightweight model? Fine.

Huge context, expensive model, multi-step agent loop? Different beast.

Possibly useful beast.

Still a beast.

---

## How Each Copilot SKU Is Impacted

The new AI Credit allowances differ by Copilot plan.

|Plan / SKU|Monthly price|Included AI Credits|What that means|
|---|--:|--:|---|
|Copilot Free|Free|Not clearly stated in the current usage-based billing table|Do not guess. Wait for clearer plan-specific detail.|
|Copilot Pro|USD $10/month|1,000 credits|USD $10 of included model usage.|
|Copilot Pro+|USD $39/month|3,900 credits|USD $39 of included model usage.|
|Copilot Business|USD $19/user/month|1,900 credits per user/month|Credits are pooled at the billing entity level.|
|Copilot Enterprise|USD $39/user/month|3,900 credits per user/month|Credits are pooled at the billing entity level.|
|Existing Business promo period|USD $19/user/month|3,000 credits per user/month|Transitional allowance during the initial move.|
|Existing Enterprise promo period|USD $39/user/month|7,000 credits per user/month|Transitional allowance during the initial move.|

The pooling model for Business and Enterprise is important. For organisations, included credits are pooled at the billing entity level. That means an organisation does not simply have thousands of tiny individual buckets that cannot help each other; lighter users can offset heavier users.

That is good.

It also means a few very heavy users, or a poorly controlled agentic workflow, can consume a meaningful chunk of the shared pool.

That is not automatically bad. Heavy users may be creating heavy value.

But it does mean the organisation needs visibility.

The Sith path here is to respond with blunt restrictions and accidental developer-hostility. The better path is to understand who is using what, where the value is coming from, and which workflows need more deliberate governance.

---

## The Honest Truth for Individual Developers

If you mostly use Copilot for code completions, Next Edit suggestions, and occasional chat, this may not dramatically change your day-to-day workflow.

The sky is not falling.

The Death Star has not reappeared behind your IDE.

But if you are using Copilot as a serious coding partner — asking it to plan, inspect broad areas of a codebase, make changes, review diffs, iterate, and explain — then you are now much more clearly in metered territory.

That does not mean “do not use it.”

It means “use it like a powerful tool with a cost profile.”

A sharp knife is useful.

A sharp knife taped to a Roomba needs supervision.

---

## The Honest Truth for Businesses

The wrong response from organisations would be to panic and clamp everything down.

That will just train developers to avoid the tooling, route around it, or quietly build shadow workflows with personal keys and mystery endpoints. That way lies governance sadness and invoices with jump scares.

The better response is to treat AI usage like an engineering platform capability:

- Observe usage patterns.
    
- Define sane defaults.
    
- Guide teams on model choice.
    
- Reserve expensive models for work that justifies them.
    
- Put explicit governance around large agentic workflows.
    

Business and Enterprise credit pooling is useful, but pooled usage still needs management.

A hard cap can protect spend, but it can also interrupt valuable work. No cap at all can feel smooth right up until finance senses a disturbance in the Force.

The goal should not be to punish usage. The goal should be to align model choice, task shape, and cost with the value being created.

If organisations only restrict without providing an approved path for heavier AI engineering work, developers may route around the system. That is how shadow AI infrastructure starts to appear, and nobody wants to discover the “approved modernisation pipeline” is actually someone’s weekend script running against a personal API key.

Cost observability is now part of developer experience.

That is the real shift.

---

## The Bit Everyone Will Be Annoyed About

Some users will experience this as paying the same amount for less practical high-end usage.

That reaction is not irrational.

If your current workflow relies heavily on expensive models under a request-based model, token-based billing may feel like a downgrade.

At the same time, the old model treated a tiny chat question and a long-running repository-wide agent task too similarly. That was never going to survive contact with real inference costs.

Both things can be true:

```text
Users are allowed to be annoyed.

GitHub is allowed to make the pricing model more closely match the cost model.
```

The useful question is not whether we can defeat billing changes through sheer keyboard force.

The useful question is how we adapt.

---

## Part 1 Takeaway

This is not just a pricing update.

It is a visibility update.

The cost of AI-assisted development was already there. It was just hidden behind simpler pricing and request-based abstractions.

Now the token meter is becoming visible.

That will be uncomfortable for some users. It will also be useful for teams that need to understand where AI is creating value and where usage is becoming wasteful.

The path forward is not panic.

It is not denial.

It is understanding the new model, making sensible choices, and refusing to let misinformation do donuts in the car park.

In Part 2, we will get practical: how many tokens you can realistically use, what cached tokens are, why context windows matter, and how to avoid turning every prompt into a token bonfire with syntax highlighting.

---

## Sources

- GitHub Blog — GitHub Copilot is moving to usage-based billing: [https://github.blog/news-insights/company-news/github-copilot-is-moving-to-usage-based-billing/](https://github.blog/news-insights/company-news/github-copilot-is-moving-to-usage-based-billing/)
    
- GitHub Blog Changelog — GitHub Copilot code review will start consuming GitHub Actions minutes on June 1, 2026: [https://github.blog/changelog/2026-04-27-github-copilot-code-review-will-start-consuming-github-actions-minutes-on-june-1-2026/](https://github.blog/changelog/2026-04-27-github-copilot-code-review-will-start-consuming-github-actions-minutes-on-june-1-2026/)
    
- GitHub Docs — Usage-based billing for individuals: [https://docs.github.com/en/copilot/concepts/billing/usage-based-billing-for-individuals](https://docs.github.com/en/copilot/concepts/billing/usage-based-billing-for-individuals)
    
- GitHub Docs — Usage-based billing for organizations and enterprises: [https://docs.github.com/en/copilot/concepts/billing/usage-based-billing-for-organizations-and-enterprises](https://docs.github.com/en/copilot/concepts/billing/usage-based-billing-for-organizations-and-enterprises)
    
- GitHub Docs — Models and pricing for GitHub Copilot: [https://docs.github.com/en/copilot/reference/copilot-billing/models-and-pricing](https://docs.github.com/en/copilot/reference/copilot-billing/models-and-pricing)
    
- GitHub Docs — Preparing for your move to usage-based billing: [https://docs.github.com/en/copilot/how-tos/manage-and-track-spending/prepare-for-your-move-to-usage-based-billing](https://docs.github.com/en/copilot/how-tos/manage-and-track-spending/prepare-for-your-move-to-usage-based-billing)
    
- GitHub Docs — Preparing your organization for usage-based billing: [https://docs.github.com/en/copilot/how-tos/manage-and-track-spending/prepare-for-usage-based-billing](https://docs.github.com/en/copilot/how-tos/manage-and-track-spending/prepare-for-usage-based-billing)