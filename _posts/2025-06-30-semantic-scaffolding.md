---
title: "Helping Blind Readers of charts Make Sense of Data with a Semantic Scaffold of Domain Knowledge"
author: Daniel Hajas
AI_assistance: AI-generated
hero: 
hero_alt: 
hero_caption: 
tags: [representational-productivity-tools]
related_publications: [semantic-scaffolding-preprint-2025]
related_external_posts:
  - title:
    url:
---

When you open a dataset for the first time, the numbers rarely speak for themselves. You might see patterns in a chart but not know what they mean — or you might have an idea in mind (“sports cars”) but struggle to translate it into the dataset’s fields. For blind and low-vision screen reader users, this challenge is even sharper, since interfaces rarely provide the kind of overview that sighted readers get at a glance.

<!--more-->

In our latest research with the MIT Visualisation Group, available as a preprint, we introduce **semantic scaffolding**: a technique that uses large language models (LLMs) to generate domain-specific **groupings of data** that can guide exploration. Rather than producing generic summaries, the LLM creates structured “scaffolds” — for example, a grouping called *Fuel-Efficient Japanese Cars* with an explanation and a clear query predicate.

We developed two interface elements: **semantic bins**, which divide a field into meaningful intervals or categories (like “heritage” vs. “modern” crop varieties), and **data highlights**, which annotate subsets of records with real-world significance (like *low horsepower European cars*). Integrated into Olli, our accessible visualisation tool, these scaffolds helped blind and low-vision participants quickly grasp a dataset’s meaning while still thinking critically about the AI’s influence.

Our takeaway: semantic scaffolding can jump-start comprehension for all readers, but especially screen reader users. By combining domain knowledge with flexible navigation, we can make data exploration more intuitive, equitable, and collaborative across sighted and blind audiences alike.