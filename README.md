so you are interested in opsec (operational security)? this should provide a brief but practical guide to get you started

![freedom eagle header](freedom.jpg)

# what is opsec?

google's ai defines opsec as "OPSEC is a risk management strategy that focuses on identifying and mitigating vulnerabilities that 
could allow adversaries to learn about planned or ongoing operations, intentions, capabilities, or limitations."

in general, opsec is about risk management for whatever you are doing. it is a way to avoid downsides that are unnecessary

we see people facing the consequences of opsec failures daily. especially in repressive regimes, opsec failures
can get you tortured and killed, and regularly do

perhaps it is time to upgrade your opsec today?

# starting out

Here are a few basic rules of opsec that should be immediately operationalized in your life:
1. know thy threats
2. opsec is not retroactive
3. when in doubt, be paranoid
4. do your research. never stop learning
5. always assume you are compromised
6. trust nobody / suspect everyone
7. never trust technology
8. there is no perfect opsec, especially against resourced threat actors, but you must do your best

I will expand the first two, which I consider the most important pillars of opsec

Start by burning these rules into your brain. Repeat them every day, like a mantra. Practice makes perfect

# know the threats

opsec is centered around protection from current and future threats. opsec is also a *risk management* strategy. it is about
knowing and avoiding risks, although risks can never be avoided completely

at the end of the day, opsec is different for every person. a protestor needs different opsec than a hacker needs different opsec 
than a soldier needs different opsec than a private citizen, and even within these categories, your opsec needs will depend on what 
you are doing

the first step to an opsec analysis is to list your threats. learn their capabilities, and list the scenarios you are afraid of.
running a classic security risk management process on your life is something i practically recommend
https://www.researchgate.net/figure/nformation-security-risk-management-process_fig2_261310411

list each threat you are worried about. list all the ways these threats tend to act, and all the vulnerabilities you may
have to these threats. make a spreadsheet for each vulnerability, and estimate the likelihood something like this would
happen to you (1-5 is fine), the impact/damage should it happen, and the difficulty of mitigating the threat

this will start to serve as a map. for each threat you want to mitigate, develop and implement a strategy. review your
threat analysis and your plan regularly, perhaps as often as once a month in fast moving situations. never stop learning
your enemy and looking for new ways they use vulnerabilities against their targets. by running a formal process and giving
numbers to each, you can start thinking objectively about how to best manage the risk to avoid as much downside as possible
for yourself

some resources include, osint https://www.youtube.com/watch?v=J6LsVq-TS28 and reading indictments, as well as building a community
around your specific threats. I find the government's efforts to take down darknet markets a fascinating and deep reflection of
current state of the art offensive techniques and bleeding edge opsec failures, there is a wealth of information availabile
on these here https://gwern.net/doc/darknet-market/ that will be very helpful to "know thy enemy"

# OPSEC IS NOT RETROACTIVE

governments and corporations store massive amounts of data they cannot use today, but will be able to use in the future. Even
if your opsec techniques are perfect against today's threats, tomorrow's threats may have access to a huge trove of past data
that they can use in new ways that are impossible for you or anyone to predict today

so, no matter what you do, expect some aspect of your opsec to eventually fail to the march of time, especially if you are 
attempting to protect yourself against a surveillance actor

if your opsec has been poor in the past, expect that your behavior and activities are known. incoprorate this into the threat
and vulnerability analysis you are doing above

# secure your internet connection

