---
permalink: /assets/transcripts/textual-descriptions-for-upset-plots.html
title: "Textual descriptions for upset plots"
date: 2025-08-21
categories: transcript
audio_length: "13:07"
recorded: "10:30 AM"
participants:
  - Speaker 1 (AI host 1)
  - Speaker 2 (AI host 2)
source_url: /media/podcasts/textual-descriptions-for-upset-plots/
---

**Speaker 1**
Data visualizations are everywhere, aren't they? I mean, news reports, government sites, work stuff, scientific papers. Just how we seem to grasp complex info quickly. Now, understanding them feels, well, pretty crucial. But here's the thing, the fundamental challenge. What if you actually can't see them?

**Speaker 2**
Yeah, that really gets to the heart of it. For millions of people with visual impairments, most data visualizations are frankly inaccessible. Text descriptions are supposed to be the workaround, the main one anyway, but you'd be shocked how often they're just missing, especially with really complex scientific visuals. And it's not just, you know, an inconvenience. It genuinely creates this significant gap, this information access inequality.

**Speaker 1**
That's a really powerful way to put it, information access inequality. And that's exactly what we're diving into today. We're looking at some really groundbreaking research tackling this exact problem specifically for one notoriously tricky scientific visualization called an upset plot.

**Speaker 2**
Right. So our mission really is to explore how these researchers are going beyond just adding basic text. They're essentially teaching computers to truly understand the visual data, the complex stuff, to make knowledge accessible for everyone. We'll unpack the patterns they found, which were kind of surprising, how their system actually works. And you know, what it all means for accessing information in the future.

**Speaker 1**
Okay, so let's talk scale. How big is this accessibility problem really? You mentioned text descriptions help, and studies show they help everyone sighted or not. But they're often missing in scientific journals.

**Speaker 2**
Massively missing. Yeah, it's a strange disconnect. Studies consistently confirm rich descriptions significantly boost understanding for both sighted and visually impaired users. Yet especially in science publishing, they're frequently just not there.

**Speaker 1**
So why, why the gap, especially when the benefits seem so clear?

**Speaker 2**
Well, it's complicated. Part of it, especially with these really intricate scientific charts we're talking about, is that the traditional automatic methods for creating text descriptions, they're mostly built for simpler things, bar charts, line graphs. You know, the patterns in more complex visuals like these upset plots, just weren't well understood. It's like trying to describe a complex piece of art without knowing what elements are actually important.

**Speaker 1**
Right. You don't even have the vocabulary. And this is where it gets really critical, doesn't it? The lack of good alt text, these descriptions, it's not just an academic thing, it's a real barrier for people with visual impairments who want science careers.

**Speaker 2**
Absolutely. Think about it. Scientific figures often hold the key results, the core data. If you rely on non visual means and that information isn't properly described, well, you're locked out, it creates that information access inequality, right, where discovery happens.

**Speaker 1**
And standard figure captions don't cut it either, do they?

**Speaker 2**
No, not at all. Typically, they just say what the figure is, maybe the method used. They rarely summarize the actual content or the key insights within the data itself. That's the crucial missing piece for someone who can't see the visual trends.

**Speaker 1**
Okay, so let's get specific. This brings us to the upset plot. You said it's complex. And the research even notes they're arguably unfamiliar to novices, mostly used in science, especially biomedicine.

**Speaker 2**
That's right. But for researchers dealing with complex set intersections, they're incredibly useful. Widely adopted, actually. Think of it like a Venn diagram, but on steroids.

**Speaker 1**
Okay.

**Speaker 2**
Venn diagrams are great for maybe two or three overlapping circles, right? Upset plots, they're designed to handle many more sets. They do it by plotting the intersections, the overlaps, as a matrix.

**Speaker 1**
A matrix. Okay, so for someone who can't see it, paint a picture. What's the structure like?

**Speaker 2**
All right, imagine a grid. The columns, they represent your individual sets, your categories of data. And usually above those columns, there's some kind of visual, like a bar chart showing the total size of each set.

**Speaker 1**
Got it. Sets or columns, then the rows.

**Speaker 2**
Each row represents a specific combination of those sets, an intersection. And within that row, you'll have markers, maybe filled in dots or cells, showing which sets are part of that particular overlap.

**Speaker 1**
Okay, so rows show the overlaps.

