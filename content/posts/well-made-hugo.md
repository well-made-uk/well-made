+++
draft = false
date = 2022-03-02T14:28:37Z
title = "How I used Hugo to build well-made"
description = "Well-made.uk has switched to a different site generator."
slug = "well-made-hugo"
tags = ["well-made.uk"]
categories = ["Dev"]
externalLink = ""
series = []
+++

It's my first big website update of the year!

In general, I produce very low code sites using technologies like Webflow and Bubble. However, this version of the website is completely hand-coded. Each template is in HTML code, and each piece of content is written in markdown.

[Hugo, the static site generator](https://gohugo.io/), provides markup to stick it all together and make a site from it all. This is great, because it means I can work in [Atom](https://atom.io/), my favourite code editor, and benefit from all the plugins there to code websites really nicely.

Before I continue.. [you can view all the code for this website publicly here](https://github.com/well-made-uk/well-made).

## Uses of Hugo

I think that Hugo will be especially useful in the following use-cases:

### Use-case 1
- Editorial content is important
- The content creators/editors are happy using GitHub for Editorial

### Use-case 2
- Design and control is very important
- A lot of custom code or advanced functionality makes the project incompatible with Webflow

It's also possible to create a webflow site and transpose it into a Hugo theme, with a bit of extra work and ingenuity, for the best of both platforms.

## Installing it

I used Homebrew on my Mac...

```
brew install hugo
hugo new site well-made
cd well-made
```

Added a theme...

```
git init
git submodule add https://github.com/luizdepra/hugo-coder themes/coder
```

Started a server...

```
hugo server
```

And we've got a website! It took just a bit of juggling to add my content types, fiddle with the templates to match my website design, and add a custom.css (auto-minified by Atom). It took about a day in total to rebuild my website with numerous upgrades.

## Files & Directory

In the root directory, we've got a config.toml file so we can customise the site, adding the site name and favicon, and a bunch of other parameters that the theme uses. Here's an example:

```toml
baseURL = 'https://well-made.uk/'
title = 'Well-made.uk'
theme = "coder"
languagecode = "en"
defaultcontentlanguage = "en"
```

Content is added simply by adding markdown files to the /content/ folder. Hugo has something called "frontmatter", which is TOML or YAML at the top of the file, that sets some parameters like the page title, slug, and anything else the theme might use. Here's an example - the +++ signs are for signify the start and end of the frontmatter:

```toml
+++
draft = false
date = 2022-03-02T14:28:37Z
title = "Well-made.uk: Meet Hugo"
description = "Well-made.uk has switched to a different site generator."
slug = "well-made-hugo"
tags = ["well-made.uk"]
categories = ["Dev"]
externalLink = ""
series = []
+++

```

/content/ can have as many folder levels as you like, and taxonomies can be either shared between content types, or unique to their own. This makes for really unique and flexible content management, and a bunch of stuff that Wordpress users could only dream of doing, but super quickly and simply.

The theme takes care of all the HTML page templates, but you can add a custom CSS file and hook it up in the config file. Everything is done by filename, so an html file in the root directory's /templates/ folder will override the theme file, as long as it has the same name. So, in essence, theme files can be overridden just by duplicating them into the project folder and making edits there.

## Advantages

I'm using Hugo for well-made, for now. I love that I can work in Atom and Github, for easy coding and versioning. The DOM is human-made, rather than generate as in Webflow, so it makes more sense and it's generally smaller, leading to smaller files and better performance. I get complete control over the code, so I can do advanced accessibility and best practice stuff. My chosen theme had a bunch of stuff, like Pygments and dark mode, built in.

Looking at Wappalyzer, I've only got two technologies on here: Hugo, and Netlify. This makes me happy. While it's not a certain sign of a well-made website, it's certainly a good one.

![Wappalyzer's analysis of well-made.uk](/img/well-made-wappalyzer.jpg)
