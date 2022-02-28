+++
title = 'Google Free'
description = 'Why Google services have no place in a well-made web project.'
+++

**Well-made websites are fast, accessible, privacy-conscious, easy to update, and have a very low carbon footprint.** As a consequence, well-made websites are also Google-free. That means that Google services aren't allowed in well-made web projects. That includes:
- Analytics
- Fonts
- Cloud & Cloud CDN
- Ads
- Maps
- YouTube

## What's wrong with Google services?
Google services are (naturally) very carefully made. They're packed with features, super easy to use, and usually free. That's for very good reason. Google wants to be the obvious choice for every web project, and generally speaking, they are.

However, it's really important to note what comes alongside this. If you add Google-made scripts to your website, you're handing over access to all of your data to Google. *Analytics* stores data from your users' computers and behaviours - not just for you to see, but for Google to see and use. *Fonts* serves fonts in a relatively efficient way, but the script required for this also gives Google access to usage data, which is identifiable and non-GDPR-compliant. The story is the same with *Maps*, *YouTube* and *Ads*.

Google's script-based approach means that every service you use has its own impact on site performance and carbon usage, too. The scripts loaded by Google are quite large, and some amount of that script has no benefit to you whatsoever; it's just there for Google to track your users and your own data.

## Well-made's approach
I do not object to using Google services, however I advise all of my clients against doing so. I also advise my clients not to use any "standard" service at all, unless there's a real need to do so. Question: do you actually need analytics? Is there a better, more transparent way to track how users are using your website?

The well-made.uk website does not use anything by Google, though by nature of being online, Google may factor into the process without me or anyone else realising. My Netlify hosting makes use of Amazon servers - whether Amazon uses any Google technology in their stack is unknowable, since the source is not made publically available. Google is pervasive and invasive, so developers should be helping to reduce the impact by using non-Google services.
