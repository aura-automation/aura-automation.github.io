---
layout: docs
title: Rules XML
prev_section: deploydata
next_section: posts
permalink: /docs/rulesxml/
---

AuraConfigLite supports rules. Rules are defined in a xml file. Rule can be  used to restrict or control the changes to resources type. 

For e.g.
* User cannot manage Cell.
* User cannot manage Node.
* User cannot manage Server.

{% highlight xml %}

<resources-metadata> 
<ConfigObject type="Cell" editable="none"> 
   <ConfigObject type="Node" editable="none">   
	<ConfigObject type="Server" editable="none">   
	</ConfigObject>   
   </ConfigObject>    
</ConfigObject>   
</resources-metadata>  
{% endhighlight %}

Rule can be applied at the Resource level or at attribute level.

At resource level options are
* create - Resource can be created or updated
* update - Resource can be only updated, new resource of this type cannot be created.
* none - Resource cannot be created or updated.

As seen in the above example that resource of type Cell, Node or Server cannot be created or modified.
	 
At attribute level, following rules can be applied editable="false", min, max

* editable - true or false. Define value of the attribute can be changed, default is true.
* min - Range of the value for a attribute that has numeric value. Set min range using this rule.
* max - Range of the value for a attribute that has numeric value. Set max range using this rule.
* pattern - Specify the pattern that must be exists in a value of an attribute.


{% highlight xml %}							
<resources-metadata>
<ConfigObject type="Cell" editable="none">
    <ConfigObject type="ServerCluster" editable="none">
	<ConfigObject type="ClusterMember" editable="update">
	     <attributes>
		<attribute name="name" editable="false" />
		<attribute name="weight" min="2"  max="4"/>
	     </attributes>
	</ConfigObject>
    </ConfigObject> 
</ConfigObject>
</resources-metadata>
{% endhighlight %}
							
In the quickstart version rule.xml is located in resources/rule folder. User can create different rule.xml for different user groups in the organisation. For e.g. developerRule.xml, administratorRule.xml, monitorRule.xml etc

Either create seperate bat/sh file for each user type or you can dynamically load the rule.xml based on user type in script. 
