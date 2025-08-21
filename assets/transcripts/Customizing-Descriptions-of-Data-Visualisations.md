---
permalink: /assets/transcripts/Customizing-Descriptions-of-Data-Visualisations.html
title: "Customizing Descriptions of Data Visualisations"
date: 2025-08-21
categories: transcript
audio_length: "19:31"
recorded: "09:08 AM"
participants:
  - Speaker 1 (AI host 1)
  - Speaker 2 (AI host 2)
source_url: /media/podcasts/Customizing-Descriptions-of-Data-Visualisations/
---

**Speaker 1**
Have you ever felt like you're just drowning in information? You know, maybe prepping for a big meeting or trying to get up to speed on a new field.

**Speaker 2**
Or maybe you're just really curious about something, but you need to grasp the important bits fast.

**Speaker 1**
Exactly. It's this universal challenge, right? Information overload. But now imagine facing that same challenge with data visualizations—but you're also blind or have low vision.

**Speaker 2**
That's where the problem really hits home for people who are blind and low vision, or BLV. Current ways of making data visualizations accessible often fall short. They tend to give these static, one-size-fits-all descriptions.

**Speaker 1**
One size fits all never really works, does it?

**Speaker 2**
Not here, no. What works for one person might just be overwhelming for someone else, burying the details they actually need.

**Speaker 1**
Or the opposite, I guess—missing key information.

**Speaker 2**
Precisely. For another person, the important stuff might be completely left out. It's kind of like being handed a pre-written script for every single conversation, no matter who you're talking to or what you want to get out of it.

**Speaker 1**
That's a really powerful analogy. So it sounds like the real breakthrough—the key, like the research title says—is about letting people customize their experience.

**Speaker 2**
Exactly. Customization.

**Speaker 1**
Because that's what this deep dive is all about. We're looking at some fascinating new research. It's titled *Customization is Key: Reconfigurable Content Tokens for Accessible Data Visualizations.*

**Speaker 2**
And it introduces this pretty groundbreaking new model and even a toolkit.

**Speaker 1**
Right. So today our mission is basically to unpack four crucial design goals for how BLV individuals should be able to customize these visualizations.

**Speaker 2**
Yeah, and then we'll dive into the conceptual model behind it—this idea of content tokens—and see how it actually works in a real tool called Ollie.

**Speaker 1**
That's the plan. And finally, we'll look at what a study with 13 BLV participants found—the real-world impact and what might come next.

**Speaker 2**
Okay, let's start with the basics then. Why is digital accessibility just so crucial, especially when we're talking about data?

**Speaker 1**
Well, it's fundamental.

**Speaker 2**
And why can't we just, you know, build one perfect accessible version and be done with it?

**Speaker 1**
Yeah, that's the core issue, really. When we talk about BLV individuals, it's so important to remember this is an incredibly diverse group. People have wildly different needs, different levels of experience with things like screen readers, different preferences.

**Speaker 2**
So no one size fits all?

**Speaker 1**
Definitely not. The research really confirms that. I mean, there are best practices, sure, but these fixed methods like static text descriptions can actually create more problems.

**Speaker 2**
So like what kind of problems?

**Speaker 1**
Well, for example, some users find they get way too much detail. They have to listen through all this extra information just to find the bit they need. It buries the signal in the noise, basically.

**Speaker 2**
Okay, I can see how that would be frustrating.

**Speaker 1**
Very. But then others find that important information they do need is just missing from those same descriptions. And even the general screen reader settings, like choosing if it reads punctuation, just don't have the flexibility you need for something specific like data visualization.

**Speaker 2**
Right, because how you want stock price read out might change depending on what you're doing.

**Speaker 1**
Exactly. Or even if you want it read out. It depends entirely on you—the user—and your specific task, not just some universal setting.

**Speaker 2**
So it sounds like the real issue isn't just giving people information, but making sure that information is actually useful and doesn't become a barrier itself.

**Speaker 1**
That's it. Precisely.

**Speaker 2**
So how did the researchers figure out what those friction points were? What specific design principles did they find were essential for giving users control?

**Speaker 1**
Well, those challenges directly led to the four key design goals for customization. These came out of a co-design process that included a blind co-author plus a lot of analysis of user needs.

