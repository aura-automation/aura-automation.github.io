---
layout: docs
title: Resources
prev_section: structure
next_section: resourcexml
permalink: /docs/auraxml/
---

The aura XML is where user can configure aura. Location of config, ear etc can be configured.

{% highlight xml %}

<aura>
	<aura-was-config>
		<output-file-base-location>output</output-file-base-location>
		<properties>config/properties</properties>
		<resource-set>
			<resource>config/resources-dev</resource>
		</resource-set>
		<resource-set>
			<resource>config/resources</resource>
		</resource-set>
	</aura-was-config>
	<aura-was-deploy>
		<ear>config/ear</ear>
		<deploydata>config/ear</deploydata>
		<unix-user>my-user</unix-user>
		<keyfile>/home/user/id_rsa</keyfile>
	</aura-was-deploy>
</aura>
{% endhighlight %}

This is sample file listing the supported configuration. aura.xml must be located in location from where aura command is invoked. 
The location must be relative to aura.xml

