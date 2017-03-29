# Introduction

## What Is It

An extensible, __by design__, natural language processing library and detection framework for **node.js**.

## Motivation

There are more than few NLP projects out there, however when your project is built with Node.js and the NLP you're using is written in another language (python is common choice), this puts an unnecessary level of complexity and more experience requirements for your team.

JavaScript and Node.js is rising in the bots world, where natural language processing is a core requirement, yet the best natural language processing projects are written in other languages.

I'm not saying that this project is supposed to be an alternative to the established state of the art current solutions, but it tries to provide you with a handy features and tools that might cover your needs.

## Extensibility by Nature

To understand the concept of __extensibility by nature__ you must understand the core architecture of this project and how it's supposed to be used.

Almost every natural language processor comes bundled with the following processors:

- A lexer: which separates tokens (words) from each other, converting a string of text that represents a sentence like this one: `"That's a sentence"` to a list (array) of tokens: `["That","'s","a","sentence]`.

- A part of speech tagger: that is basically annotates each token with the appropriate part of speech (POS) tag. `a` is tagged as `determiner`, `Alex` is tagged as `proper noun` ...etc.

- A dependency parser: which tries to analyze the sentence and figure out the relationships between the tokens. e.g. what an adjective describes, what's the subject and the object of a given verb ...etc.

__Fin__ gives you those processors out of the box. But in the real world use cases, the result of such processors may not be of a great use. This is why it has been designed to be extensible in a way that each extension build it's results on top of the aforementioned processors and may require other extensions as well.

Those extensions (that relies on the aforementioned processors) is what we're going to call "detectors" through this documentation.

For example using the tokens and the dependency parser you can detect local token emphasis. So a sentence like this one: `"Alex explicitly stated his dissatisfaction"` a detector can look for adverbs of emphasis, like `"explicitly"` and based on the dependency parser looks for the nearest ancestral verb, which is `"stated"` in the above example and mark it as being emphasized.

## Comparison with Other Solutions

The current state of natural language processing in javascript can not be described as "satisfactory".

- [Natural](https://github.com/NaturalNode/natural)
	- Doesn't have a dependency parser.
	- Their POS tagger is based on [fasttag](https://github.com/mark-watson/fasttag_v2), which can only get you around 87% accuracy.
	- Too complex to get start with.
- [speakEasy](https://github.com/nhunzaker/speakeasy) (Not being maintained)
	- Doesn't have a dependency parser, however they have implemented a technique that detects the subject and the object of the sentence, yet it fails on most of the cases and it's mostly not usable for creating smart bots.
	- Inaccurate POS tagger.
	- The project is most likely dead, since the last commit was two years ago.
- [Compendium](https://github.com/Ulflander/compendium-js) (Not being maintained)
	- It has two dependency parser, both of which are experimental, not yet fully implemented and require a lot of additional rules.
	- You can only extend it by adding more detectors.
	- This project _once_ seemed to be promising, however it's not being maintained at the moment. In fact, most of the processors and the detectors of this library are actually inspired by Compendium.


## Getting Started

You should head over to the sidebar menu and read about the processors and how to author detectors.