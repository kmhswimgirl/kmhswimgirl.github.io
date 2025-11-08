---
layout: topic_page
title: Projects
permalink: /projects/
description: My personal projects
---

# My Projects

{% for post in site.posts %}
## [{{ post.title }}]({{ post.url }})
*{{ post.date | date: "%B %-d, %Y" }}*

{{ post.description }}
{{ post.excerpt }}

[Read more...]({{ post.url }})

---
{% endfor %}