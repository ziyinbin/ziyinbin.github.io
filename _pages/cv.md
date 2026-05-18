---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* **Ph.D. Candidate in Management Science**, *2021 – present (MPhil-PhD Program)*
  * School of Management, Fudan University, Shanghai
  * Advisor: **Prof. Xiaole Wu**
  * **Visiting PhD Student**, Olin Business School, Washington University in St. Louis, *Jan – Jul 2026* (host: **Prof. Panos Kouvelis**)
* **B.S. in Management Science**, *2017 – 2021*
  * School of Government, Beijing Normal University, Beijing
  * Visiting Student, UC Berkeley Summer Program, Jul – Aug 2019

Research Interests
======
* Operations Management
* Supply Chain Risk Management
* Financial/Operational Hedging in Operations
* Empirical / Structural Operations Management

Working Papers
======
{% for post in site.publications reversed %}
  {% include archive-single-cv.html %}
{% endfor %}

Conference Presentations & Invited Talks
======

<!-- Grouped by paper for brevity. Per-talk detail pages still live under /_talks/ and /talks/. -->
<!-- When adding a new talk: 1) add the file under /_talks/, 2) add a bullet under the matching paper below. -->

**Integrated Hedging Strategies for Exchange Rate and Commodity Price Risks**

* INFORMS MSOM Annual Conference, Harvard Business School, Boston, MA, Jul 2026 *(Accepted)*
* POMS Annual Conference, Reno, NV, May 2026 *(Invited)*
* ISCOM (International Symposium on Contemporary Operations Management), Dec 2025
* CSAMSE Annual Meeting, Jul 2025
* Supply Chain Finance & Risk Management Workshop, Olin Business School, WUSTL, May 2025
* POMS-HK International Conference, Hong Kong, Jan 2025
* POMS-China Annual Meeting, Dec 2024
* CSAMSE Annual Meeting, Jul 2024
* POMS-China Annual Meeting, Dec 2023

**Competition, Overcapacity, and Consolidation in a Multi-Tier Solar Manufacturing Chain**

* Supply Chain Finance Workshop, Singapore Management University, May 2026
* POMS Annual Conference, Reno, NV, May 2026 *(Invited)*
* ISCOM (International Symposium on Contemporary Operations Management), Dec 2025

{% comment %}
Industry Experience: hidden from rendered site (2026-05-03). Remove this Liquid comment wrapper to re-enable.

Industry Experience
======
* **Data Analyst Intern**, Nielsen, *Dec 2020 – Feb 2021*
  * Cleaned, encoded and analyzed survey data from 46 branches of a regional bank and 59 branches of a state-owned commercial bank using R and Excel.
  * Co-authored 10+ client reports on customer satisfaction (banking, insurance).
* **Trading Department Intern**, CITIC Securities Futures, *Aug – Sep 2019*
  * Analyzed natural-rubber industry chain and TSR-20 futures contracts; built option hedging strategies for tire manufacturers.
  * Maintained daily option-hedging risk dashboard; priced options in MATLAB with volatility-adjusted quotes.
{% endcomment %}


Research Projects (Selected)
======
* **Research Assistant**, NSFC Major Project *"Theoretical Foundations of Supply Chain Resilience and Security"*, Fudan University, Jul 2022 – present

{% comment %}
Honors & Awards: hidden from rendered site (2026-05-03). Remove this Liquid comment wrapper to re-enable.

Honors & Awards
======
* First-Class Ph.D. Academic Scholarship, Fudan University
* Outstanding Master's Academic Scholarship, Fudan University
* "Outstanding Student" Award, Fudan University
* First-Class Jingshi Scholarship, Beijing Normal University
{% endcomment %}

Professional Service
======
* Ad-hoc Reviewer, *Naval Research Logistics*

Teaching Experience
======
{% for post in site.teaching reversed %}
  {% include archive-single-cv.html %}
{% endfor %}
