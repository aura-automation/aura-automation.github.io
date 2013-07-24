---
layout: docs
title: Directory structure
prev_section: usage
next_section: configuration
permalink: /docs/structure/
---

Aura is, at its core, a text deployment and configuration automation engine for WebSphere. 
The concept is to define the configuration as code in XML and version control with application code.
Throughout that Resource xml are tokenised thus can be applied to any environment. Configuration can be 
previewed and compared so that you can make an informed judgment.


Aura Working directory: This is structure in your source code tree, Run aura commands from cn

{% highlight bash %}
├── _config
|   ├── resources
|   |	├── ..Resource.xml
|   |	├── ..Resource.xml
|   ├── properties
└── └── └── [env.name].properties
{% endhighlight %}



