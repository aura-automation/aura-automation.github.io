---
layout: docs
title: Resource XML
prev_section: structure
next_section: properties
permalink: /docs/resourcexml/
---

The Resource XML is where Aura starts to get really cool. Any file that ends with Resource.xml
will be processed by Aura as a configuration data file. Root node for this file must be resources and nested between resources are WAS configuration items. 
. Here is a basic example:

{% highlight yaml %}

 <resources>

     <Cell name=”{% raw %}${{CellName}}{% endraw %}”>
            <JDBCProvider name="MyProvider">
            </JDBCProvider>
      </Cell>		
 </resources>
{% endhighlight %}

Between these resources tag, you can set Cell with name being variables. 
Other attribute values like database name can tokenised and replaced with variable as required. 
Syntax of tokens is {% raw %}${{ }}{% endraw %}. Tokens within the curly brackets will be replaces with values 
specified in the environment properties file.

