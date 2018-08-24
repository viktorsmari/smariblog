---
author: Smári McCarthy
categories: [Linguistics, Programming]
date: 2010-07-18
has_been_twittered: [true]
language: en
permalink: /2010/07/the-language-of-ui/
title: The Language of UI
---
<p class="wp-flattr-button">
  <a class="FlattrButton" style="display:none;" href="http://www.smarimccarthy.is/2010/07/the-language-of-ui/" title="The Language of UI" rev="flattr;uid:smarimc;language:en_GB;category:text;button:compact;">Every now and then people I know, mostly nontechnical folks, prod fun at the fact that I spend a lot of my time typing obscure sequences of letters into a black and white terminal. "Why," they ask, "don't you just use the mouse?" These people spend similar amounts of time clicking on various buttons, equally obscure if slightly more aesthetically pleasing, reveling in the fact that they can solve a lot of their problems by way of moving their mouse to and fro, clicking on graphical artifacts and enjoying the feedback. The command line is an old and archaic thing, true, but it is also extremely powerful. Where others go through alarmingly complex procedures to manipulate data using tools that are neither intuitive nor particularly ingenious, I can build at a moments notice advanced data processing pipelines that yield sophisticated results. I often ask GUI-toting pundits how they would go about counting how often a particular word occurs in a selection of, say, fifteen files, which exist in three differ</a>
</p>

Every now and then people I know, mostly nontechnical folks, prod fun at the fact that I spend a lot of my time typing obscure sequences of letters into a black and white terminal. &#8220;Why,&#8221; they ask, &#8220;don&#8217;t you just use the mouse?&#8221; These people spend similar amounts of time clicking on various buttons, equally obscure if slightly more aesthetically pleasing, reveling in the fact that they can solve a lot of their problems by way of moving their mouse to and fro, clicking on graphical artifacts and enjoying the feedback.

The command line is an old and archaic thing, true, but it is also extremely powerful. Where others go through alarmingly complex procedures to manipulate data using tools that are neither intuitive nor particularly ingenious, I can build at a moments notice advanced data processing pipelines that yield sophisticated results.

I often ask GUI-toting pundits how they would go about counting how often a particular word occurs in a selection of, say, fifteen files, which exist in three different directories with a common parent directory. That is to say, how many times, total, does a word, such as &#8220;foreshadowing&#8221;, come up in each single file. The answer I get is usually somewhere along the lines of using the search function in the operating system to find which of these files contain the word, and then opening each one in an appropriate application and doing instance counting there, then adding the results together by hand. My response to this is:

> grep foreshadowing \*/\* | wc -l

At this point I&#8217;m faced with one of two different arguments:

1.  It&#8217;s a stupid example; in reality you rarely have to know things like that and if you did then appropriate GUI tools would be produced to solve the problem.
2.  That&#8217;s a very complicated way of solving the problem, which requires you to remember keywords such as &#8220;grep&#8221; and &#8220;wc&#8221;, flags such as &#8220;-l&#8221;, symbols such as the pipe character and the stars, in addition to having a keen understanding of what each does, when it&#8217;s appropriate, and which order they should appear in.

The first argument is inexorably silly, because it&#8217;s a question of work habits. Clearly, if performing a particular task is unreasonably complex then you will develop work habits that prevent you from having to do them. On one extreme you will start maintaining very advanced indices of every potential aggregation, summation and other manipulation of every dataset you are working with, ad nauseam, in addition to having a stunning array of special purpose GUI applications that each is capable of producing a particular type of report given such a data set. On the other extreme you&#8217;ll simply accept not being able to get that kind of information (without the kind of manual hassle mentioned above) and ignore that it was ever a possibility. What most users do is actually somewhere in between these extremes, although somewhat tilted towards the side of ignoring the possibility. &#8220;GUI power users&#8221; tend to keep all sorts of utilities around, and have an uncanny ability to recall which sequence of mouse clicks will produce the utility at any given time and which check boxes and such are required to have it perform in the desired manner.

The second argument actually raises a very important philosophical question, and is actually deeply related to the first one.

In linguistics, the [Sapir-Whorf hypothesis][1] is the idea that the expressive capacity and flexibility of a language is fundamental to how the user of that language experiences reality. Per Wikipedia, it is &#8220;the idea that differences in the way languages encode cultural and cognitive categories affect the way people think, so that speakers of different languages think and behave differently because of it.&#8221; Or, in the worlds of Humboldt:

> The diversity of languages is not a diversity of signs and sounds but a diversity of views of the world

The canonical example of this is the [Piraha language][2] of the Amazon in which there is no mechanism for expressing values higher than 2 &#8211; they have words for &#8220;one&#8221;, &#8220;two&#8221; and &#8220;many&#8221;, without any ability to differentiate between greater values of many. Various experiments have been conducted to attempt to ascertain whether the speakers of the language are simply incapable of counting higher, but the conclusions are confusing at best. An interesting and to my mind important feature of this numerics issue is that the words for &#8220;one&#8221;, &#8220;two&#8221; and &#8220;many&#8221; are essentially the same, except with slightly different inflections and emphasis: &#8220;hói&#8221; and &#8220;hoí&#8221;. Also interesting is the fact that there is no nesting structure, which means that nested statements and complicated sentences cannot be constructed in the language.

