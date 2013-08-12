---
layout: docs
title: Basic Usage
prev_section: installation
next_section: structure
permalink: /docs/usage/
---

QuickStart package provides extract templates for many commonly used WebSphere Configuration items. 
For application deployment PetClinic application has be packaged
 
{% highlight bash %}
$ aura extract [-Dnoprompt=true -Denv.name=(env name) -Dscope=(cell,server,cluster,node) -Dresource.name=(resource name)]
# => Reports and ResourceXML files will be generated in AURA_REPO/resources directory. Run in noprompt mode for silent processes.

$ aura extractAll [-Dnoprompt=true -Denv.name=(env name) -Dscope=(cell,server,cluster,node) ]
# => Extract all supported configuration resources from all or requested scope. Reports and ResourceXML files will be generated in AURA_REPO/resources directory. Run in noprompt mode for silent processes.

$ aura preview [-Dnoprompt=true -Denv.name=(env name)]
# => Run this from location containing config and properties folder. 
All ResourceXML in config directory will be processed and reports will be generated in AURA_REPO/resources directory

$ aura commit  [-Dnoprompt=true -Denv.name=(env name)]
# => Run this from location containing config and properties folder. 
All ResourceXML in config directory will be processed and reports will be generated in AURA_REPO/resources directory

{% endhighlight %}



QuickStart package provides dummy configuration that you can compare 
This will give you a flavour of what to expect when you automate your application configuration and deployment using Aura

{% highlight bash %}

$ aura compareFiles
# =>  Resource xml files in 
workdir/Default/config and workdir/archive/DefaultApp/config/ are compared
Reports will be generated in resources/reports/<datetime> folder. 

{% endhighlight %}

Commands to manage application 


{% highlight bash %}

$ aura startApp [-Dnoprompt=true -Denv.name=(env name)]
# =>  Start all application matching the ear file name in ear dir

$ aura stopApp [-Dnoprompt=true -Denv.name=(env name)]
# =>  Stop all application matching the ear file name in ear dir

$ aura deployApp [-Dnoprompt=true -Denv.name=(env name) -Dcluster.name=(cluster to deploy) -Dserver.name=(server to deploy) -Dnode.name=(node of the server) -Dwebserver.name=(webserver for webmodule)]
# =>  deploy all application matching the ear file name in ear dir; cluster or server & node must be specified, webserver is optional

$ aura exportApp [-Dnoprompt=true -Denv.name=(env name)]
# =>  Export all application matching the ear file name in ear dir

{% endhighlight %}


