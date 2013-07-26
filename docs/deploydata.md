---
layout: docs
title: Deploy Data
prev_section: properties
next_section: posts
permalink: /docs/deploydata/
---

DeployData XML is used to configure EAR file while deploying. Configuration like virtual host, ejb bindings etc can be managed using deploydata.
 
You can download an example sample deploydata.xml from [here] (/docs/deploydata.xml).
Below is the description of deploydata tags

 deploy and deployversion tag

deploy tag is root tag and all the deploydata files must have deploy tag as root tag.

deployversion tag is used to get the version of deploydata.xml format. 

Example

{% highlight xml %}
<deploy>

<deployversion value="1.0.0" />

{% endhighlight %}

**startWeight:**

startWeight tag is used to configure the weight of the application in shared environment.

Example
{% highlight xml %}
<startingWeight value="1"/>
{% endhighlight %}
**libraries:**

libraries tag is used to include the shared library for the application. Slick-Deploy maps the shared library to the application at application level.

Example
{% highlight xml %}
<libraries>

    <sharedLibName name="TestSharedLib"/> 

</libraries>
{% endhighlight %}

**generateEJBDeployCode:**

If you need to generate the deployed code of EJB while deploying the application then set value attribute of this tag true.

Example
{% highlight xml %}
    <generateEJBDeployCode value="true"/> 
{% endhighlight %}

**role-binding and special-binding:**

role-binding tag groups the role to group mapping tags. Sub tags of role-binding tag are role tags. Value of the attribute name of role tag is the name of the role in the application being deployed. Sub tags of the role tag are the group tags to which this role should be mapped while deploying the application. Value of the attribute name of group tag is the name of the group to which the role is bound when the application is deployed.

Add the role tags as required by the application.

Tip: Number of roles in the application must be equal the number of the role tags in the deploydata.xml (including the special roles). Number of groups mapped to each role in the application must be equal the number of the group tags in the deploydata.xml for each role (including the special roles).

special-binding tag groups the role to group mapping tags for the role that mapped to Everyone or All Authenticated Users. Sub tags of special-binding tag are role tags. Value of the attribute name of role tag is the name of the role in the application being deployed. Sub tags of the role tag are the group tags to which this role should be mapped while deploying the application. Value of the attribute name of group tag is either AllAuthenticatedUsers or Everyone.

Add the special-binding tags as required by the application.

Example
{% highlight xml %}
<role-binding>

    <role name="RoleName"> 

        <group name="GroupName1"/>

    </role>

</role-binding>

<special-binding>

    <role name="SpecialRoleName">

        <group name="AllAuthenticatedUsers" />

        <group name="Everyone" />

    </role>

</special-binding>
{% endhighlight %}

**run-as role-binding:**

Run as role-binding tag maps role to user and password. Sub tags of run-as-binding tag are role tags. role tag must have attributes name, username and password.

Example
{% highlight xml %}
<run-as-binding>

    <role name="RoleName" 

    username="Administrators" 

    userpassword="Administpasswd" /> 

</run-as-binding>
{% endhighlight %}

**ejb-module:**

Each EJB module in the application should have corresponding ejb-module tag in the deploydata.xml. ejb-module tag groups the configuration for the ejb-module. Name attribute of the ejb-module tag has value as name of the ejb jar file. Second attribute of ejb-module tag is module-ds-bnd. Value of module-ds-bnd is the jndi name of the datasource for the module.

NOTE: The value of the name attribute is name of the jar file and not name of the EJB module.

There can be 2 different types of sub tags of the ejb-module enterprise-bean-binding and message-bean-binding. If the EJB is Message Driven bean then use message-bean-binding and for any other type of EJB use enterprise-bean-binding.

**enterprise-bean-binding** is tag for EJBs (except MDBs) in the EJB module. Total number of enterprise-bean-binding in each module in deploydata.xml must equal the number of EJBs in the module in the application. Value of name attribute is name of the EJB and value of jndi-name attribute is the JNDI name of the EJB.

