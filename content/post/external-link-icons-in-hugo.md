+++
draft = false
date = 2022-03-04
lastmod = 2022-04-28
title = "External Link Icons in Hugo"
description = "Making links more accessible by default"
slug = "hugo-external-links"
tags = ["Hugo","Static Sites","Accesibility","Best Practice","Dev"]
externalLink = ""
series = []
+++

I just launched a little update to my website that includes a markdown hook, making all links open safely in a new tab. I'm sharing the markdown hook here.

``` html
{{- $parsedTitle := dict -}}
{{- with .Title -}}
  {{- $parsedTitle = partial "functions/parse-title-attribute.html" . -}}
{{- end -}}
{{- $baseurl := urls.Parse .Page.Site.BaseURL -}}
{{- $desturl := urls.Parse .Destination -}}

<a href="{{ .Destination | safeURL }}"
  {{- with $parsedTitle.title }} title="{{ . }}"{{- end -}}
  {{- with $parsedTitle.attributes -}}
    {{- range $k, $v := . -}}
      {{- printf " %s=%q" $k $v | safeHTMLAttr -}}
    {{- end -}}
  {{- end -}}
  {{- if and (strings.HasPrefix .Destination "http") (not (strings.HasPrefix $desturl.Host $baseurl.Host)) }} target="_blank" rel="external nofollow noopener"{{ end -}}
  >{{ .Text | safeHTML }}{{- if and (strings.HasPrefix .Destination "http") (not (strings.HasPrefix $desturl.Host $baseurl.Host)) }}{{ end -}}</a>

```

We also need to add an icon (using CSS) to show users what the behaviour of the link will be:

``` CSS
a[href]:not(:where(
  /* exclude hash only links */
  [href^="#"],
  /* exclude relative but not double slash only links */
  [href^="/"]:not([href^="//"]),
  /* domains to exclude */
  [href*="//well-made.uk"]
)):not(.social__link):after {
  content: ' ↗️';
}
```

## What are Markdown hooks?
Hugo features markdown hooks - so I can intercept the markdown renderer and change the output. In the example above, I've maintained the title attribute, but added an {{- if }} condition: if the URL starts with "http" (and therefore also "https"), an extra bit of code is added: that which is required to open in a new tab (safely). [Read why this is important here](/post/new-tab).
