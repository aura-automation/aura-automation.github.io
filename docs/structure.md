---
layout: docs
title: Directory structure
prev_section: usage
next_section: configuration
permalink: /docs/structure/
---

Aura is, at its core, a deployment and configuration automation engine with currect support for WebSphere. 
The concept is to define the configuration as code in XML and version control it with application code.
Throughout that Resource xml are tokenised thus can be applied to any environment.


Aura Working directory: This is structure in your source code tree, Run aura commands from cn

{% highlight bash %}
├── PetClinic
|   ├── pom.xml
|   ├── aura.xml
|   ├── src
.
.
├── _config
|   ├── resources
|   |	├── ..Resource.xml
|   |	├── ..Resource.xml
|   ├── properties
|   |	├── [env.name].properties
|   ├── ear
|   |	├── PetClinic.ear
|   |	├── ...ear
|   ├──	├── DeployData
|   |	|   ├── PetClinic-deploydata.xml
└── └── └── └── ..-deploydata.xml
 
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
        <p><code>aura.xml</code></p>
      </td>
      <td>
        <p>

	   Optional file to specify the location directoies.  	
        </p>
      </td>
    </tr>
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

A basic Aura install looks like this

{% highlight bash %}

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
|   	├── node
|   	└── server
├── _var
|   ├── common
|   └── scripts
└── └── was
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
        <p><code>bin</code></p>
      </td>
      <td>
        <p>

	   Aura bat/shell scripts.  	
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p><code>lib</code></p>
      </td>
      <td>
        <p>
	aura and supporting lib jars,	
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p><code>opt</code></p>
      </td>
      <td>
        <p>
	Thirparty tools like ant-contrib, ant and groovy.
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p><code>properties</code></p>
      </td>
      <td>
        <p>
	 properties required for core aura, e.g. log4j, commons-logging etc
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p><code>resources</code></p>
      </td>
      <td>
        <p>

          This is location for templates Resource xml for extract operation. 

        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p><code>var</code></p>
      </td>
      <td>
        <p>
	Directory contains groovy, ant etc scripts required.
        </p>
      </td>
    </tr>
  </tbody>
</table>
</div>


Aura Repo structure looks like. Aura keeps extracted config, reports, plugins in Aura_Repo

{% highlight bash %}
├── _plugins
|   ├── was-remote
|   |	├── etc
|   |	├── properties
|   |	└── lib
|   ├── resources
|   |	├── config
|   |	└── report
|   |	└── ear
└── └── environments

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
        <p><code>plugins</code></p>
      </td>
      <td>
        <p>

	   Location where plugins will be installed.  	
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p><code>resources</code></p>
      </td>
      <td>
        <p>

	Location where the outputs like ResourceXML, HTML reports and ear are exported
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p><code>environments</code></p>
      </td>
      <td>
        <p>

	Environment connection details are stored in this location	
        </p>
      </td>
    </tr>
  </tbody>
</table>
</div>



