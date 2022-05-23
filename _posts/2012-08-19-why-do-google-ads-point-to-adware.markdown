---
layout: post
title:  "Why do Google ads point to adware?"
date:   2012-08-19 12:00:00 -0700
categories: programming
---
Try downloading Paint.NET, an excellent free image editor, or Audacity, an open source audio editor, without an adblocker these days, and you’re in for quite a surprise. A disturbing trend in the type of ads served via Google Ad Sense and its affiliates will likely bring you to a page that looks like this:

<figure class="mediumfigure">
    <img src="{{ site.baseurl | prepend: site.url }}/images/google-ads/clip_image002.jpg" />
</figure>

Now, there are two very distinct download buttons above the fold, and actually neither of them will take you to the real installer you’re looking for. Even an experienced computer user could easily be misled into clicking one of the bright green download buttons. The Google “AdChoices” tag is very small, and the ads are padded with lots of whitespace as if to appear a genuine part of the main site.

By now, you probably see where this is going, and you can guess that following either of the huge green download buttons will riddle your computer with spyware. Even worse, these companies have also purchased ad keywords on major search engines (see the second case study), which also redirect users to their altered installers when people search for the names of popular open source packages.

These advertisers are likely not breaking any explicit rules, but they are using every psychological trick in the book to get you through their hijacked installers. Large green download buttons help their conversion rates, and large groups of confusing settings make it tempting to just hit next repeatedly through their installers, leading to disastrous effects. One installer conveniently minimized itself to the icon tray while it was performing its toolbar downloads and installations, yet the program I wanted to install (Audacity) popped right up, making you think that the installation was a simple success.

Google and other ad providers are certainly earning their revenue from these misleading ad clicks too. But you can’t expect open source software teams to buy out their own keywords at great expense just to prevent these types of installers. Operators of legitimate download sites often place ads to help pay for server and bandwidth costs, and manually filtering out the misleading ads is just playing a cat and mouse game.

If Google wants to help make the web a better place, I think they should take a stronger stance against these misleading advertisements. Reject them outright and the web will become a happier place!

### Case Study 1 – A link from the Paint.NET Homepage

If we click one of the links from the Paint.NET homepage, we are taken to a site like this one:

<figure class="mediumfigure">
    <img src="{{ site.baseurl | prepend: site.url }}/images/google-ads/clip_image004.jpg" />
</figure>

Seems simple enough, better click Download here too and run the appropriate installer…

<figure class="mediumfigure">
    <img src="{{ site.baseurl | prepend: site.url }}/images/google-ads/clip_image006.jpg" />
</figure>

Hmm, this doesn’t look like the installer for Paint.NET that I was used to!

Stepping through the default installation settings predictably installs spyware/adware, yet that download link we started with was so obvious, bright, and green on the Paint.NET page!

<figure class="mediumfigure">
    <img src="{{ site.baseurl | prepend: site.url }}/images/google-ads/clip_image008.jpg" />
</figure>

Within 30 seconds of installing on a patched, clean, Windows 7 install, I’ve been asked to change my homepage twice, and have seen four separate ad popups. Good thing this was in a VM…

### Case Study 2 – Downloading Audacity from a simple Google Search

Let’s say that instead I am searching for Audacity, a great free tool for audio file manipulation.

<figure class="mediumfigure">
    <img src="{{ site.baseurl | prepend: site.url }}/images/google-ads/clip_image010.jpg" />
</figure>

Free Audio & Recording Software, that’s exactly what I want, let’s click! Look, Google even made it stand out in orange for us.

<figure class="mediumfigure">
    <img src="{{ site.baseurl | prepend: site.url }}/images/google-ads/clip_image012.jpg" />
</figure>

Looks like I got the download page I was looking for, even the screenshot looks right, and look, almost a million downloads already…

<figure class="mediumfigure">
    <img src="{{ site.baseurl | prepend: site.url }}/images/google-ads/clip_image014.jpg" />
</figure>

Now, you don’t actually read through this text do you? Like anyone else, you just keep tapping accept until it shuts and the installation progress bar shows up.

<figure class="mediumfigure">
    <img src="{{ site.baseurl | prepend: site.url }}/images/google-ads/clip_image016.jpg" />
</figure>

Hmm, free games, dolphin screensavers, free music downloads, this doesn’t look good.

<figure class="mediumfigure">
    <img src="{{ site.baseurl | prepend: site.url }}/images/google-ads/clip_image018.jpg" />
</figure>

And look, here come the popups!

<figure class="mediumfigure">
    <img src="{{ site.baseurl | prepend: site.url }}/images/google-ads/clip_image020.jpg" />
</figure>

And they even hijacked the IE new tab screen, how classy!