---
author: Smári McCarthy
categories: [English, Law, Privacy, Software, Technology]
date: 2011-07-12
has_been_twittered: [true]
language: en
permalink: /2011/07/tracking-without-cookies/
title: Tracking without cookies
---
<p class="wp-flattr-button">
  <a class="FlattrButton" style="display:none;" href="http://www.smarimccarthy.is/2011/07/tracking-without-cookies/" title="Tracking without cookies" rev="flattr;uid:smarimc;language:en_GB;category:text;button:compact;">During a session at IDP 2011 (conference on Internet, Law and Politics) in Barcelona I started thinking about the issue of opt-outs / opt-ins for tracking cookies. If we were to imagine a situation where most people reject tracking cookies - which would be nice - then those who are interested in tracking users would have to resort to other methods. I just came up with one. I haven't seen this before but it's fairly obvious, I'm sure that there are dozens of variations on this theme or even much better approaches. By "better" I mean "more effective", not necessarily nicer - violating people's privacy is not nice. ﻿﻿First, create a hidden <div> containing a bunch of links, to, for example, http://smarimccarthy.com/tracking/X, with X equals numbers from 1 to 33. 33 is enough because 2^33 is greater than the number of humans (by about a billion), but you might want to add more links. The <div> is hidden using the display:none CSS directive. When the page is loaded a Javascript on the p</a>
</p>

During a session at IDP 2011 (conference on Internet, Law and Politics) in Barcelona I started thinking about the issue of opt-outs / opt-ins for tracking cookies. If we were to imagine a situation where most people reject tracking cookies &#8211; which would be nice &#8211; then those who are interested in tracking users would have to resort to other methods.

I just came up with one.

I haven&#8217;t seen this before but it&#8217;s fairly obvious, I&#8217;m sure that there are dozens of variations on this theme or even much better approaches. By &#8220;better&#8221; I mean &#8220;more effective&#8221;, not necessarily nicer &#8211; violating people&#8217;s privacy is not nice.

﻿﻿First, create a hidden <div> containing a bunch of links, to, for example, http://smarimccarthy.com/tracking/X, with X equals numbers from 1 to 33. 33 is enough because 2^33 is greater than the number of humans (by about a billion), but you might want to add more links. The <div> is hidden using the display:none CSS directive.

When the page is loaded a Javascript on the page checks each of them in sequence to see if they&#8217;ve been &#8220;clicked&#8221;, by reading the &#8220;visited&#8221; property. If none of them have been clicked, send request to server (over AJAX) which sends back a number (between 1 and 2^33). That number is decomposed and certain links opened in hidden <iframe>s based on the number (binary expanded to figure out which links to click).

From now on, when the page is opened (until the user clears browsing history) the relevant links will be marked as &#8220;visited&#8221;, so the script will figure that out and send a unique ID code back to the server (over AJAX). Anything which is relevant to the identity of the user is then sent back.

This is of course a terribly convoluted way of tracking people, but for the purposes of the exercise it is sufficient. It&#8217;s easily thwarted by clearing browsing history, but a lot of users aren&#8217;t going to do that.

What this highlights is that banning tracking cookies isn&#8217;t sufficient. Banning tracking generally probably isn&#8217;t either, as it&#8217;s an arbitrarily complex problem.

Just a thought.
