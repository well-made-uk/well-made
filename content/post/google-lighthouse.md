+++
draft = false
date = 2021-06-01T14:28:37Z
title = "How to score 100 on Google Lighthouse"
description = "How to use Lighthouse to make websites actually good."
slug = "lighthouse"
tags = ["well-made.uk"]
categories = ["Dev"]
externalLink = ""
series = []
+++

## Google what?
Lighthouse is a little tool that Google provides, which lets us measure the performance, accessibility, SEO and best practices of our websites. It gives us pointers on how to improve them, because Google uses this to choose which websites to show first when people search for things.

I really recommend getting to know Lighthouse (it’s really easy to use), because you can run it on your favourite websites to see if they’re technically well-made. I put one of my clients’ favourite websites through it, and it came back with five question marks. The website renders its contents using JavaScript, so Google can’t read a single word on there. As far as Google knows, it’s an empty page.

{{<notice info Note>}}FYI: I am quite vocal on my aversion to Google Services. This is a weird world where, since Google is so pervasive and gets the final say on whether our content is seen or not, we sometimes have to work within their parameters, however painful that may be.{{</notice>}}

## What should I aim for?
Always 100. I can say that because I spent a few hours getting this blog up to 100, and then climbed a very high horse to tell you about it.

Google gives you a green light if your score is 90 or above. Most people are happy with green, but really, green means you’re on the final stretch, and you might as well take it all the way, right?

Most people are also happy with green in the performance category, and fine to ignore accessibility, best practices and SEO, because poor performance has the most obvious effect on user experience ( = conversions = sales). But - trust me - this is complete nonsense.

Of course, the main reason you want to hit 100 is that Google rewards you with literal, genuine, real (animated) fireworks if you do it. Nothing beats your first Lighthouse fireworks.

## How do I hit 100?
Lighthouse has some handy tips but they can be really difficult to pull off if you’re using frameworks, templates, libraries and the likes.

What I’d suggest is to throw out your whole website, and rethink every part of it with the question: “Do I need this?”

This blog has under 2Kb of styling in total, only one script, and up to one bitmap per page. It doesn’t even have a navigation section - because it doesn’t need one.

If you’re technical enough to make the distinction, make sure all your complicated stuff happens on the server. Use caching sensibly, deliver static content from the right place, make sure everything has metadata, and [follow WCAG standards](https://www.w3.org/WAI/standards-guidelines/wcag/) for design and layout.

{{<notice info Footnote>}}Lighthouse is not the final word on what is right and wrong. If anything, it’s too easy to score 100. There’s always more you can do, and there are a number of best practices to look for. You just have to keep your eye out for them.{{</notice>}}