**Speaker 2**
Exactly. And then usually off to the right side, there's another set of visuals, often bar charts again, showing the sizes of each of those intersections. How many items fall into that specific combination. And what's powerful is you can sort these rows, often by the size of the intersection, to quickly see the biggest overlaps, the most significant trends.

**Speaker 1**
That does sound intricate. So why was this plot type so hard for automated description?

**Speaker 2**
Well, simply because before this research we're discussing, nobody had really systematically studied what kinds of patterns people even look for in an upset plot. What insights are considered meaningful? Without knowing that, how can you teach a computer to describe it effectively? They had to figure out the meaning first.

**Speaker 1**
Right? You need to know what constitutes an insight before you can generate one. Can you give us a concrete example, something relatable?

**Speaker 2**
Yeah, the movie genre example they use is perfect. Think of genres, drama, comedy, action, as your sets. A movie can belong to one genre, or it might be a comedy drama or maybe an action thriller. Movies spanning multiple genres, they land in the set intersections. And the example from their paper, from their figure one, was looking at movie data and finding the biggest intersection is between comedy and drama, with 210 movies.

**Speaker 1**
Hmm.

**Speaker 2**
That's the kind of specific takeaway someone needs, visually impaired or not.

**Speaker 1**
Gotcha. Okay, so how did the researchers even start? They couldn't just build the description tool right away. They have this foundational step, right. Figuring out what patterns actually exist that people find interesting in these plots.

**Speaker 2**
Exactly. They couldn't guess. It was some serious detective work. They gathered what they called a convenience sample, basically readily available plots. They ended up surveying 79 upset plots pulled from 40 different published papers. And that was from a pool of over 4,000 papers that even mentioned upset plots.

**Speaker 1**
Wow. Okay.

**Speaker 2**
And they kept adding plots until they hit what's called saturation of code. Yeah, it basically means they reached a point where looking at more plots wasn't revealing any fundamentally new kinds of patterns or insights. They'd seen the main types. Then two of the authors worked together, systematically coding each plot, looking for things like, you know, the biggest intersections, the smallest ones, how much the set sizes varied, whether all the sets overlapped anywhere.

**Speaker 1**
Meticulous work.

**Speaker 2**
Very. And they did a couple of rounds of review to make sure they agreed on the coding, reached a consensus.

**Speaker 1**
So all that coding wasn't just number crunching. It let them build a framework, right. These four big categories to classify the patterns they kept seeing.

**Speaker 2**
Precisely. These categories became the foundation for understanding and describing the plots. The first was intersection patterns. This helps you grasp the basic nature of the overlaps. Are most items in just one set, or are there lots of connections involving many sets?

**Speaker 1**
Okay, so the type of overlap.

**Speaker 2**
Right. Like with movie genres, you'd probably expect lots of low order intersections, maybe two or three genres overlapping. You wouldn't expect many movies to be drama, comedy, action, sci fi, thriller, all at once.

**Speaker 1**
Makes sense. What was the second category?

**Speaker 2**
Intersection size patterns. So once you know the type of overlap, you look at the size. Are those high order intersections actually big or small? What about the common, low order ones? Are they large or small? They classified these sizes small, medium, large, largest, which tells you the significance of those patterns.

**Speaker 1**
Right. Is the complex overlap actually common or rare?

**Speaker 2**
Exactly. Then third was specific attributes. This honed in on unique intersections. Like, is there an intersection where all the sets overlap, or is the empty intersection where items belong in none of the displayed sets present? And importantly, if these exist, are they large intersections or small ones? It gives context.

**Speaker 1**
Okay, and the last one, set sizes.

**Speaker 2**
Just looking at the overall size of the individual sets themselves, are they roughly equal? Or does one set dominate the data set? Do they diverge a lot or just a bit? Because that context matters, like their example: there are many more drama than adventure movies. That imbalance shapes how you interpret the intersection patterns.

**Speaker 1**
So these categories really create a structured way to analyze the plot. It's not just random observations.

**Speaker 2**
Absolutely. If you're looking at shared genes between species, a common use case, you might expect high order overlaps, lots of shared genes. But for movie genres, you expect lower order overlaps. The categories help confirm or contradict those expectations based on the data.

