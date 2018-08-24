---
author: Smári McCarthy
date: 2015-03-10
language: en
tags: [Software, JSON]
title: Bulk and memory
---

I'm working a lot with huge datasets these days, and it's becoming par for the course to end up with large files in various formats. I found myself showing up to work this morning to find a 13GB JSON file waiting for me to load it into ElasticSearch. The JSON file was an array containing some 550000 large objects. Unfortunately the file isn't structured in such a way as to allow just throwing it at ElasticSearch's bulk loader, so I need to parse it out and do stuff with the objects. The list as such doesn't matter.

If you know how JSON parsers work, you'll understand why this is a problem. If you don't, suffice to say that there are two general approaches to parsing JSON. The common one is to iterate over the entire document, loading each entity, when fully parsed, into memory, and returning a data structure. This of course would result in the program eating up about 14GB of memory (or more, because pointers and refcounts), which is kind of okay in this case since I have more RAM than that, but is less and less acceptable as the data size grows.

The other approach is what some refer to as a "SAX-like" parser, although it's probably better to call it an event parser. Such a parser iterates over the document, but instead of loading everything into memory resident data structures, it just announces events like "object start" or "string end", sometimes including a value. The value is typically only filled if the event has a natural value field.

Since my weapon of choice for this project is Python, the standard module is (not surprisingly) `json`. It does the former type of parsing, so that's no good. `ijson` is a module that does event parsing, but the events are so granular that I'd have to keep track of the entire document as a stack in order to be know what's going on, and essentially reconstruct each part of the document in memory based on the events. That's way too much work, and seems to me like the wrong approach for most of the processing I'm going to be doing.

I couldn't find any modules that don't use either of these approaches. What I need is a middle-ground parser, that allows me to specify something like: "give me all objects that are nested 1 deep", or "give me anything that's on the third nesting level".

Building this kind of parser requires managing a certain amount of state. Specifically, it needs to keep track of three things:

 1. What nesting level are we at.
 2. The type of entity we're dealing with at each nesting level.
 3. The sequence of bytes from the beginning of the place where we entered a nesting level we care about until the the end of it. (This can then be run through the standard `json` parser.)

For now, I'll just do the simplest thing: skip the first line ("["), skip the last line ("]"), and drop the trailing comma from each line. But since I expect to run into gargantuan JSON blobs every now and then, I might take a shot at writing a midway parser.

In the meantime, by all means let me know if this already exists.

