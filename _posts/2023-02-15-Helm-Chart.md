---
layout: post
title: Helm Chart Tips
subtitle: Each post also has a subtitle
tags: [helm,CI/CS,devops]
comments: true
---

Here's a code chunk:

~~~
helm upgrade --install [name] [chart]  --version 3.0.14 --values [yaml path] -n [kubernetes namespace] --kube-context [kubernetes context]
~~~

### Warning

{: .box-warning}
**Warning:** set pwd in chart folder.
