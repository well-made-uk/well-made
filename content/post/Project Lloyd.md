+++
draft = false
date = 2022-01-09
lastmod = 2022-02-28
title = "Project Lloyd"
description = "The year of silliness and love."
slug = "Lloyd"
tags = ["Netlify","Dev"]
externalLink = ""
series = []
+++

{{< notice info Update>}}This post was updated and re-published. The original post was published 09/01/2022.{{< /notice >}}

Announcing Project Lloyd: a static-site generator for Webflow, powered by Netlify.

## What Lloyd does
Lloyd downloads Webflow websites, uses several postbuild plugins to optimise the site, and then re-deploys it on Netlify. This makes the website much faster.

It's super simple: it just takes the Webflow auto-generated URL and your destination domain, and the rest is taken care of by the build script. It also means that no Webflow site plan is needed.

Netlify's global CDN means that content is delivered from a datacenter nearby, instead of one central server. Netlify is free in most cases, only charging for advanced features like form management and heavy usage.

### Optimisation
Images are compressed and resized to exactly the right size, so no unnecessary image data is downloaded. Optionally, bitmaps can also be converted to WebP.

### Subfont
Subfont creates strict font subsets (only characters used on the page are loaded) and optimises the way the fonts are loaded.

### Analytics
Privacy-friendly analytics, courtesy of Plausible, is automatically added as a [Google-free](/google-free) alternative to Analytics.

### Inlining
Critical CSS is inlined by default, meaning quicker first paints.

## The results
Here's an example:
- [Triple Whale (Unoptimised, hosted on Webflow)](https://trytriplewhale.com/)
- [Triple Whale (Deployed using Project Lloyd)](https://triple-whale-lloyd.netlify.app/)

The websites are identical, apart from new content on the live site since the Project Lloyd deploy in Jan 2022, and the optimisations run by Project Lloyd.

Running Lighthouse on the homepage gives the following results:
- Original site performance: 26
- Lloyd version performance: 78

A lot of what is required to improve site performance is taken care of by Lloyd, and I only had to change 2 lines of code to get there. This is without touching _anything_ on the site - so imagine the results one could get with on-site optimisation, too.

## Availability
Project Lloyd is compatible with all Webflow sites except for those which use the built-in eCommerce system. If you have an eligible Webflow site, let me know and we can give it a go with Lloyd - it's totally free and could save you a lot of money on Webflow site plans. I'll also make the code publicly available once I've made my currently planned updates.
