---
author: Smári McCarthy
categories: [Cryptography, Economics, English]
date: 2011-01-08
has_been_twittered: [true]
language: en
permalink: /2011/01/zero-information-banking/
title: Zero information banking
---
<p class="wp-flattr-button">
  <a class="FlattrButton" style="display:none;" href="http://www.smarimccarthy.is/2011/01/zero-information-banking/" title="Zero information banking" rev="flattr;uid:smarimc;language:en_GB;category:text;button:compact;">[I posted this to the p2p-research list on 23. December 2010, but have since then had many conversations about it. Thought I'd repost it here both as an attempt to rekindle the blog and to store for posterity] I've been experimenting with a line of thought to allow for p2p social banking with a high level of privacy, but yet limiting the possibilities for fraud. The approach I'm taking is based on zero-information proofs, utilizing some features of public key crytpography. For example, the mechanism for doing a trusted transfer is as follows: First, some terms: A - Alice's name/public ID B - Bob's name/public ID Sx(m) - Sign message m with x's private key Ex(m) - Encrypt message m to x using his public key Dx(m) - Decrypt message m using x's private key Vx(m) - Verify signature of message m using x's public key Alice wants to transfer 1000 to Bob. They want the amount of the transfer to be secret, but they want their transfer to be accountable so neither can cheat. Cheating </a>
</p>

[I posted this to the p2p-research list on 23. December 2010, but have since then had many conversations about it. Thought I'd repost it here both as an attempt to rekindle the blog and to store for posterity]

I&#8217;ve been experimenting with a line of thought to allow for p2p social banking with a high level of privacy, but yet limiting the possibilities  
for fraud.

The approach I&#8217;m taking is based on zero-information proofs, utilizing some features of public key crytpography. For example, the mechanism for doing a trusted transfer is as follows:

First, some terms:

*   A &#8211; Alice&#8217;s name/public ID
*   B &#8211; Bob&#8217;s name/public ID
*   Sx(m) &#8211; Sign message m with x&#8217;s private key
*   Ex(m) &#8211; Encrypt message m to x using his public key
*   Dx(m) &#8211; Decrypt message m using x&#8217;s private key
*   Vx(m) &#8211; Verify signature of message m using x&#8217;s public key

Alice wants to transfer 1000 to Bob. They want the amount of the transfer to be secret, but they want their transfer to be accountable so neither can cheat.

Cheating is various things, but may include:

*   Alice pretending not to have transferred
*   Bob pretending not to have received the money
*   Alice or Bob lying about how much was transferred
*   Replay attacks &#8211; Bob using the same transfer repeatedly, or Eve making Alice bankrupt by replaying the transfer
*   MITM &#8211; Eve intercepts the transfer and meddles with the amount or prevents it from getting to Bob

They ask Trent (the trusted server &#8211; a broker) to be a witness, but Trent isn&#8217;t supposed to know enough about the transfer to be able to tell anybody how much was transferred, only that it happened and, if need be, he can verify which transfer it was.

(Implied: transaction identities and timestamps to prevent replay; couldn&#8217;t be bothered to work it into the algorithm described here &#8211; it would be unnecessarily cumbersome in notation)

1.  Alice creates a transfer token p = 1000 and signs it with her public key, Sa(p). Sends to Bob (Eb(Sa(p))).
2.  Bob Va(Db(Sa(p)))
3.  Bob signs and sends (Ea(Sb(Db(Eb(Sa(p)))))) = (Ea(Sb(Sa(p))) to Alice
4.  Alice notifies Trent that a transfer has occurred, (Eb(Sb(Sa(p))), Ea(Sb(Sa(p))), A, B).
5.  Trent saves this in his brokerage diary.
6.  Trent starts asking Alice and Bob questions at random. e.g., Trent asks Alice: What is the amount transferred multiplied by 400?
7.  Alice responds: Eb(p*400)
8.  Trent asks Bob: What number has the amount been multiplied with in Eb(p*400)
9.  Bob responds: Et(Db(p*400)/p)
10. Trent asks 4-5 questions like this, starting with Bob and Alice interchangably (or randomly). If Trent always gets the correct answer, he publishes a certificate:  
    St(Eb(Sb(Sa(p))), Ea(Sb(Sa(p))), A, B)
11. Alice stores a transfer out on her ledger:  (-p, St(Eb(Sb(Sa(p))), Ea(Sb(Sa(p))), A, B), A, B)
12. Bob stores a transfer in on his ledger:  (p, St(Eb(Sb(Sa(p))), Ea(Sb(Sa(p))), A, B), A, B)

This essentially allows Trent to verify that a transaction has occurred from Alice to Bob, and they agree on the amount transferred on both ends, and that nobody has tampered with the transaction&#8230; all without Trent ever knowing how much is being transferred. As zero information proofs go, this is fairly simple &#8211; the only &#8220;innovation&#8221; (if it could be called that&#8230;) here is the use of &#8220;accounting logic&#8221;&#8230;

Now, this is all well and good, although an early critique of this is that it doesn&#8217;t immediately guard against collusion between Eve and Trent; or indeed Trent being an impostor. The inclusion of a trusted third party is, unfortunately, an unavoidable fact; but since it&#8217;s a zero information proof arbitrarily many trusted parties can be included in the process. There&#8217;s also an assumption here that validation of Trent&#8217;s identity is done prima facie, and that some mechanism is used to enforce his trustworthiness&#8230; but what that mechanism is, I don&#8217;t know.

This is not the whole story though. In order to do secure Peer-to-Peer banking with no central authority structure, we need several things.

*   Zero information transfers (transfer between two parties such that neither party can cheat, without any third party knowing how much was transferred) (done-ish)
*   1 bit &#8220;can X pay&#8221;? (one party can, given the permission of the other, find out whether the latter can afford to pay a certain amount, without being given any information about how much that party has)
*   Circuitous roundups (an algorithm allowing circular debt elimination; if A owes B and B owes C and C owes A, then the minimum of their common debt can be eliminated)

&#8230; I haven&#8217;t yet figured out if these three are sufficient for a complete system (assuming that we have key exchange and such out of the way). Probably not.

For the 1 bit &#8220;clearance&#8221;, Alice wants to know if Bob can afford to pay her 1000 CryptoDollars &#8211; this is a prerequisite to her accepting a transaction from him, since no other entity will be able to confirm this [having such an entity would cause an authority disequilibrium in the system, which I'm trying to avoid...]. Bob can choose to show Alice his account (showing that you have the money is the traditional method, but harder in digital currencies &#8211;), but not without revealing all of the transfers and amounts transferred to date; or at least back until the previous roundup [a feature of the system].

Some requirements of such a system are that

*   Bob must give permission before Alice is allowed to learn the value of the bit.
*   Bob must not be trusted to give the correct value of the bit.
*   Trent can be asked, but only questions that he has the answer to&#8230;

Circuitous roundups are easy in the case where a trusted party (Trent) has full knowledge of the system, but full information very quickly becomes impossible if you have a federated or truly p2p system, and we don&#8217;t want anybody to have that much information anyway.

For the record, I&#8217;m not adverse to probabilistic approaches &#8211; heck, zero information proofs like the one above are almost always probabilistic. I&#8217;m fairly sure that some would argue against having a probabilistic banking system, but they don&#8217;t understand the law of large numbers and should read up on it.. <img src="http://www.smarimccarthy.is/wp-includes/images/smilies/icon_wink.gif" alt=";)" class="wp-smiley" /> 

&#8230; to address the most obvious criticism of this, it&#8217;s a very clearly technocratic approach with a lot of implicit faith in the idea of public key crypto and doesn&#8217;t take human nature much into account. Well, yes. If I were trying to build a system to regulate human nature, it&#8217;d probably involve a lot of violence and be ultimately unsuccessful - that&#8217;s not the goal. The goal is to take the currency-trade model that&#8217;s been working well in meatspace and raise it to a level where it becomes independently reliable in cyberspace. The more successful such an attempt is, the less regulation of human behaviour is necessary to ensure the stability of the monetary system. &#8220;Stability by design&#8221; versus &#8220;stability by policy&#8221; is a good direction to go in, even if we can&#8217;t get there.
