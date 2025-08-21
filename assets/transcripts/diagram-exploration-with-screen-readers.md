---
permalink: /assets/transcripts/diagram-exploration-with-screen-readers.html
title: "Diagram exploration with screen readers"
date: 2025-08-21
categories: transcript
audio_length: "20:41"
recorded: "10:30 AM"
participants:
  - Speaker 1 (AI host 1)
  - Speaker 2 (AI host 2)
source_url: /media/podcasts/diagram-exploration-with-screen-readers/
---

**Speaker 1**
Welcome to the Deep Dive. Your shortcut to being genuinely well-informed on the innovations shaping our world. Just stop for a moment and think about how many charts, diagrams, infographics—

**Speaker 2**
Yeah.

**Speaker 1**
How much of this visual stuff you see every single day?

**Speaker 2**
It's absolutely everywhere, right?

**Speaker 1**
News articles, work presentations, even, you know, putting together furniture. They're just baked into how we get information. But here's the really interesting question we're diving into today: what if you can't see them? And I don't just mean getting a basic description like alt text. The real challenge, the thing that technology is only just starting to crack, is understanding the complex relationships these visuals show—the structure.

**Speaker 2**
That's exactly it. Graphics aren't just decoration. They have this inherent visual structure. Think about it: a line connects things. One shape inside another usually means a part–whole thing.

**Speaker 1**
Or even just text being close to something tells you it's a label.

**Speaker 2**
Precisely. These are cues that sighted people process almost instantly. But the problem is most screen readers, while great for text, completely miss conveying this crucial underlying structure for blind and low vision (BLV) users.

**Speaker 1**
So it's like getting the ingredients but not the recipe.

**Speaker 2**
Yeah, that's a great analogy. You know it's there, but not how it all fits together.

**Speaker 1**
And that's where Benthic comes in. It's this really groundbreaking system from MIT CSAIL. Today we're going to unpack how Benthic is trying to make these complex visual structures genuinely accessible—moving beyond just description to real…

**Speaker 2**
Understanding. To deep interpretation.

**Speaker 1**
Yeah. Okay, so let's unpack this a bit more. When we say graphics are more than just shapes, what does that actually mean? How do our brains instinctively make sense of them?

**Speaker 2**
It's actually pretty fascinating. These graphical representations are basically data structures. They use visual cues. Psychologists call them Gestalt principles.

**Speaker 1**
Right—things like grouping stuff that's close together.

**Speaker 2**
Exactly. Proximity, alignment, containment, connectedness. These are just the sort of built-in rules our brains use to organize visual elements and see relationships, often without us even consciously thinking about it.

**Speaker 1**
So sighted users just tap into this automatically. It makes understanding faster, less effortful.

**Speaker 2**
Precisely. It reduces the cognitive load. You can see the big picture and the details simultaneously.

**Speaker 1**
And this is where current accessibility tools struggle.

**Speaker 2**
Yeah, they fall short. Take alt text for example. It's useful for a high-level summary—“bar chart showing sales over time”—

**Speaker 1**
But it doesn’t give you the structure.

**Speaker 2**
Nope. It tells you what’s there, but not how it’s organized, or more importantly, why it’s organized that way. The structural logic is missing.

**Speaker 1**
And there were other attempts before Benthic, right? You mentioned things like Ollie and Data Navigator.

**Speaker 2**
That's right. People have tried structured approaches. Ollie used a tree-based model, kind of like a file directory. Data Navigator was more graph-based, focused on connections.

**Speaker 1**
But they had limitations.

**Speaker 2**
They did. Tree-based systems like Ollie are good for simple hierarchies, but they really stumble when things belong to multiple groups at once.

**Speaker 1**
Like in a complex chart.

**Speaker 2**
Yeah. Imagine a bar in a chart representing, say, Arsenal’s Premier League performance. In a tree, if you group by team and by league, that Arsenal bar might have to appear twice in the structure.

**Speaker 1**
Duplication. That doesn’t sound right.

**Speaker 2**
It isn’t. It breaks what the researchers call perceptual congruence. Basically, the structure the BLV user navigates doesn’t feel like the single coherent visual anymore.

**Speaker 1**
Okay, so trees had issues. What about the graph-based ones like Data Navigator?

**Speaker 2**
Well, they were better at handling those adjacent relationships—like things next to each other—but they often lost the parent–child information, the hierarchy. This meant you couldn’t always reliably navigate back up the structure. It could break the path.