If one is to ignore the chicken-egg problem and take Sapir-Whorf at face value (sinking into the depths of linguistic relativism, for better or worse), then the fact the language doesn&#8217;t provide any mechanism for expressing these things would mean that in the hard case, they are incapable of *thinking* in terms of more complicated numbers or complicated relations, or in the weaker case, that they simply have a strong tendency not to think in such terms, and when they do, they lack the necessary tools to be able to express these thoughts.

I&#8217;m fonder of the weaker case, and there are various arguments that have essentially demolished the stronger case.

So what this would mean is that languages such as English, which have a high degree of flexibility and an ability to express very complicated abstract ideas, are more likely to encourage speakers of the language to do so. Whether they do or not is besides the point, because being able to express ideas in a handy language will inevitably mean that somebody will, eventually, take use of the ability.

[On a side, I've sometimes poked fun at the fact that Icelandic has no word for what we call "abstract" in English, and many abstract concepts have no names. Those that do have names are more often than not analogical in some sense, such as the Icelandic word for "vector", "vigur", which is originally the name of a few different islands, all of which share the form of being narrow and tall. Likewise, the word for [duality][3] is "nykur", which is a horse-like animal from mythology with it's hooves facing backwards. Could it be that Icelandic speakers, having gained the capacity to discuss more abstract things than our language permits through other languages, or through cultural development, are in the process of compensating?]

The ability to express concepts succinctly and accurately is important. In mathematics there is a stunning array of symbols that have been developed over the centuries in order to facilitate greater accuracy than a language such as English can in any easy way express. The resulting symbology is in itself a separate language common amongst those who use mathematics, existing only in written form but having a great many accurate translations into natural languages.

In what way is this different from a computer&#8217;s user interface?

The sequences of clicks used by GUI-people, remarkably enough, has a grammar of its own. Buttons, menus and other widgets have syntactical rules governing them (you won&#8217;t see many text edit fields inside a drop down menu, for example) and have contextual meanings (when you right click on a text edit field, it is rare for a new window to open; you expect a context menu which provides tools relevant to the text field) that allow the person using that language to quickly assess the function being exposed.

Likewise, the sequence of terms and symbols that we command-line cowboys use on our black-and-white terminals also follow a grammar. Each term has a meaning which the user of the language learns and internalizes, each symbol has a purpose which is instantly distinguishable to anybody who &#8220;speaks&#8221; the language. In the same way as the GUI-user knows that the item in the &#8220;edit&#8221; drop-down menu labeled &#8220;cut&#8221; will remove the piece of selected text and store it in an invisible buffer, I know that when I type &#8220;wc&#8221; (meaning &#8220;**w**ord **c**ount&#8221;) it will count lines, words and characters in a stream of characters for me, unless I specifically tell it (by way of a parameter; akin to declinations) to only return one of these three values.

Which, then, is the more expressive language?

I&#8217;m not about to argue that graphical user interfaces are the computer interface equivalent of Piraha (not in any way to say that Piraha is rudimentary or &#8220;unadvanced&#8221; &#8211; although it is clearly less advanced than English for example in many ways, there are undoubtedly some things in the language that are superior to most other languages.), but I am going to argue that people who use only the GUI are going to have a much harder time expressing certain concepts than those who use the command line interface (CLI). The obverse is less true, since the CLI is provably capable, by virtue of being a text stream, of expressing everything the GUI can express, and much more. However, it is an important fact that many types of interaction are easier to express via the GUI, and are potentially less demanding of the user in terms of cognitive capacity.

Which is to say, GUIs are easy. We know that CLIs are harder. But they are more powerful by leaps and bounds, they&#8217;re more flexible and yield more sophisticated results quicker, and are less bound by the shortsightedness of particular GUI software developers. The CLI isn&#8217;t always the best way to do things; I use GUI&#8217;s all the time. My favorite photo editing software, The Gimp, provides a perfectly usable command line interface through which every possible manipulation of images is possible. However, for most photo editing purposes the buttons made available to me through the GUI and the filters available through context menus are far faster and more intuitive, so I use them instead. If, however, I ever find myself incapable of expressing the photo manipulation I wish to achieve by clicking on a sequence of buttons, I can always crack out the Scheme interpreter.

What I&#8217;m suggesting here is that people attempt to maximize their expressive capacity, by learning as many languages as possible. Natural languages, computer languages, funky abstract grammars like GUIs, and anything else that helps them to think in more accurate terms about the world we live in.

 [1]: http://en.wikipedia.org/wiki/Sapir-Whorf_hypothesis
 [2]: http://en.wikipedia.org/wiki/Pirahã_language
 [3]: http://en.wikipedia.org/wiki/Duality_(mathematics)
