---
title: "Assignment 2"
excerpt: "Can a Computer Separate Style from Content?"
layout: single
date: 2026-04-26
categories:
  - assignments
---
# Can a Computer Separate Style from Content?

Literature does more than carry information; it creates patterns, rhythms, and textures that shape how the reader moves through a text. With the help of digital tools, in this essay we tried to examine whether those patterns can be meaningfully distinguished from the content they carry. 

This work applies two computational methods to 18 science fiction texts from Project Gutenberg, written by six authors: Leigh Brackett, Philip K. Dick, Henry Kuttner, Andre Norton, H.G. Wells, and Marion Zimmer Bradley. Stylo analyzes style through the most frequent words, the grammatical scaffolding that tends to remain consistent across an author’s work regardless of subject. TF-IDF analyzes content through the most distinctive words, the vocabulary that sets each text apart from others. Running both methods on the same corpus gives us a good insight of different pictures of the same texts, and comparing those pictures is where the interesting questions begin to arise.

Our guiding question in this essay is whether style and content reliably pull apart or whether they collapse back into each other. Here, we tried to use the agreement and disagreement between the two methods to explore what each one sees and what each one misses. As Ted Underwood warns in Distant Horizons (2019), computational results carry an air of authority that can obscure the many choices behind them. Running two methods side by side is one way of keeping those choices more visible.

The Corpus includes 18 texts that span nearly seventy years.
Here is short summary about every author:
### [Leigh Brackett](https://www.isfdb.org/cgi-bin/ea.cgi?334)
Nicknamed “the Queen of Space Opera”, Leigh Brackett was one of the most prominent female writers of the Golden Age of Science Fiction. She worked across genres; her hard-boiled mystery writing impressed Howard Hawks enough to hire her for The Big Sleep (1946), and she delivered an early draft of The Empire Strikes Back before her death in 1978. Her style includes punchy dialogues, atmospheric worlds, and emotionally driven stories. Two of her texts from the corpus feature Eric John Stark (Black Amazon of Mars and Enchantress of Venus), while The Blue Behemoth is a separate story following Bucky Shannon’s struggling space circus, where interference with alien life leads to chaos. What ties all three together is Brackett’s broader fingerprints like morally complex protagonists, vivid alien settings, and a sensitivity to power dynamics.

### [Philip K. Dick](https://www.isfdb.org/cgi-bin/ea.cgi?23)
Philip K. Dick is one of the most philosophically ambitious writers in the corpus. His fiction obsessively probed questions of reality, identity, perception, and what it means to be human. All three of his texts in the corpus are from 1953 and are steeped in Cold War anxiety, featuring self-replicating robots, nuclear wastelands, machine-controlled societies, and the terrifying possibility that reality is a carefully constructed lie. He is arguably the writer whose concerns feel most contemporary, and his short stories directly anticipate themes he would develop in later celebrated novels.

### [Henry Kuttner](https://www.isfdb.org/cgi-bin/ea.cgi?452)
Kuttner wrote across science fiction, horror, and cosmic horror. He frequently collaborated with his wife C.L. Moore, publishing under pseudonyms like Lewis Padgett. His corpus here is the most varied: Thunder in the Void is a dark space adventure about alien energy beings, The Ego Machine is a satirical comedy set in Hollywood, and The Black Kiss is a horror story co-authored with Robert Bloch, making it a particularly interesting test case for authorship detection tools like Stylo.

### [Andre Norton](https://www.isfdb.org/cgi-bin/ea.cgi?209)
Norton was one of the first major female sci-fi writers, though she deliberately used a gender-neutral pen name (“Andre”) to be taken seriously in a male-dominated field; she also wrote as Andrew North and Allen Weston. Her writing is immersive, strong on world-building, and focused on themes of space travel, survival, and alien worlds. Her three texts range from a quarantine thriller (Plagueship) to questions of identity and manipulation (Star Hunter) to science versus superstition (Voodoo Planet).

### [H.G. Wells](https://www.isfdb.org/cgi-bin/ea.cgi?65)
The oldest and most canonical writer in the corpus, Wells wrote across fiction and nonfiction. Trained in biology and deeply influenced by Darwinian thought, he foresaw aircraft, nuclear weapons, space travel, and something resembling the internet. His three texts in the corpus span fiction (The War of the Worlds, The Island of Doctor Moreau) and nonfiction (The Salvaging of Civilization), the last of which makes him a genre outlier in this sci-fi corpus, which is important for interpreting the computational results.

### [Marion Zimmer Bradley](https://www.isfdb.org/cgi-bin/ea.cgi?185)
Bradley was an American author who wrote from the 1950s onward, known for integrating female perspectives and exploring gender, sexuality, and social hierarchies in genres that largely excluded them. Her author tags on [ISFDB](https://www.isfdb.org/cgi-bin/ea.cgi?185) include telepathy, alien contact, time travel, and mind transfer. Her three texts in the corpus vary considerably in tone and scale. Jackie Sees a Star is a short, lighter story about a child communicating psychically with an alien; Falcons of Narabedla follows a modern protagonist transported into a distant alien future; and The Door Through Space is full space opera, following a former intelligence agent dragged back into a planetary rivalry threatening a galactic empire. 

