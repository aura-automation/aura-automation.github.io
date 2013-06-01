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
$ aura extract
# => The current folder will be generated into ./_site
This will prompt you to enter WebSphere Configuration Item names as a comma sepearted list. 
You can enter the name of any resource. 
For e.g. DataSource if you want to extract the datasources. 

Result of the extract is an xml and html file. 
XML file is generated in resources/output/<datetime> folder 
and html is in resources/reports/<datetime>

{% endhighlight %}

QuickStart package provides dummy configuration that you can preview or commit in your play WebSphere environment
This will give you a flavour of what to expect when you automate your application configuration and deployment using Aura

{% highlight bash %}

$ aura preview
# => Configuration in Resourcexml files in 
workdir/DefaultApp/config will be previewed against target environment. 
Reports will be generated in resources/reports/<datetime> folder. 

$ aura commit
# => Configuration in Resourcexml files in 
workdir/DefaultApp/config will be previewed against target environment. 
Reports will be generated in resources/reports/<datetime> folder. 
{% endhighlight %}


QuickStart package provides dummy configuration that you can compare 
This will give you a flavour of what to expect when you automate your application configuration and deployment using Aura

{% highlight bash %}

$ aura compareFiles
# =>  Resource xml files in 
workdir/Default/config and workdir/archive/DefaultApp/config/ are compared
Reports will be generated in resources/reports/<datetime> folder. 

{% endhighlight %}

QuickStart package PetClinic application that can be used to deploy 


{% highlight bash %}

$ aura deploy
# =>  Application will be deployed to the target environment

{% endhighlight %}


