+++
draft = false
date = 2022-02-05T14:28:37Z
title = "Project Lloyd"
description = "The year of silliness and love."
slug = "Lloyd"
tags = ["Netlify"]
categories = ["Dev"]
externalLink = ""
series = []
+++

This is a re-write of a post dated 09/01/2022.

I previously mentioned Project Lloyd, a  site generator that helps me produce beautifully fast and simple static sites from Webflow.

The idea came from a little app called [Cryolayer](https://cryolayer.com/), which does a lot of what I wanted to do, but it wasn't quite what I was looking for - and I wanted something I could fork and edit anyway.

## What Lloyd does
### Index-building
Project Lloyd scrapes the Weblow site, looks at the sitemap and all the scripts and styles linked in <head>, and then scours it for any internal or relative links. Once it's built an index of the site and any linked files, it parses everything it can.

### Parsing: XML, HTML, and CSS
I created three little plugins to parse the three kinds of file. Why do I need to parse them? Firstly, I need to replace URLs and prettify them a bit. Beyond that, there were a number of improvements I wanted to make. I added build plugins for WebP conversion and optimisation (though it's disabled by default), critical inlining (still working on that one..), font subsetting and more.

I built all of this with Yarn, so that when I deploy this in Netlify, all of the plugins and dependencies are checked and verified, and I can create a log of every build. Lloyd can take Webflow API triggers, so every time I update something in Webflow, Netlify runs Lloyd again.

### Analytics
Another neat addition to Lloyd is that it automatically adds every built site to my Analytics platform. I use Plausible, which is anonymous and GDPR-compliant, which means that my clients can have a really neat analytics tool without needing to go anywhere near Google or add a privacy statement to their website.

### Netlify Plugins
During the build, I can also ask Netlify to run the resulting code through their own build plugins. I'm currently using the Subfont plugin to optimise font loading and subsetting, but I'll be looking at more options in future.

## Lloyd in action
At the time of posting, there are two static sites using Lloyd: well-made.uk, and NASHorn (a German healthcare app, and client of mine). Have a look and see what's going on there. You can also see the analytics for well-made.uk here.
