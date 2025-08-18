---
title: Rich Screen Reader Experiences for Accessible Data Visualization
author: Jonathan Zong
date: 2022-06-14
youtube_id: oc4GQNM7tUw
youtube_title: "EuroVis 2022 Talk: Rich Screen Reader Experiences for Accessible Data Visualization"
tags: [representational-productivity-tools]
related_publications: [rich-sr-experiences-cgf-2022]
summary: This pre-recorded conference talk introduces the design space relevant to rich screen reader experiences, during the interaction with data visualisations embedded in web content.
---

Hi, my name is Jonathan Zong and I’m excited to present our work on rich screen reader experiences for accessible data visualization. This work is the result of a collaboration between myself, Crystal Lee, Alan Lundgard, JiWoong Jang, Daniel Hajas, and Arvind Satyanarayan. I’m grateful to be working with such an amazing team.

In the United States, where I live, there are about seven million people with a visual disability according to the National Federation of the Blind. For them and many more people globally, much of the web simply does not work. WebAIM conducted a study showing that 96.8 percent of the top million pages on the internet fail to conform to basic standards for making content accessible to screen readers. If you’re not familiar with how screen readers work, there’s essentially a cursor that users move around the page with keyboard shortcuts. Whatever is selected by the cursor is read aloud as text-to-speech.

I can demonstrate what the accessible HTML version of our paper looks like to a screen reader. It reads: “visit link. heading level one. Hi, we’re the visualization group. visit link. home. link. link. heading level one. rich screen reader experiences for accessible data visualization. best paper honorable mention. article. abstract. current accessibility guidelines ask visualization designers to support screen readers via basic non-visual alternatives like textual descriptions…” For many people who primarily browse the web using screen readers, the average experience is more like what’s shown in a video by Sarah Fossheim of reading a map: “image. image. image.” This highlights the scale of the problem.

So the question we focused on is: how do we make charts more accessible to screen reader users? Current best practices recommend that charts include both alt text and a link to the underlying data table. For example, the alt text for a U.S. election results map might say: “Map of 2020 U.S. presidential election results. Joe Biden has 227 electoral votes. Donald Trump has 213. 98 votes remain.” Alt text is better than nothing, but it falls short. It’s static and non-interactive. It doesn’t allow control over granularity — we might know Biden has 227 votes, but which states contributed? And it limits agency; users can’t pose new questions with only the information provided.

Tables help somewhat. They provide agency to browse rows and columns and ask questions. But they are tedious and time-consuming, requiring significant cognitive load. Tables also miss what visualizations provide: guiding narratives and interpretations. Despite these shortcomings, alt text and tables are still the current best practices.

Could we do better with custom screen reader interfaces? A state-of-the-art example is Highcharts’ accessible line chart demo, but it still essentially reads out individual data points, similar to a table. Our main contribution is a set of design dimensions for richer screen reader experiences. To contrast with current best practices, I’ll first show an example interface before explaining our framework.

In our demo scatterplot of penguin data, the system represents the visualization as a keyboard-navigable data structure containing text descriptions at varying levels of detail. At the top level, a user hears: “Scatterplot showing body mass and flipper lengths of penguins.” By pressing the down arrow, they can access encodings such as axes and legends: “x axis flipper length from 170 to 240, y axis body mass from 2500 to 6500, legend with species adelie, chinstrap, gentoo.” Descending further into the x-axis, they can hear descriptions of intervals: “220–230, 35 values,” and so on. They can press left and right to get a sense of distribution. Descending again, they can access individual data points: “Flipper length 190 mm, body mass 3650 g, species adelie.” Alternatively, they can move spatially across the scatterplot grid using WASD keys, as if feeling a tactile graphic. Or they can jump directly to a location using a dropdown navigation menu.

There are a few key differences here. First, our interface uses a hierarchical structure: users can dive deeper into entries if they want, but don’t have to. Second, there are multiple ways to navigate — along the structure, spatially, or by jumping directly to a target. Third, descriptions have varied granularity, from high-level overviews to detailed data values.

Building on these ideas, we developed our design dimensions through a six-month iterative co-design process with our blind co-author, Daniel Hajas. We engaged deeply with disability studies literature and prioritized Daniel’s expertise as a blind HCI researcher. We created 15 prototypes exploring different design points, and from these refined a framework with three dimensions: **structure, navigation, and description**.

**Structure** refers to the underlying representation of a visualization. Two considerations are form and entities. Form could be linear, as in current Vega charts, where every data point is read out sequentially. Or it could be hierarchical, as in our prototype, allowing selective deep dives. Entities are what the nodes represent — data intervals, encodings like axes and legends, or author-defined annotations.

**Navigation** refers to how users move around. Structural navigation moves up and down hierarchies. Spatial navigation lets users move across x/y grids, drawing on tactile metaphors and shared language with sighted users. Targeted navigation allows users to jump directly to known locations via menus.

**Description** is about the narration itself. Key considerations are semantic content (from low-level encodings to higher-level patterns), composition (ordering of information, putting important details first), and verbosity (balancing between detailed and concise descriptions depending on user preference).

We evaluated our approach with 13 blind and low-vision participants through interviews and prototype demonstrations. One participant liked the ability to scroll at a higher level and then drill down, similar to how sighted people selectively attend to visualizations. Another said it gave them different ways of thinking, affording spatial mental models. But a third raised concerns about learnability, preferring to fall back on tables until they became more familiar. This reminds us that accessibility improvements must be designed with learning and adoption in mind.

Looking forward, most accessible visualizations today are ad hoc, time-consuming to build, and lack shared UX conventions. Toolkits like Highcharts and Vega providing accessibility by default are crucial. Our collaborator Matt Blanco has been developing tools to automatically generate accessible structures from existing Vega-Lite specs with just a few lines of code.

Finally, our design dimensions open prompts for future work: composing across modalities (e.g., applying structure and navigation not only to text but also sonification and tactile graphics); designing accessible interaction techniques beyond static navigation (such as view respecification and custom queries); and supporting authoring, so that screen reader users can produce as well as consume visualizations. These directions raise exciting possibilities for richer, more inclusive data interaction.

Thank you for your attention. You can find the accessible HTML version of our paper on our website, vis.mit.edu.
