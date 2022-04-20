+++
draft = false
date = 2021-06-15T14:28:37Z
title = "Is this what a low-carbon website looks like?"
description = "If this is a low carbon website, what about the flashy, heavy websites we're used to? Can they be low carbon too?"
slug = "low-carbon-websites"
tags = []
categories = ["Dev"]
externalLink = ""
series = []
+++

This blog has a carbon footprint of “0.00g of CO2” according to [Website Carbon](https://www.websitecarbon.com/website/well-made-uk/). That means that if I remove just a few more things, it may even end up being carbon negative and causing trees to grow spontaneously.

The plausibility of this remains to be seen (and I’ll certainly keep working on it), but what it does mean for sure is that this website has a very low carbon footprint. It is also, one could argue, quite boring and empty (just the way I like my websites). So, for those wanting a compromise a bit closer to the current status quo, with more images, dynamic content, scripts and styling, I’ve been looking at how visually rich a website can be without having an unnecessarily high carbon footprint.

## Figure 1: [Rights4children](https://rights4children.org.uk/), 0.14g CO2
Let’s forget aesthetics here - whether you like floating orange blobs or not, this is a good demonstration of building something which is visually rich yet technically light. The vast majority of images here are SVGs, which typically have a far lower footprint than bitmaps. There are a few scripts being used - a little too many for my liking, but it’s quite well put together. You can see how with a bit more work, this footprint could be lowered further, as jQuery may not be truly necessary and, with 4 stylesheets loading, there’s probably some unused styling going on too.

## Figure 2: [Low-Tech Magazine](https://solar.lowtechmagazine.com/), 0.24g CO2
It’s interesting how this super light, retro-styled blog has a higher footprint than Rights4Children. However, it is run entirely on solar power (which means it sometimes goes offline). Of course, a solar power operation can be scaled up with extra panels and batteries to make sure this becomes near-impossible, but you get the idea. My fave bits here include the weather forecast in the footer - using a simple icon and 1-3 words per day is awesome.

It reminds me of the question: do I really need this? I guess you could say that a low-tech magazine doesn’t need a forecast at all, but I think they’re making a point about how we can strip things back while keeping things as functional as we need them to be.

## Figure 3: [Ecosia](http://ecosia.org/), 0.26g CO2
This is equivalent to Google. Still, it adds an entirely new concept to the website carbon concept: per-use-offsets. It’s not uncommon for businesses to pay Google upwards of £1 per lead via pay-per-click advertising - so how about a carbon tariff? How much is it worth to you to offset the carbon footprint of your website? A few pence extra per lead? It’s worth a lot to Ecosia, because they spend a lot of their advertising revenue on offsets.

If you want to offset the footprint of your website viewership, you just need to figure out the footprint (you can get an estimate by multiplying your Website Carbon score by your monthly page views).

So yeah, “normal” websites can also be low carbon. The aim is to look at each individual piece of your website (especially the higher footprint stuff) and ask the question: do I need this? How can I lighten the load? And, if all else fails, is it worth the cost to offset it?
