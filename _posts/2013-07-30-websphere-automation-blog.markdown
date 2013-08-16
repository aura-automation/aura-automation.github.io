---
layout: post
title: "WebSphere Application Configuration Automation"
date: "2013-07-30 00:18:52 +0100"
author: aura-automation
categories: [blog]
---

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

Aura is available as CLI that can be used by developers locally or can be intergated with exisiting automation scripts.

Aura is also packaged as ANT tasks. This can be extended and built up to integrate to your binary repository.


### What is Aura and Why Should I care?

Aura is very minimalistic and very efficient.
The most important thing to realize about Aura  is that it creates a simple xml representation of your config without requiring heavy tools.
Traditional/Commercial tools require a database, server-side code, UI which is self defeating when you want rapid time to market.

Therefore if you like to keep things simple and you prefer the command-line over an admin panel UI then give Aura a try.

**Developers like Aura because we can write configuration like we write code:**

- Ability to write configuration in XML in your favorite text-editor.
- Ability to preview changes against environments.
- No release notes or manaul steps required.
- Ability to extract configuration from know good envirnment.
- Ability to version configuration with source code.
- Ability to use rules to block certain configuration types.
- Easy to read reports.

**Thank you** for reading this far.



