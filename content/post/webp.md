+++
draft = false
date = 2021-09-07T14:28:37Z
title = "Why I don't use WebP"
description = "You guessed it - another thing I dislike."
slug = "webp"
tags = []
categories = ["Dev"]
externalLink = ""
series = []
+++

When I first started using WebP, I soon had complaints from clients that people couldn’t download images from the website and share them easily, because the format wasn’t supported on their device. I wanted to have a look at what the reduction really is and what that means for performance.

I recently came across a compression comparison [here](https://webp-test-500.b-cdn.net/), which does the hard work for me.

In the comparison, I calculated an average of 16% reduction in file size between a compressed JPEG to a WebP between the first 10 images. This is a substantial reduction. However, there is clearly a consideration here for usability. Visitors often like to download and share content from the websites they use, and have done so since I first used the internet as a teenager. It’s a lot more difficult these days, with file protection more common, Google making it more difficult for the average user to access an image file from the search engine, and many image downloads being in a file format which most people are unfamiliar with.

For most businesses, user sharing of their content is something very appealing, and so putting measures in place which limit this may be counter-intuitive. It also contributes to the general trend away from usability of the internet.

I prefer to compress JPEGs in an intelligent way and avoid using images when possible, rather than to use “novel” compression types which reduce usability.

If you have a website with performance issues caused by image use, there are many better options that switching to WebP or similar. How about reducing the number of images, increasing the level of JPEG compression, and ensuring that the images are served correctly.