**Speaker 1**
Okay, so now they have this deep understanding of the patterns. How did they build the actual system to automate generating descriptions? You mentioned a Python package.

**Speaker 2**
Yep. A custom Python package is the core engine, and the really smart part is how it takes input. I read something called a JSON grammar.

**Speaker 1**
JSON grammar. What's the advantage of that?

**Speaker 2**
Think of it like a universal adapter. JSON is a standard data format, and by defining a grammar for upset plots in JSON, their Python tool can understand plot data coming from any software that can output that format. It means their system isn't locked into one specific way of creating upset plots. It's platform independent, much more flexible and widely usable.

**Speaker 1**
Ah, clever. So it's versatile. And how does the process work once it gets that JSON data?

**Speaker 2**
So the plot specification in that JSON format gets passed to their Python package. The package parses it, understands the structure, then runs statistical analysis based on those four pattern categories we just talked about. And based on that analysis, it identifies and generates a list of the most salient trends, the key takeaways from that specific plot.

**Speaker 1**
And they didn't just build this in isolation, right? You mentioned collaboration.

**Speaker 2**
Critically important, yes. They had an iterative feedback process, working very closely with a blind collaborator and co author. This wasn't an afterthought, it was fundamental to ensure the descriptions were genuinely useful and conveyed the right information.

**Speaker 1**
How did that feedback loop actually work?

**Speaker 2**
It was back and forth. They generated descriptions, the collaborator would review them from a non visual perspective, provide feedback on clarity and completeness—what was most helpful. And through that iteration, they developed descriptions at two main levels of detail, a shorter summary and a really comprehensive one, making sure the text truly offered similar insights to actually seeing the chart. Human centered design, really.

**Speaker 1**
That makes a huge difference. So what are the actual outputs? What kinds of text does it generate?

**Speaker 2**
The system, which they made available as a web API backed by that Python package, generates three types of descriptions. First, there's a very brief technical description, just a quick intro sentence basically.

**Speaker 1**
Okay.

**Speaker 2**
Second, a short description. This is like two or three sentences hitting the single most important trend, designed for things like the alt text property you see on web images. A quick summary.

**Speaker 1**
Right, the quick hit. And then the main one, the long description.

**Speaker 2**
Exactly. That's the really comprehensive one. It's designed to communicate pretty much the same amount of information as looking at the chart itself. It's structured, featured, with sections: an introduction, details on the data, the set properties, the intersection properties.

**Speaker 1**
So it breaks it all down.

**Speaker 2**
Yeah. And crucially, it includes statistical information—things like percentile data, the percentage breakdown of largest, smallest sets, average divergence. It gives you the statistical backup, the context. And then the trend analysis section really synthesizes those findings into the key insights, the "so what" of the plot.

**Speaker 1**
So if we go back to the movie example one last time, the long description would not only state the basic facts about the genres and overlaps, but it would also highlight those higher level trends, like confirming comedy and drama being the biggest intersection and maybe providing statistical context for how much bigger it is.

**Speaker 2**
Precisely. It translates that whole visual story—structure, trends, statistics—into accessible, meaningful text.

**Speaker 1**
Amazing. So thinking back, we started with this really significant challenge: complex data visuals being out of reach for so many. And what these researchers did was, well, pretty elegant. They didn't just slap on labels. They first did the hard work of understanding the patterns people actually see and find meaningful in these complex upset plots. And then they built a system to automatically find and articulate those patterns in text.

**Speaker 2**
It really is a breakthrough because this deep dive, it wasn't just about one cool piece of tech. It was about demonstrating something more fundamental: that the way humans analyze visual data, the patterns we look for, can be codified, can be taught to a machine. And doing that unlocks this incredibly complex scientific information for potentially millions of people who rely on non visual ways to learn and work. It's about leveling the playing field.

**Speaker 1**
Absolutely. It really makes you think. So here's something to mull over. If we can now automatically generate these rich, genuinely insightful descriptions for something as complex as an upset plot, what else is out there? What other forms of scientific data or even everyday information that have always been primarily visual and therefore inaccessible—what could be next? How might this kind of approach fundamentally change how we all learn, how we share knowledge, how we consume information in the future?

**Speaker 2**
It's a powerful question. It definitely underscores how vital accessibility is right from the start and the sheer ingenuity needed sometimes to make complex information truly universal.