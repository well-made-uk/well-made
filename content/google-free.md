+++
title = 'Google Policy'
description = 'Why Google services have no place in a well-made web project.'
+++

This website does not require a privacy policy because it doesn't track or store any identifiable information from its users. I used the space normally used for a privacy policy to write my Google Policy instead.

Well-made websites are fast, accessible, privacy-conscious, easy to update, and have a very low carbon footprint. As a consequence, well-made websites are also Google-free.

## Google Developer Tools?
Google tools are (naturally) very carefully made. They're packed with features, super easy to use, and usually free. That's for very good reason. Google wants to be the obvious choice for every web project, and generally speaking, they are.

Here's a list of tools often used by developers to speed up the development process or provide additional features:
- Google Analytics
- Google Fonts
- Google Cloud & Cloud CDN
- Google Ads
- Google Maps
- YouTube
- Google Play services
- reCAPTCHA

All of these tools do their job really well. However, it's really important to note what comes alongside this.

If you add Google-made scripts to your website, you're handing over access to all of your data to Google. All of Google's developer services, in some way, track usage data and store it. All of this data is attached to your IP address and is therefore identifiable - and that's why we get these consent popups on a lot of websites, which tell us that various scripts on the website are tracking identifiable information about us. Most people just click "accept" immediately to get rid of the annoyance*.

## Analytics is not the only culprit
There's a belief that Analytics is the only tool that footprints and tracks users while they're browsing.

It's true that most of Google's developer tools only track users' IP addresses, so what's the big deal? Well, by tracking your IP on every site you visit, Google gets a full profile of everything you do. And as soon as you land on a website that does have Analytics, the rest of the picture is painted: they now know every site you've accessed, everything you've bought, and a full footprint of your device(s).

For context, read Google founder Eric Schmidt's repeated assertions that Google does not, and will not, respect people's right to data privacy [here](https://www.theregister.com/2009/12/07/schmidt_on_privacy/) and [here](https://web.archive.org/web/20100815042507/http://www.thinq.co.uk/2010/8/5/no-anonymity-future-web-says-google-ceo/). Google has even used its influence to [block attempts by W3C](https://www.cpomagazine.com/data-privacy/google-blocking-web-privacy-proposals-at-w3c/) (the organisation responsible for creating standards for the world wide web) from creating more strict privacy rules.

Google's script-based approach means that every service you use has its own impact on site performance and carbon usage, too. The scripts loaded by Google are quite large, and some amount of that script has no benefit to you whatsoever; it's just there for Google to track your users and your own data.

## Well-made's approach
I advise all of my clients against using Google services. I also advise my clients not to use any script at all, unless there's a real need to do so.

The well-made.uk website does not use anything by Google, though by nature of being online, Google may factor into the process without me or anyone else realising. My Netlify hosting makes use of Amazon servers - whether Amazon uses any Google technology in their stack is unknowable, since the source is not made publicly available.

Finally, I develop and browse the web using [Brave browser](https://brave.com/). You can also use [Firefox](https://www.mozilla.org/en-GB/firefox/new/), or anything else - **just not Chrome.** Chrome is the ultimate evil when it comes to privacy, because if you're using it, regardless of which websites you use and what scripts they load, you're being tracked and footprinted anyway.

## For other developers/site-owners
By using Google services, you're making life easier for yourself, but taking away the liberties of your users. There are a bunch of alternatives to Google services, including:

- Privacy-friendly analytics like Plausible, Fathom, and Netlify
- Self-hosted or CDN-based fonts, which can be subsetted and optimised to make them much more efficient than Google
- hCaptcha, a privacy-friendly alternative to reCaptcha
- Any number of maps alternatives, like MapBox
- Self-hosted or Vimeo video hosting

And don't develop in Chrome. Some apps or websites may not work fully outside of Chrome, but that's a sign of a badly developed app, not a badly developed browser. NB: [Brave](https://brave.com/) is based on Chrome, but without the tracking. So you shouldn't have any issues there.

**I love talking about privacy. [Email me](mailto:ben-wilde@hey.com) if you have any questions or you're looking for advice on how to improve the privacy on your website.**

{{<notice info No-consent-needed>}}*You won't see a popup like that here, or even a privacy policy. That's because there's nothing on well-made that will track or store any identifiable or personal information.{{</notice>}}
