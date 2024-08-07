---
product: campaign
title: Technote - Adobe Campaign - Apache version security update
description: Adobe Campaign - Apache version security update
hide: yes
hidefromtoc: yes
exl-id: 68e42fe4-7fb6-4b53-9f39-e77374e3753d
---
# Adobe Campaign - Apache version security update {#apache-update}

>[!CAUTION]
>This article applies to: Campaign Classic v7 Managed Cloud Services customers, Campaign v8 customers and Campaign Standard customers.

Adobe Campaign works with 3rd party tools, and compatibility is updated on a regular basis, in order to implement supported versions only, and benefit from the latest fixes and improvements. 

Adobe Campaign includes Apache Tomcat which acts as the entry point in the application server via HTTP, and is integrated with Apache Web server. The Apache Software Foundation has released Apache HTTP Server 2.4.53. This version addresses vulnerabilities which may allow a remote attacker to take control of an affected system. Learn more in [Apache 2.4.53 annoucement](https://downloads.apache.org/httpd/Announcement2.4.html){target="_blank"}.

The Adobe Campaign team will conduct the Apache version security upgrade activity by **June 15, 2022** to mitigate this Apache vulnerability and make your instance environment more secure. This upgrade applies to all Campaign Classic v7 Managed Cloud Services customers, Campaign v8 and Campaign Standard customers running on a vulnerable version of Apache HTTP Server. If you are impacted, Adobe already contacted you to inform you about this upgrade.

This upgrade is expected to run automatically outside of your normal business hours for you to continue using the Campaign service without any disruption. 

Your non-production instance(s) will be upgraded by our teams first before we upgrade your production instance(s). Since this is an automatic upgrade process owned by Adobe, there is no action required from your side. However, if you experience any issues, please contact [Adobe Customer Care](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


>[!NOTE]
>This upgrade requires to restart the Apache web server. The downtime will not exceed 10 minutes within the time slot mentioned below.
> 
  
## Frequently Asked Questions {#apache-faq}

* **Why is this a mandatory upgrade?**

    The current Apache version is vulnerable and has a potential security threat. It is important for your Campaign instance(s) to be upgraded to the latest applicable Apache version to address the security risk. 


* **Which customers are targeted for security upgrades?**

    All the customers using Campaign environments implemented on older Apache versions are upgraded to the latest applicable Apache version.

* **What is the expected downtime?**

    The expected downtime is under 10 minutes.  

* **Are there any actions required by the customer for this security upgrade?** 
    
    No actions is required since the security upgrade will run automatically. 

* **What validations need to be run by the customers?** 
    
    No specific testing is needed for this security upgrade. In case any issue is observed, please reach out to [Adobe Customer Care](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **Can I request a change in Date/Time to the scheduled security upgrade slot?** 
    
    Since this is a security fix, we strongly recommend you adapt to the existing schedule.  


For any other question, you can reach out to [Adobe Customer Care](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.