**Speaker 2**
Co-design, that's great.

**Speaker 1**
Yeah. And these goals are specifically aimed at the realities of using screen readers. Listening takes more time, it's harder to skim, and it puts more load on your short-term memory.

**Speaker 2**
Makes sense. So what are these four goals?

**Speaker 1**
Okay. First is DG1: Presence. This is basically choosing which pieces of information get included in the narration.

**Speaker 2**
Right, like what actually gets spoken.

**Speaker 1**
Exactly. Because different tasks need different info. Maybe you just want the overall trend. Or perhaps you need specific stats like the average.

**Speaker 2**
Or just the raw data points.

**Speaker 1**
Right. If you include everything all the time without choice, it can just be overwhelming for some people—very inefficient.

**Speaker 2**
Okay, presence, got it. What's next?

**Speaker 1**
Then there's DG2: Verbosity. This is about controlling the length—the conciseness—of the content.

**Speaker 2**
So how much detail you get for each piece.

**Speaker 1**
Yeah, like generally lower verbosity, less wordiness is faster and less tiring. Think “X5” versus “the value for the X field is 5.” Much quicker. But sometimes you need that higher verbosity, especially if you're less familiar with the chart or the conventions.

**Speaker 2**
Ah, so it's a trade-off.

**Speaker 1**
It is. And because screen readers read linearly, you can't easily skip the bits you don't need, like you might visually. So controlling verbosity is key.

**Speaker 2**
Okay. Presence, verbosity. What's number three?

**Speaker 1**
Number three is DG3: Ordering. This lets you control the sequence, the order in which information is presented.

**Speaker 2**
Why does order matter so much?

**Speaker 1**
Again, it comes back to that linear reading. If the most important information is buried at the end of a long description, you have to wait for it. It slows you down and honestly increases the chance you'll miss details because you're waiting for the relevant part.

**Speaker 2**
Like reading a report where the main point is always in the last paragraph.

**Speaker 1**
Exactly. You need to be able to put what's important to you for your task right at the front.

**Speaker 2**
Makes total sense. And the last one?

**Speaker 1**
Finally, DG4: Duration. This is about how long a customization setting stays active.

**Speaker 2**
Ah, so temporary versus permanent changes.

**Speaker 1**
Pretty much. Your preferences aren't static. They change over time, with different tasks. So a customization you make for one quick task should be easy to undo when you move on.

**Speaker 2**
But other preferences might be long term.

**Speaker 1**
Right. Maybe an expert user always wants to hide certain structural info they already know—that should stick around until they deliberately change it.

**Speaker 2**
So these four goals—presence, verbosity, ordering, duration—are really about putting the user in control of their information stream?

**Speaker 1**
Fundamentally, yes. Much like customizing your news feed or app settings to get exactly what you need quickly.

**Speaker 2**
That's a really clear picture of the problem space. We've got the *why*—the need for user control. So what about the *how*? What's the underlying concept that makes this kind of detailed customization possible?

**Speaker 1**
This is where it gets really interesting. The researchers came up with a model based on breaking down the accessible content into individual content tokens.

**Speaker 2**
Content tokens, like little building blocks of information.

**Speaker 1**
Exactly. Think of them as individual LEGO bricks of information. Each token is a specific piece—a number, a label, maybe a summary, a description of part of the chart.

**Speaker 2**
And just like LEGOs have different shapes and colors, each token has properties. You can adjust these, define what it means and how it gets spoken.

**Speaker 1**
So a customization is just arranging these blocks?

**Speaker 2**
Pretty much. A customization is simply a specific sequence of these tokens. Controlling which tokens are there and their order addresses DG1: Presence and DG3: Ordering. And tokens have specific properties too.

**Speaker 1**
They do. Each token has parameters. First is *affordance.* This is about the type of task the token helps with. There are two main kinds: wayfinding tokens, which help you figure out where you are or where you can go...

**Speaker 2**
Like signposts?

**Speaker 1**
Exactly. There are location tokens answering *where am I?*—like values from 2004 to 2006. And surroundings tokens answering *where can I go?*—like “view 1 of 5 charts” or “24 values.”

**Speaker 2**
Okay. Wayfinding. And the other type?

