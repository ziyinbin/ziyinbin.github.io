---
permalink: /
title: "Ziyin Bin · 宾梓吟"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

{%- comment -%}
  Two-mode homepage:
  · production (GitHub Pages) → "Site under construction" placeholder
  · development / docker (jekyll serve / Codespaces) → full bio + research
  When ready to launch, just delete the {% if %}/{% else %}/{% endif %} wrapper
  and keep the full-content branch as the only content.
{%- endcomment -%}

{% if jekyll.environment == "production" %}

<style>
  .construction-card{max-width:560px;margin:6rem auto 0;padding:2.5rem 2rem;text-align:center;font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;line-height:1.6;}
  .construction-card h1{font-weight:600;font-size:1.6rem;margin:0 0 .25rem;color:#1a1a1a;}
  .construction-card .zh{color:#777;font-size:1rem;margin-bottom:2rem;}
  .construction-card .status{display:inline-block;padding:.35rem .9rem;background:#f3f3f3;border-radius:999px;font-size:.85rem;color:#555;margin-bottom:2rem;letter-spacing:.02em;}
  .construction-card p{color:#555;font-size:.95rem;margin:.75rem 0;}
  .construction-card a{color:#1a3a8a;text-decoration:none;border-bottom:1px solid #cbd6f0;padding-bottom:1px;}
  .construction-card a:hover{border-color:#1a3a8a;}
  .construction-card .links{margin-top:2rem;font-size:.95rem;}
  .construction-card .links span{margin:0 .5rem;color:#bbb;}
</style>

<div class="construction-card" markdown="1">

<span class="status">Site under construction</span>

# Ziyin Bin
<div class="zh">宾梓吟</div>

PhD Candidate in Operations Management, Fudan University.

The full personal site will launch ahead of the **2026–2027 academic job market**.

For research inquiries, please contact me directly.

<div class="links" markdown="1">
[Email](mailto:zybin23@m.fudan.edu.cn) <span>·</span> [SSRN](https://papers.ssrn.com/sol3/cf_dev/AbsByAuth.cfm?per_id=8432028)
</div>

</div>

{% else %}

I am a PhD candidate in **Management Science** at the [School of Management, Fudan University](https://www.fdsm.fudan.edu.cn/en/), advised by **Prof. Xiaole Wu**. My research lies at the intersection of **operations management** and **financial risk management**, with a current focus on hedging strategies for supply chains exposed to exchange rate, commodity, and policy risks, and structural analysis of capital-intensive manufacturing supply chains.

I will be on the **2026–2027 academic job market** for tenure-track positions in Operations Management.

## Working Papers

- **[Integrated Hedging Strategies for Exchange Rate and Commodity Price Risks](https://ssrn.com/abstract=5559558)** &nbsp;*(with Panos Kouvelis, Xiaole Wu, Yixuan Xiao)* — Optimal joint hedging of FX and commodity risks; competition induces complementary hedging strategies in equilibrium. **Major Revision at *Management Science***. [SSRN](https://ssrn.com/abstract=5559558)
- **A Structural Analysis of the Four-tier Photovoltaic Industry: The Effects of Capacity, Mergers, and Policies** &nbsp;*(with Mengfei Li, Zibo Liu, Lezhen Wu, Xiaole Wu)* — Cournot oligopoly model for the four tiers of China's crystalline-silicon PV supply chain; recursive cost-shock and merger counterfactuals.

See the [Research](/publications/) page for full details.

## Upcoming Talks

- **2026 POMS Annual Conference** (Las Vegas, NV)
  - *PV paper* — Saturday, May 9, 1:45–3:15 PM (Nevada 6); session: *Strategic Competition and Cooperation in Sustainable Markets*
  - *Hedging paper* — Sunday, May 10, 10:20–11:50 AM (Nevada 11); session: *Risk, Signals, and Supply Chain Strategy*
- **2026 Supply Chain Finance Workshop**, Singapore Management University — May 18–19, 2026 (PV paper)

See [Talks](/talks/) for the full list.

## Contact

- **Email:** [zybin23@m.fudan.edu.cn](mailto:zybin23@m.fudan.edu.cn)
- **Office:** Li Da San Building (李达三楼), School of Management, Fudan University, Shanghai
- **CV:** [PDF](/files/cv.pdf) · **SSRN:** [author page](https://papers.ssrn.com/sol3/cf_dev/AbsByAuth.cfm?per_id=8432028)

{% endif %}