**Speaker 1**
Hmm, inconsistent.

**Speaker 2**
Right. And the real kicker is that so many graphics in the wild—think about a chemical molecule diagram, for instance—use both kinds of relationships extensively.

**Speaker 1**
Like functional groups being hierarchical.

**Speaker 2**
Exactly. And atomic bonds being adjacent connections. Current tools just couldn’t really capture both fluidly in one single coherent way.

**Speaker 1**
So that’s the critical gap. BLV users needed access to that rich multidimensional logic that sighted users get implicitly. Not just a summary, but the ability…

**Speaker 2**
To really interpret. To reason with the visual information.

**Speaker 1**
And that’s where Benthic comes in. This is where it gets really interesting, isn’t it?

**Speaker 2**
It really is. Benthic’s main design goal was to create perceptually congruent screen reader structures. Fancy phrase. But what it means is building an accessible version that truly mirrors the visual experience.

**Speaker 1**
The structure you hear matches the structure you’d see.

**Speaker 2**
Exactly. Creating a mental model for the blind user that aligns with the visual layout.

**Speaker 1**
And the key technology behind this is the hypergraph. Sounds intense.

**Speaker 2**
It does sound a bit sci-fi, maybe, but fundamentally it’s just a really flexible way to represent structure. In a normal tree, every item—every node—has only one parent.

**Speaker 1**
Right.

**Speaker 2**
In a hypergraph, elements can belong to multiple groups at the same time. A single connection, called a hyperedge, links a parent to a whole set of children nodes, not just one.

**Speaker 1**
Ah, okay. So one thing can be part of group A and group B simultaneously in the structure.

**Speaker 2**
Precisely. And this is a huge deal. It means a hypergraph is the generalization. It can naturally represent both hierarchical structures like trees, and adjacent connections like graphs, all within one single coherent system.

**Speaker 1**
No more trade-offs. You get both.

**Speaker 2**
You get both. It’s like having a language that’s fluent in describing all the different ways visuals connect things.

**Speaker 1**
Wow. So what are the big advantages of using this hypergraph structure?

**Speaker 2**
Well, several key benefits. First, no duplication. That bar in the chart we talked about exists once, but it can be accessed via its team group or its competition group. That preserves the perceptual congruence.

**Speaker 1**
Okay, that makes sense. What else?

**Speaker 2**
Second, it enforces something called a structural invariant. The upshot is predictable, logical navigation. Basically, children nodes are considered neighbors only if they share a parent in the current context.

**Speaker 1**
Meaning you can always go back and forth reliably.

**Speaker 2**
Yes, exactly. Like navigating a physical space. You can retrace your steps. It’s consistent. Third, it’s domain-agnostic, meaning it works for different kinds of graphics.

**Speaker 1**
Right.

**Speaker 2**
Because it focuses on those universal visual grouping principles—proximity, containment, connection. It applies equally well to charts, diagrams, notations, even maps. And finally, it enables really fluid traversal. The whole system is designed for rapid shifts between different ways of grouping the data, and you can easily reverse your actions.

**Speaker 1**
So it kind of blurs that line between hierarchy and adjacency, just like the visuals themselves often do.

**Speaker 2**
That’s a perfect way to put it. Whether something is grouped by being inside a box or connected by a line, the hypergraph can handle it naturally.

**Speaker 1**
And it’s important to mention this wasn’t just cooked up in a lab in isolation. It was co-design.

**Speaker 2**
Absolutely. Crucial point. Benthic includes a screen reader interface developed through iterative collaboration with a blind researcher, Daniel Hodges. It’s grounded in actual user needs and feedback from the very beginning.

**Speaker 1**
Okay, theory is great, but let’s make this concrete. Walk us through how someone, say, Marina, might actually use Benthic with a real example, like that stacked bar chart you mentioned.

**Speaker 2**
Okay, perfect. Marina loads up Benthic with this chart. It shows football teams and their trophy wins in different contests. First she hits the home key.

**Speaker 1**
Like a starting point.

**Speaker 2**
Exactly. It gives her the overview: the title, chart type, maybe the axis labels. “Stacked bar chart showing trophies won by…” etc.

**Speaker 1**
Got it. Then what?

**Speaker 2**
Then she wants to dive in. She uses Shift+A—think of it like stepping into the chart. Maybe she lands on the X-axis node first and it tells her: contains four teams, Arsenal, Chelsea…

