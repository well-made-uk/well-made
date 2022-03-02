+++
draft = false
date = 2021-06-15T14:28:37Z
title = "Should links open in a new tab?"
description = "What is the best policy for link opening behaviour?"
slug = "new-tab"
tags = []
categories = ["Dev"]
externalLink = ""
series = []
+++

There seems to be a growing habit for websites to open external links in a new tab. In an age when companies are producing 50-page documents to standardise the way their branding and website should be used, we should be putting a bit of thought to the way that links behave. After all, hyperlinks were one of the first features built into HTML - but we still don’t have a universally accepted policy on how they should behave.

While making this blog, I had to decide what my policy would be on external links - should they open in a new tab, or replace the current tab contents?

## Accessibility and Expectations
When we’re talking about accessibility and best practice, it’s generally better to make things behave in the way that people would expect them to.

When a visitor clicks a link on your website, they would expect it to replace the content of their current tab. This is the standard behaviour of an anchor tag in every browser I’m aware of.

## User Experience
When something works in a non-standard way, it should be for good reason. The most commonly cited reason for making links open in a new tab is that the link is to an external website, and the organisation doesn’t want to purposely point users away from their own website.

However, if you’re forcing a link to open in a new tab in order to keep your website open in the background, you are creating a different browsing experience. Depending on the device the user is on, you may be creating quite an unpleasant one.

**Let’s think about what it’s like to open/close tabs:**

| | Opening a tab      | Closing a tab |
| --- | ----------- | ----------- |
| Desktop| Hold cmd/ctrl while clicking a link. Or middle-click. Or right click. Or two-finger tap. Opens in an instant, and I can switch back an instant too.      | ctrl+w on Windows. cmd+w on Mac.       |
| Mobile |  A bit annoying. I have to long-press, tap, then wait for a needless animation to open up a new tab, and there’s no quick way to go back.   | Depends on your phone, but on mine, I have to scroll up to reveal the UI, tap on the tabs button, wait a painfully long time for the tabs to animate in, press a very small and fiddly close button, and then tap on the tab I want to re-enter.        |

It’s really easy to manually open a new tab on desktop, and a pleasant experience to close it. So, while auto-opening tabs aren’t an issue, it’s probably better to give people the option to do it themselves manually as and when they wish.

On mobile, closing a tab is a really unpleasant and fiddly experience. Quite frankly, if a website is needlessly opening links in new tabs on mobile, there’s no chance I’ll stay there.

## User ability
I just want to add: not everyone knows how to operate tabs, especially on mobile. My mother often has upward of 50 tabs open on her phone at any given time, without realising it.

## Security
I’m not going to write in detail about the security implications of opening links in a new tab - they’ve been covered in abundance. In short, though, if you’re going to target a new tab, you should add an appropriate rel tag, too.

## Standardising link behaviour
I’m not going to tell you whether you should open your links in a new tab or not. I just want you to consider the effect it has on user experience. How many times can you open links in a new tab on mobile before people start to get annoyed and leave? How many users are you going to confuse by using non-standard behaviour?

If there’s one thing you should take away from this, it is that you should try to follow standard behaviour unless you have a good, experience- or functionality-related reason to do so.

So what’s my policy? I’m not forcing any kind of alternative link behaviour. Links will open in the standard way determined by your browser. If I ever wish to make a link open in a new tab, I will make that clear before someone opens it (“opens in a new tab” is a good go-to).
