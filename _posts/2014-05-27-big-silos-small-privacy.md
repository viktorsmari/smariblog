---
{categories: English, date: 2014-05-27, language: en, title: 'Big Silos, Small Privacy'}
---

For many months I've been going around claiming that about 90% of all e-mail users use the top ten e-mail providers. This claim was always a ballpark estimate, but it was based on a bunch of statistics that I collected from here and there around the Internet. 

Most importantly, there appear to be between 2.5 and 3 billion Internet users globally, and there appear to be between 2.4 and 2.7 billion e-mail users. Some old self-reporting figures from GMail - dated because it's probably no longer in Google's interest to say how many users they have, since they're dominant - said they had 435 million users. That was in 2008. It's not a stretch to think they've stil got about 20-25% of the total market. Hotmail/Outlook.com and Yahoo add substantially to these figures, at least sucking up the first billion. The next seven after that (which include services like the Russian Yandex and the Chinese QQ) easily cover the next 1.1 billion users.

Ballpark figures are nice, but it's always good to back them up with data. Benjamin Mako Hill presented some data the other day which helps us with this. Based on a conversation with the Electronic Frontier Foundation's Peter Eckersley, he started investigating how much of his private e-mail goes through Google's servers. In [his posting][1], he says that "Peter pointed out that if all of your friends use Gmail, Google has your email anyway. Any time I email somebody who uses Gmail — and anytime they email me — Google has that email."

Mako went on to make [a simple Python script and R script][2] to run through his MailDir, extract the data, and generate some nice graphs from them, including a LOESS smoother showing a floating average over several weeks.

