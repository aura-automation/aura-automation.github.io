---
layout: docs
title: Config ANT Tasks
prev_section: rulesxml
next_section: posts
permalink: /docs/configanttasks/
---

### AuraConfigLiteResource Task

This task can be used to in multiple modes. It can used to commit changes, get report of the changes and run sync operation against the environment. You will supply all connection details as the attributes, in addition you need to set the auraconfiglite resource XML file location. 

_**operationMode is sync**_
For operation mode sync, auraconfiglite will compare the resources in the Aura Config Lite resources XML file and resources on the target Server. It will produce a report highlighting all the resources that are different, all the resources that not configured on the target environment and also all the resources and attributes that are not configured in the auraconfiglite resources XML file. auraconfiglite will produce new auraconfiglite xml resources file with all the missing and new resources. 

_**operationMode is normal**_
For operation mode normal, auraconfiglite will parse the resource XML file. Replace tokens in the file with values from the properties file supplied. auraconfiglite will produce html report of all the changes applied. The format of the report is similar to the compare report. The changes applied will be highlighted.

_**operationMode is reportOnly**_
For operation mode reportOnly, auraconfiglite will implement same logic as in normal except changes will not be commited. This gives you an option to check what changes will be implemented if you run in normal mode.   

Attribute | Description | Required |
----------|-------------|----------|
opertionMode|Normal/reportOnly/sync. Details of these modes has been explained above.|Yes| 
Host|Host location of target DMGR or standalone server.|Yes| 
Port|RMI or SOAP bootstrap Port of target DMGR or standalone server|Yes| 
connectionType|Either RMI/SOAP. Protocol to use for connection|Yes| 
userName|User name for connection to dmgr or standalone server|Yes| 
password|Password for connection to dmgr or standalone server|Yes| 
resourceXML|Set this attribute to location of the resource XML file. Details of the file are explained in the section for resource xml file|Yes| 
environmentProperties|Set this attribute to location of the environment properties files. Details of the file are explained in the section for Aura Config Lite environment properties file section|Yes| 
syncResourceXML|This is resource file produced after sync operation. This file contains all the resource that are missing in the Aura Config Lite resources xml file|Yes| 
syncReportLocation|This is resource file produced after sync operation. This file contains all the resource that are missing in the Aura Config Lite resources xml file|Yes| 
includeAllChildren|For many resources in WAS value of the attributes can be a resource, for e.g. for foreign bus SIBus’s attribute but SIBForeignBus is a resource. By setting this attribute to true all the children are included when a sync operation is performed |Yes| 

***
### AuraConfigLiteCompare Task

This task is used to compare resource type between 2 cells. This task will compare the configuration items mentioned in the resource xml that is passed as attribute to this task

Attribute | Description | Required |
----------|-------------|----------|
resourceXML|Set this attribute to location of the resource XML file. Details of the file are explained in the section for resource xml file|Yes| 
sourceHost|Host location of target DMGR or standalone server.|Yes| 
sourcePort|RMI or SOAP bootstrap Port of target DMGR or standalone server|Yes| 
sourceConnectionType|Either RMI/SOAP. Protocol to use for connection|Yes| 
sourceUserName|User name for connection to dmgr or standalone server|Yes| 
sourcePassword|Password for connection to dmgr or standalone server|Yes| 
sourceEnvironmentProperties|Set this attribute to location of the environment properties files. Details of the file are explained in the section for Aura Config Lite environment properties file section|Yes| 
targetHost|Host location of target DMGR or standalone server.|Yes| 
targetPort|RMI or SOAP bootstrap Port of target DMGR or standalone server|Yes| 
targetConnectionType|Either RMI/SOAP. Protocol to use for connection|Yes| 
targetUserName|User name for connection to dmgr or standalone server|Yes| 
targetPassword|Password for connection to dmgr or standalone server|Yes| 
targetEnvironmentProperties|Set this attribute to location of the environment properties files. Details of the file are explained in the section for Aura Config Lite environment properties file section|Yes| 
syncResourceXML|This is resource file produced after sync operation. This file contains all the resource that are missing in the Aura Config Lite resources xml file|Yes| 
syncReportLocation|This is resource file produced after sync operation. This file contains all the resource that are missing in the Aura Config Lite resources xml file|Yes| 
includeAllChildren|For many resources in WAS value of the attributes can be a resource, for e.g. for foreign bus SIBus’s attribute but SIBForeignBus is a resource. By setting this attribute to true all the children are included when a sync operation is performed |Yes| 
workingArea|Temporary filesystem location|Yes|

***

### AuraConfigLiteXML Task
This task is used to compare XML outputs generated from AuraConfigLite. It can also be used to compare the WebSphere Portal Exports. Output is produced as html displaying the difference. 

Attribute | Description | Required |
----------|-------------|----------|
resourceXML1|AuraConfigLite xml output from an environment. Or portal export XML|Yes|
resourceXML2|AuraConfigLite xml output from an environment. Or portal export XML|Yes|
environmentProperties1|Environment properties for environment used to produce resourceXML1 |Yes|
environmentProperties2|Environment properties for environment used to produce resourceXML2|Yes|
syncReportLocation|HTML Output showing the difference|Yes|
