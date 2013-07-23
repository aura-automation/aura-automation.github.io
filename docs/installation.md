---
layout: docs
title: Installation
prev_section: home
next_section: usage
permalink: /docs/installation/
---

Getting Aura installed and ready-to-go should only take a few minutes. You can install Aura on same host where WebSphere 
to be managed is installed or on some a central host from where you can manage all your WebSphere hosts.

### Requirements

Installing Aura on a central host will required WebSphere thin client jars (looking at size of the jars it is not that thin!), security property files and 
key stores

- IBM JDK copied or installed; 1.6 or above

<div class="note info">
  <h5>Key installation</h5>
  <p>
	IBM JDK 1.6. or above is required
  </p>
</div>

## Install 

1: Unzip/Untar the download in location

2: Set JAVA_HOME to location of IBM JDK

3: Set AURA_HOME to location Aura installation location

4: Optionally set AURA_REPO, default is directory ".aura_repo" in users home directory

## Install WAS Plugin

1: Run below the command and follow the instructions

```
$ aura was:install-plugin
```

<div class="note info">
  <h5>Key installation</h5>
  <p>
	IBM Thin Client JAR files com.ibm.ws.admin.client_X.X.X.jar, com.ibm.ws.security.crypto_X.X.X.jar, properties and certs will be 
	copied to AURA_REPO
  </p>
</div>


