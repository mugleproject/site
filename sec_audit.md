---
layout: page
---

{% assign current_amount = 17.28 %}
{% assign target_amount = 16.0 %}

# Security Audit Funding

{:.has-text-right}
{{current_amount| divided_by: target_amount | times: 100.0 | round}}% Funded

<div class="funding-progress" style="width: 100%; background-color: green; border-color: green;"></div>
<div class="funding-progress-container"></div>

**The mugle security audit funding campaign was completed on December 20th 2018. Thank you to all who generously donated!**

**UPDATE 2019-10-23: The report and findings have now been published: https://forum.mugle.org/t/mugle-security-audit-2-results/6264**

TL;DR Mugle is nearing its final phases of development before the release of
its cryptocurrency network (mainnet). To do so safely, the Mugle codebase needs
to undergo a security audit.

Status: Closed

Goal: {{target_amount | round}} BTC

Raised: {{current_amount}} BTC

## Who?

- You, the investor who plans to acquire mugles, and believes in its value
  proposition of privacy and scalability.
- You, the miner or mining industry participant, who plans on participating in
  the mining of the Mugle chain.
- You, the cypherpunk or otherwise bitcoin, ethereum, monero or zcash adopter,
  who believes Mugle makes an important contribution in furthering some of those
  early cryptocurrency ideals.
- You, the technology enthusiast, who sees something in Mugle that has never
  been tried before and is new and exciting.
- You, who's not in any of the above categories, but believes that the current
  financial system status quo could use a good kick in the pants.

On our end, the Mugle Council (which handles all governance oversight) nominated
5 secretaries. Those 5 individuals generated a 3-of-5 bitcoin segwit multisig
address under supervision of the council, to guarantee funds' safety. Note that
everyone in both the council and the secretary group are fully independent
individuals, working in entirely different capacity in different parts of the
world.

## Why?

When Mugle launches, it will likely be used to secure the equivalent of
millions of dollars (or euros, yuans, yens, pesos, etc) on its chain within
a few days or weeks. While the Mugle development team has done everything it
can to identify and fix possible major security failures, Mugle is still a very
young and unproven codebase.

To reduce risks and follow standard industry practices (at least in the
security industry), the Mugle team is requesting a general code audit by a
professional firm. The cost of the audit is estimated to be around $100,000.

## How?

Multiple firms have already been contacted and we will be undergoing a process
of selection in the next few weeks. Once a firm is retained, we will strive to
pay it directly from the fund (most firms accept bitcoin). Any excess will be
used for the general maintenance of the Mugle project.

We expect the audit to last one to two months, during which every new Mugle
development will undergo extreme scrutiny. Once the audit is finished and all
discovered issues are either fixed or found to be minor, we will be ready to
launch Mugle's main network.

More generally, the guidelines in the Mugle [security policy](https://github.com/mugleproject/mugle/blob/master/SECURITY.md)
apply.