1. **your browser** your browser leaks TONS of information about you, especially chrome/firefox/safari. you must use a privacy focused
browser (eg librewolf) to avoid this. this will be less convenient, as anti-fingerprinting requires things like cookie clearing on
exit, which influences your ability to do things like stay logged into services. accept the inconvenience, because if you are using a 
default browser, there is not much point of employing a vpn or other protections as it is already fingerprinting you 
(see here https://fingerprint.com/blog/browser-fingerprinting-techniques/)
2. **your PC** even if you secure your browser, your computer may contain traces of whatever you look at. make sure to highly secure
any device you use against compromise or data retention, using encryption with rotated passwords and regular wipes as detailed in
the computer section is essential
3. **wardriving** consider learning about wardriving / using unsecured wifis via things like cantennas to further hide your footprint
4. **VPN/Tor** commonly provided advice but poorly understood, see below for some notes on when and how to use each one

## what is a vpn?

VPNs are one of the most poorly understood security and privacy technologies out there, mostly because VPN companies market them as
a magical silver bullet to sell subscriptions while playing on peoples' fears. here we will dive into HOW a vpn works and WHEN it can
or cannot protect you, so you can apply VPNs **to your specific threat analysis** and judge whether they would be effective for mitigating
risks

To understand why a VPN works, first consider why web traffic leaks. When you use the internet, your connection looks like this:

```
YOU <> Internet Provider 1 <> Internet Provider 2 <> Internet Provider 3 <> Website/App/Service
```

Because you are not directly connected to the apps/websites, you use intermediaries called providers to send and receive messages there.
Here, Provider 1 is whoever you pay for Internet, but notice there may be many other providers *between* them and the website that you
may not even be aware of

Each of these providers can see (or be subpoenad for):
1. All websites you visit, when you visit them, and likely what pages (through metadata), even if the website or app is secured with 
encryption
2. If the connection is unsecured with encryption, the full content of what you are doing

This is obviously concerning if you are doing something sensitive, especially as Provider 1 often carries your identificiation as well,
either because you pay them for service or because it is a corporation/university/public wifi which likely requires an identifying login.

When you use a VPN, **the VPN becomes a middleman that essentially replaces your provider**. It looks something like this:
```
YOU <> (Internet Providers 1,2,3) <> VPN Provider <> (Internet Providers 3,4,5) <> Website/App/Service
```

Here, internet providers 1,2,3 are your providers, and 3,4,5 are the providers of the VPN service itself

What have we changed? Let us be systematic:

1. YOUR internet providers, 1,2,3, can no longer see as much website traffic as before. They can however see that you are using a VPN, 
so if you have a group of people using the same VPN on the same provider, this group can easily be isolated and identified. They can
also see when and how much you are browsing the Internet, but can no longer see what sites or content
2. Your VPN provider replaces Provider 1 before. This means they can see everything, identify you (through your payment to them and
Providers 1-3), and can be subpoenad for the full content and browsing data enumerated for your providers above
3. The VPN service's providers, 3,4,5, similarly get similar data as your providers did before, and can also be subpoenad
4. The website/service can no longer see Internet Providers 1,2,3, because the VPN is in the middle. This may stop you from being
fingerprinted by the website, though the website can still fingerprint that you are using the VPN, so the value here is dubious

So, a VPN provides no protection if either the VPN service itself is compromised or if the adversary is able to access any of these 
services. Specifically, VPN providers are frequently subpoenad by law enforcement: https://www.pcworld.com/article/2367508/vpns-and-the-law-how-often-does-law-enforcement-actually-request-vpn-logs.html
and provide a very convenient single point of collection, usually with an office dedicated to handling law enforcement inquiries.
This is especially problematic for counter regime demonstrators, as in practice most regime responses (eg hong kong protests) are simply
to consider any vpn use suspicious cause for action in and of itself, at which point the VPN in fact fingerprints you as suspicious
and provides a false sense of security, if anything

Using VPNs as protection from a regime-level actor or law enforcement thus requires extreme caution, as it may in fact be self defeating

On the other hand, stopping YOUR PROVIDER from seeing data, especially if this is a company, university, or open wifi network, may still
be a worthwhile application of a VPN, especially if you do not believe that a subpoena to a VPN provider is in your threat model or 
analysis

In general, for pure anonymity, I would strongly recommend using Tor alone over a VPN if you need anonymity and can stand the fingerprint
risk

## Tor

Tor mostly works the same way as VPNs above, with a few key differences. Rather than using a single provider in the middle of the traffic
stream, Tor will choose 3-5 random computers around the world, and insert them into the place of your VPN provider. So now, your 
traffic stream will look like this:
```
YOU <> (Internet Providers 1,2,3) <> TOR <> (Internet Providers 3,4,5) <> Website/App/Service
```
specifically, rather than a single provider, the TOR box will look like this:
```
YOU <> (Internet Providers 1,2,3) <> TOR Node 1 <> TOR Node 2 <> TOR Node 3 <> (Internet Providers 3,4,5) <> Website/App/Service
```
	
in addition, Tor uses onion routing https://en.wikipedia.org/wiki/Onion_routing to prevent Tor Nodes 1,2,3 from knowing the full
path listed above. Specifically, the TOR nodes can only see what is directly adjacent to them, so in this flow, Tor Node 3 would not
be able to even know Tor Node 3 was involved in the traffic. This provides an additional layer of protection, since as long as 
one of the Tor nodes is outside the control of your threat, your threat will not be able to decode the full chain

There are, however, a lot of gothcas. So, now we have:
1. YOUR providers 1,2,3 can see you are using Tor, and the same metadata they see for a VPN, but that's it. Similar to a VPN in this
regard.
2. To "subpoena"/"pwn" or compromise the Tor chain, an adversary must compromise all 3 Tor nodes. This is difficult as Tor is secured
by the military and other organizations for their own communications, as well as maintained by a global network of privacy
activists.
3. Internet providers 3/4/5 still have all the same data access as before, but all they know is that the traffic is coming from Tor.
They cannot fingerprint it to you specifically, but over time, may still be able to gather metadata about you.

This is of course assuming Tor is working correctly. It is a complex system that has been attacked before, so it is not a silver bullet...
see eg https://www.theverge.com/2015/11/11/9719098/fbi-reportedly-paid-1-million-carnegie-mellon-tor

Unfortunately, there is no perfect system for Internet security, so this is the best we have for now. To use Tor easily, I recommend
the built in tor browser, which also comes with anti fingerprinting and privacy extensiosn that will help you stay anonymous on Tor
... see here for more info https://tb-manual.torproject.org/running-tor-browser/


## when to use each?

So, use Tor when you need the most anonymity, especially from state actors and subpoenas. Be aware that either technique is prone
to fingerprinting without applied steganography

If you must protect your traffic specifically from YOUR PROVIDER ONLY, and you trust your VPN provider, use a VPN

If you must use both, be extremely careful and talk to an expert, as using both together incorrectly can actually leak your private 
information. See the top comment here for more https://www.reddit.com/r/TOR/comments/ydsmf8/vpntor_do_we_have_a_conclusive_answer_or_is_it/

## internet security pitfalls

Don't forget that in addition to how you access the internet, what you do on it can be prone to fingerprinting or information leakage.
Messaging services, social media websites, etc can collect data on your usage and build a profile on you even without your provider
data. Always assume everything you do online is compromised and apply defense in depth (multiple mitigations against a threat, used
together)


# secure your computer

if you use a computer for anything sensitive, be aware this will be a natural target for any threat actors. you can mitigate some 
vulnerabilities with the following advice

1. **regular wipes** make sure these are secure, dban is a classic tool but you may find other guides for your platform
2. **USE FULL DISK ENCRYPTION** there is no excuse not to be doing this. use a long secure unique password and 
look up a guide for your operating system
3. **keep sensitive PCs powered down when not in use** even if you use encryption, data can be extracted from your PC while it is in 
use / powered on. keep your devices powered off when not in use. for the extreme, remove the battery from your laptop internals and 
wrap the power cable around your elbow, so if you are raided while the device is in use you can easily yank the power and protect 
your data. practice this. this would have saved Ross Ulbrict from 10 years in jail had he done it
4. **never use biometrics (fingerprint, face ID)** biometrics are totally insecure, as your fingerprint can easily be cloned or lifted
and even subpoenad by part of standard operating procedure. never use any form of authentication you cannot change. secure, unique, 
long passwords and pins you regularly rotate are the only secure way
5. **use unique passwords** nuff said
6. **know your threats** look into deeper advice for securing against whatever specific threats exist in your analysis, as general
computer security has a very lage surface
7. **find specific guides for your platform** don't hesitate to find specific guides for linux, windows, os x, or whatever you use

# secure your phone

your phone is probably your biggest weakness. secure it today

1. **use a privacy focused os** default cell phone OSs are basically trackers. look up privacy guides for your mobile operating 
system. I highly recommend running something like Graphene or Calyx https://grapheneos.org/ and following the optimal privacy guide 
for each. Do not use Google Play or iOS services, or location services
2. **leverage any TPM features** your phone has to secure your data, and wipe your phone on a regular schedule
3. **DO NOT use apps** apps leak an enormous amount of data, from mic data to granular location data. this data is bought and sold 
to many companies and governments on a wide series of marketplaces. just avoid apps, seriously. use the web version if you can. keep 
apps to a bare minimum; perhaps an encrypted messenger and nothing else. if you cannot do that get a burner phone
4. **change your browser** unless you are using a privacy os like graphene or calyx, your default browser is tracking you in a 
million different ways. find a secure browser for your phone platform
5. **securely wipe regularly** despite the above, your phone WILL track and store a wealth of data on you. wipe it SECURELY 
(graphene and other OSs provide an encrypted wipe feature) every once in a while
6. **find a privacy guide for your specific phone** if you can't use graphene and must use eg an iphone, google "iphone ios privacy 
guide", read several, and implement their advice
7. **never use biometrics (fingerprint, face ID)** same tip as for the computer. seriously, never ever ever, convenience and security
DO NOT MIX

https://www.youtube.com/@robbraxmantech is an accessible resource on phone privacy and the major problems with existing phone OSs.
If you can avoid phone use for anything sensitive, and use it to call your family once and a while and nothing else, this is ideal.
Never fool yourself into thinking anything other than that your phone is tracking and listening to you 24x7, because it is

# notes on messaging

Messaging is one of the hardest things to secure from an opsec pov. We need it, it is hard to comparmentalize, and it is intimately
linked with very sensitive information about our lives

When it comes to messaging, there are two primary angles to think about: content, and metadata

Securing content is easy. Use secure encrypted communication protocols, like Signal or PGP over email, and unless an endpoint is 
compromised, your content stays secure

Securing metadata is much harder. Metadata is data about your conversations: who you talk to, how often, how long your messages are,
where you are when you send the messages, how quickly the receiver reads it, etc

Securing metadata today is **ALMOST IMPOSSIBLE**. No off the shelf messaging solutions are metadata secure. Signal leaks 100% of your
metadata to the US government, as all the metadata is processed on servers located in Amazon and Microsoft facilities in the United
States. Signal also uses phone numbers for accounts, a very powerful form of metadata that can be used to link many communications
and profiles across time. In addition, your phone number can be compromised by any government entity, so if you do use Signal,
make sure you do not trust people unless you MANUALLY VERIFY THEIR FINGERPRINT IN PERSON, and do so after every notification that
their safety number has changed

You may think metadata is not a big deal? Not so. Michael Hayden, ex head of the NSA, was famously known to have said "we kill people
based off metadata alone" https://abcnews.go.com/blogs/headlines/2014/05/ex-nsa-chief-we-kill-people-based-on-metadata
Indeed, most signals intelligence these days focuses on metadata collection and analysis, as the actual content is almost always
irrelevant. Be thoughtful about minimizing your metadata

Given this, my practical advice is to keep most sensitive communications to in person small group comms. Where this is not possible,
assume your metadata is compromised, and act appropriately. Burner mesaging accounts on platforms like Session, frequently rotated,
on top of Tor may start getting closer

However, be aware that even this may not be perfect, as messaging metadata is core to US national security strategy and there
have been billions invested over centuries to establish hegemony here (see eg https://medium.com/@NafeezAhmed/why-google-made-the-nsa-2a80584c9c1)
So, Session+Tor? Better than nothing, but in person is still key, and you should plan to mitigate any metadata leaks that are
inevitable if your adversary has any surveillance or legal capabilities

# messaging opsec for in person events

one special case relevant for protestors/resistors is how to operate in person groups. here are a few notes that may provoke thought
as you do your own threat analysis

1. Leave your phone at home if possible
2. If you can't, keep your phone powered off or at the very least on airplane mode if you are not actively relying on it. 
Optionally, add a Faraday bag for signals resistance
3. Be aware that if your phone is active, you are an easy target
4. Treat every messaging group as if it is infiltrated and public. Do not say anything you would not defend in court or public. 
Rotate identities frequently. Keep messaging to 1/1 sets of trusted people
5. Explore alternative off grid communication that is less traceable (lora, meshtastic, etc)
6. Keep in mind you can be tracked even after a protest or event ends, as carriers record cellphone tower data
7. Avoid social media at all costs. If you must post on social media, do so from a dedicated device in your house

# more resources

I like reddit's r/privacy and r/opsec to stay up to date on the technical side of opsec

On the physical side, resources depend highly on what you are doing. Collecting a resource set for your community is not a bad idea


# tldr

A few simple steps that if you care about privacy, will get you 99% of the way there --

Use Tor. Keep your sensitive activity to a single device. Encrypt it. Wipe it securely, regularly. Keep it powered off when not in use.
Operate in person. Leave your phone at home and use it as little as possible. Assume everything you do is compromised

Stay safe and good luck :)


![no excuses lets go](lfg.jpg)
