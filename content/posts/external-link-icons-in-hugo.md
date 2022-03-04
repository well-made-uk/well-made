+++
draft = false
date = 2022-03-04T11:46:37Z
title = "External Link Icons in Hugo"
description = "Making links more accessible by default"
slug = "hugo-external-links"
tags = ["Hugo","Static Sites","Accesibility","Best Practice"]
categories = ["Dev"]
externalLink = ""
series = []
+++

I just launched a little update to website that includes a markdown hook, adding an icon to all external links and making them open in a new tab (safely). I'm sharing the markdown hook here.

[*/layouts/_default/_markup/render-link.html*](https://github.com/well-made-uk/well-made/tree/master/layouts/_default/_markup)
```
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
  >{{ .Text | safeHTML }}{{- if and (strings.HasPrefix .Destination "http") (not (strings.HasPrefix $desturl.Host $baseurl.Host)) }}<i class="fa fa-external-link"></i>{{ end -}}</a>

```

## Markdown hooks
Hugo features markdown hooks - so I can intercept the markdown renderer and change the output. In the example above, I've maintained the title attribute, but added an {{- if }} condition: if the URL starts with "http" (and therefore also "https"), an extra bit of code is added: that which is required to open in a new tab (safely), and a FontAwesome icon to indicate it'll open in a new tab. [Read why this is important here](/posts/new-tab).

## FontAwesome dependency

My website uses FontAwesome free, and my build script subsets it to make it extra tiny. If you don't use FontAwesome, here's a version that doesn't require it:

```
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
  >{{ .Text | safeHTML }}{{- if and (strings.HasPrefix .Destination "http") (not (strings.HasPrefix $desturl.Host $baseurl.Host)) }}(opens in new tab){{ end -}}</a>
```

If you use either of these, you'll probably want to add some CSS styling to make the icon/text smaller and less intrusive.
