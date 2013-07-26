---
layout: docs
title: Deploy Data
prev_section: properties
next_section: posts
permalink: /docs/deploydata/
---

DeployData XML is used to configure EAR file while deploying. Configuration like virtual host, ejb bindings etc can be managed using deploydata.
 
You can download an example sample deploydata.xml from [here] (/docs/deploydata.xml).
Below is the description of deploydata tags

 deploy and deployversion tag

deploy tag is root tag and all the deploydata files must have deploy tag as root tag.

deployversion tag is used to get the version of deploydata.xml format. 

Example
{% raw %}

<deploy>

<deployversion value="1.0.0" />

{% raw %}