**ejb-ref-binding** sub tag is for the ejb-refs of this EJB. Value of the name attribute is the name of the EJB reference and value of jndi-name-link attribute is the JNDI name mapping.

**resource-ref-binding** sub tag is for the res-ref for this EJB. Value of the name attribute is the name of the Resource reference and value of jndi-name-link attribute is the JNDI name mapping.

**resource-env-binding** sub tag is for the res-env for this EJB. Value of the name attribute is the name of the Resource environment and value of jndi-name-link attribute is the JNDI name mapping.

**cmp2-ds-binding** tag is for the CMP beans. Value of the jndi-name-link should be the JNDI name of the datasource which is default datasource for this CMP EJB.

**message-bean-binding**is tag for MDB EJBs in the EJB module. Total number of message-bean-binding in each module in deploydata.xml must equal the number of MDB EJBs in the module in the application. Value of name attribute is name of the EJB and value of messagelistener is the message listener name that must be assigned to this EJB.

**ejb-ref-binding**, resource-ref-binding and resource-env-binding are valid sub tags for the message-bean-binding. Details for these sub tags are same as above.

Example
{% highlight xml %}
<ejb-module name="trade3EJB.jar" module-ds-bnd="jdbc/Trade3/TradeDataSource">

    <enterprise-bean-binding name="TradeEJB" jndi-name="ejb/Trade3/Trade" >

        <ejb-ref-binding name="ejb/Trade">

            <jndi-name-link name="ejb/Trade3/Trade" />

        </ejb-ref-binding>

        <resource-ref-binding name="jms/QueueConnectionFactory">

            <jndi-name-link name="jms/Trade3/TradeBrokerQCF" />

        </resource-ref-binding>

        <resource-env-binding name="jms/TradeStatsTopic">

            <jndi-name-link name="jms/Trade3/TradeStatsTopic" />

        </resource-env-binding>

    </enterprise-bean-binding>

    <enterprise-bean-binding name="HoldingEJB" jndi-name="ejb/Trade3/Holding">

        <cmp2-ds-binding>

            <jndi-name-link name="jdbc/Trade3/TradeDataSource" />

        </cmp2-ds-binding>

    </enterprise-bean-binding>

    <message-bean-binding name="TradeBrokerMDB" messagelistner="trade3tradeport">

        <ejb-ref-binding name="ejb/Trade3/Trade ">

            <jndi-name-link name="ejb/Trade3/Trade" />

        </ejb-ref-binding>

    </message-bean-binding>

</ejb-module>
{% endhighlight %}

**web-module:**

Each web module in the application should have corresponding web-module tag in the deploydata.xml. web-module tag groups the configuration for the web-module. Name attribute's value is the war file name. virtualhost attributes value is the virtual host that web module is bound to.

ejb-ref-binding sub tag is for the ejb-ref for this web module. Value of the name attribute is ejb-ref name and value of jndi-name-link is JNDI name name mapping.

resource-ref-binding sub tag is for the res-ref for this web module. Value of the name attribute is the name of the Resource reference and value of jndi-name-link attribute is the JNDI name mapping.

resource-env-binding sub tag is for the res-env for this web module. Value of the name attribute is the name of the Resource environment and value of jndi-name-link attribute is the JNDI name mapping.

Example
{% highlight xml %}
<web-module name="trade3Web.war" virtualhost="www_host">

    <ejb-ref-binding name="ejb/Trade">

        <jndi-name-link name="ejb/Trade3/Trade" />

    </ejb-ref-binding>

    <resource-ref-binding name="jms/QueueConnectionFactory">

        <jndi-name-link name="jms/Trade3/TradeBrokerQCF" />

    </resource-ref-binding>

    <resource-env-binding name="jms/TradeBrokerQueue">

        <jndi-name-link name="jms/Trade3/TradeBrokerQueue" />

    </resource-env-binding>

</web-module>

<web-module name="soap.war" virtualhost="www_host">

</web-module>
{% endhighlight %}
