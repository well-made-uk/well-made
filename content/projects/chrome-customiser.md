+++
draft = false
date = 2022-04-14T13:24:37Z
title = "Chrome Customiser"
description = "Your own custom internet"
slug = "chrome-customiser"
tags = ["Chrome"]
categories = ["Developer Tools"]
externalLink = ""
series = []
featuredImage = ""
+++

[View the project here.](https://github.com/well-made-uk/chrome-customiser)

Nothing spectacular - I just wanted to add some custom CSS to Brave (a Chromium-based browser) to remove age elements on my frequently-visited sites

The main issue was YouTube, which I find really useful for informational purposes, but I strongly dislike being recommended/forced to watch videos I didn't specifically choose. I also don't have a Google account, so all account-related functionality just becomes an inconvenience, and because I disabled trackers and cookies, YouTube doesn't remember that I prefer to watch in Cinema Mode at a low quality setting, and disable Autoplay. I wanted to remove all recommendations and page clutter.

## Making a Chrome Extension
It's a really simple thing to do - you just need a ``manifest.json`` file in the root folder. That contains a few bits of housekeeping:

``` json
{
  "name": "Chrome Customiser",
  "description": "Build an Extension!",
  "version": "1.0",
  "manifest_version": 3,
}
```

Simply the extension name/description, a version number, and the manifest version you're using (3 is the latest version at time of writing and highly recommended).

Under ``"manifest_version"``, we need to add a section for ``content_scripts``, which is an array of objects.

``` json
"content_scripts": [{
    "matches": ["*://*.youtube.com/*"],
    "css": ["css/youtube.css"],
    "js": ["js/youtube.js"]
  }]
```

In this example, we're loading two files, youtube.css, and youtube.js, whenever the tab URL matches the one above (the * wildcard symbols mean that it'll still match on subdomains, regardless of whether www is present, it's http or https, etc.)

The referenced files are completely standard css and js files, and they don't need to be minified since they're being loaded locally, not from a server. [View my setup here](https://github.com/well-made-uk/chrome-customiser), and play with it yourself. Feel free to pull the project and make your own version.
