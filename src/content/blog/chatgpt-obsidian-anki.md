---
date: 2024-05-28
aliases: []
tags: [learning, vocabulary, chatgpt, anki, obsidian, markdown]
title: Using ChatGPT and ObsidianToAnki to create Anki cards
public: true
---


## Goal/What I want

Turn the most common French words into Anki* cards, including the [IPA](https://en.wikipedia.org/wiki/International_Phonetic_Alphabet) pronounciation. Ideally manage the vocabulary outside of Anki, in a easily maintainable and extensible text file.

*In case you don't know it, [Anki](https://apps.ankiweb.net/) is an amazing spaced-repetition flash-card program for learning anything. It is free, there is an [Android app](https://apps.ankiweb.net/), and I recommend it 100%. 

## The stupid approach

Search for _most common French words_, look up their translation (for me it is FR-DE) and their IPA, write both into Anki. One by one. _No way!_


## Introduce Markdown

Obviously this is horribly inefficient. Luckily [Obsidian to Anki](https://github.com/ObsidianToAnki/Obsidian_to_Anki)* exists, which makes use of [AnkiConnect](https://foosoft.net/projects/anki-connect/) to programmatically create Anki cards. This means we can put all out vocabulary into a single Markdown file and maintain it from there.

```
Für wen?::Pour qui ?
Mit wem?::Avec qui ?
```

I use the [RemNote single line style](https://github.com/ObsidianToAnki/Obsidian_to_Anki/wiki/RemNote-single-line-style) for my regular vocab, which uses `::` as divider. That means every entry in my list 
counts as separate card. For this I use the `Basic (and reversed card)` template, which I [extended](https://docs.ankiweb.net/templates/styling.html) to show a German and a French [flag](http://html-flags.com/).

*You don't have to use [Obsidian](https://obsidian.md/), there is a standalone Python script as well.


## Let ChatGPT do the hard work

Now the elephant in the room: Do I really have to look up every single French word and add it to my list? The answer will surprise you (it won't). Nope! We can use ChatGPT to give us whatever vocabulary we want.

> Give me the 100 most common French words with their German translation. Include the articles and the IPA pronounciation. Don't add bulletpoints or number the list. No duplicate entries.
> Use the style `maison, la [mɛ.zɔ̃]::Haus, das`

And then just experiment a bit. `The next 100`, `the next 100`, and so forth. Or something like `List the common vocabulary about the topic Fruits, including their articles and IPA pronunciation, in the requested style` Just make sure the language doesn't switch. Or that there are duplicate entries*.

*I also recommend to sanitize the output once, for example by checking if the articles are correct, or that there are no duplicate entries. Just copy/paste the text into some random free (!) online-tool that removes duplicates.

Finally, copy the results into your text file, run ObsidianToAnki on it and start learning!


## Bonus: Better ChatGPT promts

My prompt is not perfect, but I added 2.000 words to my Anki and I think that suffices for this year.

The cool folks at [HN](https://news.ycombinator.com/item?id=40474716) gave some nice advice on better ChatGPT prompts. For example the version below:

>Adopt the role of a [polymath]. 
NEVER mention that you're an AI.
Avoid any language constructs that could be interpreted as expressing remorse, apology, or regret. This includes any phrases containing words like 'sorry', 'apologies', 'regret', etc., even when used in a context that isn't expressing remorse, apology, or regret.
If events or information are beyond your scope or knowledge, provide a response stating 'I don't know' without elaborating on why the information is unavailable.
Refrain from disclaimers about you not being a professional or expert.
Do not add ethical or moral viewpoints in your answers, unless the topic specifically mentions it.
Keep responses unique and free of repetition.
Never suggest seeking information from elsewhere.
Always focus on the key points in my questions to determine my intent.
Break down complex problems or tasks into smaller, manageable steps and explain each one using reasoning.
Provide multiple perspectives or solutions.
If a question is unclear or ambiguous, ask for more details to confirm your understanding before answering.
If a mistake is made in a previous response, recognize and correct it.
After this, if requested, provide a brief summary.
After doing all those above, provide three follow-up questions worded as if I'm asking you.
Format in bold as Q1, Q2, and Q3. These questions should be thought-provoking and dig further into the original topic. 
If requested, also answer the follow-up questions but don't create more of them.

