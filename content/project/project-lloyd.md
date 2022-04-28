+++
date = 2022-03-02
title = "Project Lloyd"
description = "A static site generator that turns Webflow staging sites into optimised static sites."
slug = "lloyd"
tags = ["Netlify","Static Sites","Developer Tools"]
toc = false
+++

This is the "official" post to accompany the release of [Project Lloyd](https://github.com/well-made-uk/project-lloyd), a static site generator that takes a [Webflow](https://webflow.io) site and deploys it on [Netlify](https://netlify.app).

## Rationale
I started building Project Lloyd in 2021 for the following reasons:

### Hosting
Building on Webflow is great, but [Webflow's hosting](https://webflow.com/pricing#site-plans) is unaffordable for small businesses, and its performance is pretty poor in general. I now host all of my projects on Netlify, the Jamstack host that makes websites super fast and secure, and I wanted to host my Webflow sites on Netlify too. NB: Netlify is also totally free for most sites, too.

It's easy to export a Webflow site and re-upload to Netlify, but that means that all forms and CMS stuff are stripped out in the process, which is no good at all.

### Optimisations
Webflow isn't made for developers. Its publishing process is super straightforward, but it doesn't allow for any [custom build scripts or onPostBuild plugins](https://www.netlify.com/products/build/plugins/). I rely on these plugins to apply important optimisations like CSS inlining, script deferral, font subsetting, and image optimisation. These are really useful plugins for improving the carbon footprint and performance overall. That means that a website hosted on Webflow is a lot slower than the identical site hosted on Netlify, with no intervention other than switching on a few plugins.

### Functionality
Again - Webflow isn't made for developers. It's really challenging to stick to best practices, as Webflow doesn't generate semantically correct sites.

Webflow also lacks a whole lot of features provided for free by Netlify: A/B testing, custom form actions, server functions, [launch previews](https://www.netlify.com/products/deploy-previews/), and a bunch more. For clients focused on digital marketing, [the A/B function](https://docs.netlify.com/site-deploys/split-testing/) is great - it means we can test and compare multiple versions of a landing page without users even noticing. [Netlify forms](https://www.netlify.com/products/forms/) allow us to make **much** more complex and useful forms, and [server functions](https://www.netlify.com/products/functions/) and [API hooks](https://www.netlify.com/blog/announcing-netlify-graph-a-faster-way-for-teams-to-develop-web-apps-with-apis) expand the functionality of a Webflow site infinitely.

[Netlify's also really secure](https://www.netlify.com/security/) - not a big seller for my typical client, but more peace of mind for me.

## What does Project Lloyd do?
Project Lloyd crawls the Webflow staging site (which is totally free to create), and deploys it to Netlify with whatever onPostBuild plugins I want to use. By default, it optimises images perfectly and optimises the loading and subsetting of fonts for every page individually. Lloyd supports Webflow CMS and forms, too.

Project Lloyd does a bit of parsing to improve ```<a>``` tags and semantics a little, meaning that it has advantages for SEO, too.

With Lloyd, no site plan is needed in Webflow at all, taking the total cost of hosting the site to 0. Using Webflow's handy webhook, every time a new change is published on Webflow, the site is redeployed on Netlify. That means the static version of the Webflow site is just as dynamic as the dynamic version.

[You can view the code for Project Lloyd here.](https://github.com/well-made-uk/project-lloyd)

## Performance test

I took 3 nicely-designed but heavy Webflow sites and tested them locally through Project Lloyd, doing nothing other than applying the built-in optimisations and deploying on Netlify.

Here are the results from Lighthouse:

| | Original Site | Lloyd-hosted Site
| --- | --- | ---
| Performance | 65 | 92
| Time to Interactive | 13.9 s | 6.1 s
| Speed Index | 5.6 s | 3.2 s
| Accessibility | 88 | 88
| Best Practices | 85 | 92

So it's a pretty huge improvement. The best practice would be to do some on-page improvements, too, pre-optimising the images, CSS and scripts, before using project Lloyd. But with only a few hours' optimisation work and Lloyd's own optimisations, we could get these rather heavy sites close to 100 and under the recommended 3-second speed index.

## The future of Lloyd
Work for Lloyd is ongoing. I'm going to be improving the efficiency of the app, so that it takes fewer Netlify build minutes, and continue testing in more use-cases to support as many Webflow features as is possible (hopefully I can redirect to Webflow for eCommerce checkout, for example). There are also other features I started work on but did not complete, so I'll be going through and removing chunks of code.

I do not plan on extending functionality at the moment, as I'm really happy with it as a light (and expandable) tool.
