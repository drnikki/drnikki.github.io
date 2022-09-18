---
title: "Open Source"
date: 2022-09-18
published: true
---


# Open Source







## Open Source PhD
<ul>
      {{ range where .Paginator.Pages ".Params.tags" "intersect" (slice "open-source-phd")}}
      <li>
        <span>{{ .Date.Format (.Site.Params.dateFormat | default "January 2, 2006" ) }}</span>
        <a href="{{ .URL }}">{{ .Title }}</a>
      </li>
      {{ end }}
    </ul>