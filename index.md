---
layout: page
title: Aura Automation Blogs!
tagline: Automate Application Configuration and Deployment
---
{% include JB/setup %}

Read [Aura Home Page](http://aura-automation.org)

## My Posts


<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>