**Speaker 1**
The other is consuming tokens. These directly give you the actual data you're looking for. So that's where you'd hear things like “price \$400” or “average temperature is 82 degrees Fahrenheit.”

**Speaker 2**
So you use wayfinding to navigate, then consuming to get the data itself.

**Speaker 1**
That's the general idea, yeah.

**Speaker 2**
Makes sense. What other parameters do tokens have?

**Speaker 1**
Next is *direction.* This relates to the hierarchy in the visualization. Imagine drilling down into data like layers.

**Speaker 2**
Yeah. Like going from yearly sales down to monthly, then to individual products.

**Speaker 1**
Exactly. So this parameter affects the filters being applied. Downwards info is about filters you can apply to go deeper—data below where you are now. Upwards info gives context about filters applied earlier in the hierarchy—tells you how you got to this point. And in-place info is just about the current selection of data right where you are.

**Speaker 2**
So you can prioritize based on context.

**Speaker 1**
Exactly. And the last parameter is *brevity.* This is applied at the token level, allowing fine-grained control over verbosity.

**Speaker 2**
So individual LEGO bricks can be short or long.

**Speaker 1**
Precisely. An expert might want short wayfinding cues but long detailed stats. A beginner might want the opposite.

**Speaker 2**
That’s incredibly elegant. Breaking it down into customizable LEGO bricks.

**Speaker 1**
Yeah.

**Speaker 2**
So how did they actually build this into a tool people could use?

**Speaker 1**
They implemented it in *Ollie*, an open-source toolkit for accessible visualizations. Ollie is designed to create navigable, hierarchically structured text descriptions so you can explore the data almost like moving through nested folders.

**Speaker 2**
Okay, so Ollie existed before.

**Speaker 1**
Yes, but it generated static text. With this new model, those descriptions became flexible token-generated text. And to give users control, Ollie now offers two main ways to customize: a settings menu for persistent changes, and a command box for on-the-fly adjustments.

**Speaker 2**
Okay, tell me about the settings menu first.

**Speaker 1**
The settings menu is for persistent tweaks to presence, brevity, and ordering—DG1, 2, and 3. It’s designed to feel familiar to screen reader users, like their own settings menu. It offers three verbosity presets—high, medium, low—for each hierarchy level: facet, axis, section, and data point. Crucially, you can also create and save your own custom presets.

**Speaker 2**
Okay, and the quick changes?

**Speaker 1**
That’s the command box. It’s for ephemeral, task-based adjustments. Three main functions:

* **Speak token commands**: quick readouts.
* **Focus token commands**: temporarily re-order content.
* **Shortcut settings**: apply saved presets quickly.

They use dropdowns—easy for novices, efficient for experts with autocomplete.

**Speaker 2**
That’s really thoughtful design. But how did people respond in the study?

**Speaker 1**
The study with 13 BLV participants found:

* **Presence** was crucial—users wanted to include/exclude tokens flexibly.
* **Verbosity**: most preferred as little speech as possible, but valued detail when needed.
* **Ordering**: vital, since linear reading meant buried details were otherwise missed.
* **Duration**: both persistent and temporary options were valued.

Overall, customization improved efficiency, clarity, and—most importantly—user autonomy.

**Speaker 2**
So the research really validated those four design goals.

**Speaker 1**
Yes. And it also pointed to future work, like a third type of token affordance: *interpreting*, which would provide deeper contextual insights. Large language models might make this possible.

**Speaker 2**
That could be game-changing.

**Speaker 1**
Absolutely. And customization could extend beyond text—to sonification and tactile graphics too. Participants highlighted the value of tailoring multisensory experiences.

**Speaker 2**
This deep dive really shows the profound power of customizable accessibility.

**Speaker 1**
Exactly. It's not just about providing information for people who are blind or low vision—it’s about providing the *right* information, in the *right* way, at the *right* time.

**Speaker 2**
So here’s something to think about: imagine if this level of tailored, on-demand customization wasn’t just for data charts, but extended to *all* the digital information you deal with every day.

**Speaker 1**
Your news feeds, work documents, learning platforms...

**Speaker 2**
What new insights, what efficiencies, what new abilities might that unlock for you?
