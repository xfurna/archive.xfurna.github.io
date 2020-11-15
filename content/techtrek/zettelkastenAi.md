+++
categories = ["AI"]
coders = []
date = 2020-11-15T19:44:17+05:30
description = "AI for Luhmann's Zettelkasten"
github = ["https://github.com/evi1haxor/zettelkasten-ai/"]
image = "https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1591793276/logos/logos_hugo_h2xbne.svg"
title = "Zmsai"
type = "post"
draft = true
+++

Productivity is the core value of work. In the modern economy, where at every step one has to face cut-throat competition, it is becoming increasingly important to produce at an elite level. Professional activities demand an affiliation to the task at hand that can push one’s cognitive capability to its limits. In order to thrive in this new economy, one needs to master two core abilities- first, the ability to quickly master hard things and second, the ability to produce at the highest level in terms of both quality and speed. Humans have a natural tendency to alter the *form* of the idea and call it innovation. In contrast, according to first-principles thinking, it is the ideas which are perceived and worked upon for optimising the *function* that renders top-class results. Such a mindset helps in connecting the ideas from various domains and come up with the solution to the problem at hand relatively efficiently. 
Luhmann’s Zettelkasten is one technique which enables the user to organise their ideas and uncover the emergent connections between them in order to think creatively. Zettelkasten is essentially a note-taking technique, but unlike its alternatives, instead of simply jotting down the ideas on paper or cloud and burying them under some thousands of such notes, all the written pieces are kept dynamic. That means maintaining a knowledge bank where every new idea is linked with old ideas to form connections. The technique elegantly rectifies the chances of [collection fallacy](https://zettelkasten.de/posts/collectors-fallacy/) and genuinely generates value from the notes.
Zettelkasten was invented by a German scholar [Niklas Luhmann](https://en.wikipedia.org/wiki/Niklas_Luhmann). In his almost 40 years of a research career, he published [more than 400 scholarly articles and 70 books](https://www.researchgate.net/publication/278131440_Niklas_Luhmann_as_organization_theorist) on diverse topics ranging from biology and sociology to computer science. When asked how had been this prolific in his entire career, he replied *“I am not thinking everything on my own. Much of it happens in my Zettelkasten. My productivity is largely explained by the Zettelkasten method.”*
As Luhmann describes it, Zettelkasten was originally a piece of furniture consisting of several stacks of drawers. Each drawer was supposed to have paper notes filled to the brim.

![Zettelkasten]()

Each new addition is meant to go in a specific drawer based on its ​topic​. Additionally,each card was supposed to be connected with all the cards that can possibly be relatedto that card, regardless of the drawer in which they are. As a result, an establishment asdepicted below will be formed.

![mind_map]()

There are many note-taking apps and software out there that support filtering the notesbased on tags. However, when it comes to linking components, either they do not do itat all or ask for a premium subscription. This project seized this opportunity to developan AI-based solution for uncovering the hidden topical patterns in the collection of notesin the Zettelkasten, automating the annotation of each card (document) and using thoseannotations to organise, summarise and enable topic-wise search of the Zettelkasten. In the subsequent sections, various approaches to accomplishing this task of topicmodelling have been discussed from which one which seemed fit has been selectedand reverse-engineered to project it as a mix of ​constraint satisfaction problem​ andoptimisation problem​.
Read the [report](https://drive.google.com/file/d/1IONbczPPcIZWUQib1kgxrN4nCNIoTyo8/view?usp=sharing) to know more.


