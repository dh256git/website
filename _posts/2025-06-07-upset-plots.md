---
title: "Making Complex Charts Accessible: Text Descriptions for UpSet Plots"
author: Daniel Hajas
AI_assistance: AI-generated
hero: 
hero_alt: 
hero_caption: 
tags: [representational-productivity-tools]
related_publications: [upset-descriptions-eurovis-2025]
related_external_posts:
  - title: "Making Data Visualizations Talk: Accessible Text Descriptions for UpSet Plots | Visualisation Design Lab (University of Utah)"
    url: https://vdl.sci.utah.edu/blog/2025/06/07/upset-text-descriptions/
---

Not all charts are created equal when it comes to accessibility. Some, like line or bar charts, lend themselves to concise descriptions. Others, like **UpSet plots**—used widely in science to show how sets overlap—are much harder to explain. UpSet has become a staple in fields like genomics, but for blind and low-vision readers, the lack of accessible descriptions is a major barrier.

<!--more-->

In our latest work, we tackled this challenge by studying nearly 80 published UpSet plots to understand the **patterns that matter most**—such as which intersections are largest, how set sizes diverge, and whether certain intersections (like all sets or none) stand out. From this, we developed a grammar and software pipeline that automatically generates structured descriptions of UpSet plots.

The system produces text at multiple levels: a short snippet for alt text, a technical overview, and a long description with trends and statistics. It integrates into both web-based and Python implementations of UpSet, making it available to scientists directly in their workflows.

Our takeaway: even the most complex visualisations can be made accessible with carefully designed automated descriptions. This isn’t just about equity—it’s about ensuring that blind and low-vision researchers can engage fully with the scientific literature.