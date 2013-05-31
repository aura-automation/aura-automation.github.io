---
layout: docs
title: Welcome
next_section: installation
permalink: /docs/home/
---

This site aims to be a comprehensive guide to Aura. We’ll cover topics such
as getting your Aura Installed, creating and managing your configuration,
extracting configuratoin from know WebSphere environment, deploying EAR/WAR to various
environments, and give you some advice on participating in the future
development of Aura itself.

## So what is Aura, exactly?

Aura uses Java programing language and Java API to interface with WebSphere environments.
Aura represents WebSphere Configuration, such as DataSource, JMS Queues, JVM, as Resources. These Resources are expressed in XML files called Resource XML.
Relationship between the resources is captured using the XML tree hierarchy. Values in Resource XML files are tokenised to make these files environment agnostic.
Aura is packaged as ANT tasks and comes with a quick start ANT script to enable quick set up. This can be extended and built up to integrate to your binary repository.
Aura is free open source offering that uses data driven automation removing the need to write scripts whilst retaining your capability to define your WebSphere configuration.

## Quick-start guide

For the impatient, here's how to get a boilerplate Jekyll site up and running.

{% highlight bash %}
~ $ gem install jekyll
~ $ jekyll new myblog
~ $ cd myblog
~/myblog $ jekyll serve
# => Now browse to http://localhost:4000
{% endhighlight %}

That's nothing, though. The real magic happens when you start creating blog
posts, using the front-matter to control templates and layouts, and taking
advantage of all the awesome configuration options Jekyll makes available.

## ProTips™, Notes, and Warnings

Throughout this guide there are a number of small-but-handy pieces of
information that can make using Jekyll easier, more interesting, and less
hazardous. Here’s what to look out for.

<div class="note">
  <h5>ProTips™ help you get more from Jekyll</h5>
  <p>These are tips and tricks that will help you be a Jekyll wizard!</p>
</div>

<div class="note info">
  <h5>Notes are handy pieces of information</h5>
  <p>These are for the extra tidbits sometimes necessary to understand
     Jekyll.</p>
</div>

<div class="note warning">
  <h5>Warnings help you not blow things up</h5>
  <p>Be aware of these messages if you wish to avoid certain death.</p>
</div>

If you come across anything along the way that we haven’t covered, or if you
know of a tip you think others would find handy, please [file an
issue](https://github.com/mojombo/jekyll/issues/new) and we’ll see about
including it in this guide.
