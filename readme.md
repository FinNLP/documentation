# Introduction

## What Is It

An extensible, __by design__, natural language processing library and detection framework for **node.js**, that provides high and low level processing and detection.

## Motivation

There are more than few NLP projects out there, however when your project is built with Node.js and the NLP you're using is written in another language, this puts an unnecessary level of complexity and your team needs extra expertise on that language.

JavaScript and Node.js is rising in the bots world, where natural language processing is a core requirement, yet the best natural language processing projects are written in other languages

## Extensibility by Nature

The core library provides you with:

- **Sentence level lexer**: this is used to break a string of text into multiple sentences.
- **Token level lexer**: this is used to break each sentence into multiple tokens
- **POS tagger**: Annotate each token with the appropriate part of speech tag, `NN` for a noun, `NNS` for a plural noun, `VBP` for a present verb ...etc
- **Dependency Parser**: Resolve each token dependencies and annotate them, for example the verbal phrase may have two dependents: `NSUBJ` a nominal subject, and `DOBJ` a direct object.

Those are what we're going to call: **processors**. Each one of them is extensible, but that it not what I mean by extensibility by nature.

Extensibility by nature describes the fact that this framework doesn't have a detectors in it's core, but it's so trivial to add your own, and the detector you're going to add will be treated as a first citizen in the framework.

## Comparison with Other Solutions

The current state of natural language processing in javascript can not be described as "satisfactory".

- [Natural](https://github.com/NaturalNode/natural)
	- Doesn't have a dependency parser.
	- Their POS tagger is based on [fasttag](https://github.com/mark-watson/fasttag_v2), which can only get you around 87% accuracy.
	- Too complex to get start with.
- [speakEasy](https://github.com/nhunzaker/speakeasy)
	- Doesn't have a dependency parser, however they have implemented a technique that detects the subject and the object of the sentence, yet it fails on most of the cases and it's mostly not usable for creating smart bots.
	- Inaccurate POS tagger.
	- The project is most likely dead, since the last commit was two years ago.
- [Compendium](https://github.com/Ulflander/compendium-js)
	- It has two dependency parser, both of which are experimental, not yet fully implemented and require a lot of additional rules.
	- You can only extend it by adding more detectors.
	- This project _once_ seemed to be promising, however it's not being maintained at the moment. In fact, most of the processors and the detectors of this library are actually inspired by Compendium.


## Credits