![Mako's GMail delivered Email over time](http://mako.cc/copyrighteous/wp-content/uploads/2014/05/emails_gmail_over_time.png)

His results were shocking: "Last year, Google delivered 57% of the emails in my inbox that I replied to. They have delivered more than a third of all the email I’ve replied to every year since 2006 and more than half since 2010. On the upside, there is some indication that the proportion is going down. So far this year, only 51% of the emails I’ve replied to arrived from Google."

![Mako's GMail delivered Email over time (proportionate)](http://mako.cc/copyrighteous/wp-content/uploads/2014/05/emails_gmail_prop_over_time.png)


## Expanding on the scripts

Now, Mako's observations are interesting, but they don't, as such, help us figure out how much of the world's e-mail is going through the top ten providers. And actually, that doesn't matter to me really so much as the question of how much of the world's e-mail is passing through services that are compromised by [the Five Eyed Monster][3]. So time to do a bit of expanding.

First off, I have a large number of MailDirs, so I added support for scanning a whole lot of them. Then I expanded his capture rules to include some other large E-mail providers, including Outlook/Hotmail/Live, Yahoo, Mail.com and, of course, the undying AOL.

The scanning took a while. Mailpile tells me that I have about 316.000 e-mails in my current mail directory, but this is only from early 2009 - anything before that is on a separate hard drive that I didn't include in my scan.

I also had to modify my script to not include two awkward events: earlier this year, a server that used to be managed by me but still had my e-mail address on its error-reporting list decided to send me about 17000 e-mails over the course of 3 days. Another similar event happened in 2012, where a server I was managing freaked out overnight and sent me a couple of thousand e-mails. These were easily eliminated.

My modified scripts are available on [Github][4].


## Results

At first glance, my results are a bit more shocking than Makos. It appears that for a long time, almost all of my e-mail seems to have gone through the servers of the large service providers. Over the years less and less of it has done so. In particular, for most of 2009 and 2010, the average is just shy of 90%.

![My e-mail that "touched" big service provider servers (proportionate)](/img/2014-05-27-email-proportionate.png)

At first, it seemed like it had started dipping downwards quite substantially in 2010-2011, but when I added e-mails received from social networking sites such as Twitter and Facebook, which periodically come to notify of messages being sent, it pulled the data back up a bit - but not the whole way. This might be good or bad, I'm not sure.

The overall trend is more encouraging: less and less of my e-mail seems to go through these large service providers. In particular, there is a very sharp downturn that starts in the summer of 2013. This appears to coincide with the Snowden revelations, and suggests that a great many people who communicate with me have, since the summer of 2013, stopped doing so using the servers of the large e-mail providers. Good job, y'all!

Now, there are a bunch of caveats. Most importantly, my inbox is not representative of inboxes on the Internet. In particular, I was asked by a friend to whom I showed this data whether he could do a similar analysis. I responded by pointing out that his e-mail address ends with @gmail.com, and therefore 100% of his mail would have gone through the servers of large service providers. If 90% of all users use these large service providers, and we assume that the other 10% have statistical properties like mine, then there is a fair chance that around 99% of all e-mail goes through major servers. If you change those assumptions, the numbers can be worse or better, of course..

In order to get a better understanding of the actual layout, it would be good to gather a collection of data. The data generated by Mako's script is anonymous. The only fields are mail status (to get the replied data), timestamp, whether it was mailing list mail, and whether it matches critera (i.e., whether it went through a big provider or not). There is some room for abuse, in particular in that the timestamps on my incoming mail give strong indications as to which timezones I communicate with the most, and the frequency of mailing list tagged mail may be of interest to somebody. But seeing as how the Five Eyed Monster already has this data, and I'm not particularly worried about other people having *this* data, I'm okay with it.

For that reason, in the source archive, I've put my own tab seperated value output file. I'd like to solicit pull requests against that repository for more data sets. It may help to give a more accurate composite statistical overview of where we stand.


## Cost estimation

Throughout the NSA surveillance discussion, I have been arguing that the way to "win", where we define winning as cause the Five Eyes to not conduct blanket surveillance any more, is to price them off the market.

The calculus of that has been based on [a bunch of assumptions][5]. In short, we assume there are about 2.5 billion people who use the Internet, and the total surveillance budget is on the order of 120 billion dollars per year. That roughly comes out to about $0.13 per person per day.

However, it's immediately obvious that the obvious method of deriving this number is not smart: if you increase the number of Internet users, or increase the cost of monitoring any individual user, this is not correctly reflected in the figure. So I've chosen to use $0.13 per person per day as the baseline, and raise the number by arbitrary estimations.

It is pretty certain that the number of Internet users has gone up, but I'm assuming that most of the Five Eyes surveillance methods are largely insensitive to changes in population. However, there are a few things that have happened since Snowden released his documents:

 1. There are a lot more people than ever who encrypt their data. This is not a statistically significant number yet, but it's bound to impact the bottom line. I'm willing to say that progress so far amounts to +$0.01 per person per day on average.

 2. A lot of people are moving away from big e-mail providers, as evidenced by the above data. Based on my data, it looks substantial enough to warrant giving it +$0.10 per person per day. If it turns out that this trend is replicated in lots of other people's data, then I may be willing to revise it up.

 3. Morale in the NSA is apparently quite low. This is presumably because the NSA staff discovered that the people of this world do not appreciate being spied on. Low morale may reduce efficiency, but I'm not going to give them too much for that: +$0.01.

There may be other factors, but at the same time there are some other problems. The biggest is that there are all sorts of dangerous snake oil services popping up all over the place that either recreate the Lavabit stupidity wholesale or else don't even go that far and provide "security" measures that are just downright stupid and dangerous. I therefore hereby assume that [ProtonMail][6], [Virtru][7] and other comparative "secure e-mail services" are thoroughly backdoored by the NSA already. For every user that moved from GMail to ProtonMail, our figure actually went down by some fraction of a cent.

So the standing total - in my estimation - is currently around $0.25 per person per day to monitor everybody in the world. That's almost a doubling in surveillance costs since around this time last year, but we need to bring that number to about $10000 per person per day before we can safely assert that blanket surveillance is a thing of the past.


 [1]: http://mako.cc/copyrighteous/google-has-most-of-my-email-because-it-has-all-of-yours
 [2]: http://projects.mako.cc/source/?p=gmail-maildir-counter
 [3]: https://www.youtube.com/watch?v=cRfb-Lp9OGg
 [4]: https://github.com/smari/maildir-statistics/
 [5]: http://newint.org/features/2014/04/01/keynote-whistleblowers/
 [6]: http://protonmail.ch
 [7]: http://virtru.com
