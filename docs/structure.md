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
        <p><code>_layouts</code></p>
      </td>
      <td>
        <p>

          These are the templates that wrap posts. Layouts are chosen on a post-
          by-post basis in the <a href="../frontmatter">YAML front matter</a>,
          which is described in the next section. The liquid tag
          <code>{% raw %}{{ content }}{% endraw %}</code>
          is used to inject content into the web page.

        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p><code>_posts</code></p>
      </td>
      <td>
        <p>

          Your dynamic content, so to speak. The format of these files is
          important, and must follow the format:
          <code>YEAR-MONTH-DAY-title.MARKUP</code>.
          The <a href="../permalinks">permalinks</a> can be customized for each
          post, but the date and markup language are determined solely by the
          file name.

        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p><code>_site</code></p>
      </td>
      <td>
        <p>

          This is where the generated site will be placed (by default) once
          Jekyll is done transforming it. It's probably a good idea to add this
          to your <code>.gitignore</code> file.

        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p><code>index.html</code> and other HTML, Markdown, Textile files</p>
      </td>
      <td>
        <p>

          Provided that the file has a <a href="../frontmatter">YAML Front
          Matter</a> section, it will be transformed by Jekyll. The same will
          happen for any <code>.html</code>, <code>.markdown</code>,
          <code>.md</code>, or <code>.textile</code> file in your site's root
          directory or directories not listed above.

        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p>Other Files/Folders</p>
      </td>
      <td>
        <p>

          Every other directory and file except for those listed above—such as
          <code>css</code> and <code>images</code> folders,
          <code>favicon.ico</code> files, and so forth—will be copied verbatim
          to the generated site. There are plenty of <a href="../sites">sites
          already using Jekyll</a> if you're curious to see how they're laid
          out.

        </p>
      </td>
    </tr>
  </tbody>
</table>
</div>

