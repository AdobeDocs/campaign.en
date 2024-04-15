---
title: Enhanced security add-on
description: Get started with Campaign Enhanced security add-on
feature: 
role: Developer
level: Experienced

---
# Enhanced security add-on {#enhanced-security}

Adobe Campaign offers the Enahnced security add-on, which currently includes two features:

* Secure CMK integration

* Secure VPN tunneling

They are ecosystem features aiming at making the network connection more secure and providing more security for the resources.
They are the first two features of what can be seen as a security premium package / security shield services

## Secure CMK integration {#secure-cmk-integration}

This is not a product feature.
Goal = encrypting customer instances with customer managed key in their AWS account.
Customers will be generating and managing keys themselves
Customers data/resources are encrypted
More control on the key > key is encrypted in the control of customers only in their AWS account
They can revoke the key for example
Customer needs an AWS account and needs to apply a policy that Adobe provides them
If customer has Snowflake account
Enterprise Edition by default, but customer needs to switch to Business critical Edition

## Secure VPN tuneling ¶#secure-vpn-tunneling

Goal = Provide secure access over private network from customer premise to Campaign instance
3 use cases:
    * FDA over VPN
    * Instance login over VPN from thick client
    * Instance SFTP access over VPN
Customer can access on-prem database over VPN (only on-prem DB supported)
Job provided by Adobe to configure VPN automatically - customer cannot do it in a self-serving manner.
There will be 2 tunnels in case issue on one tunnel > monitoring and alerting on those VPN tunnels

## Customer onboarding and enablement

Goal = assist customer to setup CMK and VPN
Customer needs to set up AWS key to share information with us
We want to monitor the key > customer needs to have AWS bridge for us to monitor CMK
Customer needs to set up VPN on his side based on Adobe VPN configuration
On-call enablement
MSIO enablement
We will be auditing change logs too

## Callouts

Encryption is done at account level, not database level
Not through Control Panel (maybe for v2)
Customer needs to reach out through a ticket
    * Collaborative process > transition managers to help on that > manual communication via email
    * No CMK or VPN at initial provisioning It will be done post provisioning (before go live)

### CMK

There will be downtime for first setup / before go live
AWS account needed > AWS owned and procured by customer
Customer is the owner of the key
In case customer deletes the key > instance is inaccessible until reverts the action > key permanently deleted after 30 days, and all data will be lost

### VPN

Done after provisioning and before go live
Customer needs to configure his side VPN based on Adobe side VPN configuration
VPN connectivity with new UI is out of scope