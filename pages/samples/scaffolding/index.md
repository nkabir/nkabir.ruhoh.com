---
title: Bootstrap Samples
description: Capabilities of Publishing Platform
categories: [ 'samples/scaffolding' ]

---

<ul>
{{# site.samples.scaffolding?to_pages }}
<li><a href="{{url}}">{{title}}</a></li>
{{/ site.samples.scaffolding?to_pages }}
</ul>