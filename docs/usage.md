---
layout: docs
title: Basic Usage
prev_section: installation
next_section: structure
permalink: /docs/usage/
---

Below are the commands to manage Container configurations.  
 
{% highlight bash %}
$ aura extract [-Dnoprompt=true -Dtarget.name=(env name) -Dscope=(cell,server,cluster,node) -Dresource.name=(resource name)]
# => Reports and ResourceXML files will be generated in AURA_REPO/resources directory. Run in noprompt mode for silent processes.

$ aura extractAll [-Dnoprompt=true -Dtarget.name=(env name) -Dscope=(cell,server,cluster,node) ]
# => Extract all supported configuration resources from all or requested scope. Reports and ResourceXML files will be generated in AURA_REPO/resources directory. Run in noprompt mode for silent processes.

$ aura preview [-Dnoprompt=true -Dtarget.name=(env name)]
# => Run this from location containing config and properties folder. 
All ResourceXML in config directory will be processed and reports will be generated in AURA_REPO/resources directory

$ aura commit  [-Dnoprompt=true -Dtarget.name=(env name)]
# => Run this from location containing config and properties folder. 
All ResourceXML in config directory will be processed and reports will be generated in AURA_REPO/resources directory

{% endhighlight %}

Commands to manage application 

{% highlight bash %}

$ aura startApp [-Dnoprompt=true -Dtarget.name=(env name)]
# =>  Start all application matching the ear file name in ear dir

$ aura stopApp [-Dnoprompt=true -Dtarget.name=(env name)]
# =>  Stop all application matching the ear file name in ear dir

$ aura deployApp [-Dnoprompt=true -Dtarget.name=(env name) -Dcluster.name=(cluster to deploy) -Dserver.name=(server to deploy) -Dnode.name=(node of the server) -Dwebserver.name=(webserver for webmodule)]
# =>  deploy all application matching the ear file name in ear dir; cluster or server & node must be specified, webserver is optional

$ aura exportApp [-Dnoprompt=true -Dtarget.name=(env name)]
# =>  Export all application matching the ear file name in ear dir

{% endhighlight %}

Enable reporting servers  

{% highlight bash %}
$ aura serve [-Dport=(8080)]
# =>  Start aura reporting server
{% endhighlight %}
