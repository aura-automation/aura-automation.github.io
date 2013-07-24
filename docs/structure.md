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


An overview of what each of these does:

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>File / Directory</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <p><code>resources</code></p>
      </td>
      <td>
        <p>

	   Location for all the resource xml files for the application  	
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p><code>properties</code></p>
      </td>
      <td>
        <p>

	Location for values of token for all the environments
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p><code>ear</code></p>
      </td>
      <td>
        <p>

	EAR files and deploydata files for the application
        </p>
      </td>
    </tr>
  </tbody>
</table>
</div>

A basic Aura install looks like this:

{% highlight bash %}
.
├── bin
├── lib
├── opt
|   ├── ant-contrib
|   ├── apache-ant-1.7.1
|   └── groovy-1.7.4
├── properties
├── resource
|   ├── extractTemplates
|   	├── cell
|   	├── cluster
|   	└── server
├── _var
|   ├── common
|   └── scripts
└── └── was
{% endhighlight %}



