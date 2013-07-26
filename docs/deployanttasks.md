---
layout: docs
title: Deploy ANT Tasks
prev_section: configanttasks
next_section: posts
permalink: /docs/deployanttasks/
---

This task is used to deploy the EAR or WAR file to target cluster or server. 
The task also supports multi ear deploy. 
If any changes are required to the EAR then process EAR ant task explained below must be used before Deploy.

|Attribute|Description|Required|
|---------|-----------|--------|
|applicationName|Name of the application being deployed.|Yes|
|cluster|Cluster to which the application should be deployed. Either server Name or cluster name must be specified. Both cannot be specified|No|
|server|Server to which the application should be deployed. Either server Name or cluster name must be specified. Both cannot be specified|No|
|earFileLocation|Enter the full path of the EAR file location|Yes|
|deployDataLocation|Enter the full path of the Deploydata file location|Yes|
|userName|User name to connect to Target Server|Yes|
|password|User name to connect to Target Server|Yes|
|port|RMI or SOAP Number to connect to on the Target Server|Yes|
|host|Name of the server where Deployment Manager is installed|Yes|

