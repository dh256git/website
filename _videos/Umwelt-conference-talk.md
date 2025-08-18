---
title: "Umwelt: Accessible Structured Editing of Multi-Modal Data Representations"
author: Jonathan Zong
date: 2024-05-09
youtube_id: Bq6ipk2wUJI
youtube_title: "CHI 2024 Talk: Umwelt"
tags: [cross-modal-ux-collaboration]
related_publications: [umwelt-chi-2024]
summary: This pre-recorded conference talk introduces Umwelt, an open source, screen reader accessible, structured editor for multi-modal data representations, enabling collaboration between sighted and blind collaborators, through cross-modal context switching.
---

Hi, this is Jonathan Zong. I'm excited to present our work on Umwelt, a system that enables accessible structured editing of multimodal data representations. I want to start this presentation off with a bit of a provocation. The question I want to ask is: is access enough?

What I mean is that often work in accessible data visualization is about making existing charts more accessible. But that's not always enough for blind and low vision people to equally participate in data analysis. They must not only be able to consume data representations created by others, but also be empowered to create their own custom representations. Why might this matter? When we talked to expert data analysts who are blind professionals, they said things like, “I want to participate meaningfully in a discussion at work and not seem clueless,” or, “Consistently being the only person who can't comment on a topic can affect promotions and work opportunities.” One person said, “Am I going to depend on collaborators to do all the analysis, or am I going to keep trying to find ways to do it myself?”

The goal of our work with Umwelt is to answer how we empower screen reader users to create their own interactive data representations so they can contribute to, or even lead, data-driven discussions. The problem we encountered is that existing authoring tools accessible to screen reader users tend to center visual specification. That is, current tools often require an existing visualization to convert into a non-visual format, or require you to make the visualization first before producing a non-visual output. Examples include Highcharts Sonification Studio and SAS Graphics Accelerator. These are fantastic tools, but they share this limitation.

One consequence of this vision-centrism is that blind and low vision users must specify their intended non-visual designs in visual terms, which adds difficulty to the authoring process. Thinking in terms of the “gulf of execution” from HCI theory, there's a gap between how users conceive of what they want and how they can express it in the interface. Another consequence is that not all non-visual designs can be expressed as analogous visualizations. If you must first create a visualization to generate a sonification, you can only make sonifications that map onto a visualization. This limits expressivity. For example, most Highcharts Sonification Studio examples are line or bar charts. Similarly, SAS Graphics Accelerator documentation warns that while many charts can be described, not all can be explored through sonification because there is no one-to-one mapping across modalities.

Our contribution is an accessible authoring tool that de-centers the visual modality. Concretely, we've designed a web-based editing interface with an editor on the left and a multimodal viewer on the right. The viewer includes visualization, a structured textual description, and sonification. While everyone can use this tool, it was designed from the start with screen reader use in mind.

Let me walk you through an example. When I load the penguins dataset in the editor, it shows all the fields present. By default, the viewer displays a structured textual description of all seven fields. This description doesn’t reference visual concepts — it simply describes groupings by field. Suppose I only want to examine the beak length field. I uncheck the others, and the textual description updates accordingly. Now, if I add a volume encoding to the beak length field, the output includes a sonification mapping values of beak length to volume. Without ever specifying a visualization, we now have both a structured description and a sonification — something not possible in many other tools.

If I then decide to add a visualization, I can encode beak length on the x-axis and map species to color. The result is a point chart, and the textual description now incorporates visual concepts like axes and legends. But crucially, those weren’t required to begin authoring.

This decoupling has major benefits. For example, I can create a sonification with binning and aggregation (like means) that isn’t represented in the visualization. Instead of redundancy, modalities can complement each other, offering different perspectives on the data.

To recap: by de-centering visual specification, Umwelt allows blind and low vision users to create non-visual representations without first expressing them visually. It also expands the expressivity of non-visual designs beyond what visual-first tools permit.

This project involved a year of co-design led by myself and my coauthor, Daniel Hajas, a blind researcher with HCI expertise. Together we iterated through multiple prototypes, using Zoom and email reflections to discuss what worked and what didn’t. Some interesting findings included tradeoffs between field-oriented and modality-oriented editing interfaces, and the value of default specification heuristics — sensible defaults for each modality based on data semantics.

We also created an example gallery of datasets with varied visual, textual, and sonification outputs. Finally, we evaluated the system with five expert blind and low vision users. Participants highlighted how multimodal representations facilitate communication across senses. For instance, when exploring textual structures, their selections were visually highlighted for collaborators, making shared understanding easier. Another insight was how analysts shift between task-based and representation-based thinking during analysis. A participant might begin by asking about species on islands, but later reframe goals in representational terms: “I want a bar chart with island on the x-axis.” Supporting both modes of thought is important.

Looking ahead, two themes stand out. First, mixed-ability collaboration: can Umwelt support multi-user analysis where blind and sighted colleagues work together in real time? Second, modality complementarity: can we further de-center vision by designing tactile-first representations that prioritize conveying data itself, rather than replicating what a chart looks like?

Thank you, and I look forward to further discussions about this work.
