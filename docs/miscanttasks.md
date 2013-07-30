---
layout: docs
title: Misc ANT Tasks
prev_section: deployanttasks
next_section: posts
permalink: /docs/miscanttasks/
---
### AuraSyncNode Task

This task is used to sync the nodes after changes are commited to deployment manager.

Attribute | Description | Required |
----------|-------------|----------|
Host|Host location of target DMGR or standalone server.|Yes| 
Port|RMI or SOAP bootstrap Port of target DMGR or standalone server|Yes| 
connectionType|Either RMI/SOAP. Protocol to use for connection|Yes| 
userName|User name for connection to dmgr or standalone server|Yes| 
password|Password for connection to dmgr or standalone server|Yes| 

### AuraCluster Task
Use to stop/start/restart cluster

Attribute | Description | Required |
----------|-------------|----------|
Host|Host location of target DMGR or standalone server.|Yes| 
Port|RMI or SOAP bootstrap Port of target DMGR or standalone server|Yes| 
connectionType|Either RMI/SOAP. Protocol to use for connection|Yes| 
userName|User name for connection to dmgr or standalone server|Yes| 
password|Password for connection to dmgr or standalone server|Yes| 
operation|Valid operations are start,stop or restart. |Yes|

### AuraApplication Task
Use to stop/start/restart application, In case of multiple EAR, it loops through the EAR files to the list of application.

Attribute | Description | Required |
----------|-------------|----------|
Host|Host location of target DMGR or standalone server.|Yes| 
Port|RMI or SOAP bootstrap Port of target DMGR or standalone server|Yes| 
connectionType|Either RMI/SOAP. Protocol to use for connection|Yes| 
userName|User name for connection to dmgr or standalone server|Yes| 
password|Password for connection to dmgr or standalone server|Yes| 
earFileLocation|Enter the full path of the EAR file location|Yes|
deployDataLocation|Enter the full path of the Deploydata file location|Yes|
operation|Valid operations are start,stop or restart. |Yes|
isMultiEAR|True or False, If the deployment is for multiple ear files.|Yes|
multiEARDeployData|Directory location of the deploydata files for multiEar deploy, Only required if multiEar is true.|No|
multiEARLocation|Directory location of the ear files for multiEar deploy, Only required if multiEar is true.|No|


