---
title: "Customisable Textual Descriptions for Screen Reader Accessible Visualisations"
author: Daniel Hajas
AI_assistance: AI-generated
hero: 
hero_alt: 
hero_caption: 
tags: [representational-productivity-tools]
related_publications: [customization-is-key-chi-2024, rich-sr-experiences-cgf-2022]
related_external_posts:
  - title: "Four Characteristics of Textual Affordances for Accessible Data Visualization | Montreal AI Ethics Institute"
    url: https://montrealethics.ai/customization-is-key-four-characteristics-of-textual-affordances-for-accessible-data-visualization/
---

In our EuroVis 2022 paper, we mapped the design space of screen reader accessible data visualisations, showing how structure, navigation, and description can extend accessibility beyond alt text and data tables. This new study, carried out in collaboration with the MIT Visualisation Group, who also maintain the Olli open source library, takes the next step—making textual descriptions themselves *customisable*.

<!--more-->

Olli already converts visualisations into keyboard-navigable trees, enabling users to move from overviews down to details. But screen reader users face a linear reading order, which can be frustrating when descriptions are too long, too short, or poorly sequenced. To address this, we built a framework that treats descriptions as modular **tokens**—pieces of text that can be reconfigured across four characteristics:

* **Presence** — choosing which tokens are included.
* **Verbosity** — adjusting the level of detail.
* **Order** — changing the sequence in which tokens are read.
* **Duration** — deciding whether a change is temporary or persistent.

In a study with 13 blind and low-vision participants, users welcomed the ability to configure how data “spoke” to them, while emphasising the importance of sensible defaults and learnable features.

Our takeaway: there is no one-size-fits-all solution for accessible visualisation. What matters is giving users **agency to customise**—so data becomes not just accessible, but efficient, flexible, and enjoyable to explore. In future work, we want to explore how large language models can be used to **tailor** or **scaffold** textual descriptions to the preferences of the reader, or to the reading pathways they take during screen reader interaction with a chart, depending on the task they are trying to complete.