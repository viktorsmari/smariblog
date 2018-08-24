---
author: Smári McCarthy
categories: [Cryptography, English, Privacy, Software]
date: 2013-06-11
has_been_twittered: [true]
language: en
permalink: /2013/06/what-we-need/
title: What we need
---

A lot of people have been asking what can be done to counteract the NSA&#8217;s spying. There&#8217;s no simple answer to that, and frankly it&#8217;s a big mess. A number of cryptographic tools might improve privacy, including [PGP][1] and [OTR][2] for e-mail and IMs respectively, [Cryptocat][3] for multiplayer chat, [TrueCrypt][4] for encrypted hard drives, and so on. Some or all of these may be compromised, but given Glenn Greenwald&#8217;s descriptions of Edward Snowden&#8217;s behavior there is reason to believe that full disk encryption is at least practically safe for now (as far as he knows).

While we&#8217;re still somewhat in the dark about the true nature of NSA&#8217;s capabilities, there are a few interesting hints. One is that the Prism project seems directed at particular service providers rather than backbone carriers, which to me sounds like centralized infrastructures are considered to be low hanging fruit in their camp. This is not surprising, and should serve as at least some encouragement to seek out decentralized or distributed alternatives.

I tend towards a certain amount of pragmatism when dealing with issues of security, because while I don&#8217;t think people should sacrifice their security for comfort, the reality is that everybody does on some level: we need to get work done, we need to communicate with our friends, family, co-workers and clients, and there&#8217;s just no way to avoid sharing photos of kittens, they&#8217;re so adorable.

This leads to the question, how can we make comfort more secure &#8211; which is a slightly different question from how do we make security more comfortable, a question I&#8217;ll undoubtedly address at a later date. The key difference is the viewpoint: people love tools like Google Docs, GMail, Skype and Facebook, and so people use them despite knowing that they are fundamentally insecure. A lot of it is socially driven too: We use Google Docs because we&#8217;re working on documents there with our colleagues. We use Skype because our business partners are scattered around the world and it&#8217;s simply cheaper and better than phones. We use Facebook because it&#8217;s the only way to keep in touch with people &#8220;back home,&#8221; not to mention that in some countries, it is the chief mode of political or social engagement.

So can we make these tools more secure? What do we need to do it?

First off, we need some form of federated or P2P collaborative document editing. Etherpad and Etherpad Lite don&#8217;t cut it, nor does [Kune][5]. Etherpad forms the basis for Google Docs, we&#8217;re told, but it suffers from the fact that it&#8217;s more of a glorified multiplayer notepad than a serious document editing system. Things that are missing include, but are not limited to: fonts, styles, margins, pagination, headers and footers, PDF and other file export, comments, footnotes, tables, pictures, equations and automatically generated tables of contents. At minimum. Kune solves some of these issues, as a descendant of Google Wave, but still falls short in most of the important categories when it comes right down to it. The core thing is, we need documents that look and feel like documents, not just really good sharing experiences with psychedelic colors or cumbersome user interfaces.

I think Kune is actually closer to the golden standard. I&#8217;m currently on the advisory board for a project which aims to improve Kune substantially, and have proposed that &#8220;making documents look like documents&#8221; should be a priority task, but we&#8217;ll have to see how that goes.

The other thing we need is a good e-mail client that&#8217;s built around a search engine with MUA metaphor rather than a MUA with search engine metaphor. Some people will jump up and shout &#8220;[Not Much!][6]&#8221; at me, but they are wrong. Not Much is wonderful, as long as you happen to be a geek. Most people are going to need something that&#8217;s easy to set up, has a good user interface, and makes it easy to not have to trust a third party. The solution, there, I think is [MailPile][7]. It&#8217;s not as developed as Not Much, but it is in my opinion superior, in part because it&#8217;s doing a lot of fancy optimizations that Not Much simply can&#8217;t do, and more importantly because it&#8217;s developer is pretty serious about making it nice and user friendly (although part of his strategy for ensuring this is having other people do it).

On the Skype replacement front, we&#8217;re pretty much screwed. The market capture is nigh complete, and due to it being an entirely closed off protocol in an environment where the network size is everything, breaking the monopoly is kind of hard. The good news is that [Jitsi][8] is getting ever closer to being a viable Skype replacement in terms of features. It still feels a bit rough around the edges in some places, and frankly I&#8217;m not a big fan of having to run Java stuff (although the JRE has been getting substantially better in recent years), but with a bit of effort and some focus it&#8217;ll hopefully give us secure, decentralized comms soon enough.

There are of course a million other big things that need to be done, but I&#8217;d say these are the big three in terms of making comfort more secure. By all means, if you have development skills and can lend some free cycles to any of these projects, please do. The world needs you!

 [1]: http://gnupg.org
 [2]: http://www.cypherpunks.ca/otr/
 [3]: http://crypto.cat
 [4]: http://www.truecrypt.org
 [5]: http://kune.cc
 [6]: http://notmuchmail.org/
 [7]: https://github.com/pagekite/Mailpile/
 [8]: https://jitsi.org/
