---
layout: docs
title: Installation
prev_section: home
next_section: usage
permalink: /docs/installation/
---

Getting Aura installed and ready-to-go should only take a few minutes. You can either install Aura on same host where WebSphere 
to be managed is installed or you can install on some central host from where you can manage all your WebSphere hosts.

### Requirements
Aura-Automation comes with a quick start zip that will allow you to get going rapidly. 

Installing Aura on a central host will required WebSphere thin client jars (looking at size of the jars it is not that thin!), security property files and 
key stores
you’ll need to make sure your system has before you start.

- IBM JDK copied or installed; 1.6 or above

<div class="note info">
  <h5>Key installation</h5>
  <p>
	Unzip the auraquickstart.
	Configure JAVA_HOME to point to IBM JDK
	Setup IBM Client and ssl and soap properties
	Connection details to target environment
  </p>
</div>

## Install 

1: Select a server to install aura-automation. Aura can work from remote server or 
local server where WebSphere. You might select to install local on the target server for ease of install.

2: Expand the zip in a directory where you intend to install. ant lib, ant bin, 
aura jars and other thirdparty jars are already supplied.

3: IBM thin client jars are not supplied. You will need to copy Thin Client 
JAR files com.ibm.ws.admin.client_X.X.X.jar and  com.ibm.ws.security.crypto_X.X.X.jar 
from WAS installation AppServer/runtimes to waslib\runtimes directory. 

or

You can change the below property in deploy.sh to point to the runtimes folder 
WAS_CLASSPATH=$CURRENT_DIR/waslib/runtimes/*

4: If you have not installed aura on WebSphere Server then copy sas.client.properties, 
soap.client.properties and ssl.client.properties to waslib\properties.

Copy the certificate folder "etc" from remote WebSphere to waslib/etc and 
modify the content of ssl.client.properties so that location of key.p12, trust.p12
 etc points to location ${aurainstall}\waslib\etc

Change copied ssl.client.properties user.root to <root of aura install>/waslib. For 
e.g. if aura zip was expanded to \opt\aura; then value of user.root should be \opt\aura\waslib

```
user.root=\opt\aura\waslib
```

5: Set JAVA_HOME to IBM JDK in deploy.sh. 

6: Finally 

a) Define the connection details in a property file workdir/DefaultApp/environments/DEV/env.properties. 
Copy the env-template and rename it to env.properties. Set the values for the properties. 
If you have installed aura local to the target WebSphere, then websphere file path must be specified here, else specify the location 

```
SOAPSecurityConfig=WASPATH or AURAINSTALLPATH\waslib\properties/soap.client.props
SSLSecurityConfig=WASPATH or AURAINSTALLPATH\waslib\properties/ssl.client.props
SASSecurityConfig=WASPATH or AURAINSTALLPATH\waslib\properties/sas.client.props
```

b) Note the value you specified for the file
```
sourceEnvFile=HOSTNAME
```
Rename the file workdir/DefaultApp/config/properties/renamethisfile.properties to HOSTNAME.properties
Add values for 
```
CellName=
NodeName=
ServerCluster=
ClusterName=
```

We are looking to further simply setup if conection details. Should be ready for release soon

Now that you’ve got everything installed, let’s get to work!

## Common Errors

<div class="note warning">
  <h5>Warnings: SSL Error</h5>
  <p>
	If you see error like   
	[AuraConfigLiteResource] Caused by: [SOAPException: faultCode=SOAP-ENV:Client; m
	sg=Error opening socket: javax.net.ssl.SSLException: SSLSocketFactory is null. T
	his can occur if javax.net.ssl.SSLSocketFactory.getDefault()    
	<br>
	This is case where WebSphere client is not able to load the ssl certs. Check that location of ssl client props specified is correct and user.home in this file is correct. 
  </p>
</div>


