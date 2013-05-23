---
layout: post
category : blogs
tagline: "Automate Configuration"
tags : [config mangement, automation, websphere, aura]
---
{% include JB/setup %}

This introduction to Aura will outline defination of Java Container Configuraion and how can you can use Aura to automate this configuration.

## Overview 

Application Release Automation is the process of scripting application releases to remove manual tasks.

This approach delivers efficiency, quality and financial benefits.

Automation enables consistent delivery of accurate configuration across multiple environments reducing the resource overhead of the activity.

It can ensure that environments are configured accurately underpinning testing and reducing wasted effort in analysing and resolving defects related to mis-configuration.

Functions that can be automated are deployment of an application, configuring server containers and other application components such as database components and messaging components. By scripting Application Release, you can apply the same configuration to a single or multiple nodes consistently.

In this article I am going to focus on JEE application container configuration specifically on WebSphere Application Server.

You can describe configuration as a script or set of scripts used to ensure that environments are replicated, removing the potential for manual error in the release process.


### Script Driven vs. Data Driven Automation

Automation brings agility to both development and operations by enabling any authorised team member to release through the modification of scripts through a controlled release process (i.e. version control and change management).

However scripting application configuration on application servers like WebSphere can be time consuming and error prone.

It also requires specialist product knowledge.

Script-driven automation results in a non-extendable solution. This means the addition of new automation for new configuration objects which is time consuming due to duplication of effort with development teams. This often involves writing of scripts for different application to automate same configuration objects.

An alternative to script driven model is data driven automation. Data driven automation is implemented by a generic tool/engine that accepts configuration as data. This data is environment agnostic therefore can configure any environment using a generic and consistent mechanism.

### Aura is Data Driven 

Aura is free open source offering that uses data driven automation removing the need to write scripts whilst retaining your capability to define your WebSphere configuration.

Aura can be used in cloud, virtual and physical environments.

In this article, I'll focus on the using Aura for WebSphere Configuration automation.

You will learn the high level concepts of the tool and gain an understanding on how you can simply configuration tasks in your environment.

In future articles I will dive deeper in to more detailed concepts

Aura uses Java programing language and Java API to interface with WebSphere environments.

Aura represents WebSphere Configuration, such as DataSource, JMS Queues, JVM, as Resources. These Resources are expressed in XML files called Resource XML.

Relationship between the resources is captured using the XML tree hierarchy. Values in Resource XML files are tokenised to make these files environment agnostic.

Aura is packaged as ANT tasks and comes with a quick start ANT script to enable quick set up. This can be extended and built up to integrate to your binary repository.

### What is Aura and Why Should I care?

Aura is very minimalistic and very efficient.
The most important thing to realize about Aura  is that it creates a simple xml representation of your config without requiring heavy tools.
Traditional/Commercial tools require a database, server-side code, UI which is self defeating when you want rapid time to market.
Heavily trafficked dynamic blogs must employ a caching layer that ultimately performs the same job Jekyll sets out to do; serve static content.

Therefore if you like to keep things simple and you prefer the command-line over an admin panel UI then give Jekyll a try.

**Developers like Jekyll because we can write content like we write code:**

- Ability to write content in markdown or textile in your favorite text-editor.
- Ability to write and preview your content via localhost.
- No internet connection required.
- Ability to publish via git.
- Ability to host your blog on a static web-server.
- Ability to host freely on GitHub Pages.
- No database required.

### What is Java Container Configuration

JEE Containers like WebSphere have hundreds of configurable objects. These configurable objects can be grouped as defined below.

[[images/configurationdefination.jpg]]

Each group will have an author who is the team that defines these objects.

**Infrastructure Configuration

These objects are typically configured by WebSphere Administrators. Developers are not allowed to change these.

Examples of these configurations are;

    Security Configurations. E.g. SSL key to connect to nodeagents

    LDAP Server

    LDAP Server Configuration


WebSphere Administrators will be the author for this group.

**Application Container Configuration

These objects are configured on containers and used by applications at run time.

J2EE spec externalises these configurations to make an application portable .

Examples of these configurations are;

    DataSources,

    Properties,

    MQ,

    JMS

Each application can have a unique set of objects with configuration.

The Development team will be author for this group.

Some data might be authored by Database administrators/owners, MQ administrators/owners, or other back end system administrators/owners

**Application Configuration

These objects are configured on application level and are applied at the EAR level.

Examples of these configurations are;

    Security Role Mappings,

    Resource Reference Mapping

    Shared Library Binding

The Development team will be author for this group. 

# Configuration Data in Aura

Configuration data in Aura is represented in XML file called as Resource.xml.

Authors can either write these files manually or extract them from an environment using the extract feature in Aura.

Authors can group multiple configuration objects in a single Resource file, e.g. JDBC Provider, DataSources and JAAS Alias.

Similarly JMS Queue Connection Factory and Queue can be grouped into one file.

Attribute values that differ across the environments are tokenised.

These Resource files along with source and binaries are version controlled and released as holistic a Java Container environment for the application.

[[/images/singletool.jpg]]
  
**Thank you** for reading this far.

## Next Steps