**Speaker 1**
And she can move around at that level?

**Speaker 2**
Yep. Using the arrow keys, she might move laterally to the legend node. It tells her: contains three contests, BPL, FA Cup, CL. Another move might take her to the Y-axis.

**Speaker 1**
Okay, so far, it’s about exploring the main components.

**Speaker 2**
Right. Now she wants to explore by contest. She navigates back to that legend node and descends into it. She lands on BPL—Premier League.

**Speaker 1**
And she can move between contests now.

**Speaker 2**
Yes. She moves to CL—Champions League. Then she drills down again, landing on a specific bar, maybe Chelsea CL representing Chelsea’s Champions League trophies.

**Speaker 1**
Okay, she’s focused on a specific data point.

**Speaker 2**
Now here comes a really cool part: the context switch. Marina wonders how Chelsea did overall. She goes up one level. Benthic presents her with the parent context layer. It tells her Chelsea CL belongs to two groups: CL (the contest) and Chelsea (the team).

**Speaker 1**
Ah, because that bar is part of both groupings.

**Speaker 2**
Exactly. Marina switches focus to the Chelsea context. Instantly, Benthic reorganizes the navigation around Chelsea. Now she can explore all of Chelsea’s results across contests—Chelsea BPL, Chelsea FA Cup, Chelsea CL.

**Speaker 1**
Wow. So the structure adapted to her question. She switched from grouping by contest to grouping by team.

**Speaker 2**
Just like that. It’s like the chart reshaped itself based on her focus.

**Speaker 1**
Incredibly flexible. Is there only one way to navigate?

**Speaker 2**
Not at all. She could just as easily switch contexts again, compare FA Cup results across teams, or reorganize however she prefers. She’s actively choosing her path.

**Speaker 1**
That ability to fluidly reorient the data, switch between grouping by contest or by team, enables real analysis.

**Speaker 2**
Exactly. It allows for efficient comparison and pattern-spotting—tasks that were incredibly difficult or impossible with older systems.

**Speaker 1**
It’s moving beyond just reading out numbers to actually working with the data structure.

**Speaker 2**
Precisely. It mirrors the cognitive flexibility sighted users employ, shifting attention to analyze different facets of the data.

**Speaker 1**
So developing this is one thing, but proving it worked is another. You mentioned a user study.

**Speaker 2**
Yes. They brought in 15 blind participants. The goal wasn’t just, “did they get the right answer?” It was about how they used Benthic, how they explored, how they reasoned about the diagrams.

**Speaker 1**
What kinds of graphics did they use in the study?

**Speaker 2**
Two main types. First, complex scientific diagrams—pulley systems with many interconnected parts. Second, bar charts with a subtle hidden anomaly, like a child’s height decreasing over time.

**Speaker 1**
Testing both structural understanding and analytical reasoning.

**Speaker 2**
Exactly. And the results were striking. Participants generally found Benthic enjoyable and easy to use. And 12 of 15 blind participants spotted the anomaly—compared to only 54% of sighted participants in the original study.

**Speaker 1**
So blind users with Benthic actually outperformed sighted users at spotting that anomaly?

**Speaker 2**
Yes. It suggests Benthic wasn’t just making the chart accessible—it was supporting a more structured analysis.

**Speaker 1**
That’s remarkable.

**Speaker 2**
The qualitative feedback backed this up too. Participants loved the control, the context switches, the ability to reorganize. They weren’t passive; they were driving the analysis.

**Speaker 1**
Of course, there must have been challenges.

**Speaker 2**
Yes. Some participants felt navigation leaned too hierarchical, making sideways moves harder. Others struggled to build a complete global map of the diagram. And the parent context layer, while powerful, sometimes added cognitive overhead.

**Speaker 1**
So refinement is needed, but the potential is clear.

**Speaker 2**
Absolutely. Future directions include scaling up adoption, automating hypergraph creation, and extending Benthic to continuous-space visuals like maps—or even into sonification and tactile graphics.

**Speaker 1**
So the core insight is shifting from just describing visuals to empowering users to reason with them.

**Speaker 2**
Exactly. Providing access to the underlying logic, bridging the gap for BLV users.

**Speaker 1**
And it raises the big question: if Benthic enables deep exploration and understanding of visuals without sight…

**Speaker 2**
What other kinds of visual data structures could become universally accessible?

**Speaker 1**
What new worlds of information could be unlocked?

**Speaker 2**
Until next time, keep diving deep.
