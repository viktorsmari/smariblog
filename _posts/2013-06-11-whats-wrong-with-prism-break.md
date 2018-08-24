---
author: Smári McCarthy
categories: [Cryptography, English]
date: 2013-06-11
has_been_twittered: [true]
language: en
permalink: /2013/06/whats-wrong-with-prism-break/
title: What&#8217;s wrong with Prism-break
---
<p class="wp-flattr-button">
  <a class="FlattrButton" style="display:none;" href="http://www.smarimccarthy.is/2013/06/whats-wrong-with-prism-break/" title="What&#8217;s wrong with Prism-break" rev="flattr;uid:smarimc;language:en_GB;category:text;button:compact;">I like the idea of providing a list of tools for "breaking the Prism" - in fact, I started such a list with Daniel van der Velden from Metahaven yesterday, but the EFF beat us to it - they're wonderful that way. Except I don't agree on every point... See, while I agree that people should generally use free software, and should be using PGP (in the OpenPGP standard sense - not the PGP commercial software sense, an important distinction pointed out by @rikwes66) and OTR, and what not, I think their list of things is slightly lacking. First off, riseup.net is a great e-mail service except in that their entire user base consists of people who are trying to be dissidents. This is like painting a fairly massive bullseye on the service, and one can be fairly confident that this is one of the things that is actively monitored. Pidgin is a wonderful piece of software, but it is known to have a lot of security vulnerabilities. These are actively being patched, but I'd not recommend it for anything high securit</a>
</p>

I like the idea of providing a list of tools for &#8220;breaking the Prism&#8221; &#8211; in fact, I started such a list with Daniel van der Velden from [Metahaven][1] yesterday, but the [EFF][2] beat us to it &#8211; they&#8217;re wonderful that way. Except I don&#8217;t agree on every point&#8230;

See, while I agree that people should generally use free software, and should be using PGP (in the OpenPGP standard sense &#8211; not the PGP commercial software sense, an important distinction pointed out by @rikwes66) and OTR, and what not, I think their list of things is slightly lacking.

First off, riseup.net is a great e-mail service except in that their entire user base consists of people who are trying to be dissidents. This is like painting a fairly massive bullseye on the service, and one can be fairly confident that this is one of the things that is actively monitored.

Pidgin is a wonderful piece of software, but it is known to have a lot of security vulnerabilities. These are actively being patched, but I&#8217;d not recommend it for anything high security for now.

Bitmessage is an interesting concept, but to confuse it with e-mail is a very bad idea. It cannot communicate with the rest of the users of e-mail, and therefore it is not in any meaningful sense a replacement for any e-mail client.

This is where we get into some questions of licencing. I mentioned to @infil00p earlier that the licensing issue was important because, frankly, &#8220;mostly free&#8221; or &#8220;not entirely free&#8221; essentially translates to &#8220;eventually this thing will fuck you&#8221;. He disagreed, pointing at Tor, which is marked as &#8220;mostly free&#8221;. Tor is distributed under a BSD license, which is very much free software under any reasonable definition &#8211; [up to and including the Free Software Foundation&#8217;s][3] &#8211; although it is not Copyleft. I would contend that Tor is entirely free for all intents and purposes.

The issue is, less about licensing, really, and more about who has ultimate control over the infrastructure. If you can set up your own infrastructure, there is no problem.

I&#8217;m going to have to go into a much more detailed set of arguments about why I&#8217;m not entirely content with Mailvelope and WebPGP, but for now I&#8217;d say use them and enjoy them. Made simple, the problem I have with WebPG is that it&#8217;s not very user friendly, and the problem I have with Mailvelope is that it uses OpenPGP.js &#8211; a great idea, but made less secure by the fact that we can&#8217;t really trust the JavaScript engine, the browser local storage, or the DOM separation between websites and plugins to be sufficient at this point: it&#8217;s painfully complicated to audit a browser. My suggestion is roughly, forgo the Javascript-side crypto and outsource it through a thin and well audited NPAPI layer over to the PGPME library, which then speaks with the keys stored locally. If the NPAPI layer is done correctly, the vast majority of the threats have been eliminated.

I refer to my [last post][4] for why Etherpad and Ethercalc are insufficient.

As for Android and iOS, just treat them as untrustworthy. It&#8217;s way simpler.

This stuff is complicated, I&#8217;m afraid.

 [1]: http://www.metahaven.net
 [2]: http://www.eff.org
 [3]: http://www.gnu.org/licenses/license-list.html
 [4]: http://www.smarimccarthy.is/2013/06/what-we-need/
