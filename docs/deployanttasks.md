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

Attribute | Description | Required |
----------|-------------|----------|
applicationName|Name of the application being deployed.|Yes|
cluster|Cluster to which the application should be deployed. Either server Name or cluster name must be specified. Both cannot be specified|No|
server|Server to which the application should be deployed. Either server Name or cluster name must be specified. Both cannot be specified|No|
earFileLocation|Enter the full path of the EAR file location|Yes|
deployDataLocation|Enter the full path of the Deploydata file location|Yes|
userName|User name to connect to Target Server|Yes|
password|User name to connect to Target Server|Yes|
port|RMI or SOAP Number to connect to on the Target Server|Yes|
host|Name of the server where Deployment Manager is installed|Yes|
failIfResourceAbsent|Boolean value of Yes/No or True/False. If true then deploy will fail if the resource mentioned in the DeployData.xml is missing|Yes|
connectionType|RMI or SOAP Protocol|Yes|
shouldStart|True or False, If you want to start the application the value must be set to true.|Yes|
isMultiEAR|True or False, If the deployment is for multiple ear files.|Yes|
multiEARDeployData|Directory location of the deploydata files for multiEar deploy, Only required if multiEar is true.|No|
multiEARLocation|Directory location of the ear files for multiEar deploy, Only required if multiEar is true.|No|
sleepTimeForSyncRequest|Time in millisecs for AuraDeployLite to sleep before requesting synchronise status for nodesync. Defaults to 50000.|No|
remoteEARDirectory|Location of the EAR files in case of remote deployments. Default is same as multiEARLocation.|No|
parentLastClassLoaderMode|True or false, If application Parent Last classloader mode must be set to true or false.|No|
failOnError|True or false, If set to true AuraDeployLite will ignore any failures. Defaults to false. True is not recommended for Production environment.|No|
startingWeight|Integer value to determine the starting weight of the application. Value specified in the deploydata for an application overrides this value if specified.|No|
startClusterBeforeDeploy|True or false, Will start the cluster before application deployment if not started. Default is false.|No|
reStartClusterAfterDeploy|True or false, Will restart the cluster after application deployment. Default is false.|No|
operation|install, uninstall or reinstall. Default is reinstall.|No|

***

### AuraProcessEAR Task


If there are certain configurations in the applications for e.g. Security role mappings, JNDI bindings then those configurations can 
be defined in Deploydata.xml. Deploydata.xml can be supplied for each or subset of EAR files, this file 
will contain the configurations of the EAR file. Generally this file must not differ between environments, but if
 there is a requirement to support changes between the environments then tokensations can be used. In case
 of multi ear; AuraProcessEAR using maming conventions to find the deploydata in the deploydata
 directory mentioned in the ANT task. Naming conventioned is EARFileName-deploydata.xml.
If there are any Application configuration that are not supported by deloydata.xml format then you
 can use auraconfiglite to apply the configuration post deployment.


